
.. _get-health-check:

Perform health check
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{project_id}/health

This operation performs a health check for all dependent systems. 



This table shows the possible response codes for this operation:

+---------------+-----------------+-----------------------------------------------------------+
|Response Code  |Name             |Description                                                |
+===============+=================+===========================================================+
|200            | OK              | The request succeeded.                                    |
+---------------+-----------------+-----------------------------------------------------------+
|400            | Bad Request     | The server cannot or will not process the request         |
|               |                 | due to something that is perceived as a client error      |
|               |                 | (for example, malformed syntax, invalid request framing,  |
|               |                 | or deceptive request routing).                            |
+---------------+-----------------+-----------------------------------------------------------+
|401            | Unauthorized    | The request has not been applied because it lacks         |
|               |                 | valid authentication credentials for the target           |
|               |                 | resource. The credentials are either expired or invalid.  |
+---------------+-----------------+-----------------------------------------------------------+
|403            | Forbidden       | The server understood the request but refuses             |
|               |                 | to authorize it.                                          |
+---------------+-----------------+-----------------------------------------------------------+
|404            | Not Found       | The server did not find a current representation          |
|               |                 | for the target resource or is not willing to              |
|               |                 | disclose that one exists.                                 |
+---------------+-----------------+-----------------------------------------------------------+
|405            | Method Not      | The method received in the request line is                |
|               | Allowed         | known by the origin server but is not supported by        |
|               |                 | the target resource.                                      |
+---------------+-----------------+-----------------------------------------------------------+
|409            | Conflict        | The request could not be completed due to a conflict with |
|               |                 | the current state of the resource.                        |
+---------------+-----------------+-----------------------------------------------------------+
|500            | Internal Server | The server encountered an unexpected condition            |
|               | Error           | that prevented it from fulfilling the request.            |
+---------------+-----------------+-----------------------------------------------------------+
|503            | Service         | The server is currently unable to handle the request      |
|               | Unavailable     | due to a temporary overload or scheduled maintenance,     |
|               |                 | which will likely be alleviated after some delay.         |
+---------------+-----------------+-----------------------------------------------------------+




Request
""""""""""""""""




This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{project_id}              |String                   |Project ID of the user.  |
|                          |                         |Also referred to as the  |
|                          |                         |tenant ID or account ID. |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example Perform health check: HTTP request**


.. code::

   GET https://dfw.backup.api.rackspacecloud.com/v2/110011/health HTTP/1.1
   Host: dfw.backup.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept:application/json
   Content-type: application/json





Response
""""""""""""""""





This table shows the body parameters for the response:

+---------------------------+-------------------------+------------------------+
|Name                       |Type                     |Description             |
+===========================+=========================+========================+
|\ **storage**              |String                   |Information about       |
|                           |                         |storage.                |
+---------------------------+-------------------------+------------------------+
|storage.\ **cassandra**    |String                   |Information about the   |
|                           |                         |Cassandra database.     |
+---------------------------+-------------------------+------------------------+
|storage.cassandra.\        |String                   |Indicates if the        |
|**online**                 |                         |Cassandra database is   |
|                           |                         |online.                 |
+---------------------------+-------------------------+------------------------+
|storage.cassandra.\        |String                   |Links with information  |
|**links**                  |                         |about the Cassandra     |
|                           |                         |database.               |
+---------------------------+-------------------------+------------------------+
|storage.cassandra.links.\  |String                   |Location (URI).         |
|**href**                   |                         |                        |
+---------------------------+-------------------------+------------------------+
|storage.cassandra.links.\  |String                   |How the href link       |
|**rel**                    |                         |provided is related to  |
|                           |                         |this resource URI.      |
+---------------------------+-------------------------+------------------------+
|\ **transport**            |String                   |Information about the   |
|                           |                         |transport driver.       |
+---------------------------+-------------------------+------------------------+
|transport.\ **pecan**      |String                   |Information about the   |
|                           |                         |Pecan transport driver. |
+---------------------------+-------------------------+------------------------+
|transport.pecan.\          |String                   |Indicates if the Pecan  |
|**online**                 |                         |transport driver is     |
|                           |                         |online.                 |
+---------------------------+-------------------------+------------------------+
|transport.pecan.\ **node** |String                   |The node for the Pecan  |
|                           |                         |transport driver.       |
+---------------------------+-------------------------+------------------------+
|transport.pecan.\ **link** |String                   |Links for the Pecan     |
|                           |                         |transport driver.       |
+---------------------------+-------------------------+------------------------+
|transport.pecan.link.\     |String                   |Location (URI).         |
|**href**                   |                         |                        |
+---------------------------+-------------------------+------------------------+
|transport.pecan.link.\     |String                   |How the href link       |
|**rel**                    |                         |provided is related to  |
|                           |                         |this resource URI.      |
+---------------------------+-------------------------+------------------------+







**Example Perform health check with response code 200: JSON response**


.. code::

   200 (OK)
   Content-Type: application/json


.. code::

   {
     "storage": {
       "cassandra": {
         "online": true,
         "links": [
           {
             "href": "https://cloudbackupapi.apiary-mock.com/health/storage/cassandra",
             "rel": "self"
           }
         ]
       }
     },
     "transport": {
       "pecan": {
         "online": true,
         "node": "phx-web-01",
         "links": [
           {
             "href": "https://cloudbackupapi.apiary-mock.com/health/transport/pecan",
             "rel": "self"
           }
         ]
       }
     }
   }





**Example Perform health check with response code 503: JSON response**


.. code::

   503 (Service Unavailable)
   Content-Type: application/json


.. code::

   {
     "storage": {
       "cassandra": {
         "online": false,
         "links": [
           {
             "href": "https://cloudbackupapi.apiary-mock.com/health/storage/cassandra",
             "rel": "self"
           }
         ]
       }
     },
     "transport": {
       "pecan": {
         "online": true,
         "node": "phx-web-01",
         "links": [
           {
             "href": "https://cloudbackupapi.apiary-mock.com/health/transport/pecan",
             "rel": "self"
           }
         ]
       }
     }
   }





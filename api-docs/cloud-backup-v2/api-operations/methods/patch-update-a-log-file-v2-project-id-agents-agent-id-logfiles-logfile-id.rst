
.. _patch-update-a-log-file-for—an-agent:

Update a log file
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    PATCH /v2/{project_id}/agents/{agent_id}/logfiles/{logfile_id}

This operation updates the specified log file for the specified agent. Agents update the state of a log file by updating the ``/state`` path via a JSON Patch document. The ``/state`` path is the only path that can be modified. Only the ``replace`` operation is permitted. For more information about the JSON Patch, see `RFC6902 <http://tools.ietf.org/html/rfc6902>`__.

The initial state when the log file is requested is ``requested``. Agents update ``/state`` with the values ``started`` or ``completed``.



This table shows the possible response codes for this operation:


+---------------+-----------------+-----------------------------------------------------------+
|Response Code  |Name             |Description                                                |
+===============+=================+===========================================================+
|204            | No Content      | The server successfully fulfilled the request, and there  |
|               |                 | is no additional content to send in the response body.    |
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
|{agent_id}                |String *(Required)*      |Agent ID. For example,   |
|                          |                         |``8f135b4f-7a69-4b8a-    |
|                          |                         |947f-5e80d772fd97``.     |
+--------------------------+-------------------------+-------------------------+
|{logfile_id}              |String *(Required)*      |Log file ID. For         |
|                          |                         |example, ``a533a845-4279-|
|                          |                         |4838-af13-276114e90234``.|
+--------------------------+-------------------------+-------------------------+





This table shows the body parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|\ **op**                  |String *(Required)*      |The ``replace``          |
|                          |                         |operation to update the  |
|                          |                         |log file.                |
+--------------------------+-------------------------+-------------------------+
|\ **path**                |String *(Required)*      |Path. The valid value is |
|                          |                         |``/state``.              |
+--------------------------+-------------------------+-------------------------+
|\ **value**               |String *(Required)*      |Value related to the     |
|                          |                         |``path``. Valid values   |
|                          |                         |are ``started`` and      |
|                          |                         |``completed``.           |
+--------------------------+-------------------------+-------------------------+





**Example Update a log file: JSON request**


.. code::

   PATCH https://dfw.backup.api.rackspacecloud.com/v2/110011/agents/8f135b4f-7a69-4b8a-947f-5e80d772fd97/logfiles/a533a845-4279-4838-af13-276114e90234 HTTP/1.1
   Host: dfw.backup.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Content-Type: application/json-patch+json


.. code::

   [
       {
           "op": "replace",
           "path": "/state",
           "value": "started"
       }
   ]





Response
""""""""""""""""



This operation does not return a response body.






**Example Update a log file: 204 response**


.. code::

   204 (No Content)





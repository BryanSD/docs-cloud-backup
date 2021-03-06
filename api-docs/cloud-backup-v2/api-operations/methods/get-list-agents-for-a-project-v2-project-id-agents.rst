
.. _get-list-agents:

List agents for a project
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v2/{project_id}/agents

This operation lists all of the agents for a project.

If no agents have been created for the project, the ``agents`` parameter in the response is an empty array.



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



This table shows the query parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|host_machine_id           |String *(Optional)*      |ID of the host machine   |
|                          |                         |on which the agent       |
|                          |                         |resides. For example,    |
|                          |                         |``8f135b4f-7a69-4b8a-    |
|                          |                         |947f-5e80d772fd97``.     |
+--------------------------+-------------------------+-------------------------+




This operation does not accept a request body.




**Example List agents for a project: HTTP request**


.. code::

   GET https://dfw.backup.api.rackspacecloud.com/v2/110011/agents?host_machine_id=8f135b4f-7a69-4b8a-947f-5e80d772fd97 HTTP/1.1
   Host: dfw.backup.api.rackspacecloud.com
   X-Auth-Token: 0f6e9f63600142f0a970911583522217
   Accept: application/json
   Content-type: application/json





Response
""""""""""""""""





This table shows the body parameters for the response:

+-----------------------------+------------------------+-----------------------+
|Name                         |Type                    |Description            |
+=============================+========================+=======================+
|\ **agents**                 |String                  |Information about the  |
|                             |                        |agents for the project.|
+-----------------------------+------------------------+-----------------------+
|agents.\ **project_id**      |String                  |Project ID.            |
+-----------------------------+------------------------+-----------------------+
|agents.\ **id**              |String                  |Host machine ID.       |
+-----------------------------+------------------------+-----------------------+
|agents.\ **name**            |String                  |Host machine name.     |
+-----------------------------+------------------------+-----------------------+
|agents.\ **version**         |String                  |Version.               |
+-----------------------------+------------------------+-----------------------+
|agents.\ **host**            |String                  |Information about the  |
|                             |                        |host.                  |
+-----------------------------+------------------------+-----------------------+
|agents.host.\ **flavor**     |String                  |Flavor.                |
+-----------------------------+------------------------+-----------------------+
|agents.host.\ **region**     |String                  |Region.                |
+-----------------------------+------------------------+-----------------------+
|agents.host.\ **machine**    |String                  |Information about the  |
|                             |                        |machine.               |
+-----------------------------+------------------------+-----------------------+
|agents.host.machine.\ **id** |String                  |Machine ID.            |
+-----------------------------+------------------------+-----------------------+
|agents.host.machine.\        |String                  |Links with information |
|**links**                    |                        |about the machine.     |
+-----------------------------+------------------------+-----------------------+
|agents.host.machine.links.\  |String                  |Location (URI) of the  |
|**href**                     |                        |machine.               |
+-----------------------------+------------------------+-----------------------+
|agents.host.machine.links.\  |String                  |How the href link      |
|**rel**                      |                        |provided is related to |
|                             |                        |this resource URI.     |
+-----------------------------+------------------------+-----------------------+
|agents.host.\ **os**         |String                  |Information about the  |
|                             |                        |operating system.      |
+-----------------------------+------------------------+-----------------------+
|agents.host.os.\ **name**    |String                  |Name of the operating  |
|                             |                        |system.                |
+-----------------------------+------------------------+-----------------------+
|agents.host.os.\ **version** |String                  |Version of the         |
|                             |                        |operating system.      |
+-----------------------------+------------------------+-----------------------+
|agents.host.os.\             |String *(Required)*     |Architecture of the    |
|**architecture**             |                        |operating system.      |
+-----------------------------+------------------------+-----------------------+
|agents.host.\ **addresses**  |String                  |Information about the  |
|                             |                        |IP addresses.          |
+-----------------------------+------------------------+-----------------------+
|agents.host.addresses.\      |String                  |Version of the address |
|**version**                  |                        |(4 for IPv4 or 6 for   |
|                             |                        |IPv6).                 |
+-----------------------------+------------------------+-----------------------+
|agents.host.addresses.\      |String                  |IP address.            |
|**addr**                     |                        |                       |
+-----------------------------+------------------------+-----------------------+
|agents.\ **enabled**         |String                  |Specifies whether the  |
|                             |                        |agent is enabled.      |
+-----------------------------+------------------------+-----------------------+
|agents.\ **rsa_public_key**  |String                  |Information about the  |
|                             |                        |RSA public key.        |
+-----------------------------+------------------------+-----------------------+
|agents.rsa_public_key.\      |String                  |Modulus for the RSA    |
|**modulus**                  |                        |public key.            |
+-----------------------------+------------------------+-----------------------+
|agents.rsa_public_key.\      |String                  |Exponent for the RSA   |
|**exponent**                 |                        |public key.            |
+-----------------------------+------------------------+-----------------------+
|agents.\ **vault**           |String                  |Information about the  |
|                             |                        |vault.                 |
+-----------------------------+------------------------+-----------------------+
|agents.vault.\ **id**        |String                  |ID of the vault.       |
+-----------------------------+------------------------+-----------------------+
|agents.vault.\ **name**      |String                  |Name of the vault.     |
+-----------------------------+------------------------+-----------------------+
|agents.vault.\ **flavor**    |String                  |Flavor for the vault.  |
+-----------------------------+------------------------+-----------------------+
|agents.vault.\ **encrypted** |String                  |Specifies whether the  |
|                             |                        |vault is encrypted.    |
+-----------------------------+------------------------+-----------------------+
|agents.vault.\ **region**    |String                  |Region for the vault.  |
+-----------------------------+------------------------+-----------------------+
|agents.vault.\               |String                  |Specifies whether the  |
|**use_internal**             |                        |use of the vault is    |
|                             |                        |internal.              |
+-----------------------------+------------------------+-----------------------+
|agents.vault.\ **links**     |String                  |Links with information |
|                             |                        |about the vault.       |
+-----------------------------+------------------------+-----------------------+
|agents.vault.links.\ **href**|String                  |Location (URI).        |
+-----------------------------+------------------------+-----------------------+
|agents.vault.links.\ **rel** |String                  |How the href link      |
|                             |                        |provided is related to |
|                             |                        |this resource URI.     |
+-----------------------------+------------------------+-----------------------+
|agents.\ **log_level**       |String                  |Level for the logs.    |
+-----------------------------+------------------------+-----------------------+
|agents.\ **registered_time** |String                  |Time agent was         |
|                             |                        |registered.            |
+-----------------------------+------------------------+-----------------------+
|agents.\ **links**           |String                  |Links with information |
|                             |                        |about the agents.      |
+-----------------------------+------------------------+-----------------------+
|agents.links.\ **href**      |String                  |Location (URI).        |
+-----------------------------+------------------------+-----------------------+
|agents.links.\ **rel**       |String                  |How the href link      |
|                             |                        |provided is related to |
|                             |                        |this resource URI.     |
+-----------------------------+------------------------+-----------------------+







**Example List agents for a project: JSON response**


.. code::

   200 (OK)
   Content-Type: application/json


.. code::

   {
       "agents": [
           {
               "project_id": "123456",
               "id": "8f135b4f-7a69-4b8a-947f-5e80d772fd97",
               "name": "Web Server",
               "version": "1.23.008344",
               "host": {
                   "flavor": "nova",
                   "region": "DFW",
                   "machine": {
                       "id": "55f83711-85ff-49d6-9a1a-58c67d452c6a",
                       "links": [
                           {
                               "href": "https://cloudserversapi.apiary-mock.com/v2/123456/servers/55f83711-85ff-49d6-9a1a-58c67d452c6a",
                               "rel": "full"
                           }
                       ]
                   },
                   "os": {
                       "name": "Ubuntu",
                       "version": "14.04",
                       "architecture": "64-bit"
                   },
                   "addresses": [
                       {
                           "version": 4,
                           "addr": "67.23.10.132"
                       },
                       {
                           "version": 6,
                           "addr": "::babe:4317:0A83"
                       }
                   ]
               },
               "enabled": true,
               "rsa_public_key": {
                   "modulus": "E14F9A88DCFF94478E9FD16ED2CF838AE961FF981F0CA45325D0B60648E93A7C0583E02F661A8D0DB707D9566C91D156F68624C76A0620B1499C93A57FBD068DF12F2EB8F9678988582D55901E78B43F761689BA66F0E1CD6CFE1C1BB779E73EE615791FA2DCBCCE48F8D27DC2523D9E47BC04ECE9A2FE2FDD1C65394B76AEAE3569127E39519AD5A9EEBB7EA077718E2B33066F609127D7125963C9CDC081BE90E1FDC63C9FE5DAF5AB428AEACE258754E35F838AC9611FBC33F0C06A10E6F5B08BE92BE9F577BACE7B3A45D2AA2FEB2C6CF3290258F6051CC4C7428F59BE7D4D0EC3C6B48E9F0274A6022259713D40A34AB4874C762062E2B24783A6E8EA25",
                   "exponent": 10001
               },
               "vault": {
                   "id": "7cd999c3-a0c3-4985-99d4-42b544685456",
                   "name": "phoenix_7cd999c3-a0c3-4985-99d4-42b544685456",
                   "flavor": "swift",
                   "encrypted": true,
                   "region": "DFW",
                   "use_internal": false,
                   "links": [
                       {
                           "href": "https://cloudfilesapi.apiary-mock.com/v1/MossoCloudFS_f14d894e-28cd-4f31-8b08-449ec0876346/phoenix_7cd999c3-a0c3-4985-99d4-42b544685456",
                           "rel": "publicURL"
                       },
                       {
                           "href": "https://cloudfilesinternalapi.apiary-mock.com/v1/MossoCloudFS_f14d894e-28cd-4f31-8b08-449ec0876346/phoenix_7cd999c3-a0c3-4985-99d4-42b544685456",
                           "rel": "internalURL"
                       }
                   ]
               },
               "log_level": "warn",
               "registered_time": "2014-10-27T18:22:00.238640+00:00",
               "links": [
                   {
                       "href": "https://cloudbackupapi.apiary-mock.com/v2/agents/8f135b4f-7a69-4b8a-947f-5e80d772fd97",
                       "rel": "self"
                   },
                   {
                       "href": "https://cloudbackupapi.apiary-mock.com/v2/agents/8f135b4f-7a69-4b8a-947f-5e80d772fd97/activities",
                       "rel": "activities"
                   },
                   {
                       "href": "https://cloudbackupapi.apiary-mock.com/v2/agents/8f135b4f-7a69-4b8a-947f-5e80d772fd97/configuration",
                       "rel": "configuration"
                   },
                   {
                       "href": "https://cloudbackupapi.apiary-mock.com/v2/agents/8f135b4f-7a69-4b8a-947f-5e80d772fd97/configurations",
                       "rel": "configurations"
                   },
                   {
                       "href": "https://cloudbackupapi.apiary-mock.com/v2/agents/8f135b4f-7a69-4b8a-947f-5e80d772fd97/events",
                       "rel": "events"
                   },
                   {
                       "href": "https://cloudbackupapi.apiary-mock.com/v2/agents/8f135b4f-7a69-4b8a-947f-5e80d772fd97/logfiles",
                       "rel": "logfiles"
                   },
                   {
                       "href": "https://cloudbackupapi.apiary-mock.com/v2/agents/8f135b4f-7a69-4b8a-947f-5e80d772fd97/status",
                       "rel": "status"
                   }
               ]
           }
       ]
   }





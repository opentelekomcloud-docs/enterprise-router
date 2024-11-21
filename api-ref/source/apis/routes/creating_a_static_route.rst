:original_name: CreateStaticRoute.html

.. _CreateStaticRoute:

Creating a Static Route
=======================

Function
--------

This API is used to create a static route. Static routes are manually created, and effective routes are preferred routes.

Constraints
-----------

If **is_blackhole** is set to **false**, the **attachment_id** parameter must be carried. If **is_blackhole** is set to **true**, the **attachment_id** parameter cannot be passed.

URI
---

POST /v3/{project_id}/enterprise-router/route-tables/{route_table_id}/static-routes

.. table:: **Table 1** Path Parameters

   ============== ========= ====== ==============
   Parameter      Mandatory Type   Description
   ============== ========= ====== ==============
   project_id     Yes       String Project ID
   route_table_id Yes       String Route table ID
   ============== ========= ====== ==============

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+------------------------+
   | Parameter       | Mandatory       | Type            | Description            |
   +=================+=================+=================+========================+
   | X-Client-Token  | No              | String          | Idempotence identifier |
   |                 |                 |                 |                        |
   |                 |                 |                 | Minimum: **1**         |
   |                 |                 |                 |                        |
   |                 |                 |                 | Maximum: **64**        |
   +-----------------+-----------------+-----------------+------------------------+

.. table:: **Table 3** Request body parameters

   +-----------+-----------+--------------------------------------------------------------------+-----------------------------------+
   | Parameter | Mandatory | Type                                                               | Description                       |
   +===========+===========+====================================================================+===================================+
   | route     | Yes       | :ref:`CreateRoute <createstaticroute__request_createroute>` object | Request body for creating a route |
   +-----------+-----------+--------------------------------------------------------------------+-----------------------------------+

.. _createstaticroute__request_createroute:

.. table:: **Table 4** CreateRoute

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                         |
   +=================+=================+=================+=====================================================================+
   | destination     | Yes             | String          | Destination address of the route                                    |
   |                 |                 |                 |                                                                     |
   |                 |                 |                 | Minimum: **0**                                                      |
   |                 |                 |                 |                                                                     |
   |                 |                 |                 | Maximum: **256**                                                    |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------+
   | attachment_id   | No              | String          | ID of the attachment that the next hop of the route points to       |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------+
   | is_blackhole    | No              | Boolean         | Whether the route is a blackhole route. The default value is false. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 202**

.. table:: **Table 5** Response header parameters

   ============== ====== ======================
   Parameter      Type   Description
   ============== ====== ======================
   X-Client-Token String Idempotence identifier
   ============== ====== ======================

.. table:: **Table 6** Response body parameters

   +------------+---------------------------------------------------------+-------------+
   | Parameter  | Type                                                    | Description |
   +============+=========================================================+=============+
   | route      | :ref:`Route <createstaticroute__response_route>` object | Route       |
   +------------+---------------------------------------------------------+-------------+
   | request_id | String                                                  | Request ID  |
   +------------+---------------------------------------------------------+-------------+

.. _createstaticroute__response_route:

.. table:: **Table 7** Route

   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Parameter      | Type                                                                                  | Description                                                                                                       |
   +================+=======================================================================================+===================================================================================================================+
   | id             | String                                                                                | Route ID                                                                                                          |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | type           | String                                                                                | Route type. The value is **static**.                                                                              |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | state          | String                                                                                | Route status. Value options: **pending**, **available**, **modifying**, **deleting**, **deleted**, and **failed** |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | is_blackhole   | Boolean                                                                               | Whether the route is a blackhole route                                                                            |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | destination    | String                                                                                | Destination address of the route                                                                                  |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | attachments    | Array of :ref:`RouteAttachment <createstaticroute__response_routeattachment>` objects | Next hops                                                                                                         |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | route_table_id | String                                                                                | Route table ID                                                                                                    |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | created_at     | String                                                                                | Creation time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                                              |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | updated_at     | String                                                                                | Update time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                                                |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+

.. _createstaticroute__response_routeattachment:

.. table:: **Table 8** RouteAttachment

   +-----------------------+-----------------------+----------------------------+
   | Parameter             | Type                  | Description                |
   +=======================+=======================+============================+
   | resource_id           | String                | Attached resource ID       |
   +-----------------------+-----------------------+----------------------------+
   | resource_type         | String                | Attachment type.           |
   |                       |                       |                            |
   |                       |                       | -  **vpc**: VPC attachment |
   +-----------------------+-----------------------+----------------------------+
   | attachment_id         | String                | Attachment ID              |
   +-----------------------+-----------------------+----------------------------+

Example Requests
----------------

Creating a static route

.. code-block:: text

   POST https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/route-tables/0d1748a0-5188-11e5-b86f-a51b5f125b84/static-routes

   {
     "route" : {
       "destination" : "192.168.0.0/16",
       "is_blackhole" : false,
       "attachment_id" : "b70aee08-c671-4cad-9fd5-7381d163bcc8"
     }
   }

Example Responses
-----------------

**Status code: 202**

Accepted

.. code-block::

   {
     "route" : {
       "id" : "9b3b38a9-1c9d-4f01-9429-81af6b545289",
       "type" : "static",
       "destination" : "192.168.0.0/16",
       "attachments" : [ {
         "resource_id" : "9c4ab06a-0ab4-4fad-93a8-f733f3a4433d",
         "resource_type" : "vpc",
         "attachment_id" : "b70aee08-c671-4cad-9fd5-7381d163bcc8"
       } ],
       "route_table_id" : "0d1748a0-5188-11e5-b86f-a51b5f125b84",
       "is_blackhole" : false,
       "state" : "pending",
       "created_at" : "2020-03-11T15:13:31Z",
       "updated_at" : "2020-03-11T15:13:31Z"
     },
     "request_id" : "915a14a6-867b-4af7-83d1-70efceb146f9"
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
202         Accepted
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.

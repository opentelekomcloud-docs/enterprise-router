:original_name: UpdateStaticRoute.html

.. _UpdateStaticRoute:

Updating a Static Route
=======================

Function
--------

This API is used to update a static route.

Constraints
-----------

If **is_blackhole** is set to **false**, the **attachment_id** parameter must be carried. If **is_blackhole** is set to **true**, the **attachment_id** parameter cannot be passed.

URI
---

PUT /v3/{project_id}/enterprise-router/route-tables/{route_table_id}/static-routes/{route_id}

.. table:: **Table 1** Path Parameters

   ============== ========= ====== ==============
   Parameter      Mandatory Type   Description
   ============== ========= ====== ==============
   project_id     Yes       String Project ID
   route_table_id Yes       String Route table ID
   route_id       Yes       String Route ID
   ============== ========= ====== ==============

Request Parameters
------------------

.. table:: **Table 2** Request body parameters

   +-----------+-----------+--------------------------------------------------------------------+-------------+
   | Parameter | Mandatory | Type                                                               | Description |
   +===========+===========+====================================================================+=============+
   | route     | Yes       | :ref:`UpdateRoute <updatestaticroute__request_updateroute>` object | Route       |
   +-----------+-----------+--------------------------------------------------------------------+-------------+

.. _updatestaticroute__request_updateroute:

.. table:: **Table 3** UpdateRoute

   ============= ========= ======= ======================================
   Parameter     Mandatory Type    Description
   ============= ========= ======= ======================================
   attachment_id No        String  Next hop of the route
   is_blackhole  No        Boolean Whether the route is a blackhole route
   ============= ========= ======= ======================================

Response Parameters
-------------------

**Status code: 202**

.. table:: **Table 4** Response body parameters

   +------------+---------------------------------------------------------+-------------+
   | Parameter  | Type                                                    | Description |
   +============+=========================================================+=============+
   | route      | :ref:`Route <updatestaticroute__response_route>` object | Route       |
   +------------+---------------------------------------------------------+-------------+
   | request_id | String                                                  | Request ID  |
   +------------+---------------------------------------------------------+-------------+

.. _updatestaticroute__response_route:

.. table:: **Table 5** Route

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
   | attachments    | Array of :ref:`RouteAttachment <updatestaticroute__response_routeattachment>` objects | Next hops                                                                                                         |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | route_table_id | String                                                                                | Route table ID                                                                                                    |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | created_at     | String                                                                                | Creation time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                                              |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | updated_at     | String                                                                                | Update time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                                                |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | description    | String                                                                                | Route description.                                                                                                |
   +----------------+---------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------+

.. _updatestaticroute__response_routeattachment:

.. table:: **Table 6** RouteAttachment

   +-----------------------+-----------------------+--------------------------------------------+
   | Parameter             | Type                  | Description                                |
   +=======================+=======================+============================================+
   | resource_id           | String                | Attached resource ID                       |
   +-----------------------+-----------------------+--------------------------------------------+
   | resource_type         | String                | Attachment type.                           |
   |                       |                       |                                            |
   |                       |                       | -  **vpc**: VPC                            |
   |                       |                       |                                            |
   |                       |                       | -  **vpn**: VPN gateway                    |
   |                       |                       |                                            |
   |                       |                       | -  **vgw**: Direct Connect virtual gateway |
   |                       |                       |                                            |
   |                       |                       | -  **cfw**: CFW instance                   |
   +-----------------------+-----------------------+--------------------------------------------+
   | attachment_id         | String                | Attachment ID                              |
   +-----------------------+-----------------------+--------------------------------------------+
   | priority              | Integer               | Route priority, the common route is 1      |
   +-----------------------+-----------------------+--------------------------------------------+

Example Requests
----------------

Modifying a static route

.. code-block:: text

   PUT https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/route-tables/19d334b7-78c1-4e0e-ba29-b797e641e23c/static-routes/9b3b38a9-1c9d-4f01-9429-81af6b545289

   {
     "route" : {
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
       "description" : "static route",
       "attachments" : [ {
         "resource_id" : "9c4ab06a-0ab4-4fad-93a8-f733f3a4433d",
         "resource_type" : "vpc",
         "attachment_id" : "b70aee08-c671-4cad-9fd5-7381d163bcc8",
         "priority" : 0
       } ],
       "route_table_id" : "19d334b7-78c1-4e0e-ba29-b797e641e23c",
       "is_blackhole" : false,
       "state" : "pending",
       "created_at" : "2020-03-11T15:13:31",
       "updated_at" : "2020-03-11T15:13:31"
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

:original_name: ListEffectiveRoutes.html

.. _ListEffectiveRoutes:

Querying Effective Routes
=========================

Function
--------

This API is used to query effective routes. Pagination query is supported. Effective routes are preferred routes.

URI
---

GET /v3/{project_id}/enterprise-router/route-tables/{route_table_id}/routes

.. table:: **Table 1** Path Parameters

   ============== ========= ====== ==============
   Parameter      Mandatory Type   Description
   ============== ========= ====== ==============
   project_id     Yes       String Project ID
   route_table_id Yes       String Route table ID
   ============== ========= ====== ==============

.. table:: **Table 2** Query Parameters

   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                                                                             |
   +=================+=================+==================+=========================================================================================================================================================+
   | limit           | No              | Integer          | Number of records on each page. Value range: **0** to **2000**                                                                                          |
   |                 |                 |                  |                                                                                                                                                         |
   |                 |                 |                  | Minimum: **0**                                                                                                                                          |
   |                 |                 |                  |                                                                                                                                                         |
   |                 |                 |                  | Maximum: **2000**                                                                                                                                       |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | marker          | No              | String           | ID of the last route on the previous page. If this parameter is left blank, the first page is queried. This parameter must be used together with limit. |
   |                 |                 |                  |                                                                                                                                                         |
   |                 |                 |                  | Minimum: **1**                                                                                                                                          |
   |                 |                 |                  |                                                                                                                                                         |
   |                 |                 |                  | Maximum: **128**                                                                                                                                        |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | destination     | No              | Array of strings | Destination address of the route                                                                                                                        |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | resource_type   | No              | Array of strings | Attachment type.                                                                                                                                        |
   |                 |                 |                  |                                                                                                                                                         |
   |                 |                 |                  | -  **vpc**: VPC attachment                                                                                                                              |
   |                 |                 |                  |                                                                                                                                                         |
   |                 |                 |                  | -  **vpn**: VPN gateway attachment                                                                                                                      |
   |                 |                 |                  |                                                                                                                                                         |
   |                 |                 |                  | -  **vgw**: virtual gateway attachment                                                                                                                  |
   +-----------------+-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +------------+---------------------------------------------------------------------------------------+------------------------------+
   | Parameter  | Type                                                                                  | Description                  |
   +============+=======================================================================================+==============================+
   | routes     | Array of :ref:`EffectiveRoute <listeffectiveroutes__response_effectiveroute>` objects | Routes                       |
   +------------+---------------------------------------------------------------------------------------+------------------------------+
   | request_id | String                                                                                | Request ID                   |
   +------------+---------------------------------------------------------------------------------------+------------------------------+
   | page_info  | :ref:`PageInfo <listeffectiveroutes__response_pageinfo>` object                       | Pagination query information |
   +------------+---------------------------------------------------------------------------------------+------------------------------+

.. _listeffectiveroutes__response_effectiveroute:

.. table:: **Table 4** EffectiveRoute

   +------------------+-----------------------------------------------------------------------------------------+---------------------------------------------------------------+
   | Parameter        | Type                                                                                    | Description                                                   |
   +==================+=========================================================================================+===============================================================+
   | route_id         | String                                                                                  | Route ID                                                      |
   +------------------+-----------------------------------------------------------------------------------------+---------------------------------------------------------------+
   | destination      | String                                                                                  | Destination address of the route                              |
   +------------------+-----------------------------------------------------------------------------------------+---------------------------------------------------------------+
   | next_hops        | Array of :ref:`RouteAttachment <listeffectiveroutes__response_routeattachment>` objects | Next hops of the routes                                       |
   +------------------+-----------------------------------------------------------------------------------------+---------------------------------------------------------------+
   | is_blackhole     | Boolean                                                                                 | Whether the route is a blackhole route                        |
   +------------------+-----------------------------------------------------------------------------------------+---------------------------------------------------------------+
   | route_type       | String                                                                                  | Route type. Value options: **static** and **propagation**     |
   +------------------+-----------------------------------------------------------------------------------------+---------------------------------------------------------------+
   | address_group_id | String                                                                                  | IP address group ID. This parameter is not supported for now. |
   +------------------+-----------------------------------------------------------------------------------------+---------------------------------------------------------------+

.. _listeffectiveroutes__response_routeattachment:

.. table:: **Table 5** RouteAttachment

   +-----------------------+-----------------------+----------------------------------------+
   | Parameter             | Type                  | Description                            |
   +=======================+=======================+========================================+
   | resource_id           | String                | Attached resource ID                   |
   +-----------------------+-----------------------+----------------------------------------+
   | resource_type         | String                | Attachment type.                       |
   |                       |                       |                                        |
   |                       |                       | -  **vpc**: VPC attachment             |
   |                       |                       |                                        |
   |                       |                       | -  **vpn**: VPN gateway attachment     |
   |                       |                       |                                        |
   |                       |                       | -  **vgw**: virtual gateway attachment |
   +-----------------------+-----------------------+----------------------------------------+
   | attachment_id         | String                | Attachment ID                          |
   +-----------------------+-----------------------+----------------------------------------+

.. _listeffectiveroutes__response_pageinfo:

.. table:: **Table 6** PageInfo

   +---------------+---------+-------------------------------------------------------------------------------------------------------------------+
   | Parameter     | Type    | Description                                                                                                       |
   +===============+=========+===================================================================================================================+
   | next_marker   | String  | Marker of the next page. The value is the resource UUID. If the value is empty, the resource is on the last page. |
   +---------------+---------+-------------------------------------------------------------------------------------------------------------------+
   | current_count | Integer | Number of resources in the list                                                                                   |
   +---------------+---------+-------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Querying effective routes

.. code-block:: text

   GET https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/route-tables/915a14a6-867b-4af7-83d1-70efceb146f9/routes

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "routes" : [ {
       "route_id" : "9b3b38a9-1c9d-4f01-9429-81af6b545289",
       "destination" : "192.168.0.0/16",
       "next_hops" : [ {
         "resource_id" : "9c4ab06a-0ab4-4fad-93a8-f733f3a4433d",
         "resource_type" : "vpc",
         "attachment_id" : "9b3b38a9-1c9d-4f01-9429-81af6b545289"
       } ],
       "is_blackhole" : false,
       "route_type" : "static"
     } ],
     "page_info" : {
       "next_marker" : "1",
       "current_count" : 1
     },
     "request_id" : "915a14a6-867b-4af7-83d1-70efceb146f9"
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         OK
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.

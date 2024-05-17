:original_name: ShowRouteTable.html

.. _ShowRouteTable:

Querying Details About a Route Table
====================================

Function
--------

This API is used to query details about a route table.

URI
---

GET /v3/{project_id}/enterprise-router/{er_id}/route-tables/{route_table_id}

.. table:: **Table 1** Path Parameters

   ============== ========= ====== ====================
   Parameter      Mandatory Type   Description
   ============== ========= ====== ====================
   project_id     Yes       String Project ID
   er_id          Yes       String Enterprise router ID
   route_table_id Yes       String Route table ID
   ============== ========= ====== ====================

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-------------+----------------------------------------------------------------+-------------+
   | Parameter   | Type                                                           | Description |
   +=============+================================================================+=============+
   | route_table | :ref:`RouteTable <showroutetable__response_routetable>` object | Route table |
   +-------------+----------------------------------------------------------------+-------------+
   | request_id  | String                                                         | Request ID  |
   +-------------+----------------------------------------------------------------+-------------+

.. _showroutetable__response_routetable:

.. table:: **Table 3** RouteTable

   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Parameter              | Type                                                           | Description                                                                            |
   +========================+================================================================+========================================================================================+
   | id                     | String                                                         | Route table ID                                                                         |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | name                   | String                                                         | Route table name                                                                       |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | description            | String                                                         | Supplementary information                                                              |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | is_default_association | Boolean                                                        | Whether the route table is the default association route table.                        |
   |                        |                                                                |                                                                                        |
   |                        |                                                                | Default: **false**                                                                     |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | is_default_propagation | Boolean                                                        | Whether the route table is the default propagation route table.                        |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | state                  | String                                                         | Route table status. The value can be pending, available, deleting, deleted, or failed. |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | tags                   | Array of :ref:`Tag <showroutetable__response_tag>` objects     | Tag                                                                                    |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | bgp_options            | :ref:`BgpOptions <showroutetable__response_bgpoptions>` object | BGP route selection parameters. This parameter is not supported for now.               |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | created_at             | String                                                         | Creation time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                   |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | updated_at             | String                                                         | Update time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                     |
   +------------------------+----------------------------------------------------------------+----------------------------------------------------------------------------------------+

.. _showroutetable__response_tag:

.. table:: **Table 4** Tag

   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                                      |
   +=======================+=======================+==================================================================================================================================================================================================+
   | key                   | String                | Tag key. The value contain up to 128 characters (36 characters on the console), including uppercase letters, lowercase letters, digits, hyphens (-), underscores (_), and at signs (@).          |
   |                       |                       |                                                                                                                                                                                                  |
   |                       |                       | Minimum: **1**                                                                                                                                                                                   |
   |                       |                       |                                                                                                                                                                                                  |
   |                       |                       | Maximum: **128**                                                                                                                                                                                 |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value                 | String                | Tag value. The value contain up to 128 characters in API (43 characters on the console), including uppercase letters, lowercase letters, digits, hyphens (-), underscores (_), and at signs (@). |
   |                       |                       |                                                                                                                                                                                                  |
   |                       |                       | Minimum: **0**                                                                                                                                                                                   |
   |                       |                       |                                                                                                                                                                                                  |
   |                       |                       | Maximum: **128**                                                                                                                                                                                 |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _showroutetable__response_bgpoptions:

.. table:: **Table 5** BgpOptions

   +-------------------------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                     | Type    | Description                                                                                                                                         |
   +===============================+=========+=====================================================================================================================================================+
   | load_balancing_as_path_ignore | Boolean | BGP option to specify that AS-Path attributes are not compared during load balancing. This parameter is not supported for now.                      |
   +-------------------------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | load_balancing_as_path_relax  | Boolean | BGP option to specify that AS-Path attributes with the same length are not compared during load balancing. This parameter is not supported for now. |
   +-------------------------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Querying details about a route table

.. code-block:: text

   GET https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/915a14a6-867b-4af7-83d1-70efceb146f6/route-tables/4ab54142-7c92-48ad-8288-77727a231052

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "route_table" : {
       "id" : "4ab54142-7c92-48ad-8288-77727a231052",
       "name" : "my-route-table",
       "description" : "rtb-for-a",
       "is_default_association" : false,
       "is_default_propagation" : false,
       "state" : "available",
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
200         OK
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.

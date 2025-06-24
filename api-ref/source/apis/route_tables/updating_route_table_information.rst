:original_name: UpdateRouteTable.html

.. _UpdateRouteTable:

Updating Route Table Information
================================

Function
--------

This API is used to update basic information about a route table, such as the name and description.

URI
---

PUT /v3/{project_id}/enterprise-router/{er_id}/route-tables/{route_table_id}

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

.. table:: **Table 2** Request body parameters

   +-------------+-----------+-----------------------------------------------------------------------------+-----------------------------------------+
   | Parameter   | Mandatory | Type                                                                        | Description                             |
   +=============+===========+=============================================================================+=========================================+
   | route_table | No        | :ref:`UpdateRouteTable <updateroutetable__request_updateroutetable>` object | Request body for updating a route table |
   +-------------+-----------+-----------------------------------------------------------------------------+-----------------------------------------+

.. _updateroutetable__request_updateroutetable:

.. table:: **Table 3** UpdateRouteTable

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                           |
   +=================+=================+=================+=======================================================================================================================================+
   | name            | No              | String          | Route table name. The value can contain 1 to 64 characters, including letters, digits, underscores (_), hyphens (-), and periods (.). |
   |                 |                 |                 |                                                                                                                                       |
   |                 |                 |                 | Minimum: **1**                                                                                                                        |
   |                 |                 |                 |                                                                                                                                       |
   |                 |                 |                 | Maximum: **64**                                                                                                                       |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | description     | No              | String          | Supplementary information about the route table                                                                                       |
   |                 |                 |                 |                                                                                                                                       |
   |                 |                 |                 | Minimum: **0**                                                                                                                        |
   |                 |                 |                 |                                                                                                                                       |
   |                 |                 |                 | Maximum: **255**                                                                                                                      |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-------------+------------------------------------------------------------------+-------------+
   | Parameter   | Type                                                             | Description |
   +=============+==================================================================+=============+
   | route_table | :ref:`RouteTable <updateroutetable__response_routetable>` object | Route table |
   +-------------+------------------------------------------------------------------+-------------+
   | request_id  | String                                                           | Request ID  |
   +-------------+------------------------------------------------------------------+-------------+

.. _updateroutetable__response_routetable:

.. table:: **Table 5** RouteTable

   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Parameter              | Type                                                             | Description                                                                            |
   +========================+==================================================================+========================================================================================+
   | id                     | String                                                           | Route table ID                                                                         |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | name                   | String                                                           | Route table name                                                                       |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | description            | String                                                           | Supplementary information                                                              |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | is_default_association | Boolean                                                          | Whether the route table is the default association route table.                        |
   |                        |                                                                  |                                                                                        |
   |                        |                                                                  | Default: **false**                                                                     |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | is_default_propagation | Boolean                                                          | Whether the route table is the default propagation route table.                        |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | state                  | String                                                           | Route table status. The value can be pending, available, deleting, deleted, or failed. |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | tags                   | Array of :ref:`Tag <updateroutetable__response_tag>` objects     | Tag                                                                                    |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | bgp_options            | :ref:`BgpOptions <updateroutetable__response_bgpoptions>` object | BGP route selection parameters. This parameter is not supported for now.               |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | created_at             | String                                                           | Creation time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                   |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | updated_at             | String                                                           | Update time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                     |
   +------------------------+------------------------------------------------------------------+----------------------------------------------------------------------------------------+

.. _updateroutetable__response_tag:

.. table:: **Table 6** Tag

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                              |
   +=======================+=======================+==========================================================================================+
   | key                   | String                | Tag key. The key:                                                                        |
   |                       |                       |                                                                                          |
   |                       |                       | -  Can contain UTF-8 letters, digits, spaces, and the following characters: ``_.:=+-@.`` |
   |                       |                       |                                                                                          |
   |                       |                       | -  Cannot start with *sys* because it indicates a system tag.                            |
   |                       |                       |                                                                                          |
   |                       |                       | -  Cannot be empty (the length cannot be 0).                                             |
   |                       |                       |                                                                                          |
   |                       |                       | -  Can contain 1 to 128 characters.                                                      |
   |                       |                       |                                                                                          |
   |                       |                       | Minimum: **1**                                                                           |
   |                       |                       |                                                                                          |
   |                       |                       | Maximum: **128**                                                                         |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+
   | value                 | String                | Tag value. The value:                                                                    |
   |                       |                       |                                                                                          |
   |                       |                       | -  Can contain UTF-8 letters, digits, spaces, and the following characters: ``_.:=+-@.`` |
   |                       |                       |                                                                                          |
   |                       |                       | -  Can be empty or null.                                                                 |
   |                       |                       |                                                                                          |
   |                       |                       | -  Can contain 0 to 255 characters.                                                      |
   |                       |                       |                                                                                          |
   |                       |                       | Minimum: **0**                                                                           |
   |                       |                       |                                                                                          |
   |                       |                       | Maximum: **255**                                                                         |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+

.. _updateroutetable__response_bgpoptions:

.. table:: **Table 7** BgpOptions

   +-------------------------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                     | Type    | Description                                                                                                                                         |
   +===============================+=========+=====================================================================================================================================================+
   | load_balancing_as_path_ignore | Boolean | BGP option to specify that AS-Path attributes are not compared during load balancing. This parameter is not supported for now.                      |
   +-------------------------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | load_balancing_as_path_relax  | Boolean | BGP option to specify that AS-Path attributes with the same length are not compared during load balancing. This parameter is not supported for now. |
   +-------------------------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Changing the name of a route table of an enterprise router to **new-rtb**

.. code-block:: text

   PUT https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/915a14a6-867b-4af7-83d1-70efceb146f5/route-tables/4ab54142-7c92-48ad-8288-77727a231052

   {
     "route_table" : {
       "name" : "new-rtb"
     }
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "route_table" : {
       "id" : "4ab54142-7c92-48ad-8288-77727a231052",
       "name" : "new-rtb",
       "is_default_association" : false,
       "is_default_propagation" : false,
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
200         OK
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.

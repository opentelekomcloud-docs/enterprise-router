:original_name: ShowQuotas.html

.. _ShowQuotas:

Querying Quotas
===============

Function
--------

This API is used to query the used quotas of resources, such as enterprise routers and VPC attachments.

URI
---

GET /v3/{project_id}/enterprise-router/quotas

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String Project ID
   ========== ========= ====== ===========

.. table:: **Table 2** Query Parameters

   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                                                            |
   +=================+=================+==================+========================================================================================================================================+
   | type            | No              | Array of strings | You can query the quotas of the following resources:                                                                                   |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **er_instance**: total and used quotas of enterprise routers                                                                        |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **vpc_attachment**: total and used quotas of VPC attachments                                                                        |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **route_table**: total and used quotas of route tables                                                                              |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **static_route**: total and used quotas of static routes                                                                            |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **vpc_er**: total and used quotas of enterprise routers that a VPC can be attached to                                               |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **flow_log**: total and used quotas of flow logs that can be created for each attachment                                            |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **dc_attachment**: total and used quotas of Direct Connect gateway attachments                                                      |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **vpn_attachment**: total and used quotas of VPN gateway attachments                                                                |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **connect_attachment**: total and used quotas of Connect gateway attachments. This type of attachments is not supported now.        |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **peering_attachment**: total and used quotas of peering connection attachments. This type of attachments is not supported now.     |
   |                 |                 |                  |                                                                                                                                        |
   |                 |                 |                  | -  **can_attachment**: total and used quotas of intelligent access gateway attachments. This type of attachments is not supported now. |
   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | erId            | No              | Object           | Enterprise router ID                                                                                                                   |
   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | routeTableId    | No              | Object           | Route table ID                                                                                                                         |
   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | vpcId           | No              | Object           | VPC ID                                                                                                                                 |
   +-----------------+-----------------+------------------+----------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------+------------------------------------------------------------+--------------------+
   | Parameter | Type                                                       | Description        |
   +===========+============================================================+====================+
   | quotas    | Array of :ref:`Quota <showquotas__response_quota>` objects | Used quota details |
   +-----------+------------------------------------------------------------+--------------------+

.. _showquotas__response_quota:

.. table:: **Table 4** Quota

   +-------------+--------+---------------------------------------------------------------------------+
   | Parameter   | Type   | Description                                                               |
   +=============+========+===========================================================================+
   | quota_key   | String | Quota type                                                                |
   +-------------+--------+---------------------------------------------------------------------------+
   | quota_limit | Long   | Available quota. The value **-1** indicates that there is no quota limit. |
   +-------------+--------+---------------------------------------------------------------------------+
   | used        | Long   | Used quota                                                                |
   +-------------+--------+---------------------------------------------------------------------------+
   | unit        | String | Measurement unit of used quotas                                           |
   +-------------+--------+---------------------------------------------------------------------------+

Example Requests
----------------

Querying the resource quotas

.. code-block:: text

   GET https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/quotas

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "quotas" : [ {
       "quota_key" : "er_instance",
       "quota_limit" : 1,
       "used" : 0,
       "unit" : "count"
     }, {
       "quota_key" : "dc_attachment",
       "quota_limit" : 2,
       "used" : 0,
       "unit" : "count"
     }, {
       "quota_key" : "route_table",
       "quota_limit" : 20,
       "used" : 5,
       "unit" : "count"
     }, {
       "quota_key" : "static_route",
       "quota_limit" : 500,
       "used" : 2,
       "unit" : "count"
     }, {
       "quota_key" : "can_attachment",
       "quota_limit" : 10,
       "used" : 0,
       "unit" : "count"
     }, {
       "quota_key" : "connect_attachment",
       "quota_limit" : 20,
       "used" : 0,
       "unit" : "count"
     }, {
       "quota_key" : "peering_attachment",
       "quota_limit" : 10,
       "used" : 0,
       "unit" : "count"
     }, {
       "quota_key" : "vpn_attachment",
       "quota_limit" : 10,
       "used" : 0,
       "unit" : "count"
     }, {
       "quota_key" : "flow_log",
       "quota_limit" : 20,
       "used" : 4,
       "unit" : "count"
     } ]
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

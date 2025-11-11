:original_name: DisassociateRouteTable.html

.. _DisassociateRouteTable:

Deleting a Route Association
============================

Function
--------

This API is used to delete an association from the route table of an enterprise router for an attachment.

URI
---

POST /v3/{project_id}/enterprise-router/{er_id}/route-tables/{route_table_id}/disassociate

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

   +-----------------+-----------------+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                                | Description                                                                    |
   +=================+=================+=====================================================================================+================================================================================+
   | attachment_id   | No              | String                                                                              | Unique ID of the attachment                                                    |
   |                 |                 |                                                                                     |                                                                                |
   |                 |                 |                                                                                     | Maximum: **36**                                                                |
   +-----------------+-----------------+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | route_policy    | No              | :ref:`ExportRoutePolicy <disassociateroutetable__request_exportroutepolicy>` object | Route that controls outbound traffic. This parameter is not supported for now. |
   +-----------------+-----------------+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+

.. _disassociateroutetable__request_exportroutepolicy:

.. table:: **Table 3** ExportRoutePolicy

   +------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------+
   | Parameter        | Mandatory       | Type            | Description                                                                                     |
   +==================+=================+=================+=================================================================================================+
   | export_policy_id | No              | String          | ID of the route policy that controls outbound traffic. This parameter is not supported for now. |
   |                  |                 |                 |                                                                                                 |
   |                  |                 |                 | Minimum: **0**                                                                                  |
   |                  |                 |                 |                                                                                                 |
   |                  |                 |                 | Maximum: **36**                                                                                 |
   +------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 202**

Accepted

None

Example Requests
----------------

Deleting a route table association

.. code-block:: text

   POST https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/915a14a6-867b-4af7-83d1-70efceb146f8/route-tables/915a14a6-867b-4af7-83d1-70efceb146f9/disassociate

   {
     "attachment_id" : "2609ec92-ac19-4467-a527-7f9e690e7836"
   }

Example Responses
-----------------

None

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

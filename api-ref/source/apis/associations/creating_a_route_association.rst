:original_name: AssociateRouteTable.html

.. _AssociateRouteTable:

Creating a Route Association
============================

Function
--------

This API is used to create a route association. Each attachment only can be associated with one route table of its enterprise router for packet forwarding.

URI
---

POST /v3/{project_id}/enterprise-router/{er_id}/route-tables/{route_table_id}/associate

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

   +-----------------+-----------------+----------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                             | Description                                                                    |
   +=================+=================+==================================================================================+================================================================================+
   | attachment_id   | No              | String                                                                           | Unique ID of the attachment                                                    |
   |                 |                 |                                                                                  |                                                                                |
   |                 |                 |                                                                                  | Maximum: **36**                                                                |
   +-----------------+-----------------+----------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | route_policy    | No              | :ref:`ExportRoutePolicy <associateroutetable__request_exportroutepolicy>` object | Route that controls outbound traffic. This parameter is not supported for now. |
   +-----------------+-----------------+----------------------------------------------------------------------------------+--------------------------------------------------------------------------------+

.. _associateroutetable__request_exportroutepolicy:

.. table:: **Table 4** ExportRoutePolicy

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

.. table:: **Table 5** Response header parameters

   ============== ====== ======================
   Parameter      Type   Description
   ============== ====== ======================
   X-Client-Token String Idempotence identifier
   ============== ====== ======================

.. table:: **Table 6** Response body parameters

   +-------------+-----------------------------------------------------------------------+---------------------+
   | Parameter   | Type                                                                  | Description         |
   +=============+=======================================================================+=====================+
   | association | :ref:`Association <associateroutetable__response_association>` object | Association details |
   +-------------+-----------------------------------------------------------------------+---------------------+
   | request_id  | String                                                                | Request ID          |
   +-------------+-----------------------------------------------------------------------+---------------------+

.. _associateroutetable__response_association:

.. table:: **Table 7** Association

   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                              | Description                                                                                                 |
   +=======================+===================================================================================+=============================================================================================================+
   | id                    | String                                                                            | Unique association ID                                                                                       |
   |                       |                                                                                   |                                                                                                             |
   |                       |                                                                                   | Maximum: **36**                                                                                             |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | route_table_id        | String                                                                            | Unique ID of the route table                                                                                |
   |                       |                                                                                   |                                                                                                             |
   |                       |                                                                                   | Maximum: **36**                                                                                             |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | attachment_id         | String                                                                            | Unique ID of the attachment                                                                                 |
   |                       |                                                                                   |                                                                                                             |
   |                       |                                                                                   | Maximum: **36**                                                                                             |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | resource_type         | String                                                                            | -  **vpc**: VPC                                                                                             |
   |                       |                                                                                   |                                                                                                             |
   |                       |                                                                                   | -  **vpn**: VPN gateway                                                                                     |
   |                       |                                                                                   |                                                                                                             |
   |                       |                                                                                   | -  **vgw**: Direct Connect virtual gateway                                                                  |
   |                       |                                                                                   |                                                                                                             |
   |                       |                                                                                   | -  **cfw**: CFW instance                                                                                    |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | resource_id           | String                                                                            | Unique ID of the attachment                                                                                 |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | state                 | String                                                                            | Status. Value options: **pending**, **available**, **modifying**, **deleting**, **deleted**, and **failed** |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | created_at            | String                                                                            | Creation time. It is UTC time in the format of YYYY-MM-DDTHH:mm:ss.sssZ.                                    |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | updated_at            | String                                                                            | Update time. It is UTC time in the format of YYYY-MM-DDTHH:mm:ss.sssZ.                                      |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | route_policy          | :ref:`ExportRoutePolicy <associateroutetable__response_exportroutepolicy>` object | Route that controls outbound traffic. This parameter is not supported for now.                              |
   +-----------------------+-----------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+

.. _associateroutetable__response_exportroutepolicy:

.. table:: **Table 8** ExportRoutePolicy

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                     |
   +=======================+=======================+=================================================================================================+
   | export_policy_id      | String                | ID of the route policy that controls outbound traffic. This parameter is not supported for now. |
   |                       |                       |                                                                                                 |
   |                       |                       | Minimum: **0**                                                                                  |
   |                       |                       |                                                                                                 |
   |                       |                       | Maximum: **36**                                                                                 |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------+

Example Requests
----------------

Creating a route table association

.. code-block:: text

   POST https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/915a14a6-867b-4af7-83d1-70efceb146f8/route-tables/915a14a6-867b-4af7-83d1-70efceb146f9/associate

   {
     "attachment_id" : "a5b7d209-dc02-4c46-a51f-805eadd3de64"
   }

Example Responses
-----------------

**Status code: 202**

Accepted

.. code-block::

   {
     "association" : {
       "id" : "915a14a6-867b-4af7-83d1-70efceb146f9",
       "route_table_id" : "91c013e2-d65a-474e-9177-c3e1799ca726",
       "attachment_id" : "a5b7d209-dc02-4c46-a51f-805eadd3de64",
       "resource_type" : "vpc",
       "resource_id" : "4e5fe97c-82bc-432e-87d8-06d7e157dffa",
       "state" : "pending",
       "created_at" : "2020-03-11T15:13:31",
       "updated_at" : "2020-03-11T15:13:31",
       "route_policy" : {
         "export_policy_id" : ""
       }
     },
     "request_id" : "915a14a6-867b-4af7-83d1-70efceb146f8"
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

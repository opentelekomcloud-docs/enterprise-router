:original_name: EnablePropagation.html

.. _EnablePropagation:

Creating a Route Propagation
============================

Function
--------

This API is used to create a route propagation. A propagation can be created for each attachment to propagate routes to one or more route tables on an enterprise router.

URI
---

POST /v3/{project_id}/enterprise-router/{er_id}/route-tables/{route_table_id}/enable-propagations

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

   +---------------+-----------+--------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | Parameter     | Mandatory | Type                                                                           | Description                                                                   |
   +===============+===========+================================================================================+===============================================================================+
   | attachment_id | No        | String                                                                         | Unique ID of the attachment                                                   |
   +---------------+-----------+--------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | route_policy  | No        | :ref:`ImportRoutePolicy <enablepropagation__request_importroutepolicy>` object | Route that controls inbound traffic. This parameter is not supported for now. |
   +---------------+-----------+--------------------------------------------------------------------------------+-------------------------------------------------------------------------------+

.. _enablepropagation__request_importroutepolicy:

.. table:: **Table 4** ImportRoutePolicy

   +------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | Parameter        | Mandatory       | Type            | Description                                                                                    |
   +==================+=================+=================+================================================================================================+
   | import_policy_id | No              | String          | ID of the route policy that controls inbound traffic. This parameter is not supported for now. |
   |                  |                 |                 |                                                                                                |
   |                  |                 |                 | Minimum: **0**                                                                                 |
   |                  |                 |                 |                                                                                                |
   |                  |                 |                 | Maximum: **36**                                                                                |
   +------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+

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

   +-------------+---------------------------------------------------------------------+---------------------+
   | Parameter   | Type                                                                | Description         |
   +=============+=====================================================================+=====================+
   | propagation | :ref:`Propagation <enablepropagation__response_propagation>` object | Propagation details |
   +-------------+---------------------------------------------------------------------+---------------------+
   | request_id  | String                                                              | Request ID          |
   +-------------+---------------------------------------------------------------------+---------------------+

.. _enablepropagation__response_propagation:

.. table:: **Table 7** Propagation

   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                            | Description                                                                                                 |
   +=======================+=================================================================================+=============================================================================================================+
   | id                    | String                                                                          | Unique association ID                                                                                       |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | project_id            | String                                                                          | Project ID                                                                                                  |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | er_id                 | String                                                                          | Enterprise router ID                                                                                        |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | route_table_id        | String                                                                          | Unique ID of the route table                                                                                |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | attachment_id         | String                                                                          | Unique ID of the attachment                                                                                 |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | resource_type         | String                                                                          | Attachment type.                                                                                            |
   |                       |                                                                                 |                                                                                                             |
   |                       |                                                                                 | -  **vpc**: VPC attachment                                                                                  |
   |                       |                                                                                 |                                                                                                             |
   |                       |                                                                                 | -  **vpn**: VPN gateway attachment                                                                          |
   |                       |                                                                                 |                                                                                                             |
   |                       |                                                                                 | -  **vgw**: virtual gateway attachment                                                                      |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | resource_id           | String                                                                          | Unique ID of the attachment                                                                                 |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | route_policy          | :ref:`ImportRoutePolicy <enablepropagation__response_importroutepolicy>` object | Route that controls inbound traffic. This parameter is not supported for now.                               |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | state                 | String                                                                          | Status. Value options: **pending**, **available**, **modifying**, **deleting**, **deleted**, and **failed** |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | created_at            | String                                                                          | Creation time. It is UTC time in the format of YYYY-MM-DDTHH:mm:ss.sssZ.                                    |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+
   | updated_at            | String                                                                          | Update time. It is UTC time in the format of YYYY-MM-DDTHH:mm:ss.sssZ.                                      |
   +-----------------------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------+

.. _enablepropagation__response_importroutepolicy:

.. table:: **Table 8** ImportRoutePolicy

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                    |
   +=======================+=======================+================================================================================================+
   | import_policy_id      | String                | ID of the route policy that controls inbound traffic. This parameter is not supported for now. |
   |                       |                       |                                                                                                |
   |                       |                       | Minimum: **0**                                                                                 |
   |                       |                       |                                                                                                |
   |                       |                       | Maximum: **36**                                                                                |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+

Example Requests
----------------

Creating a route propagation

.. code-block:: text

   POST https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/ad838a5e-dbef-22cc-b1d9-cb46bef77ae8/route-tables/915a14a6-867b-4af7-83d1-70efceb146f9/enable-propagations

   {
     "attachment_id" : "a5b7d209-dc02-4c46-a51f-805eadd3de64"
   }

Example Responses
-----------------

**Status code: 202**

Accepted

.. code-block::

   {
     "propagation" : {
       "id" : "915a14a6-867b-4af7-83d1-70efceb146f9",
       "route_table_id" : "91c013e2-d65a-474e-9177-c3e1799ca726",
       "attachment_id" : "a5b7d209-dc02-4c46-a51f-805eadd3de64",
       "resource_type" : "vpc",
       "resource_id" : "4e5fe97c-82bc-432e-87d8-06d7e157dffa",
       "route_policy" : {
         "import_policy_id" : ""
       },
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

:original_name: DisablePropagation.html

.. _DisablePropagation:

Deleting a Route Propagation
============================

Function
--------

This API is used to delete a propagation from the route table of an enterprise router for an attachment.

URI
---

POST /v3/{project_id}/enterprise-router/{er_id}/route-tables/{route_table_id}/disable-propagations

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

   +---------------+-----------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | Parameter     | Mandatory | Type                                                                            | Description                                                                   |
   +===============+===========+=================================================================================+===============================================================================+
   | attachment_id | No        | String                                                                          | Unique ID of the attachment                                                   |
   +---------------+-----------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | route_policy  | No        | :ref:`ImportRoutePolicy <disablepropagation__request_importroutepolicy>` object | Route that controls inbound traffic. This parameter is not supported for now. |
   +---------------+-----------+---------------------------------------------------------------------------------+-------------------------------------------------------------------------------+

.. _disablepropagation__request_importroutepolicy:

.. table:: **Table 3** ImportRoutePolicy

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

None

Example Requests
----------------

Deleting a route table propagation

.. code-block:: text

   POST https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/ad838a5e-dbef-22cc-b1d9-cb46bef77ae8/route-tables/915a14a6-867b-4af7-83d1-70efceb146f9/disable-propagations

   {
     "attachment_id" : "a5b7d209-dc02-4c46-a51f-805eadd3de64"
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

:original_name: ShowResourceTag.html

.. _ShowResourceTag:

Querying Resource Tags
======================

Function
--------

This API is used to query tags of resources of a specific type.

URI
---

GET /v3/{project_id}/{resource_type}/{resource_id}/tags

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                       |
   +=================+=================+=================+===================================================+
   | project_id      | Yes             | String          | Project ID                                        |
   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | resource_id     | Yes             | String          | Resource ID                                       |
   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | resource_type   | Yes             | String          | Resource type.                                    |
   |                 |                 |                 |                                                   |
   |                 |                 |                 | -  **instance**: enterprise router                |
   |                 |                 |                 |                                                   |
   |                 |                 |                 | -  **route-table**: route table                   |
   |                 |                 |                 |                                                   |
   |                 |                 |                 | -  **vpc-attachment**: VPC attachment             |
   |                 |                 |                 |                                                   |
   |                 |                 |                 | -  **vgw-attachment**: virtual gateway attachment |
   |                 |                 |                 |                                                   |
   |                 |                 |                 | -  **vpn-attachment**: VPN gateway attachment     |
   +-----------------+-----------------+-----------------+---------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------+-------------------------------------------------------------+-------------+
   | Parameter | Type                                                        | Description |
   +===========+=============================================================+=============+
   | tags      | Array of :ref:`Tag <showresourcetag__response_tag>` objects | Tags        |
   +-----------+-------------------------------------------------------------+-------------+

.. _showresourcetag__response_tag:

.. table:: **Table 3** Tag

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

Example Requests
----------------

Querying tags of an enterprise router

.. code-block::

   https://{erouter_endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/instance/f1a28dfd-186f-4625-b6b1-f05e5e8609c0/tags

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "tags" : [ {
       "key" : "key2",
       "value" : "value2"
     }, {
       "key" : "key1",
       "value" : "value1"
     }, {
       "key" : "key3",
       "value" : "value3"
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

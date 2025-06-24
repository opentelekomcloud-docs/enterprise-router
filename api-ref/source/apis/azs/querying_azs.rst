:original_name: ListAvailabilityZone.html

.. _ListAvailabilityZone:

Querying AZs
============

Function
--------

This API is used to query AZs where enterprise routers can be created. An enterprise router can be created only when an AZ is in the available state.

URI
---

GET /v3/{project_id}/enterprise-router/availability-zones

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String Project ID
   ========== ========= ====== ===========

.. table:: **Table 2** Query Parameters

   =========== ========= ====== ====================
   Parameter   Mandatory Type   Description
   =========== ========= ====== ====================
   instance_id No        String Enterprise router ID
   =========== ========= ====== ====================

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +--------------------+--------------------------------------------------------------------------------------+-------------+
   | Parameter          | Type                                                                                 | Description |
   +====================+======================================================================================+=============+
   | availability_zones | Array of :ref:`AvailableZone <listavailabilityzone__response_availablezone>` objects | AZ list     |
   +--------------------+--------------------------------------------------------------------------------------+-------------+
   | request_id         | String                                                                               | Request ID  |
   +--------------------+--------------------------------------------------------------------------------------+-------------+

.. _listavailabilityzone__response_availablezone:

.. table:: **Table 4** AvailableZone

   +-----------+--------+-------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                   |
   +===========+========+===============================================================================+
   | code      | String | AZ code                                                                       |
   +-----------+--------+-------------------------------------------------------------------------------+
   | state     | String | Whether the AZ is available. Value options: **available** and **unavailable** |
   +-----------+--------+-------------------------------------------------------------------------------+

Example Requests
----------------

Querying AZs

.. code-block:: text

   GET https://{erouter_endpoint}/v3/0605767a9980d5762fbcc00b3537e757/enterprise-router/availability-zones

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "availability_zones" : [ {
       "code" : "az1",
       "state" : "available"
     }, {
       "code" : "az2",
       "state" : "unavailable"
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

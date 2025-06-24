:original_name: DeleteRouteTable.html

.. _DeleteRouteTable:

Deleting a Route Table
======================

Function
--------

This API is used to delete a route table.

URI
---

DELETE /v3/{project_id}/enterprise-router/{er_id}/route-tables/{route_table_id}

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

**Status code: 202**

Accepted

None

Example Requests
----------------

.. code-block:: text

   DELETE https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/4ab54142-7c92-48ad-8288-77727a231056/route-tables/4ab54142-7c92-48ad-8288-77727a231052

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

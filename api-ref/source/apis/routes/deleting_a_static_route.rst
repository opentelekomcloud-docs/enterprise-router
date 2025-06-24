:original_name: DeleteStaticRoute.html

.. _DeleteStaticRoute:

Deleting a Static Route
=======================

Function
--------

This API is used to delete a static route.

URI
---

DELETE /v3/{project_id}/enterprise-router/route-tables/{route_table_id}/static-routes/{route_id}

.. table:: **Table 1** Path Parameters

   ============== ========= ====== ==============
   Parameter      Mandatory Type   Description
   ============== ========= ====== ==============
   project_id     Yes       String Project ID
   route_table_id Yes       String Route table ID
   route_id       Yes       String Route ID
   ============== ========= ====== ==============

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

   DELETE https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/route-tables/3ddb4dc2-174e-4d43-9328-b805d5c0c774/static-routes/19d334b7-78c1-4e0e-ba29-b797e641e23c

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

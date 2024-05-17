:original_name: DeleteEnterpriseRouter.html

.. _DeleteEnterpriseRouter:

Deleting an Enterprise Router
=============================

Function
--------

This API is used to delete an enterprise router.

URI
---

DELETE /v3/{project_id}/enterprise-router/instances/{er_id}

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ====================
   Parameter  Mandatory Type   Description
   ========== ========= ====== ====================
   project_id Yes       String Project ID
   er_id      Yes       String Enterprise router ID
   ========== ========= ====== ====================

Request Parameters
------------------

None

Response Parameters
-------------------

None

Example Requests
----------------

Deleting an enterprise router

.. code-block:: text

   DELETE https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/instances/94c2b814-99dc-939a-e811-ae84c61ea3ff

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

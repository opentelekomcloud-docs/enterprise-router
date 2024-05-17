:original_name: DeleteFlowLog.html

.. _DeleteFlowLog:

Deleting a Flow Log
===================

Function
--------

This API is used to delete a flow log.

Constraints
-----------

A flow log can be deleted only when it is in the **available**, **deleting**, or **failed** state.

URI
---

DELETE /v3/{project_id}/enterprise-router/{er_id}/flow-logs/{flow_log_id}

.. table:: **Table 1** Path Parameters

   =========== ========= ====== ====================
   Parameter   Mandatory Type   Description
   =========== ========= ====== ====================
   project_id  Yes       String Project ID
   er_id       Yes       String Enterprise router ID
   flow_log_id Yes       String Flow log ID
   =========== ========= ====== ====================

Request Parameters
------------------

None

Response Parameters
-------------------

None

Example Requests
----------------

Deleting a flow log

.. code-block:: text

   DELETE https://{erouter_endpoint}/v3/0605767a9980d5762fbcc00b3537e757/enterprise-router/6f83b848-8331-4271-ac0c-ef94b7686402/flow_logs/b216bc1d-5963-41a7-89f9-779a5128c5ac

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

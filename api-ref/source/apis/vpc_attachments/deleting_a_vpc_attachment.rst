:original_name: DeleteVpcAttachment.html

.. _DeleteVpcAttachment:

Deleting a VPC Attachment
=========================

Function
--------

This API is used to delete a VPC attachment.

Constraints
-----------

A VPC attachment can be deleted only when it is in the available, deleting, or failed state.

URI
---

DELETE /v3/{project_id}/enterprise-router/{er_id}/vpc-attachments/{vpc_attachment_id}

.. table:: **Table 1** Path Parameters

   ================= ========= ====== ====================
   Parameter         Mandatory Type   Description
   ================= ========= ====== ====================
   project_id        Yes       String Project ID
   er_id             Yes       String Enterprise router ID
   vpc_attachment_id Yes       String VPC attachment ID
   ================= ========= ====== ====================

Request Parameters
------------------

None

Response Parameters
-------------------

None

Example Requests
----------------

Deleting a VPC attachment

.. code-block:: text

   DELETE https://{erouter_endpoint}/v3/08d5a9564a704afda6039ae2babbef3c/enterprise-router/4ba931b6-5273-4ed9-8eeb-484d16a4786f/vpc-attachments/b70aee08-c671-4cad-9fd5-7381d163bcc8

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

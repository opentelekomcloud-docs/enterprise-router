:original_name: DeleteResourceTag.html

.. _DeleteResourceTag:

Deleting Resource Tags
======================

Function
--------

This API is used to delete tags for resources of a specific type.

Constraints
-----------

This API is idempotent. The key cannot be left blank or be an empty string.

URI
---

DELETE /v3/{project_id}/{resource_type}/{resource_id}/tags/{key}

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                       |
   +=================+=================+=================+===================================================+
   | key             | Yes             | String          | Tag key                                           |
   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | project_id      | Yes             | String          | Project ID                                        |
   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | resource_id     | Yes             | String          | Resource ID                                       |
   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | resource_type   | Yes             | String          | Tagged resource type.                             |
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
   |                 |                 |                 |                                                   |
   |                 |                 |                 | -  **cfw-attachment**: CFW instance attachment    |
   +-----------------+-----------------+-----------------+---------------------------------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 204**

No Content

None

Example Requests
----------------

.. code-block:: text

   DELETE https://{erouter-endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/instance/3320166e-b937-40cc-a35c-02cd3f2b3ee2/tags/key1

Example Responses
-----------------

None

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
204         No Content
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.

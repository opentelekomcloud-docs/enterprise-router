:original_name: CreateResourceTag.html

.. _CreateResourceTag:

Creating Resource Tags
======================

Function
--------

This API is used to create tags for resources of a specific type.

Constraints
-----------

-  A resource can have up to 20 tags.

-  This API is idempotent.

-  If a tag to be created has the same key as an existing tag, the tag will be created and overwrite the existing one.

URI
---

POST /v3/{project_id}/{resource_type}/{resource_id}/tags

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                       |
   +=================+=================+=================+===================================================+
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

.. table:: **Table 2** Request body parameters

   +-----------+-----------+----------------------------------------------------+--------------+
   | Parameter | Mandatory | Type                                               | Description  |
   +===========+===========+====================================================+==============+
   | tag       | Yes       | :ref:`Tag <createresourcetag__request_tag>` object | Resource tag |
   +-----------+-----------+----------------------------------------------------+--------------+

.. _createresourcetag__request_tag:

.. table:: **Table 3** Tag

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                              |
   +=================+=================+=================+==========================================================================================+
   | key             | No              | String          | Tag key. The key:                                                                        |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | -  Can contain UTF-8 letters, digits, spaces, and the following characters: ``_.:=+-@.`` |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | -  Cannot start with *sys* because it indicates a system tag.                            |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | -  Cannot be empty (the length cannot be 0).                                             |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | -  Can contain 1 to 128 characters.                                                      |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | Minimum: **1**                                                                           |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | Maximum: **128**                                                                         |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------+
   | value           | No              | String          | Tag value. The value:                                                                    |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | -  Can contain UTF-8 letters, digits, spaces, and the following characters: ``_.:=+-@.`` |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | -  Can be empty or null.                                                                 |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | -  Can contain 0 to 255 characters.                                                      |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | Minimum: **0**                                                                           |
   |                 |                 |                 |                                                                                          |
   |                 |                 |                 | Maximum: **255**                                                                         |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 204**

No Content

None

Example Requests
----------------

Creating tags for a resource

.. code-block:: text

   POST https://{erouter-endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/instance/3320166e-b937-40cc-a35c-02cd3f2b3ee2/tags

   {
     "tag" : {
       "key" : "key1",
       "value" : "value1"
     }
   }

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

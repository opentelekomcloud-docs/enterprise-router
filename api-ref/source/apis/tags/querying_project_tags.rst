:original_name: ListProjectTags.html

.. _ListProjectTags:

Querying Project Tags
=====================

Function
--------

This API is used to query tags of resources of a specific type.

URI
---

GET /v3/{project_id}/{resource_type}/tags

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                       |
   +=================+=================+=================+===================================================+
   | project_id      | Yes             | String          | Project ID                                        |
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

**Status code: 200**

.. table:: **Table 2** Response body parameters

   +-----------+---------------------------------------------------------------+-------------+
   | Parameter | Type                                                          | Description |
   +===========+===============================================================+=============+
   | tags      | Array of :ref:`Tags <listprojecttags__response_tags>` objects | Tags        |
   +-----------+---------------------------------------------------------------+-------------+

.. _listprojecttags__response_tags:

.. table:: **Table 3** Tags

   +-----------+------------------+-------------------------------------------------------------------------------------+
   | Parameter | Type             | Description                                                                         |
   +===========+==================+=====================================================================================+
   | key       | String           | Tag key, which cannot be empty and can contain a maximum of 127 Unicode characters. |
   +-----------+------------------+-------------------------------------------------------------------------------------+
   | values    | Array of strings | Tag values. Each value can contain a maximum of 255 Unicode characters.             |
   +-----------+------------------+-------------------------------------------------------------------------------------+

Example Requests
----------------

Querying tags of an enterprise router

.. code-block::

   https://{erouter_endpoint}/v3/cfa563efb77d4b6d9960781d82530fd8/instance/tags

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "tags" : [ {
       "key" : "keys",
       "values" : [ "value" ]
     }, {
       "key" : "key3",
       "values" : [ "value3", "value33" ]
     }, {
       "key" : "key1",
       "values" : [ "value1" ]
     }, {
       "key" : "key2",
       "values" : [ "value2", "value22" ]
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

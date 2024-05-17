:original_name: EnableFlowLog.html

.. _EnableFlowLog:

Enabling Flow Logs
==================

Function
--------

This API is used to enable flow logs.

URI
---

POST /v3/{project_id}/enterprise-router/{er_id}/flow-logs/{flow_log_id}/enable

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

**Status code: 202**

.. table:: **Table 2** Response body parameters

   +------------+---------------------------------------------------------+------------------+
   | Parameter  | Type                                                    | Description      |
   +============+=========================================================+==================+
   | flow_log   | :ref:`FlowLog <enableflowlog__response_flowlog>` object | Flow log details |
   +------------+---------------------------------------------------------+------------------+
   | request_id | String                                                  | Request ID       |
   +------------+---------------------------------------------------------+------------------+

.. _enableflowlog__response_flowlog:

.. table:: **Table 3** FlowLog

   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | Parameter                | Type    | Description                                                                                                          |
   +==========================+=========+======================================================================================================================+
   | id                       | String  | Flow log ID                                                                                                          |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | name                     | String  | Flow log name                                                                                                        |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | description              | String  | Flow log description                                                                                                 |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | project_id               | String  | Project ID of the flow log task creator                                                                              |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | resource_type            | String  | Resource type. The value is **attachment**.                                                                          |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | resource_id              | String  | Resource ID                                                                                                          |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | log_group_id             | String  | Log group ID                                                                                                         |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | log_stream_id            | String  | Log stream ID                                                                                                        |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | log_store_type           | String  | Flow log storage type. LTS is used for log storage.                                                                  |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | log_store_name           | String  | Flow log storage name. This parameter is not supported for now.                                                      |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | log_aggregation_interval | Integer | Log aggregation time, in seconds. The value ranges from **60** to **600**.                                           |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | created_at               | String  | Creation time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                                                 |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | updated_at               | String  | Update time in the format YYYY-MM-DDTHH:mm:ss.sssZ                                                                   |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | state                    | String  | Flow log status. Value options: **pending**, **available**, **modifying**, **deleting**, **deleted**, and **failed** |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+
   | enabled                  | Boolean | Whether to enable flow logs. The value can be **true** or **false**.                                                 |
   +--------------------------+---------+----------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Enabling flow logs

.. code-block:: text

   POST https://{erouter_endpoint}/v3/0605767a9980d5762fbcc00b3537e757/enterprise-router/a43c55e9-4911-4030-90e1-5c2bf6ae6fe2/flow-logs/b216bc1d-5963-41a7-89f9-779a5128c5ac/enable

Example Responses
-----------------

**Status code: 202**

Accepted

.. code-block::

   {
     "flow_log" : {
       "id" : "b216bc1d-5963-41a7-89f9-779a5128c5ac",
       "name" : "flow_log_update",
       "project_id" : "0605767a9980d5762fbcc00b3537e757",
       "resource_type" : "attachment",
       "resource_id" : "6f83b848-8331-4271-ac0c-ef94b7686402",
       "log_group_id" : "0139393c-eeb2-49f0-bbd4-c5faec6b1497",
       "log_stream_id" : "d22c3b44-2f71-470f-83f3-96a8af6956ad",
       "log_store_type" : "LTS",
       "log_aggregation_interval" : 600,
       "created_at" : "2020-03-11T15:13:31Z",
       "updated_at" : "2022-03-11T15:13:31Z",
       "state" : "available",
       "enabled" : true,
       "description" : "Flow Logs"
     },
     "request_id" : "915a14a6-867b-4af7-83d1-70efceb146f9"
   }

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

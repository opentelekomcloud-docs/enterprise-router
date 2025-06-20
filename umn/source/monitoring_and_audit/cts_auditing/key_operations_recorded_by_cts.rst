:original_name: er_01_0091.html

.. _er_01_0091:

Key Operations Recorded by CTS
==============================

An enterprise router is a central router that interconnects all of your VPCs and on-premises networks.

With CTS, you can record operations associated with your enterprise routers for future query, audit, and backtracking.

.. table:: **Table 1** Enterprise router operations recorded by CTS

   +---------------------------------------------------------------------+---------------+------------------------------+
   | Operation                                                           | Resource Type | Trace Name                   |
   +=====================================================================+===============+==============================+
   | Creating an enterprise router                                       | erInstance    | createInstance               |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Modifying an enterprise router                                      | erInstance    | updateInstance               |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Deleting an enterprise router                                       | erInstance    | deleteInstance               |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Adding attachments to an enterprise router                          | erAttachment  | createAttachment             |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Modifying an Attachment                                             | erAttachment  | updateAttachment             |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Deleting an attachment                                              | erAttachment  | deleteAttachment             |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Accepting an attachment request                                     | erAttachment  | acceptAttachment             |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Rejecting an attachment request                                     | erAttachment  | rejectAttachment             |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Creating a route table                                              | erRouteTable  | createRouteTable             |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Modifying a route table                                             | erRouteTable  | updateRouteTable             |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Deleting a route table                                              | erRouteTable  | deleteRouteTable             |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Creating a static route                                             | erStaticRoute | createStaticRoute            |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Batch creating static routes                                        | erStaticRoute | batchCreateStaticRoute       |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Deleting a static route                                             | erStaticRoute | deleteStaticRoute            |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Batch deleting static routes                                        | erStaticRoute | batchDeleteStaticRoute       |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Modifying a static route                                            | erStaticRoute | updateStaticRoute            |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Creating an association                                             | erAssociation | createAssociation            |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Deleting an association                                             | erAssociation | deleteAssociation            |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Creating a propagation                                              | erPropagation | createPropagation            |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Deleting a propagation                                              | erPropagation | deletePropagation            |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Creating a flow log                                                 | erFlowLog     | createFlowLog                |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Modifying a flow log                                                | erFlowLog     | updateFlowLog                |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Disabling a flow log                                                | erFlowLog     | updateFlowLog                |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Enabling a flow log                                                 | erFlowLog     | updateFlowLog                |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Deleting a flow log                                                 | erFlowLog     | deleteFlowLog                |
   +---------------------------------------------------------------------+---------------+------------------------------+
   | Performing operations on enterprise router resource tags in batches | erTag         | batchOperationErResourceTags |
   +---------------------------------------------------------------------+---------------+------------------------------+

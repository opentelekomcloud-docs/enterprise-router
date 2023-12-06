:original_name: er_01_0091.html

.. _er_01_0091:

Key Operations Recorded by CTS
==============================

An enterprise router is a central router that interconnects all of your VPCs and on-premises networks.

With CTS, you can record operations associated with your enterprise routers for future query, audit, and backtracking.

.. table:: **Table 1** Enterprise router operations recorded by CTS

   +--------------------------------------------+---------------+------------------------+
   | Operation                                  | Resource Type | Trace Name             |
   +============================================+===============+========================+
   | Creating an Enterprise Router              | erInstance    | createInstance         |
   +--------------------------------------------+---------------+------------------------+
   | Modifying an Enterprise Router             | erInstance    | updateInstance         |
   +--------------------------------------------+---------------+------------------------+
   | Deleting an Enterprise Router              | erInstance    | deleteInstance         |
   +--------------------------------------------+---------------+------------------------+
   | Adding Attachments to an Enterprise Router | erAttachment  | createAttachment       |
   +--------------------------------------------+---------------+------------------------+
   | Modifying an Attachment                    | erAttachment  | updateAttachment       |
   +--------------------------------------------+---------------+------------------------+
   | Deleting an Attachment                     | erAttachment  | deleteAttachment       |
   +--------------------------------------------+---------------+------------------------+
   | Accepting an Attachment Request            | erAttachment  | acceptAttachment       |
   +--------------------------------------------+---------------+------------------------+
   | Rejecting an Attachment Request            | erAttachment  | rejectAttachment       |
   +--------------------------------------------+---------------+------------------------+
   | Creating a Route Table                     | erRouteTable  | createRouteTable       |
   +--------------------------------------------+---------------+------------------------+
   | Modifying Route Table Information          | erRouteTable  | updateRouteTable       |
   +--------------------------------------------+---------------+------------------------+
   | Deleting a Route Table                     | erRouteTable  | deleteRouteTable       |
   +--------------------------------------------+---------------+------------------------+
   | Creating a Static Route                    | erStaticRoute | createStaticRoute      |
   +--------------------------------------------+---------------+------------------------+
   | Batch Creating Static Routes               | erStaticRoute | batchCreateStaticRoute |
   +--------------------------------------------+---------------+------------------------+
   | Deleting a Static Route                    | erStaticRoute | deleteStaticRoute      |
   +--------------------------------------------+---------------+------------------------+
   | Batch Deleting Static Routes               | erStaticRoute | batchDeleteStaticRoute |
   +--------------------------------------------+---------------+------------------------+
   | Modifying a Static Route                   | erStaticRoute | updateStaticRoute      |
   +--------------------------------------------+---------------+------------------------+
   | Creating an Association                    | erAssociation | createAssociation      |
   +--------------------------------------------+---------------+------------------------+
   | Deleting an Association                    | erAssociation | deleteAssociation      |
   +--------------------------------------------+---------------+------------------------+
   | Creating a Propagation                     | erPropagation | createPropagation      |
   +--------------------------------------------+---------------+------------------------+
   | Deleting a Propagation                     | erPropagation | deletePropagation      |
   +--------------------------------------------+---------------+------------------------+
   | Creating a Flow Log                        | erFlowLog     | createFlowLog          |
   +--------------------------------------------+---------------+------------------------+
   | Disabling a Flow Log                       | erFlowLog     | updateFlowLog          |
   +--------------------------------------------+---------------+------------------------+
   | Enabling a Flow Log                        | erFlowLog     | updateFlowLog          |
   +--------------------------------------------+---------------+------------------------+
   | Deleting a Flow Log                        | erFlowLog     | deleteFlowLog          |
   +--------------------------------------------+---------------+------------------------+

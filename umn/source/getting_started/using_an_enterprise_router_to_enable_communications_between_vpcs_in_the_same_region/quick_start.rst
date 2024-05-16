:original_name: er_01_0062.html

.. _er_01_0062:

Quick Start
===========

Background
----------

Four VPCs are created in region A on public cloud and they need to communicate with each other.

You can create an enterprise router in region A and attach the four VPCs to the enterprise router. The enterprise router can route traffic among the VPCs so that they can communicate with each other.


.. figure:: /_static/images/en-us_image_0000001295153022.png
   :alt: **Figure 1** Communications among VPCs in the same region

   **Figure 1** Communications among VPCs in the same region

.. note::

   This document describes how to use an enterprise router to quickly allow multiple VPCs in the same region to communicate with each other.

   You can :ref:`share an enterprise router <er_01_0095>` with different accounts to attach VPCs of these accounts to the same enterprise router for communication.

Procedure
---------

:ref:`Figure 2 <er_01_0062__fig10285152624918>` shows the procedure for using an enterprise router to allow multiple VPCs in the same region to communicate with each other.

.. _er_01_0062__fig10285152624918:

.. figure:: /_static/images/en-us_image_0000001160921916.png
   :alt: **Figure 2** Flowchart for connecting VPCs in the same region

   **Figure 2** Flowchart for connecting VPCs in the same region

.. table:: **Table 1** Steps for connecting VPCs in the same region

   +-----------------------+-----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | No.                   | Step                                                                        | Description                                                                                                                                                                                                                                                                                                                                  |
   +=======================+=============================================================================+==============================================================================================================================================================================================================================================================================================================================================+
   | 1                     | :ref:`Step 1: Plan Networks and Resources <er_01_0063>`                     | Plan CIDR blocks and the number of resources.                                                                                                                                                                                                                                                                                                |
   +-----------------------+-----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 2                     | :ref:`Step 2: Create an Enterprise Router <er_01_0064>`                     | Create one enterprise router for connecting VPCs in the same region.                                                                                                                                                                                                                                                                         |
   +-----------------------+-----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 3                     | :ref:`Step 3: (Optional) Create VPCs and ECSs <er_01_0065>`                 | Create four VPCs and four ECSs. You can change the resource quantity and specifications as needed.                                                                                                                                                                                                                                           |
   |                       |                                                                             |                                                                                                                                                                                                                                                                                                                                              |
   |                       |                                                                             | If you already have these resources, skip this step.                                                                                                                                                                                                                                                                                         |
   +-----------------------+-----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 4                     | :ref:`Step 4: Create VPC Attachments to the Enterprise Router <er_01_0066>` | Attach the four VPCs to the enterprise router.                                                                                                                                                                                                                                                                                               |
   +-----------------------+-----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 5                     | :ref:`Step 5: (Optional) Add Routes to VPC Route Tables <er_01_0067>`       | Add routes to the route tables of the VPCs for communication with the enterprise router.                                                                                                                                                                                                                                                     |
   |                       |                                                                             |                                                                                                                                                                                                                                                                                                                                              |
   |                       |                                                                             | -  If you enable **Auto Add Routes** when creating a VPC attachment, you do not need to manually add static routes to the VPC route table. Instead, the system automatically adds routes (with this enterprise router as the next hop and 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16 as the destinations) to all route tables of the VPC. |
   |                       |                                                                             | -  If an existing route in the VPC route tables has a destination to 10.0.0.0/8, 172.16.0.0/12, or 192.168.0.0/16, the routes will fail to be added. In this case, do not need to enable **Auto Add Routes**. After the attachment is created, manually add routes.                                                                          |
   +-----------------------+-----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 6                     | :ref:`Step 6: Verify Connectivity Among VPCs <er_01_0068>`                  | Log in to the ECS and run the **ping** command to verify the connectivity among VPCs.                                                                                                                                                                                                                                                        |
   +-----------------------+-----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

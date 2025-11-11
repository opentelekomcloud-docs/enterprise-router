:original_name: er_01_0070.html

.. _er_01_0070:

Creating a VPC Attachment
=========================

Scenarios
---------

This section describes how to attach a VPC to an enterprise router so that the VPCs attached to the enterprise router can communicate with each other.

Constraints
-----------

-  If you use the propagated routes of a VPC attachment, the route table of the enterprise router automatically learns the VPC CIDR block as the destination of routes. The CIDR block cannot be changed. To ensure that routes in the route table do not conflict, the CIDR blocks of all VPCs attached to the enterprise router cannot overlap. Otherwise, communication fails.
-  If your existing VPCs have overlapping CIDR blocks, do not use propagated routes. Instead, manually add static routes to the route table of the enterprise router. The destination of the routes can be VPC subnet CIDR blocks or smaller ones.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** and choose **Networking** > **Enterprise Router**.

   The **Enterprise Router** page is displayed.

#. Search for the target enterprise router by name.


   .. figure:: /_static/images/en-us_image_0000001674900098.png
      :alt: **Figure 1** Searching for an enterprise router

      **Figure 1** Searching for an enterprise router

#. Go to the **Attachments** tab using either of the following methods:

   -  In the upper right corner of the enterprise router, click **Manage Attachment**.
   -  Click the enterprise router name and click **Attachments**.

#. On the **Attachments** tab, click **Create Attachment**.

   The **Create Attachment** page is displayed.


   .. figure:: /_static/images/en-us_image_0000001723035633.png
      :alt: **Figure 2** Create Attachment

      **Figure 2** Create Attachment

#. Configure the parameters based on :ref:`Table 1 <er_01_0070__table7204821194013>`.

   .. _er_01_0070__table7204821194013:

   .. table:: **Table 1** Parameters for adding a VPC attachment

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                                                                                                                                                                                                                                                                                                         | Example Value         |
      +=======================+=================================================================================================================================================================================================================================================================================================================================================================+=======================+
      | Name                  | Mandatory                                                                                                                                                                                                                                                                                                                                                       | er-attach-01          |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | Enter an attachment name. The name:                                                                                                                                                                                                                                                                                                                             |                       |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | -  Must contain 1 to 64 characters.                                                                                                                                                                                                                                                                                                                             |                       |
      |                       | -  Can contain letters, digits, underscores (_), hyphens (-), and periods (.).                                                                                                                                                                                                                                                                                  |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Attachment Type       | Mandatory                                                                                                                                                                                                                                                                                                                                                       | VPC                   |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | Select **VPC**, indicating that a VPC is to be attached to the enterprise router.                                                                                                                                                                                                                                                                               |                       |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | The methods for creating attachments vary depending on the attachment type. For details, see :ref:`Attachment Overview <er_01_0019>`.                                                                                                                                                                                                                           |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Attached Resource     | Mandatory                                                                                                                                                                                                                                                                                                                                                       | -  VPC: vpc-A         |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 | -  Subnet: subnet-A01 |
      |                       | a. Select the VPC to be attached to the enterprise router. You can enter a VPC name to quickly find the target VPC.                                                                                                                                                                                                                                             |                       |
      |                       | b. Select a subnet in the selected VPC. You can enter a subnet name to quickly find the target subnet.                                                                                                                                                                                                                                                          |                       |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       |    -  You can select any subnet in the VPC. All subnets in the same VPC can communicate with each other by default and the enterprise router can connect to the entire VPC.                                                                                                                                                                                     |                       |
      |                       |    -  You are advised to select a subnet that is dedicated for connecting to the enterprise router. To ensure that the subnet has enough IP addresses for the system and the enterprise router, make the subnet mask /28 or smaller.                                                                                                                            |                       |
      |                       |    -  The traffic from the enterprise router to the VPC will be routed based on the VPC route table associated with the subnet.                                                                                                                                                                                                                                 |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Auto Add Routes       | Optional                                                                                                                                                                                                                                                                                                                                                        | Enable                |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | -  Enable this option if you want to automatically add routes (with this enterprise router as the next hop and 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16 as the destinations) to all route tables of the selected VPC.                                                                                                                                      |                       |
      |                       | -  Do not enable this option if an existing route in the VPC route tables has a destination set to 10.0.0.0/8, 172.16.0.0/12, or 192.168.0.0/16 because the routes will fail to be added. After the attachment is created, manually add routes to the VPC route tables. For details, see :ref:`Step 5: (Optional) Add Routes to VPC Route Tables <er_01_0067>`. |                       |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | .. note::                                                                                                                                                                                                                                                                                                                                                       |                       |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       |    This parameter is only displayed when a VPC attachment is created. It cannot be enabled after the VPC attachment is created.                                                                                                                                                                                                                                 |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Optional                                                                                                                                                                                                                                                                                                                                                        | ``-``                 |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | Describe the attachment for easy identification.                                                                                                                                                                                                                                                                                                                |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Tag                   | Optional                                                                                                                                                                                                                                                                                                                                                        | **Tag key**: test     |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | Add tags to help you quickly find your attachment.                                                                                                                                                                                                                                                                                                              | **Tag value**: 01     |
      |                       |                                                                                                                                                                                                                                                                                                                                                                 |                       |
      |                       | For details, see :ref:`Overview <er_01_0049>`.                                                                                                                                                                                                                                                                                                                  |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

   The attachment list is displayed.

#. Check the attachment status.

   If the status changes from **Creating** to **Normal**, the attachment is successfully created.

.. _er_01_0070__section582517444316:

Follow-up Procedure
-------------------

If **Default Route Table Association** and **Default Route Table Propagation** are not enabled for an enterprise router, you need to:

#. Create a custom route table for the enterprise router. For details, see :ref:`Creating a Route Table <er_01_0025>`.
#. Create associations for the attachments of the enterprise router. For details, see :ref:`Creating an Association for an Attachment in a Route Table <er_01_0031>`.
#. Use either of the following methods to add routes for the attachment to the route table:

   -  Create a propagation in the route table. For details, see :ref:`Creating a Propagation for an Attachment in the Route Table <er_01_0036>`.

      After the propagation is created, routes of the attachments to the enterprise router will be automatically propagated to the route table of the enterprise router.

   -  Add static routes to the route table. For details, see :ref:`Creating a Static Route <er_01_0041>`.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

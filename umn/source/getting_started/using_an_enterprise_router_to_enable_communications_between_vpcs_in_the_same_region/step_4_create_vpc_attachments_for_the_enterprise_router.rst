:original_name: er_01_0066.html

.. _er_01_0066:

Step 4: Create VPC Attachments for the Enterprise Router
========================================================

Perform the following operations to attach the four VPCs to the enterprise router:

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** and choose **Networking** > **Enterprise Router**.

   The **Enterprise Router** page is displayed.

#. Search for the target enterprise router by name.

#. .. _er_01_0066__li25751958135516:

   Go to the **Attachments** tab using either of the following methods:

   -  In the upper right corner of the enterprise router, click **Manage Attachment**.
   -  Click the enterprise router name and click **Attachments**.

#. On the **Attachments** tab, click **Create Attachment**.

   The **Create Attachment** page is displayed.


   .. figure:: /_static/images/en-us_image_0000001723035633.png
      :alt: **Figure 1** Create Attachment

      **Figure 1** Create Attachment

#. Configure the parameters based on :ref:`Table 1 <er_01_0066__table7204821194013>`.

   .. _er_01_0066__table7204821194013:

   .. table:: **Table 1** Parameter description

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
      | Parameter             | Setting                                                                                                                                                                                                                                                                                                                                                                                                                             | Example Value             |
      +=======================+=====================================================================================================================================================================================================================================================================================================================================================================================================================================+===========================+
      | Name                  | Specify the name of the VPC attachment. You can change it after the attachment is created.                                                                                                                                                                                                                                                                                                                                          | er-attach-01              |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
      | Attachment Type       | Select **VPC**. The type cannot be changed after the attachment is created.                                                                                                                                                                                                                                                                                                                                                         | VPC                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
      | Attached Resource     | a. Select the VPC to be attached to the enterprise router from the drop-down list. The VPC cannot be changed after the attachment is created.                                                                                                                                                                                                                                                                                       | -  VPC: vpc-demo-01       |
      |                       | b. Select the subnet to be attached to the enterprise router from the drop-down list. The subnet cannot be changed after the attachment is created.                                                                                                                                                                                                                                                                                 | -  Subnet: subnet-demo-01 |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
      | Auto Add Routes       | -  If you enable **Auto Add Routes** when creating a VPC attachment, you do not need to manually add static routes to the VPC route table. Instead, the system automatically adds routes (with this enterprise router as the next hop and 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16 as the destinations) to all route tables of the VPC.                                                                                        | Enable                    |
      |                       | -  If an existing route in the VPC route tables has a destination to 10.0.0.0/8, 172.16.0.0/12, or 192.168.0.0/16, the routes will fail to be added. In this case, do not enable **Auto Add Routes**. After the attachment is created, manually add routes.                                                                                                                                                                         |                           |
      |                       | -  Do not set the destination of a route (with an enterprise router as the next hop) to 0.0.0.0/0 in the VPC route table. If an ECS in the VPC has an EIP bound, the VPC route table will have a policy-based route with 0.0.0.0/0 as the destination, which has a higher priority than the route with the enterprise router as the next hop. In this case, traffic is forwarded to the EIP and cannot reach the enterprise router. |                           |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
      | Description           | Provide supplementary description about the attachment. You can change it after the attachment is created.                                                                                                                                                                                                                                                                                                                          | ``-``                     |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+
      | Tag                   | Add tags to help you identify your attachment. You can change them after the attachment is created.                                                                                                                                                                                                                                                                                                                                 | **Tag key**: test         |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                     |                           |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                     | **Tag value**: 01         |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------+

#. Click **Create Now**.

   The attachment list is displayed.

#. .. _er_01_0066__li1377219211383:

   Check the attachment status.

   If the status changes from **Creating** to **Normal**, the attachment is successfully created.

#. Repeat :ref:`5 <er_01_0066__li25751958135516>` to :ref:`9 <er_01_0066__li1377219211383>` to attach the other three VPCs to the enterprise router.

   .. important::

      In the example given, **Default Route Table Association** and **Default Route Table Propagation** are enabled when you create the enterprise router. After the VPCs are attached to the enterprise router, the system will automatically:

      -  Associate VPC attachments with the route table of the enterprise router.
      -  Propagate VPC attachments to the route table of the enterprise router. The CIDR blocks of the VPCs are propagated to the route table.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

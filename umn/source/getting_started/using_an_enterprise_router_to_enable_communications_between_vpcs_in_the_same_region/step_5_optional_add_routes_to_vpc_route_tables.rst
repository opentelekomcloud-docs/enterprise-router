:original_name: er_01_0067.html

.. _er_01_0067:

Step 5: (Optional) Add Routes to VPC Route Tables
=================================================

Perform the following operations to configure the routes for the enterprise router in the VPC route table:

.. note::

   -  If you enable **Auto Add Routes** when creating a VPC attachment, you do not need to manually add static routes to the VPC route table. Instead, the system automatically adds routes (with this enterprise router as the next hop and 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16 as the destinations) to all route tables of the VPC.
   -  If an existing route in the VPC route tables has a destination to 10.0.0.0/8, 172.16.0.0/12, or 192.168.0.0/16, the routes will fail to be added. In this case, do not enable **Auto Add Routes**. After the attachment is created, manually add routes.

Notes and Constraints
---------------------

-  If your VPC only has a default route table, all subnets in it are associated with the default route table. You only need to add routes to the default route table for traffic to route through the enterprise router.
-  If your VPC has multiple custom route tables and different subnets in the VPC are associated with different route tables, you need to add routes to each route table associated with the subnets for traffic to route through the enterprise router.

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

#. .. _er_01_0067__li18721151820134:

   Locate the target attachment and click the VPC in the **Attached Resource** column.

   The VPC basic information page is displayed.

#. In the **Networking Components** area, click the number next to **Subnets**.

   The **Subnets** page is displayed.

#. Locate the target subnet and click the route table name in the **Route Table** column.

   The route table details page is displayed.

#. Under **Routes**, click **Add Route**.

   The **Add Route** dialog box is displayed.

#. Configure the parameters based on :ref:`Table 1 <er_01_0067__table7204821194013>`.

   .. _er_01_0067__table7204821194013:

   .. table:: **Table 1** Parameter description

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                                                                                                                                                                                                                                                                                                                                                                             | Example Value         |
      +=======================+=====================================================================================================================================================================================================================================================================================================================================================================================================================================+=======================+
      | Destination Type      | The destination can only be **IP address**. You can set a single IP address or network segment.                                                                                                                                                                                                                                                                                                                                     | IP address            |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Destination           | The destination is used to route traffic from this VPC to other VPCs attached to the enterprise router. You can change it after the route is created.                                                                                                                                                                                                                                                                               | 10.0.0.0/8            |
      |                       |                                                                                                                                                                                                                                                                                                                                                                                                                                     |                       |
      |                       | -  Set the destination to the CIDR blocks of VPCs or their subnets that your VPC need to communicate with.                                                                                                                                                                                                                                                                                                                          |                       |
      |                       | -  Do not set the destination of a route (with an enterprise router as the next hop) to 0.0.0.0/0 in the VPC route table. If an ECS in the VPC has an EIP bound, the VPC route table will have a policy-based route with 0.0.0.0/0 as the destination, which has a higher priority than the route with the enterprise router as the next hop. In this case, traffic is forwarded to the EIP and cannot reach the enterprise router. |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Next Hop Type         | Select **Enterprise Router**. You can change it after the route is created.                                                                                                                                                                                                                                                                                                                                                         | Enterprise Router     |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Next Hop              | Select the target enterprise router. You can change it after the route is created.                                                                                                                                                                                                                                                                                                                                                  | er-test-01            |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Provide supplementary information about the route. You can change the route after it is created.                                                                                                                                                                                                                                                                                                                                    | ``-``                 |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. .. _er_01_0067__li484795713352:

   Click **OK**.

   You can view the route in the route list.

#. Repeat :ref:`6 <er_01_0067__li18721151820134>` to :ref:`11 <er_01_0067__li484795713352>` to add routes to route tables of other VPCs.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

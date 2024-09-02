:original_name: er_01_0042.html

.. _er_01_0042:

Modifying a Static Route
========================

Scenarios
---------

This section describes how to modify static routes, including common routes and blackhole routes, in a route table of an enterprise router. For example, you can perform the following operations:

-  Change a common route to a blackhole route.
-  Change the attachment type and next hop of a common route.

Only static routes can be modified. Propagation routes cannot be modified.

Notes and Constraints
---------------------

To change the destination of a static route, delete this static route and create another one with your desired destination.

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

#. Go to the **Route Tables** tab using either of the following methods:

   -  In the upper right corner of the enterprise router, click **Manage Route Table**.
   -  Click the enterprise router name and click **Route Tables**.


   .. figure:: /_static/images/en-us_image_0000001723183941.png
      :alt: **Figure 2** Modifying a static route

      **Figure 2** Modifying a static route

#. Click the route table where you want to modify a route. On the **Routes** tab, locate the route and click **Modify** in the **Operation** column.

   The **Modify Route** dialog box is displayed.

#. Modify the route based on :ref:`Table 1 <er_01_0042__er_01_0041_table7204821194013>`.

   .. _er_01_0042__er_01_0041_table7204821194013:

   .. table:: **Table 1** Parameter description

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                                                                                                                                                                                                                       | Example Value         |
      +=======================+===============================================================================================================================================================================================================================================================================+=======================+
      | Blackhole Route       | Optional                                                                                                                                                                                                                                                                      | ``-``                 |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | If **Blackhole Route** is enabled, you do not need to configure **Attachment Type** and **Next Hop** for the route. If the destination of a route is the same as, or is contained in, that of this blackhole route, all packets destined for the destination will be dropped. |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Attachment Type       | -  If **Blackhole Route** is not enabled, you need to configure this parameter.                                                                                                                                                                                               | VPC                   |
      |                       | -  If **Blackhole Route** is enabled, you do not need to configure this parameter.                                                                                                                                                                                            |                       |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | **VPC**: A VPC is attached to the enterprise router.                                                                                                                                                                                                                          |                       |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | For more information, see :ref:`Attachment Overview <er_01_0019>`.                                                                                                                                                                                                            |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Next Hop              | -  If **Blackhole Route** is not enabled, you need to configure this parameter.                                                                                                                                                                                               | er-attach-01          |
      |                       | -  If **Blackhole Route** is enabled, you do not need to configure this parameter.                                                                                                                                                                                            |                       |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | In the drop-down list, select the target attachment.                                                                                                                                                                                                                          |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   View the modified static route in the route list.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

:original_name: er_01_0041.html

.. _er_01_0041:

Creating a Static Route
=======================

Scenarios
---------

You can create static routes in a route table of an enterprise router.

Static routes are classified into common routes and blackhole routes. A blackhole route only has a destination and has no next hop. It drops all traffic sent to the specified destination.

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


   .. figure:: /_static/images/en-us_image_0000001675304226.png
      :alt: **Figure 2** Creating a static route

      **Figure 2** Creating a static route

#. Click the route table where you want to create a static route. On the **Routes** tab, click **Create Route**.

   The **Create Route** dialog box is displayed.

#. Configure the parameters based on :ref:`Table 1 <er_01_0041__table7204821194013>`.

   .. _er_01_0041__table7204821194013:

   .. table:: **Table 1** Parameter description

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                                                                                                                                                                                                                       | Example Value         |
      +=======================+===============================================================================================================================================================================================================================================================================+=======================+
      | Destination           | Mandatory                                                                                                                                                                                                                                                                     | 192.168.2.0/24        |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | Enter the IP address or CIDR block of the attachment. For example, if it is a VPC attachment, enter the CIDR block of the VPC or a subnet of the VPC.                                                                                                                         |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Blackhole Route       | Optional                                                                                                                                                                                                                                                                      | ``-``                 |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | If **Blackhole Route** is enabled, you do not need to configure **Attachment Type** and **Next Hop** for the route. If the destination of a route is the same as, or is contained in, that of this blackhole route, all packets destined for the destination will be dropped. |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Attachment Type       | -  If **Blackhole Route** is not enabled, you need to configure this parameter.                                                                                                                                                                                               | VPC                   |
      |                       | -  If **Blackhole Route** is enabled, you do not need to configure this parameter.                                                                                                                                                                                            |                       |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | Select an attachment type.                                                                                                                                                                                                                                                    |                       |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | -  **VPC**: Create a static route for a VPC attachment.                                                                                                                                                                                                                       |                       |
      |                       | -  **CFW instance**: Create a static route for a VPC border firewall that is attached to the enterprise router.                                                                                                                                                               |                       |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | For more information, see :ref:`Attachment Overview <er_01_0019>`.                                                                                                                                                                                                            |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Next Hop              | -  If **Blackhole Route** is not enabled, you need to configure this parameter.                                                                                                                                                                                               | er-attach-01          |
      |                       | -  If **Blackhole Route** is enabled, you do not need to configure this parameter.                                                                                                                                                                                            |                       |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | In the drop-down list, select the target attachment.                                                                                                                                                                                                                          |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Optional                                                                                                                                                                                                                                                                      | ``-``                 |
      |                       |                                                                                                                                                                                                                                                                               |                       |
      |                       | Describe the route for easy identification.                                                                                                                                                                                                                                   |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   Wait for 2 to 3 seconds, and click |image2| to refresh the route list. The created static route is displayed.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png
.. |image2| image:: /_static/images/en-us_image_0000001383934230.png

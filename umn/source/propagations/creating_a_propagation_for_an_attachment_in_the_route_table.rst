:original_name: er_01_0036.html

.. _er_01_0036:

Creating a Propagation for an Attachment in the Route Table
===========================================================

Scenarios
---------

This section describes how to create a propagation in the route table of an enterprise router.

Notes
-----

You can create propagations for the same attachment in different route tables.

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


   .. figure:: /_static/images/en-us_image_0000001675129792.png
      :alt: **Figure 2** Create Propagation

      **Figure 2** Create Propagation

#. Click the route table where you want to create a propagation. On the **Propagations** tab, click **Create Propagation**.

   The **Create Propagation** dialog box is displayed.

#. Configure the parameters based on :ref:`Table 1 <er_01_0036__table7204821194013>`.

   .. _er_01_0036__table7204821194013:

   .. table:: **Table 1** Parameters for creating a propagation

      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                                        | Example Value         |
      +=======================+================================================================================================+=======================+
      | Attachment Type       | Mandatory                                                                                      | VPC                   |
      |                       |                                                                                                |                       |
      |                       | Select an attachment type.                                                                     |                       |
      |                       |                                                                                                |                       |
      |                       | -  **VPC**: A VPC is attached to the enterprise router.                                        |                       |
      |                       | -  **Virtual gateway**: A Direct Connect virtual gateway is attached to the enterprise router. |                       |
      |                       | -  **VPN gateway**: A VPN gateway is attached to the enterprise router.                        |                       |
      |                       |                                                                                                |                       |
      |                       | For more information, see :ref:`Attachment Overview <er_01_0019>`.                             |                       |
      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+
      | Attachment            | Mandatory                                                                                      | er-attach-02          |
      |                       |                                                                                                |                       |
      |                       | In the drop-down list, select the attachment who will propagate routes to the route table.     |                       |
      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   The propagation list is displayed. You can view your propagation.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

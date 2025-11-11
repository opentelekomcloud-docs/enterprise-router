:original_name: er_01_0025.html

.. _er_01_0025:

Creating a Route Table
======================

Scenarios
---------

This section describes how to create a custom route table for an enterprise router.

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


   .. figure:: /_static/images/en-us_image_0000001675299306.png
      :alt: **Figure 2** Route Tables

      **Figure 2** Route Tables

#. On the **Route Tables** tab, click **Create Route Table**.

   The **Create Route Table** dialog box is displayed.

#. Configure the parameters based on :ref:`Table 1 <er_01_0025__table7204821194013>`.

   .. _er_01_0025__table7204821194013:

   .. table:: **Table 1** Parameters for creating a route table for an enterprise router

      +-----------------------+--------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                        | Example Value         |
      +=======================+================================================================================+=======================+
      | Name                  | Mandatory                                                                      | er-rtb-01             |
      |                       |                                                                                |                       |
      |                       | Enter a name for the route table. The name:                                    |                       |
      |                       |                                                                                |                       |
      |                       | -  Must contain 1 to 64 characters.                                            |                       |
      |                       | -  Can contain letters, digits, underscores (_), hyphens (-), and periods (.). |                       |
      +-----------------------+--------------------------------------------------------------------------------+-----------------------+
      | Tag                   | Optional                                                                       | **Tag key**: test     |
      |                       |                                                                                |                       |
      |                       | Add tags to help you quickly find your route table.                            | **Tag value**: 01     |
      |                       |                                                                                |                       |
      |                       | For details, see :ref:`Overview <er_01_0049>`.                                 |                       |
      +-----------------------+--------------------------------------------------------------------------------+-----------------------+
      | Description           | Optional                                                                       | ``-``                 |
      |                       |                                                                                |                       |
      |                       | Describe the route table for easy identification.                              |                       |
      +-----------------------+--------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   The route table list is displayed.

#. View the route table status.

   If the status changes from **Creating** to **Normal**, the route table is successfully created.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

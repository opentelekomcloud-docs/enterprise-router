:original_name: er_01_0026.html

.. _er_01_0026:

Modifying a Route Table
=======================

Scenarios
---------

This section describes how to modify the name and description of a route table.

Constraints
-----------

Only the name and description of route tables named **defaultRouteTable** and custom route tables can be changed.

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


   .. figure:: /_static/images/en-us_image_0000001723058845.png
      :alt: **Figure 2** Renaming a route table

      **Figure 2** Renaming a route table

#. In the route table list, click |image2| next to the name of the target route table.

   The **Modify Route Table** dialog box is displayed.

#. Enter a new name.

   .. table:: **Table 1** Parameter description

      +-----------------------+--------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                        | Example Value         |
      +=======================+================================================================================+=======================+
      | Name                  | Mandatory                                                                      | er-rtb-01             |
      |                       |                                                                                |                       |
      |                       | Enter a new name for the route table. The name:                                |                       |
      |                       |                                                                                |                       |
      |                       | -  Must contain 1 to 64 characters.                                            |                       |
      |                       | -  Can contain letters, digits, underscores (_), hyphens (-), and periods (.). |                       |
      +-----------------------+--------------------------------------------------------------------------------+-----------------------+
      | Description           | Optional                                                                       | ``-``                 |
      |                       |                                                                                |                       |
      |                       | Modify the description of the route table.                                     |                       |
      +-----------------------+--------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   The route table list is displayed.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png
.. |image2| image:: /_static/images/en-us_image_0000001848122286.png

:original_name: er_01_0031.html

.. _er_01_0031:

Creating an Association for an Attachment in a Route Table
==========================================================

Scenarios
---------

This section describes how to create an association in a route table of an enterprise router to associate a specified attachment with the route table.

Notes and Constraints
---------------------

Each attachment can only be associated with one route table. Packets from the attachment will be forwarded based on the route table.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** and choose **Networking** > **Enterprise Router**.

   The **Enterprise Router** homepage is displayed.

#. Search for the target enterprise router by name.


   .. figure:: /_static/images/en-us_image_0000001674900098.png
      :alt: **Figure 1** Searching for an enterprise router

      **Figure 1** Searching for an enterprise router

#. Go to the **Route Tables** tab using either of the following methods:

   -  In the upper right corner of the enterprise router, click **Manage Route Table**.
   -  Click the enterprise router name and click **Route Tables**.


   .. figure:: /_static/images/en-us_image_0000001675131132.png
      :alt: **Figure 2** Create Association

      **Figure 2** Create Association

#. Click the route table where you want to create an association. On the **Associations** tab, click **Create Association**.

   The **Create Association** dialog box is displayed.

#. Configure the parameters based on :ref:`Table 1 <er_01_0031__table7204821194013>`.

   .. _er_01_0031__table7204821194013:

   .. table:: **Table 1** Parameters for creating an association

      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                                        | Example Value         |
      +=======================+================================================================================================+=======================+
      | Attachment Type       | Mandatory                                                                                      | VPC                   |
      |                       |                                                                                                |                       |
      |                       | Select an attachment type.                                                                     |                       |
      |                       |                                                                                                |                       |
      |                       | -  **VPC**: A VPC is attached to the enterprise router.                                        |                       |
      |                       | -  **Virtual gateway**: A Direct Connect virtual gateway is attached to the enterprise router. |                       |
      |                       |                                                                                                |                       |
      |                       | For more information, see :ref:`Attachment Overview <er_01_0019>`.                             |                       |
      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+
      | Attachment            | Mandatory                                                                                      | er-attach-02          |
      |                       |                                                                                                |                       |
      |                       | In the drop-down list, select the attachment to be associated with the route table.            |                       |
      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   The association list is displayed. You can view your association.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

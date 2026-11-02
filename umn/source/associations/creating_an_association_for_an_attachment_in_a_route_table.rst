:original_name: er_01_0031.html

.. _er_01_0031:

Creating an Association for an Attachment in a Route Table
==========================================================

Scenarios
---------

You can refer to the following operations to create an association in the route table of an enterprise router to associate an attachment with the route table. After an association is created, packets from the attachment are forwarded based on the association route table, and the attachment network can automatically learn the routes in the association route table.

You can create an association in either of the following ways:

-  :ref:`Automatically Creating an Association When Creating an Attachment <er_01_0031__section1646713151120>`
-  :ref:`Creating an Association for an Existing Attachment <er_01_0031__section1846122044218>`

Constraints
-----------

Each attachment can only be associated with one route table. Packets from the attachment will be forwarded based on the route table.

.. _er_01_0031__section1646713151120:

Automatically Creating an Association When Creating an Attachment
-----------------------------------------------------------------

If the **Default Route Table Association** function is enabled for an enterprise router, adding an attachment to the enterprise router automatically creates an association in the specified association route table. The attachment will forward packets based on the association route table and automatically learn its routes.

To enable the **Default Route Table Association** function, refer to the following:

-  When creating an enterprise router, you can enable the **Default Route Table Association** function. The system will automatically create a default route table as the association route table. For details, see :ref:`Creating an Enterprise Router <er_01_0069>`.
-  After an enterprise router is created, you can enable the **Default Route Table Association** function and change the association route table. For details, see :ref:`Modifying Enterprise Router Settings <er_01_0013>`.

.. _er_01_0031__section1846122044218:

Creating an Association for an Existing Attachment
--------------------------------------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** and choose **Networking** > **Enterprise Router**.

   The **Enterprise Router** page is displayed.

#. Search for the target enterprise router by name.


   .. figure:: /_static/images/en-us_image_0000002725423276.png
      :alt: **Figure 1** Searching for an enterprise router

      **Figure 1** Searching for an enterprise router

#. Go to the **Route Tables** tab using either of the following methods:

   -  In the upper right corner of the enterprise router, click **Manage Route Table**.
   -  Click the enterprise router name and click **Route Tables**.


   .. figure:: /_static/images/en-us_image_0000002756953173.png
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
      |                       | -  **VPN gateway**: A VPN gateway is attached to the enterprise router.                        |                       |
      |                       | -  **CFW instance**: A VPC border firewall is attached to the enterprise router.               |                       |
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

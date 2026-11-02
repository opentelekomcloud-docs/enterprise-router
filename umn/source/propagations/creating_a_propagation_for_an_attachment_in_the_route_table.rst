:original_name: er_01_0036.html

.. _er_01_0036:

Creating a Propagation for an Attachment in the Route Table
===========================================================

Scenarios
---------

You can refer to the following operations to create a propagation for an attachment in the route table of an enterprise router. After a propagation is created, the route information of the attachment can be automatically propagated to the enterprise router route table. This eliminates the need for manual configuration and further improves configuration efficiency.

You can create a propagation in either of the following ways:

-  :ref:`Automatically Creating a Propagation When Creating an Attachment <er_01_0036__section1646713151120>`
-  :ref:`Creating a Propagation for an Existing Attachment <er_01_0036__section1846122044218>`

Constraints
-----------

You can create propagations for the same attachment in different route tables.

.. _er_01_0036__section1646713151120:

Automatically Creating a Propagation When Creating an Attachment
----------------------------------------------------------------

If the **Default Route Table Propagation** function is enabled for an enterprise router, adding an attachment to the enterprise router automatically creates a propagation in the specified propagation route table. The route table will automatically learn the routes of the attachment.

To enable the **Default Route Table Propagation** function, refer to the following:

-  When creating an enterprise router, you can enable the **Default Route Table Propagation** function. The system will automatically create a default route table as the propagation route table. For details, see :ref:`Creating an Enterprise Router <er_01_0069>`.
-  After an enterprise router is created, you can enable the **Default Route Table Propagation** function and change the propagation route table. For details, see :ref:`Modifying Enterprise Router Settings <er_01_0013>`.

.. _er_01_0036__section1846122044218:

Creating a Propagation for an Existing Attachment
-------------------------------------------------

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


   .. figure:: /_static/images/en-us_image_0000002727433708.png
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
      |                       | -  **CFW instance**: A VPC border firewall is attached to the enterprise router.               |                       |
      |                       |                                                                                                |                       |
      |                       | For more information, see :ref:`Attachment Overview <er_01_0019>`.                             |                       |
      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+
      | Attachment            | Mandatory                                                                                      | er-attach-02          |
      |                       |                                                                                                |                       |
      |                       | In the drop-down list, select the attachment that will propagate routes to the route table.    |                       |
      +-----------------------+------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   The propagation list is displayed. You can view your propagation.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

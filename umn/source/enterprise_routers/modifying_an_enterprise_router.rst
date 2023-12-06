:original_name: er_01_0013.html

.. _er_01_0013:

Modifying an Enterprise Router
==============================

Scenarios
---------

This section describes how to modify settings of an enterprise router. You can:

-  Modify the name of an enterprise router.
-  Enable or disable **Default Route Table Association**.
-  Enable or disable **Default Route Table Propagation**.

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

#. In the upper right corner of the target enterprise router, choose **More** > **Modify Settings**.

   The **Modify Settings** page is displayed.


   .. figure:: /_static/images/en-us_image_0000001674952208.png
      :alt: **Figure 2** Modify Settings

      **Figure 2** Modify Settings

#. Modify the enterprise router based on :ref:`Table 1 <er_01_0013__table7204821194013>`.

   .. _er_01_0013__table7204821194013:

   .. table:: **Table 1** Parameter description

      +---------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                       | Setting                                                                                                                                                                | Example Value         |
      +=================================+========================================================================================================================================================================+=======================+
      | Name                            | Mandatory                                                                                                                                                              | er-test-01            |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | If you want to change the name of the enterprise router, enter a new name. The name:                                                                                   |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | -  Must contain 1 to 64 characters.                                                                                                                                    |                       |
      |                                 | -  Can contain letters, digits, underscores (_), hyphens (-), and periods (.).                                                                                         |                       |
      +---------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Default Route Table Association | Optional                                                                                                                                                               | Enable                |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | Enabling **Default Route Table Association** can simplify network configurations. After this function is enabled:                                                      |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | a. Select a route table for **Default Association Route Table**.                                                                                                       |                       |
      |                                 | b. If you create an attachment to this enterprise router, the attachment will be automatically associated with the default association route table.                    |                       |
      +---------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Association Route Table         | Optional                                                                                                                                                               | er-rtb-b931           |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | If you enable **Default Route Table Association**, select a route table for **Association Route Table**.                                                               |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | -  You can select a custom route table.                                                                                                                                |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | -  If you do not select a route table, the system will create a route table named **defaultRouteTable** as the default association route table.                        |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 |    If a route table named **defaultRouteTable** already exists, the system will not create it again.                                                                   |                       |
      +---------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Default Route Table Propagation | Optional                                                                                                                                                               | Enable                |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | Enabling **Default Route Table Propagation** can simplify network configurations. After this function is enabled:                                                      |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | a. Select a route table for **Association Route Table**.                                                                                                               |                       |
      |                                 | b. If you create an attachment to this enterprise router, the attachment will be automatically propagated to the default propagation route table.                      |                       |
      +---------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Propagation Route Table         | Optional                                                                                                                                                               | er-rtb-b931           |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | If you enable **Default Route Table Propagation**, select a route table for **Propagation Route Table**.                                                               |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | -  You can select a custom route table.                                                                                                                                |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | -  If you do not select a route table, the system will create a route table named **defaultRouteTable** as the default propagation route table.                        |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 |    If a route table named **defaultRouteTable** already exists, the system will not create it again.                                                                   |                       |
      +---------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Auto Accept Shared Attachments  | Optional                                                                                                                                                               | Enable                |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | As the owner, you can share your enterprise router with other users. These other users can create attachments for your enterprise router.                              |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | -  If you do not select this option, you must manually accept attachments to this enterprise router from the accounts that this enterprise router is shared with.      |                       |
      |                                 | -  If you select this option, the system will automatically accept attachments to this enterprise router from the accounts that this enterprise router is shared with. |                       |
      |                                 |                                                                                                                                                                        |                       |
      |                                 | For details, see :ref:`Sharing Overview <er_01_0095>`.                                                                                                                 |                       |
      +---------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   The enterprise router list is displayed.

#. Check the enterprise router settings.

   The settings take effect immediately.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

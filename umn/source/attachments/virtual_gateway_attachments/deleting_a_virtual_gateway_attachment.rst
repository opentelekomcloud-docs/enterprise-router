:original_name: er_01_0073.html

.. _er_01_0073:

Deleting a Virtual Gateway Attachment
=====================================

Scenarios
---------

This section describes how to delete a virtual gateway attachment from an enterprise router.

Notes and Constraints
---------------------

-  Deleting a VPC attachment will also delete its associations, propagations, and propagated routes in the route table.

-  If flow logging is enabled for a VPC attachment, flow logging will be disabled, but collected flow logs will not be deleted.

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

   .. important::

      A virtual gateway attachment cannot be directly deleted on the **Attachments** tab.

      A virtual gateway attachment will be automatically deleted after you perform the following operations to delete the virtual gateway and its virtual interfaces.

#. Locate the target virtual gateway attachment and click the attached resource.

   Example: vgw-demo

   The virtual gateway attachment details page is displayed.

#. On the details page, click the virtual gateway.

   The virtual gateway list is displayed.

#. Check whether the virtual gateway has virtual interfaces.

   -  If the virtual gateway has virtual interfaces, delete the virtual interfaces first.

      For details, see section "Deleting a Virtual Interface" in the **Direct Connect User Guide**.

   -  If the virtual gateway has no virtual interfaces, go to :ref:`9 <er_01_0073__li1323115372813>`.

#. .. _er_01_0073__li1323115372813:

   Locate the target virtual gateway and click **Delete** in the **Operation** column.

   A confirmation dialog box is displayed.


   .. figure:: /_static/images/en-us_image_0000002024742029.png
      :alt: **Figure 2** Deleting a virtual gateway

      **Figure 2** Deleting a virtual gateway

#. Click **OK**.

   A deleted virtual gateway cannot be recovered.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

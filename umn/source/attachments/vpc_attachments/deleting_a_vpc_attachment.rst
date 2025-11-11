:original_name: er_01_0072.html

.. _er_01_0072:

Deleting a VPC Attachment
=========================

Scenarios
---------

This section describes how to delete a VPC attachment from an enterprise router.

Constraints
-----------

-  Deleting a VPC attachment will also delete its associations, propagations, and propagated routes in the route table.
-  If a VPC attachment is deleted, the next hop of its related static routes will be **Blackhole**. If the destination of a packet matches the blackhole route, the packet will be discarded.
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

#. In the attachment list, locate the target VPC attachment, and click **Delete** in the **Operation** column.

   A confirmation dialog box is displayed.

#. Confirm the information and click **OK**.

   A deleted attachment cannot be recovered.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

:original_name: er_01_0114.html

.. _er_01_0114:

Deleting a VPN Gateway Attachment
=================================

Scenarios
---------

This section describes how to delete a VPN gateway attachment from an enterprise router.

Constraints
-----------

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

      A VPN gateway attachment cannot be directly deleted on the **Attachments** tab.

      A VPN gateway attachment will be automatically deleted after you perform the following operations to delete its VPN connections, unbind the EIP from the VPN gateway, and delete the VPN gateway.

#. Locate the target VPN gateway attachment and click the attached resource.

   Example: vpngw-demo

   The VPN gateway attachment details page is displayed.

#. On the attachment details page, click |image2| in the upper left corner.

   The VPN gateway list is displayed.

#. In the VPN gateway list, locate the target VPN gateway, click **More** in the **Operation** column, and click **Delete**.

   A confirmation dialog box is displayed.

#. Click **Yes**.

   A deleted VPN gateway cannot be recovered.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png
.. |image2| image:: /_static/images/en-us_image_0000001432667421.png

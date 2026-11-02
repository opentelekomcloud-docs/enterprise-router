:original_name: er_01_0020.html

.. _er_01_0020:

Enabling IPv6 for a VPC Attachment
==================================

Scenarios
---------

If IPv6 is not enabled when you add a VPC attachment to an enterprise router, you can enable IPv6 for the VPC attachment by referring to this section.

After IPv6 is enabled, you can add IPv6 routes to or associate an IPv6 address group with the enterprise router route table.

.. note::

   IPv6 is not applicable in **eu-nl**.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** and choose **Networking** > **Enterprise Router**.

   The **Enterprise Router** page is displayed.

#. Search for the target enterprise router by name.


   .. figure:: /_static/images/en-us_image_0000002725423276.png
      :alt: **Figure 1** Searching for an enterprise router

      **Figure 1** Searching for an enterprise router

#. Go to the **Attachments** tab using either of the following methods:

   -  In the upper right corner of the enterprise router, click **Manage Attachment**.
   -  Click the enterprise router name and click **Attachments**.

#. On the **Attachments** tab, locate the target attachment and click its name.

   The attachment details page is displayed.

#. Click |image2| next to **IPv6**.

   -  If IPv6 is enabled, no more actions are required.

   -  If a message appears indicating that IPv6 failed to be enabled because IPv6 is not enabled for the VPC subnet, perform the following operations to enable IPv6 for the VPC subnet first:

      a. On the attachment details page, click the subnet name.

         The subnet details page is displayed.

      b. Enable IPv6 for the subnet.

         A confirmation dialog box is displayed.

      c. Click **OK**.

      d. Switch to the attachment details page and enable IPv6 for the attachment again.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png
.. |image2| image:: /_static/images/en-us_image_0000001503089606.png

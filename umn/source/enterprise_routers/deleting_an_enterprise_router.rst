:original_name: er_01_0017.html

.. _er_01_0017:

Deleting an Enterprise Router
=============================

Scenarios
---------

Delete an enterprise router that is no longer needed.

Notes and Constraints
---------------------

-  An enterprise router that has attachments cannot be deleted. Delete the attachments first. For details, see :ref:`Attachment Overview <er_01_0019>`.
-  An enterprise router that has route tables can be deleted directly.
-  An enterprise router that is shared with other accounts can be deleted directly.
-  Deleting an enterprise router will also delete all of its flow logs.

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

#. In the upper right corner of the target enterprise router, choose **More** > **Delete**.

   A confirmation dialog box is displayed.

#. Click **OK**.

   A deleted enterprise router cannot be recovered.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

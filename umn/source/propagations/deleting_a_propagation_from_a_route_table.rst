:original_name: er_01_0038.html

.. _er_01_0038:

Deleting a Propagation from a Route Table
=========================================

Scenarios
---------

This section describes how to delete a propagation from the route table of an enterprise router.

Constraints
-----------

Propagated routes are learned through propagation. Deleting a propagation will also delete the propagated routes.

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


   .. figure:: /_static/images/en-us_image_0000001675130592.png
      :alt: **Figure 2** Deleting a propagation

      **Figure 2** Deleting a propagation

#. Click the route table where you want to delete a propagation. On the **Propagations** tab, locate the propagation you want to delete and click **Delete** in the **Operation** column.

   A confirmation dialog box is displayed.

#. Confirm the information and click **Yes**.

   A deleted propagation cannot be recovered.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

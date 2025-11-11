:original_name: er_01_0044.html

.. _er_01_0044:

Deleting a Static Route
=======================

Scenarios
---------

Delete a static route from a route table of an enterprise router.

Only static routes can be deleted. To delete a propagated route, you need to delete its propagation. The route will be deleted together with the propagation. For details, see :ref:`Deleting a Propagation from a Route Table <er_01_0038>`.

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


   .. figure:: /_static/images/en-us_image_0000001723184881.png
      :alt: **Figure 2** Deleting a static route

      **Figure 2** Deleting a static route

#. Click the route table where you want to delete a route. On the **Routes** tab, locate the route and click **Delete** in the **Operation** column.

   A confirmation dialog box is displayed.

#. Confirm the information and click **Yes**.

   A deleted static route cannot be recovered.

   Wait for 2 to 3 seconds, and click |image2| to refresh the route list. The route does not exist in the list.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png
.. |image2| image:: /_static/images/en-us_image_0000001434293421.png

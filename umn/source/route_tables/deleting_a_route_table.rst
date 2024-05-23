:original_name: er_01_0028.html

.. _er_01_0028:

Deleting a Route Table
======================

Scenarios
---------

This section describes how to delete a route table of an enterprise router.

Notes and Constraints
---------------------

-  If a route table is used as the default association route table and/or default propagation route table, the route table cannot be deleted.

   -  If **Default Route Association** is set to **Yes** on the basic information page of the route table, the route table is used as the default association route table.
   -  Also, if **Default Route Propagation** is set to **Yes** on the basic information of the route table, the route table is used as the default propagation route table.

   To delete such a route table, change **Default Route Association** and **Default Route Propagation** settings. For details, see :ref:`Modifying an Enterprise Router <er_01_0013>`.

-  A route table cannot be deleted if it contains an association or a propagation. You need to delete the association and propagation before deleting this route table.

   -  For details about how to delete an association, see :ref:`Deleting an Association from a Route Table <er_01_0033>`.
   -  For details about how to delete a propagation, see :ref:`Deleting a Propagation from a Route Table <er_01_0038>`.

-  A route table can be deleted if it contains only static routes. Ensure that the routes are no longer required before deleting their route table.

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

#. Go to the **Route Tables** tab using either of the following methods:

   -  In the upper right corner of the enterprise router, click **Manage Route Table**.
   -  Click the enterprise router name and click **Route Tables**.


   .. figure:: /_static/images/en-us_image_0000001675120256.png
      :alt: **Figure 2** Deleting a route table

      **Figure 2** Deleting a route table

#. In the route table list, click |image2| next to the name of the target route table.

   A confirmation dialog box is displayed.

#. Click **Yes**.

   A deleted route table cannot be recovered.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png
.. |image2| image:: /_static/images/en-us_image_0000001142144144.png

:original_name: er_01_0064.html

.. _er_01_0064:

Step 2: Create an Enterprise Router
===================================

Scenarios
---------

This section describes how to create an enterprise router.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List** and choose **Networking** > **Enterprise Router**.

   The **Enterprise Router** homepage is displayed.

#. Click **Create Enterprise Router** in the upper right corner.

   The **Create Enterprise Router** page is displayed.


   .. figure:: /_static/images/en-us_image_0000001675058246.png
      :alt: **Figure 1** Create Enterprise Router

      **Figure 1** Create Enterprise Router

#. Configure the parameters based on :ref:`Table 1 <er_01_0064__table7204821194013>`.

   .. _er_01_0064__table7204821194013:

   .. table:: **Table 1** Parameters for creating an enterprise router

      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                       | Setting                                                                                                                                                                        | Example Value         |
      +=================================+================================================================================================================================================================================+=======================+
      | Region                          | Select the region nearest to your target users. Once the enterprise router is created, the region cannot be changed.                                                           | ``-``                 |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | AZ                              | Select two AZs to deploy your enterprise router. You can change them after the enterprise router is created.                                                                   | AZ1                   |
      |                                 |                                                                                                                                                                                |                       |
      |                                 |                                                                                                                                                                                | AZ2                   |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                            | Specify the enterprise router name. You can change it after the enterprise router is created.                                                                                  | er-test-01            |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | ASN                             | Set the Autonomous System Number (ASN) for the cloud side of a Border Gateway Protocol (BGP) session. You cannot change it after the enterprise router is created.             | 64512                 |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Default Route Table Association | If you select this option, you do not need to create route tables or associations. You can change your option after the enterprise router is created.                          | Enable                |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Default Route Table Propagation | If you select this option, you do not need to create route tables, propagations, or routes. You can change your option after the enterprise router is created.                 | Enable                |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Auto Accept Shared Attachments  | If you do not select this option, you must accept the requests for creating attachments to this enterprise router from other users with whom this enterprise router is shared. | Disable               |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Enterprise Project              | Select an enterprise project for the enterprise router. You can change it after the enterprise router is created.                                                              | default               |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Tag                             | Add tags to help you identify your enterprise router. You can change them after the enterprise router is created.                                                              | **Tag key**: test     |
      |                                 |                                                                                                                                                                                |                       |
      |                                 |                                                                                                                                                                                | **Tag value**: 01     |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description                     | Provide supplementary information about the enterprise router. You can change it after the enterprise router is created.                                                       | ``-``                 |
      +---------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

#. Confirm the enterprise router configurations and click **Submit**.

   The enterprise router list is displayed.

#. Check the enterprise router status.

   If the status changes from **Creating** to **Normal**, the enterprise router is successfully created.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

:original_name: er_01_0109.html

.. _er_01_0109:

Creating a Flow Log
===================

Scenarios
---------

This section describes how to create a flow log to record information about the traffic of enterprise router attachments.

Constraints
-----------

Only one flow log can be created for an attachment in the same log group and log stream.

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

#. Click the enterprise router name and click **Flow Logs**.

   The flow log list is displayed.


   .. figure:: /_static/images/en-us_image_0000001725954305.png
      :alt: **Figure 2** List of flow logs

      **Figure 2** List of flow logs

#. On the **Flow Logs** tab, click **Create Flow Log**.

   The **Create Flow Log** dialog box is displayed.


   .. figure:: /_static/images/en-us_image_0000001726070865.png
      :alt: **Figure 3** Creating a flow log

      **Figure 3** Creating a flow log

#. Configure the parameters based on :ref:`Table 1 <er_01_0109__table7204821194013>`.

   .. _er_01_0109__table7204821194013:

   .. table:: **Table 1** Parameters for creating a flow log

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Setting                                                                                                                                                                 | Example Value         |
      +=======================+=========================================================================================================================================================================+=======================+
      | Name                  | Mandatory                                                                                                                                                               | flowlog-ab            |
      |                       |                                                                                                                                                                         |                       |
      |                       | Enter a name for the flow log. The name:                                                                                                                                |                       |
      |                       |                                                                                                                                                                         |                       |
      |                       | -  Must contain 1 to 64 characters.                                                                                                                                     |                       |
      |                       | -  Can contain letters, digits, underscores (_), hyphens (-), and periods (.).                                                                                          |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Resource Type         | Mandatory                                                                                                                                                               | VPC                   |
      |                       |                                                                                                                                                                         |                       |
      |                       | Select the type of the resource whose traffic information is to be collected. The enterprise router flow log function can capture traffic of the following attachments: |                       |
      |                       |                                                                                                                                                                         |                       |
      |                       | -  VPC                                                                                                                                                                  |                       |
      |                       | -  Virtual gateway: Virtual gateway of Direct Connect                                                                                                                   |                       |
      |                       | -  VPN gateway                                                                                                                                                          |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Resource              | Mandatory                                                                                                                                                               | vpc-ab                |
      |                       |                                                                                                                                                                         |                       |
      |                       | In the resource list, select the resource whose traffic information is to be collected.                                                                                 |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Log Group             | Mandatory                                                                                                                                                               | lts-group-ab          |
      |                       |                                                                                                                                                                         |                       |
      |                       | Select a log group.                                                                                                                                                     |                       |
      |                       |                                                                                                                                                                         |                       |
      |                       | If there is no log group, click **Create Log Group**.                                                                                                                   |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Log Stream            | Mandatory                                                                                                                                                               | lts-topic-ab          |
      |                       |                                                                                                                                                                         |                       |
      |                       | Select a log stream.                                                                                                                                                    |                       |
      |                       |                                                                                                                                                                         |                       |
      |                       | If there is no log stream, click **Create Log Stream**.                                                                                                                 |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Optional                                                                                                                                                                | ``-``                 |
      |                       |                                                                                                                                                                         |                       |
      |                       | Describe the flow log as required.                                                                                                                                      |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

   The flow log list is displayed.

#. View the flow log status.

   If the flow status changes from **Creating** to **Enabled**, the flow log is successfully created.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

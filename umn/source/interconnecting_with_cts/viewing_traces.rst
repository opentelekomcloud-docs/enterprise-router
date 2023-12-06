:original_name: er_01_0092.html

.. _er_01_0092:

Viewing Traces
==============

**Scenarios**
-------------

After CTS is enabled, CTS starts recording operations on cloud resources. The CTS management console stores the last seven days of operation records.

This section describes how to query or export the last seven days of operation records on the management console.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click **Service List**. Under **Management & Governance**, click **Cloud Trace Service**.

   The **Cloud Trace Service** console is displayed.

#. In the navigation pane on the left, choose **Trace List**.

   The **Trace List** page is displayed.

#. Specify filters as needed.

   The following filters are available:

   -  **Trace Source**, **Resource Type**, and **Search By**

      -  If you select **Trace name** for **Search By**, select a trace name.
      -  If you select **Resource ID** for **Search By**, select or enter a resource ID.
      -  If you select **Resource name** for **Search By**, select or enter a resource name.

   -  **Operator**: Select a specific operator (a user other than an account).
   -  **Trace Status**: Select **All trace statuses**, **Normal**, **Warning**, or **Incident**.
   -  Time range: Select any time range in the last seven days.

#. Expand the trace for details.

#. Click **View Trace**. A dialog box is displayed, in which the trace details are displayed.

   For more information about CTS, see `Cloud Trace Service User Guide <https://docs.otc.t-systems.com/cloud-trace-service/umn/overview/index.html>`__.

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

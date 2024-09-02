:original_name: er_01_0110.html

.. _er_01_0110:

Viewing Details About a Flow Log
================================

Scenarios
---------

This section describes how to view details about a flow log, including the attachment ID, source/destination address, source/destination port, data packet size, and packet quantity.

Constraints
-----------

Flow logs are generated every 10 minutes. After creating a VPC flow log, you need to wait about 10 minutes before you can view the flow log record.

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

#. Locate the target flow log and click **View Log Record** in the **Operation** column.

   The LTS console is displayed.

#. View details about the flow log.

   Flow log format:

   .. code-block::

      <version> <project_id> <resource_id> <instance_id> <srcaddr> <dstaddr> <srcport> <dstport> <protocol> <packets> <bytes> <start> <end> <direct>

   Example 1:

   .. code-block::

      1 0605768ad980d5762f8ac010b919754c 9e00a67c-b21e-435f-9da6-20004b8392e9 a5cbd16c-7d99-4000-8f14-526ec48298ce 1.1.1.1 192.168.1.199 0 0 1 229 22442 1664007127 1664007727 ingress

   Example 2:

   .. code-block::

      1 0605768ad980d5762f8ac010b919754c 9e00a67c-b21e-435f-9da6-20004b8392e9 a5cbd16c-7d99-4000-8f14-526ec48298ce 192.168.1.199 1.1.1.1 8 0 1 229 22442 1664007127 1664007727 egress

   :ref:`Table 1 <er_01_0110__table1313851722313>` describes the flow log parameters.

   .. _er_01_0110__table1313851722313:

   .. table:: **Table 1** Enterprise router flow log parameters

      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Parameter             | Description                                                                                                                        | Example                              |
      +=======================+====================================================================================================================================+======================================+
      | version               | Flow log version                                                                                                                   | 1                                    |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | project_id            | Project ID                                                                                                                         | 5f67944957444bd6bb4fe3b367de8f3d     |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | resource_id           | ID of the attachment that the traffic is generated for                                                                             | 10a163ee-6efa-4e4d-9937-ead59f308497 |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | instance_id           | Enterprise router ID                                                                                                               | a5cbd16c-7d99-4000-8f14-526ec48298ce |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | srcaddr               | Source IP address                                                                                                                  | 192.168.0.154                        |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | dstaddr               | Destination IP address                                                                                                             | 192.168.3.25                         |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | srcport               | Source port                                                                                                                        | 38929                                |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | dstport               | Destination port                                                                                                                   | 53                                   |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | protocol              | Internet Assigned Numbers Authority (IANA) protocol number of the traffic                                                          | 17                                   |
      |                       |                                                                                                                                    |                                      |
      |                       | For more information, see `Internet Protocol Numbers <http://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml>`__. |                                      |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | packets               | Number of data packets during the flow log capture                                                                                 | 1                                    |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | bytes                 | Size of the data packet during the flow log capture                                                                                | 96                                   |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | start                 | The time when the capture started, in Unix seconds                                                                                 | 1548752136                           |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | end                   | The time when the capture ended, in Unix seconds                                                                                   | 1548752736                           |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | direct                | Traffic direction                                                                                                                  | egress                               |
      |                       |                                                                                                                                    |                                      |
      |                       | -  **ingress**: traffic going in to the attachment                                                                                 |                                      |
      |                       | -  **egress**: traffic going out of the attachment                                                                                 |                                      |
      +-----------------------+------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001190483836.png

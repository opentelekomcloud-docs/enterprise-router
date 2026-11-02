:original_name: er_01_0103.html

.. _er_01_0103:

Supported Metrics
=================

Function
--------

This section describes monitoring metrics reported by Enterprise Router to Cloud Eye as well as their namespaces, metrics, and dimensions. You can use the Cloud Eye management console or APIs to obtain the monitoring metrics and alarms generated for Enterprise Router.

.. note::

   Cloud Eye can monitor dimensions nested to a maximum depth of four levels (levels 0 to 3). 3 is the deepest level. For example, if the monitored dimension of a metric is **er_instance_id,er_attachment_id**, **er_instance_id** indicates level 0 and **er_attachment_id** indicates level 1.

Namespace
---------

SYS.ER

Metrics
-------

You can use Cloud Eye to monitor the network status of enterprise routers and their attachments.

-  :ref:`Table 1 <er_01_0103__en-us_topic_0024607920_table6444895193247>`
-  :ref:`Table 2 <er_01_0103__table1914912214313>`

.. _er_01_0103__en-us_topic_0024607920_table6444895193247:

.. table:: **Table 1** Monitoring metrics of an enterprise router

   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+
   | Metric ID                       | Metric Name                             | Metric Description                                                                             | Value Range | Unit  | Conversion Rule | Monitored Object (Dimension) | Monitoring Interval (Raw Data) |
   +=================================+=========================================+================================================================================================+=============+=======+=================+==============================+================================+
   | instance_bytes_in               | Inbound Traffic                         | Network traffic going into the enterprise router                                               | >= 0        | Byte  | 1024 (IEC)      | er_instance_id               | 1 minute                       |
   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+
   | instance_bytes_out              | Outbound Traffic                        | Network traffic going out of the enterprise router                                             | >= 0        | Byte  | 1024 (IEC)      | er_instance_id               | 1 minute                       |
   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+
   | instance_bits_rate_in           | Inbound Bandwidth                       | Network traffic per second going into the enterprise router                                    | >= 0        | bit/s | 1000 (SI)       | er_instance_id               | 1 minute                       |
   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+
   | instance_bits_rate_out          | Outbound Bandwidth                      | Network traffic per second going out of the enterprise router                                  | >= 0        | bit/s | 1000 (SI)       | er_instance_id               | 1 minute                       |
   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+
   | instance_packets_in             | Inbound PPS                             | Packets per second going into the enterprise router                                            | >= 0        | PPS   | 1000 (SI)       | er_instance_id               | 1 minute                       |
   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+
   | instance_packets_out            | Outbound PPS                            | Packets per second going out of the enterprise router                                          | >= 0        | PPS   | 1000 (SI)       | er_instance_id               | 1 minute                       |
   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+
   | instance_packets_drop_blackhole | Packets Dropped by Black Hole Route     | The number of packets dropped because they matched a black hole route on the enterprise router | >= 0        | Count | N/A             | er_instance_id               | 1 minute                       |
   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+
   | instance_packets_drop_noroute   | Packets Dropped Due to No Route Matched | The number of packets dropped because they did not match a route on the enterprise router      | >= 0        | Count | N/A             | er_instance_id               | 1 minute                       |
   +---------------------------------+-----------------------------------------+------------------------------------------------------------------------------------------------+-------------+-------+-----------------+------------------------------+--------------------------------+

.. _er_01_0103__table1914912214313:

.. table:: **Table 2** Monitoring metrics of an attachment

   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | Metric ID                         | Metric Name                             | Metric Description                                                                      | Value Range | Unit  | Conversion Rule | Monitored Object (Dimension)    | Monitoring Interval (Raw Data) |
   +===================================+=========================================+=========================================================================================+=============+=======+=================+=================================+================================+
   | attachment_bytes_in               | Inbound Traffic                         | Network traffic going into the attachment                                               | >= 0        | Byte  | 1024 (IEC)      | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_bytes_out              | Outbound Traffic                        | Network traffic going out of the attachment                                             | >= 0        | Byte  | 1024 (IEC)      | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_bits_rate_in           | Inbound Bandwidth                       | Network traffic per second going into the attachment                                    | >= 0        | bit/s | 1000 (SI)       | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_bits_rate_out          | Outbound Bandwidth                      | Network traffic per second going out of the attachment                                  | >= 0        | bit/s | 1000 (SI)       | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_packets_in             | Inbound PPS                             | Packets per second going into the attachment                                            | >= 0        | PPS   | 1000 (SI)       | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_packets_out            | Outbound PPS                            | Packets per second going out of the attachment                                          | >= 0        | PPS   | 1000 (SI)       | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_packets_drop_blackhole | Packets Dropped by Black Hole Route     | The number of packets dropped because they matched a black hole route on the attachment | >= 0        | Count | N/A             | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_packets_drop_noroute   | Packets Dropped Due to No Route Matched | The number of packets dropped because they did not match a route on the attachment      | >= 0        | Count | N/A             | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+

If an object is in a hierarchical system, specify the monitored dimension in hierarchical form when you use an API to query the metrics of this object.

-  To query a single metric by calling an API, the **mount_point** dimension is used as follows:

   .. code-block::

      dim.0=er_instance_id,d9f7b61f-e211-4bce-ac5f-2b76f3d0cf1d&dim.1=er_attachment_id,659614a0-e559-46c0-86ca-00c03c3d61b8

   **d9f7b61f-e211-4bce-ac5f-2b76f3d0cf1d** and **659614a0-e559-46c0-86ca-00c03c3d61b8** are the dimension values of **er_instance_id** and **er_attachment_id**, respectively. For details about how to obtain the values, see :ref:`Dimensions <er_01_0103__section91771135191816>`.

-  To query multiple metrics by calling an API, the **mount_point** dimension is used as follows:

   .. code-block::

      "dimensions": [
          {
              "name": "er_instance_id",
              "value": "d9f7b61f-e211-4bce-ac5f-2b76f3d0cf1d"
          },
          {
              "name": "er_attachment_id",
              "value": "659614a0-e559-46c0-86ca-00c03c3d61b8"
          }
      ]

   **d9f7b61f-e211-4bce-ac5f-2b76f3d0cf1d** and **659614a0-e559-46c0-86ca-00c03c3d61b8** are the dimension values of **er_instance_id** and **er_attachment_id**, respectively. For details about how to obtain the values, see :ref:`Dimensions <er_01_0103__section91771135191816>`.

.. _er_01_0103__section91771135191816:

Dimensions
----------

================ ====================
Key              Value
================ ====================
er_instance_id   Enterprise router ID
er_attachment_id Attachment ID
================ ====================

:original_name: er_01_0103.html

.. _er_01_0103:

Supported Metrics
=================

Function
--------

This section describes monitoring metrics reported by Enterprise Router to Cloud Eye as well as their namespaces, metrics, and dimensions. You can use the Cloud Eye management console or APIs to obtain the monitoring metrics and alarms generated for Enterprise Router.

Namespace
---------

SYS.ER

Metrics
-------

You can use Cloud Eye to monitor the network status of enterprise routes and their attachments.

-  :ref:`Table 1 <er_01_0103__en-us_topic_0024607920_table6444895193247>`
-  :ref:`Table 2 <er_01_0103__table1914912214313>`

.. _er_01_0103__en-us_topic_0024607920_table6444895193247:

.. table:: **Table 1** Monitoring metrics of an enterprise router

   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+
   | ID                              | Name                                      | Description                                                          | Value Range | Monitored Object  | Monitoring Interval (Raw Data) |
   +=================================+===========================================+======================================================================+=============+===================+================================+
   | instance_bytes_in               | Inbound Traffic                           | Network traffic going into the enterprise router                     | >= 0        | Enterprise router | 1 minute                       |
   |                                 |                                           |                                                                      |             |                   |                                |
   |                                 |                                           | Unit: byte                                                           |             |                   |                                |
   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+
   | instance_bytes_out              | Outbound Traffic                          | Network traffic going out of the enterprise router                   | >= 0        | Enterprise router | 1 minute                       |
   |                                 |                                           |                                                                      |             |                   |                                |
   |                                 |                                           | Unit: byte                                                           |             |                   |                                |
   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+
   | instance_bits_rate_in           | Inbound Bandwidth                         | Network traffic per second going into the enterprise router          | >= 0        | Enterprise router | 1 minute                       |
   |                                 |                                           |                                                                      |             |                   |                                |
   |                                 |                                           | Unit: bit/s                                                          |             |                   |                                |
   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+
   | instance_bits_rate_out          | Outbound Bandwidth                        | Network traffic per second going out of the enterprise router        | >= 0        | Enterprise router | 1 minute                       |
   |                                 |                                           |                                                                      |             |                   |                                |
   |                                 |                                           | Unit: bit/s                                                          |             |                   |                                |
   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+
   | instance_packets_in             | Inbound PPS                               | Packets per second going into the enterprise router                  | >= 0        | Enterprise router | 1 minute                       |
   |                                 |                                           |                                                                      |             |                   |                                |
   |                                 |                                           | Unit: packet/s                                                       |             |                   |                                |
   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+
   | instance_packets_out            | Outbound PPS                              | Packets per second going out of the enterprise router                | >= 0        | Enterprise router | 1 minute                       |
   |                                 |                                           |                                                                      |             |                   |                                |
   |                                 |                                           | Unit: packet/s                                                       |             |                   |                                |
   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+
   | instance_packets_drop_blackhole | Packets Dropped by Black Hole Route       | Packets dropped by black hole route of the enterprise router         | >= 0        | Enterprise router | 1 minute                       |
   |                                 |                                           |                                                                      |             |                   |                                |
   |                                 |                                           | Unit: count                                                          |             |                   |                                |
   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+
   | instance_packets_drop_noroute   | Packets Dropped Due to No Matching Routes | Packets dropped because the enterprise router has no matching routes | >= 0        | Enterprise router | 1 minute                       |
   |                                 |                                           |                                                                      |             |                   |                                |
   |                                 |                                           | Unit: count                                                          |             |                   |                                |
   +---------------------------------+-------------------------------------------+----------------------------------------------------------------------+-------------+-------------------+--------------------------------+

.. _er_01_0103__table1914912214313:

.. table:: **Table 2** Monitoring metrics of an attachment

   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | ID                                | Name                                      | Description                                                   | Value Range | Monitored Object | Monitoring Interval (Raw Data) |
   +===================================+===========================================+===============================================================+=============+==================+================================+
   | attachment_bytes_in               | Inbound Traffic                           | Network traffic going into the attachment                     | >= 0        | Attachment       | 1 minute                       |
   |                                   |                                           |                                                               |             |                  |                                |
   |                                   |                                           | Unit: byte                                                    |             |                  |                                |
   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | attachment_bytes_out              | Outbound Traffic                          | Network traffic going out of the attachment                   | >= 0        | Attachment       | 1 minute                       |
   |                                   |                                           |                                                               |             |                  |                                |
   |                                   |                                           | Unit: byte                                                    |             |                  |                                |
   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | attachment_bits_rate_in           | Inbound Bandwidth                         | Network traffic per second going into the attachment          | >= 0        | Attachment       | 1 minute                       |
   |                                   |                                           |                                                               |             |                  |                                |
   |                                   |                                           | Unit: bit/s                                                   |             |                  |                                |
   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | attachment_bits_rate_out          | Outbound Bandwidth                        | Network traffic per second going out of the attachment        | >= 0        | Attachment       | 1 minute                       |
   |                                   |                                           |                                                               |             |                  |                                |
   |                                   |                                           | Unit: bit/s                                                   |             |                  |                                |
   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | attachment_packets_in             | Inbound PPS                               | Packets per second going into the attachment                  | >= 0        | Attachment       | 1 minute                       |
   |                                   |                                           |                                                               |             |                  |                                |
   |                                   |                                           | Unit: packet/s                                                |             |                  |                                |
   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | attachment_packets_out            | Outbound PPS                              | Packets per second going out of the attachment                | >= 0        | Attachment       | 1 minute                       |
   |                                   |                                           |                                                               |             |                  |                                |
   |                                   |                                           | Unit: packet/s                                                |             |                  |                                |
   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | attachment_packets_drop_blackhole | Packets Dropped by Black Hole Route       | Packets dropped by black hole route of the attachment         | >= 0        | Attachment       | 1 minute                       |
   |                                   |                                           |                                                               |             |                  |                                |
   |                                   |                                           | Unit: count                                                   |             |                  |                                |
   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | attachment_packets_drop_noroute   | Packets Dropped Due to No Matching Routes | Packets dropped because the attachment has no matching routes | >= 0        | Attachment       | 1 minute                       |
   |                                   |                                           |                                                               |             |                  |                                |
   |                                   |                                           | Unit: count                                                   |             |                  |                                |
   +-----------------------------------+-------------------------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+

If a monitored object has multiple dimensions, all dimensions are mandatory when you use APIs to query the metrics.

-  Query a single metric:

   .. code-block::

      dim.0=er_instance_id,d9f7b61f-e211-4bce-ac5f-2b76f3d0cf1d&dim.1=er_attachment_id,659614a0-e559-46c0-86ca-00c03c3d61b8

-  Query metrics in batches:

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

Dimensions
----------

================ =================
Key              Value
================ =================
er_instance_id   Enterprise router
er_attachment_id Attachment
================ =================

-  The monitoring metric measurement dimension of an enterprise router is **er_instance_id**.
-  The monitoring metric measurement dimensions of an attachment are **er_instance_id** and **er_attachment_id**.

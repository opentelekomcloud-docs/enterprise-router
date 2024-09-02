:original_name: er_01_0004.html

.. _er_01_0004:

When to Use Enterprise Routers
==============================

You can use enterprise routers to build cloud, on-premises, or hybrid networks. Here are some typical application scenarios:

-  :ref:`Scenario 1: Multiple VPCs communicating or not communicating with each other on the cloud, but communicating with the on-premises data center through a Direct Connect connection <er_01_0004__section16111115210>`
-  :ref:`Scenario 2: Dynamic switchover between Direct Connect connections <er_01_0004__section12577403566>`
-  :ref:`Scenario 3: Active/Standby Direct Connect and VPN connections <er_01_0004__section198551355121620>`

.. _er_01_0004__section16111115210:

Scenario 1: Multiple VPCs communicating or not communicating with each other on the cloud, but communicating with the on-premises data center through a Direct Connect connection
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


.. figure:: /_static/images/en-us_image_0000001190538519.png
   :alt: **Figure 1** Diagram for scenario 1

   **Figure 1** Diagram for scenario 1

.. table:: **Table 1** Using enterprise routers in scenario 1

   +--------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Customer Requirements                | Multiple service networks communicate or do not communicate with each other on the cloud but communicate with the on-premises data center. Suppose you require three VPCs for running the workloads on the public cloud, and the three VPCs (services A, B, and C) need to access public services in VPC 4 and your on-premises data center. |
   +--------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Pain Points                          | -  VPC peering connections are required for communications among these VPCs, but they will complicate the network topology and make the network hard to manage.                                                                                                                                                                              |
   |                                      | -  VPC peering connections and routes are required for the public service VPC to communicate with each VPC. However, VPC peering connections do not fit in large-scale networks because of the following limitations:                                                                                                                        |
   |                                      |                                                                                                                                                                                                                                                                                                                                              |
   |                                      |    -  A maximum of 50 VPC peering connections can be created in one region.                                                                                                                                                                                                                                                                  |
   |                                      |    -  A VPC route table can have a maximum of 200 routes.                                                                                                                                                                                                                                                                                    |
   |                                      |                                                                                                                                                                                                                                                                                                                                              |
   |                                      | -  Direct Connect connections are required for each VPC to communicate with the on-premises data center, but they will incur high costs.                                                                                                                                                                                                     |
   +--------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Benefits of Using Enterprise Routers | -  VPCs can be associated with different route tables on the enterprise router to enable communication or isolation. The network topology is simple and easy to manage.                                                                                                                                                                      |
   |                                      | -  Enterprise routers can route traffic among all the connected VPCs without the need to configure a large number of VPC peering connections.                                                                                                                                                                                                |
   |                                      |                                                                                                                                                                                                                                                                                                                                              |
   |                                      |    -  Each enterprise router can have a maximum of 2,000 routes in each route table, making it ideal for large-scale complex networks.                                                                                                                                                                                                       |
   |                                      |                                                                                                                                                                                                                                                                                                                                              |
   |                                      | -  Multiple VPCs can access the on-premises data center over a Direct Connect connection, eliminating the need to configure multiple Direct Connect connections and reducing the costs.                                                                                                                                                      |
   +--------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _er_01_0004__section12577403566:

Scenario 2: Dynamic switchover between Direct Connect connections
-----------------------------------------------------------------


.. figure:: /_static/images/en-us_image_0000001144919892.png
   :alt: **Figure 2** Diagram for scenario 2

   **Figure 2** Diagram for scenario 2

.. table:: **Table 2** Using enterprise routers in scenario 2

   +--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Customer Requirements                | Some services run on the public cloud and some in the on-premises data center. Two independent high-bandwidth Direct Connect connections are deployed between the public cloud and the data center to enable communication between them. |
   +--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Pain Points                          | Two Direct Connect connections are independent of each other and cannot work in load-sharing or active/standby mode.                                                                                                                     |
   +--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Benefits of Using Enterprise Routers | Direct Connect connections are connected to the enterprise router.                                                                                                                                                                       |
   |                                      |                                                                                                                                                                                                                                          |
   |                                      | -  Two Direct Connect connections can work in load-sharing mode to ensure high bandwidth and reliability.                                                                                                                                |
   |                                      | -  Two Direct Connect connections can also work in active/standby mode. If one of the connections becomes unavailable, services are switched over to the other available connection within seconds, preventing service interruptions.    |
   +--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _er_01_0004__section198551355121620:

Scenario 3: Active/Standby Direct Connect and VPN connections
-------------------------------------------------------------


.. figure:: /_static/images/en-us_image_0000001730846789.png
   :alt: **Figure 3** Diagram for scenario 3

   **Figure 3** Diagram for scenario 3

.. table:: **Table 3** Using enterprise routers in scenario 3

   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Customer Requirements                | You are running workloads in your on-premises data center and on the public cloud. A single Direct Connect connection connects your on-premises data center to the cloud, which cannot ensure reliability.                                                                                                    |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Pain Points                          | You cannot afford another Direct Connect connection.                                                                                                                                                                                                                                                          |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Benefits of Using Enterprise Routers | In this example, there are two connections, one Direct Connect connection and a VPN connection. Enterprise Router, Direct Connect, and VPC are used to build a hybrid cloud. When the Direct Connect connection becomes faulty, the VPN connection takes over to ensure that connectivity is not interrupted. |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

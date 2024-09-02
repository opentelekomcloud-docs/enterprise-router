:original_name: er_01_0003.html

.. _er_01_0003:

Why Using Enterprise Routers
============================

Enterprise routers have the following advantages:

High Performance
----------------

Enterprise routers use exclusive resources and are deployed in clusters to deliver the highest possible performance for workloads on large-scale networks.

High Availability
-----------------

Enterprise routers can be deployed in multiple availability zones to work in active-active or multi-active mode, thereby ensuring service continuity and real-time seamless switchovers.

Simplified Management
---------------------

Enterprise routers can route traffic among instances, simplify network topology and network management, and improve network O&M efficiency. The network topology is simpler and the network is easier to manage and maintain.

-  For cross-VPC communications, you only need to maintain the route tables on the VPCs without requiring so many VPC peering connections.
-  For communications between VPCs and an on-premises data center, multiple VPCs can connect to an enterprise router and then communicate with the data center over one Direct Connect or VPN connection. You do not need to establish a Direct Connect or VPN connection between the data center and each of the VPCs.
-  Enterprise routers can automatically learn, update, and synchronize routes, eliminating the need to manually configure or update routes whenever the network topology changes.

Seamless Failover Between Lines
-------------------------------

Enterprise routers use the Border Gateway Protocol (BGP) to select the best path from multiple lines working in load-sharing or active/standby mode. If a single line fails, services can be failed over to another functioning line within seconds to ensure service continuity.

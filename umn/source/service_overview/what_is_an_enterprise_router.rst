:original_name: er_01_0002.html

.. _er_01_0002:

What Is an Enterprise Router?
=============================

An enterprise router connects VPCs and on-premises networks to build a central hub network. It has high specifications, provides high bandwidth, and delivers high performance. Enterprise routers use the Border Gateway Protocol (BGP) to learn, dynamically select, or switch between routes, thereby ensuring the service continuity and significantly improving network scalability and O&M efficiency.

:ref:`Figure 1 <er_01_0002__fig1160410331975>` and :ref:`Figure 2 <er_01_0002__fig12604833873>` show the networks with and without enterprise routers, respectively. :ref:`Table 1 <er_01_0002__table126045339718>` compares the two networks.

.. _er_01_0002__fig1160410331975:

.. figure:: /_static/images/en-us_image_0000001427301842.png
   :alt: **Figure 1** A network without enterprise routers

   **Figure 1** A network without enterprise routers

.. _er_01_0002__fig12604833873:

.. figure:: /_static/images/en-us_image_0000001559118632.png
   :alt: **Figure 2** A network with enterprise routers

   **Figure 2** A network with enterprise routers

.. _er_01_0002__table126045339718:

.. table:: **Table 1** Comparison between the networks with and without enterprise routers

   +------------------------------------------------------------+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------+
   | Item                                                       | Without Enterprise Routers                                                                 | With Enterprise Routers                                                                                                                                                                                    | Benefits of Using Enterprise Routers                                                          |
   +============================================================+============================================================================================+============================================================================================================================================================================================================+===============================================================================================+
   | Communications among VPCs in the same region               | -  Create six VPC peering connections between these four VPCs in the same region.          | -  Attach the four VPCs to one enterprise router. This router can then handle the traffic from and to all the connected VPCs.                                                                              | -  There is no need to configure a large number of VPC peering connections.                   |
   |                                                            | -  Add 12 routes, with three routes for each VPC to communicate with the other three VPCs. | -  Add routes to the route tables of these four VPCs for routing traffic through the enterprise router. The enterprise router can automatically learn the VPC CIDR blocks and add them to its route table. | -  Fewer routes need to be added, simplifying the maintenance.                                |
   +------------------------------------------------------------+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------+
   | Communications between an on-premises data center and VPCs | Establish Direct Connect or VPN connections between each VPC and the data center.          | Attach the Direct Connect or VPN connection to the enterprise router. These VPCs can then share the connection.                                                                                            | -  Route propagation simplifies the route configuration and the O&M.                          |
   |                                                            |                                                                                            |                                                                                                                                                                                                            | -  Multiple lines work in load-sharing or active/standby mode to achieve higher availability. |
   +------------------------------------------------------------+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------+

The comparison shows that the network with enterprise routers is simpler and highly scalable and is also easier to maintain.

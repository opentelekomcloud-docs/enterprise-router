:original_name: er_01_0122.html

.. _er_01_0122:

How Do I Route Traffic to 100.64.x.x Through an Enterprise Router?
==================================================================

Scenarios
---------

A route with 100.64.x.x as the destination and an enterprise router as the next hop cannot be added to a VPC route table.

Solutions
---------

If you want to route traffic to 100.64.x.x through an enterprise router, you need to create a transit VPC. :ref:`Figure 1 <er_01_0122__en-us_topic_0000001135431190_fig121911186551>` shows the network diagram.

.. _er_01_0122__en-us_topic_0000001135431190_fig121911186551:

.. figure:: /_static/images/en-us_image_0000001446449166.png
   :alt: **Figure 1** Transit VPC network diagram

   **Figure 1** Transit VPC network diagram

The request traffic from the service VPC to the on-premises data center will be forwarded through the transit VPC, but the response traffic will not. For details, see :ref:`Table 1 <er_01_0122__table198114341557>`.

.. _er_01_0122__table198114341557:

.. table:: **Table 1** Network traffic flows

   +------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Path                                                                                                       | Description                                                                                                                                                                                |
   +============================================================================================================+============================================================================================================================================================================================+
   | Request traffic: service VPC → transit VPC → enterprise router → virtual gateway → on-premises data center | #. The service VPC route table has a route with the VPC peering connection as the next hop to forward traffic from the service VPC to the transit VPC.                                     |
   |                                                                                                            | #. The transit VPC route table has a route with next hop set to the enterprise router to forward traffic from the transit VPC to the enterprise router.                                    |
   |                                                                                                            | #. The enterprise router route table has a route with next hop set to virtual gateway attachment to forward traffic from the enterprise router to the virtual gateway.                     |
   |                                                                                                            | #. The virtual gateway is connected to the virtual interface. Traffic from the virtual gateway is forwarded to the physical connection through the remote gateway of the virtual interface |
   |                                                                                                            | #. Traffic is sent to the on-premises data center over the connection.                                                                                                                     |
   +------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Response traffic: on-premises data center → virtual gateway → enterprise router → service VPC              | #. Traffic is forwarded to the virtual interface through the connection.                                                                                                                   |
   |                                                                                                            | #. The virtual interface is connected to the virtual gateway. Traffic from the virtual interface is forwarded to the virtual gateway through the local gateway of the virtual interface.   |
   |                                                                                                            | #. Traffic is forwarded from the virtual gateway to enterprise router.                                                                                                                     |
   |                                                                                                            | #. The enterprise router route table has a route with next hop set to the service VPC attachment to forward traffic from the enterprise router to the service VPC.                         |
   +------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

The required resources and routes are as follows:

-  :ref:`Table 2 <er_01_0122__table14233740534>`: Required service VPC, transit VPC, enterprise router, and Direct Connect connection that connects the cloud and the on-premises data center
-  :ref:`Table 3 <er_01_0122__en-us_topic_0000001135431190_table5325182820514>`: Required routes of the service VPC, transit VPC, and enterprise router

.. _er_01_0122__table14233740534:

.. table:: **Table 2** Resource planning

   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------+
   | Resource              | Quantity              | Description                                                                                                                      |
   +=======================+=======================+==================================================================================================================================+
   | VPC                   | 2                     | Service VPC that your services are deployed and needs to be attached to the enterprise router                                    |
   |                       |                       |                                                                                                                                  |
   |                       |                       | -  VPC CIDR block: 10.1.0.0/16                                                                                                   |
   |                       |                       | -  Subnet CIDR block: 10.1.1.0/24                                                                                                |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------+
   |                       |                       | Transit VPC that is connected to the service VPC over a VPC peering connection and needs to be attached to the enterprise router |
   |                       |                       |                                                                                                                                  |
   |                       |                       | -  VPC CIDR block: 192.168.0.0/16                                                                                                |
   |                       |                       | -  Subnet CIDR block: 192.168.1.0/24                                                                                             |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------+
   | Enterprise router     | 1                     | Three attachments on the enterprise router:                                                                                      |
   |                       |                       |                                                                                                                                  |
   |                       |                       | -  Service VPC attachment: service VPC                                                                                           |
   |                       |                       | -  Transit VPC attachment: transit VPC                                                                                           |
   |                       |                       | -  Virtual gateway attachment: virtual gateway of Direct Connect                                                                 |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------+
   | Direct Connect        | 1                     | -  Connection                                                                                                                    |
   |                       |                       | -  Virtual gateway that needs to be attached to the enterprise router                                                            |
   |                       |                       | -  Virtual interface                                                                                                             |
   |                       |                       |                                                                                                                                  |
   |                       |                       |    -  Local gateway: 10.0.0.1/30                                                                                                 |
   |                       |                       |    -  Remote gateway: 10.0.0.2/30                                                                                                |
   |                       |                       |    -  Remote subnet: subnet of the on-premises data center (100.64.x.x)                                                          |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------+

.. _er_01_0122__en-us_topic_0000001135431190_table5325182820514:

.. table:: **Table 3** Route planning

   +-------------------+-----------------------------------------------+----------------------------+-----------------------+
   | Route Table       | Destination                                   | Next Hop                   | Route Type            |
   +===================+===============================================+============================+=======================+
   | Service VPC       | 100.64.x.x                                    | VPC peering connection     | Static route (custom) |
   +-------------------+-----------------------------------------------+----------------------------+-----------------------+
   | Transit VPC       | 2.2.2.2/32                                    | VPC peering connection     | Static route (custom) |
   |                   |                                               |                            |                       |
   |                   | .. note::                                     |                            |                       |
   |                   |                                               |                            |                       |
   |                   |    2.2.2.2/32 is mandatory and must be added. |                            |                       |
   +-------------------+-----------------------------------------------+----------------------------+-----------------------+
   |                   | 0.0.0.0/0                                     | Enterprise router          | Static route (custom) |
   +-------------------+-----------------------------------------------+----------------------------+-----------------------+
   | Enterprise router | 10.1.0.0/16                                   | Service VPC attachment     | Propagated route      |
   +-------------------+-----------------------------------------------+----------------------------+-----------------------+
   |                   | 100.64.x.x                                    | Virtual gateway attachment | Propagated route      |
   +-------------------+-----------------------------------------------+----------------------------+-----------------------+

#. Create a transit VPC, attach it to the enterprise router, and associate the transit VPC with the default route table of the enterprise router.

   -  The subnet of the transit VPC cannot overlap with that of the service VPC, or the VPC peering connection to be created in :ref:`2 <er_01_0122__li14564823993>` cannot take effect.
   -  The transit VPC cannot have the following situations. Otherwise, the default route (0.0.0.0/0) to be configured in :ref:`3 <er_01_0122__li92642018194217>` cannot forward traffic.

      -  An ECS in the VPC has an EIP bound.
      -  The VPC is being used by ELB, NAT Gateway, VPC Endpoint, or DCS.

#. .. _er_01_0122__li14564823993:

   Create a VPC peering connection between the service VPC and transit VPC.

   .. important::

      You do not need to add routes for the VPC peering connection. For details about the routes to be added, see :ref:`3 <er_01_0122__li92642018194217>`.

#. .. _er_01_0122__li92642018194217:

   Add routes to the VPC route tables.

   For details about required routes, see :ref:`Table 3 <er_01_0122__en-us_topic_0000001135431190_table5325182820514>`.

   a. Add the route to the service VPC route table.
   b. Add two routes to the transit VPC route table.

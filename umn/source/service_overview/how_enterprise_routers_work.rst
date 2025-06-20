:original_name: er_01_0011.html

.. _er_01_0011:

How Enterprise Routers Work
===========================

You can attach your network connections to an enterprise router to quickly construct diversified networks and meet various service requirements. :ref:`Figure 1 <er_01_0011__fig6579195613359>` shows the process of using an enterprise router, including creating an enterprise router, adding attachments to the enterprise router, and configure routes.

Enterprise routers support the following attachments:

-  **VPC attachment**: Attach a VPC from the same region as that of an enterprise router.
-  **Virtual gateway attachment**: Attach a Direct Connect virtual gateway from the same region as that of an enterprise router.
-  **VPN gateway attachment**: Attach a VPN gateway from the same region as that of an enterprise router.
-  **CFW instance attachment**: Connect an enterprise router to the VPC border firewall in the same region.

.. _er_01_0011__fig6579195613359:

.. figure:: /_static/images/en-us_image_0000001586175602.png
   :alt: **Figure 1** Processing of using an enterprise router

   **Figure 1** Processing of using an enterprise router

:ref:`Figure 2 <er_01_0011__fig1050492818281>` shows how an enterprise router works. :ref:`Table 2 <er_01_0011__table133841251278>` describes the traffic flows in detail if an enterprise router is used for networking.

.. _er_01_0011__fig1050492818281:

.. figure:: /_static/images/en-us_image_0000001529950265.png
   :alt: **Figure 2** How an enterprise router works

   **Figure 2** How an enterprise router works

.. table:: **Table 1** Network traffic flows

   +-----+-------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | No. | Route                                                 | Description                                                                                                                                                                                                           |
   +=====+=======================================================+=======================================================================================================================================================================================================================+
   | 1   | Request from VPC 1 to Direct Connect virtual gateway  | After receiving requests from VPC 1 to the virtual gateway, enterprise router 1 searches the default route table for the route to the virtual gateway and forwards the requests through this route.                   |
   +-----+-------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |     | Response from Direct Connect virtual gateway to VPC 1 | After receiving responses from the virtual gateway to VPC 1, enterprise router 1 searches the default route table for the route to VPC 1 and forwards the responses through this route.                               |
   +-----+-------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 2   | Request from VPC 2 to Direct Connect virtual gateway  | Enterprise router 1 cannot forward requests from VPC 2 to the virtual gateway because the custom route table of enterprise router 1 that is associated with VPC 2 does not contain the route to this virtual gateway. |
   +-----+-------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _er_01_0011__table133841251278:

.. table:: **Table 2** Working principles of an enterprise router

   +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | No.                   | Action                                                                                                                                                                                                                                    | Description                                                                                                                                                                                                                     |
   +=======================+===========================================================================================================================================================================================================================================+=================================================================================================================================================================================================================================+
   | 1                     | Add :ref:`attachments <er_01_0011__section692619383113>` to the enterprise router.                                                                                                                                                        | Attach network instances to enterprise router 1 in region A.                                                                                                                                                                    |
   |                       |                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                 |
   |                       |                                                                                                                                                                                                                                           | Network instances from the same region                                                                                                                                                                                          |
   |                       |                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                 |
   |                       |                                                                                                                                                                                                                                           | -  **VPC attachments**: VPC 1, VPC 2, and VPC 3                                                                                                                                                                                 |
   |                       |                                                                                                                                                                                                                                           | -  **Virtual gateway attachment**: Virtual gateway                                                                                                                                                                              |
   |                       |                                                                                                                                                                                                                                           | -  **VPN gateway attachment**: VPN gateway                                                                                                                                                                                      |
   +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 2                     | #. Associate the :ref:`attachments <er_01_0011__section131904714219>` with the :ref:`route tables <er_01_0011__section14844328152418>` of the enterprise router.                                                                          | -  Associate VPC 1 with the default route table of enterprise router 1 and create a propagation to propagate the routes learned from VPC 1 attachment to the default route table and custom route table of enterprise router 1. |
   |                       |                                                                                                                                                                                                                                           | -  Associate VPC 2 with the custom route table of enterprise router 1 and create a propagation to propagate the routes learned from VPC 2 to the custom route table.                                                            |
   |                       |    Each attachment can only be associated with one route table.                                                                                                                                                                           | -  Associate VPC 3 with the custom route table of enterprise router 1, and add static routes for VPC 3 to this custom route table.                                                                                              |
   |                       |                                                                                                                                                                                                                                           | -  Associate the Direct Connect virtual gateway with the default route table of enterprise router 1 and create a propagation to propagate the routes learned from the virtual gateway attachment to the default route table.    |
   |                       | #. Create :ref:`propagation <er_01_0011__section134131541823>` for the attachments to propagate the :ref:`routes <er_01_0011__section11725172512435>` to the enterprise router's :ref:`route tables <er_01_0011__section14844328152418>`. | -  Associate the VPN gateway with the default route table of enterprise router 1 and create a propagation to propagate the routes learned from the VPN gateway attachment to the default route table.                           |
   |                       |                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                 |
   |                       |    You can create multiple propagation records for the same attachment.                                                                                                                                                                   |                                                                                                                                                                                                                                 |
   +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _er_01_0011__section692619383113:

Attachments
-----------

If you want to attach a network instance to an enterprise router, you need to add an attachment of a specific type to the enterprise router. The attachment type varies by type of the network instance, as listed in :ref:`Table 3 <er_01_0011__table1989203755810>`.

.. _er_01_0011__table1989203755810:

.. table:: **Table 3** Attachments

   ========================== =================================
   Attachment Type            Network Instance
   ========================== =================================
   VPC attachment             VPC
   Virtual gateway attachment Virtual gateway of Direct Connect
   VPN gateway attachment     VPN gateway
   CFW instance attachment    VPC border firewall
   ========================== =================================

.. _er_01_0011__section14844328152418:

Route Tables
------------

Route tables are used by enterprise routers to forward packets. Route tables contain associations, propagations, and routes. Route tables are classified into custom and default route tables, as detailed in :ref:`Table 4 <er_01_0011__table113001814111111>`.

.. _er_01_0011__table113001814111111:

.. table:: **Table 4** Route tables

   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Route Table Type                  | Description                                                                                                                                                                                      |
   +===================================+==================================================================================================================================================================================================+
   | Custom route table                | You can create multiple custom route tables on an enterprise router and use different routes for flexible communication and isolation between network instances.                                 |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Default route table               | If you enable **Default Route Table Association** and **Default Route Table Propagation**, the system then automatically associates and propagates new attachments with the default route table. |
   |                                   |                                                                                                                                                                                                  |
   |                                   | You can specify a custom route table as the default route table. If you do not specify any route table as the default route table, the system automatically creates a default route table.       |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _er_01_0011__section131904714219:

Associations
------------

Each attachment can be associated with one route table for:

-  Packet forwarding: Packets from the attachment are forwarded through the routes specified in the associated route table.
-  Route propagation: The routes in the associated route tables are automatically propagated to the route table of the attachment.

Not all attachments can propagate routes. For details, see :ref:`Table 5 <er_01_0011__table11754113392813>`.

.. _er_01_0011__table11754113392813:

.. table:: **Table 5** Associations

   =============== ==============
   Attachment Type Route Learning
   =============== ==============
   VPC             Not supported
   Virtual gateway Supported
   VPN gateway     Supported
   CFW instance    Not supported
   =============== ==============

.. _er_01_0011__section134131541823:

Route Propagation
-----------------

You can create a propagation for each attachment to propagate routes to one or more route tables on an enterprise router.

For VPC attachments, their CIDR blocks are propagated to the enterprise router. For other attachments, all routes are propagated to the enterprise router. For details, see :ref:`Table 6 <er_01_0011__table18744443292>`.

.. _er_01_0011__table18744443292:

.. table:: **Table 6** Propagation

   =============== ========================================
   Attachment Type Propagated Info
   =============== ========================================
   VPC             VPC CIDR blocks
   Virtual gateway All routes
   VPN gateway     All routes
   CFW instance    CIDR blocks of the VPCs protected by CFW
   =============== ========================================

.. _er_01_0011__section11725172512435:

Routes
------

Routes are used to forward packets. A route contains information such as the destination, next hop, and route type. :ref:`Table 7 <er_01_0011__table132552223219>` describes the routes of different types.

.. _er_01_0011__table132552223219:

.. table:: **Table 7** Routes

   +-----------------------+----------------------------------------------------------------------------------------------------+-----------------------+
   | Route Type            | Description                                                                                        | Attachment            |
   +=======================+====================================================================================================+=======================+
   | Propagated routes     | Propagated routes are automatically learned through propagation and cannot be modified or deleted. | -  VPC                |
   |                       |                                                                                                    | -  Virtual gateway    |
   |                       |                                                                                                    | -  VPN gateway        |
   |                       |                                                                                                    | -  CFW instance       |
   +-----------------------+----------------------------------------------------------------------------------------------------+-----------------------+
   | Static routes         | Static routes are manually created and can be modified or deleted.                                 | -  VPC                |
   |                       |                                                                                                    | -  CFW instance       |
   +-----------------------+----------------------------------------------------------------------------------------------------+-----------------------+

:original_name: er_01_0040.html

.. _er_01_0040:

Route Overview
==============

What Is a Route?
----------------

Routes are used to forward packets. A route contains information such as the destination, next hop, and route type.

You can create a propagation for attachments to automatically propagate routes to route tables or manually add static routes to route tables.

.. _er_01_0040__fig2088721517588:

.. figure:: /_static/images/en-us_image_0000001347809009.png
   :alt: **Figure 1** Propagated routes and static routes

   **Figure 1** Propagated routes and static routes

.. table:: **Table 1** Route types

   +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Route Type        | Description                                                                                                                               | How to Create                                                                                                 | Description                                                                                                                                                                  |
   +===================+===========================================================================================================================================+===============================================================================================================+==============================================================================================================================================================================+
   | Propagated routes | Propagated routes are routes that attachments propagate to the route tables of the enterprise router. They cannot be modified or deleted. | To create a propagation, see :ref:`Creating a Propagation for an Attachment in the Route Table <er_01_0036>`. | Routes are classified into propagated routes and static routes. The routes shown in :ref:`Figure 1 <er_01_0040__fig2088721517588>` are described as follows:                 |
   |                   |                                                                                                                                           |                                                                                                               |                                                                                                                                                                              |
   |                   |                                                                                                                                           |                                                                                                               | -  Propagated routes are from:                                                                                                                                               |
   |                   |                                                                                                                                           |                                                                                                               |                                                                                                                                                                              |
   |                   |                                                                                                                                           |                                                                                                               |    -  Propagations automatically created in the default route table of the enterprise router for attachments, such as VPC 1, VPC 2, and virtual gateway 1 attachments.       |
   |                   |                                                                                                                                           |                                                                                                               |    -  Propagations manually created in the custom route table of the enterprise router for attachments, such as VPC 1, virtual gateway 1, and virtual gateway 2 attachments. |
   |                   |                                                                                                                                           |                                                                                                               |                                                                                                                                                                              |
   |                   |                                                                                                                                           |                                                                                                               | -  Static routes are manually added to the custom route table of the enterprise router for attachments, such as VPC 3 and VPC 4 attachments.                                 |
   +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Static routes     | Static routes are manually created and can be modified or deleted.                                                                        | To create a route, see :ref:`Creating a Static Route <er_01_0041>`.                                           |                                                                                                                                                                              |
   +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Route Priority
--------------

If there are multiple routes with the same destination but different targets in a route table, the route priority is as follows:

Static route > propagated route for VPC attachment > propagated route for virtual gateway attachment route

.. note::

   -  Static routes are manually configured and the destination of each static route must be unique in a route table.
   -  Propagated routes are automatically learned by the system and may have the same destination in a route table.
   -  A static route and a propagated route may have the same destination in a route table.

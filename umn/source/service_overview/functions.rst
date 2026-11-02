:original_name: er_01_0005.html

.. _er_01_0005:

Functions
=========

Enterprise Routers
------------------

An enterprise router is a high-performance centralized router that supports route learning. When creating an enterprise router, you can set parameters such as its region, AZ, and name.

After an enterprise router is created, you can still change its parameters based on service requirements.

For more information, see :ref:`Creating an Enterprise Router <er_01_0069>`.

Attachments
-----------

You can attach network instances to the enterprise router.

Network instances are attached to the enterprise router in different ways.

-  VPCs are attached to the enterprise router on the Enterprise Router console.
-  Virtual gateways are attached through the Direct Connect console.
-  VPN gateways are attached through the VPN console.
-  CFW instances are created on the Cloud Firewall console.

For more information, see :ref:`Attachment Overview <er_01_0019>`.

Route Tables
------------

Route tables are used by enterprise routers to forward packets. Route tables contain associations, propagations, and routes.

An enterprise router can have multiple route tables. You can associate attachments with different route tables to enable communication or isolation between network instances.

For more information, see :ref:`Route Table Overview <er_01_0024>`.

Associations
------------

Associations are created manually or automatically to associate attachments with enterprise router route tables.

-  Manually: You need to select a route table and create an association in the route table for an attachment.
-  Automatically: You just need to enable **Default Route Table Association** and specify the default route table. The system automatically creates an association for an attachment in the default route table.

For more information, see :ref:`Association Overview <er_01_0030>`.

Propagations
------------

A propagation is created manually or automatically to enable an enterprise router to learn the routes to an associated attachment.

-  Manually: You need to select a route table and create a propagation for an attachment in the route table.
-  Automatically: You just need to enable **Default Route Table Propagation** and specify the default route table. The system automatically creates a propagation in the default route table for an attachment.

For more information, see :ref:`Propagation Overview <er_01_0035>`.

Routes
------

A route consists of information such as the destination address, next hop, and route type. There are two types of routes:

-  Propagated routes
-  Static routes

Enterprise routers support both IPv4 and IPv6 routes.

.. note::

   IPv6 is not applicable in **eu-nl**.

For more information, see :ref:`Route Overview <er_01_0040>`.

Sharing
-------

You are the owner of the enterprise router, and other accounts are the users of your enterprise router.

After you share your enterprise router with other accounts, these other users can attach their network instances to your enterprise router, so that their network instances can access your enterprise router.

This allows VPCs in the same region but different accounts to be attached to the same enterprise router.

For more information, see :ref:`Sharing Overview <er_01_0095>`.

Flow Logs
---------

A flow log records traffic of attachments on enterprise routers in real time. These logs allow you to monitor the network traffic of attachments and analyze network attacks, improving the O&M efficiency.

Flow logs can capture traffic of the following types of attachments:

-  A VPC attachment indicates that a VPC is attached to an enterprise router. Flow logs can collect the traffic between the VPC and other attachments of the enterprise router.
-  A virtual gateway attachment indicates that a Direct Connect virtual gateway is attached to an enterprise router. Flow logs can collect the traffic between the on-premises data center and the cloud connected by Direct Connect.
-  A VPN gateway attachment indicates that a VPN gateway is attached to an enterprise router. Flow logs can collect the traffic between the on-premises data center and the cloud connected by VPN.

For more information, see :ref:`Flow Log Overview <er_01_0108>`.

Monitoring
----------

You can use Cloud Eye to monitor the network status of enterprise routers and their attachments.

For more information, see :ref:`Supported Metrics <er_01_0103>`.

Auditing
--------

You can use Cloud Trace Service (CTS) to record operations associated with your enterprise routers for future query, audit, and backtracking.

For more information, see :ref:`Key Operations Recorded by CTS <er_01_0091>`.

Tags
----

Tags are used to identify cloud resources for purposes of easy categorization and quick search. You can add tags to enterprise routers, attachments, and route tables.

For more information, see :ref:`Overview <er_01_0049>`.

Quotas
------

Quotas can limit the number or capacity of resources available to users, for example, how many enterprise routers can be created, how many attachments can be created for each enterprise router, and how many routes can be added to each route table. You can request a quota increase if your existing quota cannot meet your service requirements.

For more information, see :ref:`Overview <er_01_0056>`.

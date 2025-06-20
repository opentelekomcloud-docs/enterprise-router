:original_name: er_01_0006.html

.. _er_01_0006:

Notes and Constraints
=====================

Specifications
--------------

:ref:`Table 1 <er_01_0006__table591864733813>` lists the specifications of the enterprise router.

.. _er_01_0006__table591864733813:

.. table:: **Table 1** Enterprise router specifications

   +--------------------------------------------------------------------------+-----------------+---------------------------+
   | Item                                                                     | Default Setting | Adjustable                |
   +==========================================================================+=================+===========================+
   | Maximum number of enterprise routers that can be created by each account | 1               | Contact customer service. |
   +--------------------------------------------------------------------------+-----------------+---------------------------+
   | Maximum forwarding capability supported by each enterprise router        | 100 Gbit/s      | Contact customer service. |
   +--------------------------------------------------------------------------+-----------------+---------------------------+

Constraints
-----------

-  Enterprise routers cannot be used together with virtual IP addresses of VPCs. If virtual IP addresses are used, contact customer service.

-  Traffic cannot be forwarded from a VPC to its attached enterprise router if the destination of a route with an enterprise router as the next hop is set to 0.0.0.0/0 in the VPC route table and if:

   -  An ECS in the VPC has an EIP bound.
   -  The VPC is being used by ELB, NAT Gateway, VPC Endpoint, or Distributed Cache Service (DCS).

   To solve this problem, refer to :ref:`Why Traffic Can't Be Forwarded from a VPC with a Route Destination of 0.0.0.0/0 to Its Enterprise Router? <er_01_0121>`

-  The VPC route table does not allow you to add a route whose destination address is 100.64.x.x and next hop is an enterprise router.

   To solve this problem, refer to :ref:`How Do I Route Traffic to 100.64.x.x Through an Enterprise Router? <er_01_0122>`

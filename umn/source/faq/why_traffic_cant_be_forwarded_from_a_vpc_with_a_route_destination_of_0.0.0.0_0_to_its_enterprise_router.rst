:original_name: er_01_0121.html

.. _er_01_0121:

Why Traffic Can't Be Forwarded from a VPC with a Route Destination of 0.0.0.0/0 to Its Enterprise Router?
=========================================================================================================

Scenarios
---------

Traffic cannot be forwarded from a VPC to the enterprise router that the VPC is attached to if you set the destination of a route to 0.0.0.0/0 in the VPC route table and:

-  An ECS in the VPC has an EIP bound.

   .. note::

      Refer to solution 1.

-  ELB, NAT Gateway, VPC Endpoint and DCS are deployed in the VPC.

   .. note::

      Refer to solution 1 or solution 2.

      When method 2 is used, if a VPC wants to access public network, the traffic from the VPC is forwarded to the enterprise router and then to the public network. For this reason, if a VPC accesses the public network using an EIP, do not use this method.

Solutions
---------

Select a solution based on your actual service scenario.

-  Solution 1: Change the destination (0.0.0.0/0) of the default route to a specific IP address range, for example, 192.168.0.0/16.
-  Solution 2: Add eight routes with specific IP address ranges as the destination to replace the default route (with a destination of 0.0.0.0/0).

   .. table:: **Table 1** Route destinations and next hops

      =========== =================
      Destination Next Hop
      =========== =================
      128.0.0.0/1 Enterprise router
      64.0.0.0/2  Enterprise router
      32.0.0.0/3  Enterprise router
      16.0.0.0/4  Enterprise router
      8.0.0.0/5   Enterprise router
      4.0.0.0/6   Enterprise router
      2.0.0.0/7   Enterprise router
      1.0.0.0/8   Enterprise router
      =========== =================

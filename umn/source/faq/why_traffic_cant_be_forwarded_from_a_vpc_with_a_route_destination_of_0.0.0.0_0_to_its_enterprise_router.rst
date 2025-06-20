:original_name: er_01_0121.html

.. _er_01_0121:

Why Traffic Can't Be Forwarded from a VPC with a Route Destination of 0.0.0.0/0 to Its Enterprise Router?
=========================================================================================================

Scenarios
---------

Traffic cannot be forwarded from a VPC to its attached enterprise router if the destination of a route with an enterprise router as the next hop is set to 0.0.0.0/0 in the VPC route table and if:

-  An ECS in the VPC has an EIP bound.

   .. note::

      Refer to solution 1.

-  The VPC has ELB, NAT Gateway, VPCEP, or DCS deployed.

   .. note::

      Refer to solution 1 or solution 2.

      In solution 2, VPC traffic to the public network is routed through the enterprise router. Therefore, do not use this solution if the VPC uses an EIP for public network access.

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

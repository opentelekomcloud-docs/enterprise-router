:original_name: er_01_0065.html

.. _er_01_0065:

Step 3: (Optional) Create VPCs and ECSs
=======================================

Scenarios
---------

This section describes how to create VPCs and ECSs.

If you already have VPCs and ECS, skip this section.

Notes and Constraints
---------------------

-  The CIDR blocks of the VPCs to be connected cannot overlap with each other.

   In this example, the CIDR blocks of the VPCs are propagated to the enterprise router route table as the destination in routes. The CIDR blocks cannot be modified and overlapping CIDR blocks may cause route conflicts.

   If your existing VPCs have overlapping CIDR blocks, do not use propagated routes. Instead, you need to manually add static routes to the route table of the enterprise router. The destination can be VPC subnet CIDR blocks or smaller ones.

-  Four ECSs must be in the same security group. If your ECSs are in different security groups, add rules to their security groups to allow access to each other.

Procedure
---------

#. Create four VPCs with subnets.

   For details, see "Creating a VPC" in the *Virtual Private Cloud User Guide*.

   For VPC and subnet details in this example, see :ref:`Table 6 <er_01_0063__table195012516413>`.

#. Create four ECSs.

   For details, see "Creating an ECS" in the *Elastic Cloud Server User Guide*.

   For ECS details in this example, see :ref:`Table 7 <er_01_0063__table154151647412>`.

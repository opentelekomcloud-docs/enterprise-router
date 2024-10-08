:original_name: er_01_0129.html

.. _er_01_0129:

Selecting a Networking Scheme
=============================

You can use enterprise routers to build a central network and to simplify the network architecture. There are two typical schemes to use Enterprise Router together with Direct Connect to allow an on-premises data center to access multiple VPCs.

.. _er_01_0129__fig16662957112716:

.. figure:: /_static/images/en-us_image_0000001557627546.png
   :alt: **Figure 1** Networking for allowing an on-premises data center to access two service VPCs directly (scheme 1)

   **Figure 1** Networking for allowing an on-premises data center to access two service VPCs directly (scheme 1)

.. _er_01_0129__fig536751734919:

.. figure:: /_static/images/en-us_image_0000001607947069.png
   :alt: **Figure 2** Networking for allowing an on-premises data center to access two service VPCs over a transit VPC (scheme 2)

   **Figure 2** Networking for allowing an on-premises data center to access two service VPCs over a transit VPC (scheme 2)

.. table:: **Table 1** Comparison between the two schemes

   +-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | Scheme          | Networking Architecture                                                                                                                                                                                                       | Network Path Description                                                                                                                                           | Remarks                                                                                           |
   +=================+===============================================================================================================================================================================================================================+====================================================================================================================================================================+===================================================================================================+
   | Scheme 1        | In :ref:`Figure 1 <er_01_0129__fig16662957112716>`:                                                                                                                                                                           | -  The enterprise router enables the two VPCs to communicate with each other.                                                                                      | For details, see :ref:`How Do I Select a Networking Scheme? <er_01_0129__section125661717185015>` |
   |                 |                                                                                                                                                                                                                               | -  Direct Connect enables the on-premises data center to access the cloud, and the enterprise router connects the on-premises data center to both VPCs.            |                                                                                                   |
   |                 | Two service VPCs (VPC-A and VPC-B) and the Direct Connect virtual gateway are attached to an enterprise router.                                                                                                               |                                                                                                                                                                    |                                                                                                   |
   +-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | Scheme 2        | In :ref:`Figure 2 <er_01_0129__fig536751734919>`:                                                                                                                                                                             | -  Each service VPC is connected to the transit VPC over a VPC peering connection.                                                                                 |                                                                                                   |
   |                 |                                                                                                                                                                                                                               | -  Direct Connect enables the on-premises data center to access the cloud, and the enterprise router connects the on-premises data center to the two service VPCs. |                                                                                                   |
   |                 | The two service VPCs (VPC-A and VPC-B) are not attached to the enterprise router. Instead, a transit VPC (VPC-Transit) is used. The transit VPC and the Direct Connect virtual gateway are attached to the enterprise router. |                                                                                                                                                                    |                                                                                                   |
   +-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+

.. _er_01_0129__section125661717185015:

How Do I Select a Networking Scheme?
------------------------------------

In scheme 1, the service VPCs are directly attached to the enterprise router. In scheme 2, a transit VPC is used and attached to the enterprise router. Each service VPC is connected to the transit VPC over a VPC peering connection. Compared with scheme 1, scheme 2 costs less and eliminates some constraints, as detailed below:

-  Scheme 2 frees you from the following constraints that scheme 1 has on attaching service VPCs to an enterprise router:

   -  If a service VPC is used by ELB, VPC Endpoint, NAT Gateway (private NAT gateways), or DCS, contact customer service to confirm the service compatibility and preferentially use a transit VPC for networking.
   -  Traffic cannot be forwarded from a VPC to the enterprise router if you set the destination of a route to 0.0.0.0/0 in the VPC route table and:

      -  An ECS in the VPC has an EIP bound.
      -  The VPC is being used by ELB (either dedicated or shared load balancers), NAT Gateway, VPC Endpoint, and DCS.

.. important::

   If you still want to use scheme 1 to attach service VPCs to an enterprise router, contact customer service to evaluate the feasibility.

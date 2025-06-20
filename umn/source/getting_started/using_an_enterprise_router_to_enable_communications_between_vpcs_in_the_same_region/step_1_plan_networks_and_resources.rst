:original_name: er_01_0063.html

.. _er_01_0063:

Step 1: Plan Networks and Resources
===================================

To use an enterprise router to connect VPCs in the same region, you need to:

-  :ref:`Network Planning <er_01_0063__section2162184314336>`: Plan CIDR blocks of VPCs and subnets, and route tables of VPCs and the enterprise router.
-  :ref:`Resource Planning <er_01_0063__section94881859164511>`: Plan the quantity, names, and parameters of cloud resources, including VPCs, ECSs, and the enterprise router.

.. _er_01_0063__section2162184314336:

Network Planning
----------------

:ref:`Figure 1 <er_01_0063__fig121911186551>` and :ref:`Table 2 <er_01_0063__table350914311846>` show the network planning and its description for communications among VPCs in the same region.

.. _er_01_0063__fig121911186551:

.. figure:: /_static/images/en-us_image_0000001193598903.png
   :alt: **Figure 1** Network planning for communications among VPCs in the same region

   **Figure 1** Network planning for communications among VPCs in the same region

.. table:: **Table 1** Network traffic flows

   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Scenario                          | Description                                                                                                                                                          |
   +===================================+======================================================================================================================================================================+
   | Request from VPC 1 to VPC 3       | #. The route table of VPC 1 has a route with next hop set to the enterprise router to forward traffic from VPC 1 to the enterprise router.                           |
   |                                   | #. The route table of the enterprise router has a propagated route with next hop set to the VPC 3 attachment to forward traffic from the enterprise router to VPC 3. |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Response from VPC 3 to VPC 1      | #. The route table of VPC 3 has a route with next hop set to the enterprise router to forward traffic from VPC 3 to the enterprise router.                           |
   |                                   | #. The route table of the enterprise router has a propagated route with next hop set to the VPC 1 attachment to forward traffic from the enterprise router to VPC 1. |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _er_01_0063__table350914311846:

.. table:: **Table 2** Network planning for communications among VPCs in the same region

   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Resource                          | Description                                                                                                                                                                                                                                          |
   +===================================+======================================================================================================================================================================================================================================================+
   | VPC                               | -  The CIDR blocks of the VPCs to be connected cannot overlap with each other.                                                                                                                                                                       |
   |                                   |                                                                                                                                                                                                                                                      |
   |                                   |    In this example, the CIDR blocks of the VPCs are propagated to the enterprise router route table as the destination in routes. The CIDR blocks cannot be modified and overlapping CIDR blocks may cause route conflicts.                          |
   |                                   |                                                                                                                                                                                                                                                      |
   |                                   |    If your existing VPCs have overlapping CIDR blocks, do not use propagated routes. Instead, you need to manually add static routes to the route table of the enterprise router. The destination can be VPC subnet CIDR blocks or smaller ones.     |
   |                                   |                                                                                                                                                                                                                                                      |
   |                                   | -  Each VPC has a default route table.                                                                                                                                                                                                               |
   |                                   |                                                                                                                                                                                                                                                      |
   |                                   | -  Routes in the default route table can be:                                                                                                                                                                                                         |
   |                                   |                                                                                                                                                                                                                                                      |
   |                                   |    -  Local: a system route for communications between subnets in a VPC.                                                                                                                                                                             |
   |                                   |    -  Enterprise router: custom routes with 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16 as the destinations for routing traffic from a VPC subnet to the enterprise router. See :ref:`Table 3 <er_01_0063__table5325182820514>` for route details. |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Enterprise router                 | After **Default Route Table Association** and **Default Route Table Propagation** are enabled and a VPC attachment is created, the system will automatically:                                                                                        |
   |                                   |                                                                                                                                                                                                                                                      |
   |                                   | -  Associate VPC attachments with the default route table of the enterprise router.                                                                                                                                                                  |
   |                                   | -  Propagate VPC attachments with the default route table of the enterprise router. The route table automatically learns the VPC CIDR block as the destination of routes. For details, see :ref:`Table 4 <er_01_0063__table4211920161010>`.          |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ECS                               | The four ECSs are in different VPCs. If the ECSs are associated with different security groups, add rules to their security groups to allow access to each other.                                                                                    |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _er_01_0063__table5325182820514:

.. table:: **Table 3** VPC route table

   ============== ================= =====================
   Destination    Next Hop          Route Type
   ============== ================= =====================
   10.0.0.0/8     Enterprise Router Static route (custom)
   172.16.0.0/12  Enterprise Router Static route (custom)
   192.168.0.0/16 Enterprise Router Static route (custom)
   ============== ================= =====================

.. note::

   -  If you enable **Auto Add Routes** when creating a VPC attachment, you do not need to manually add static routes to the VPC route table. Instead, the system automatically adds routes (with this enterprise router as the next hop and 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16 as the destinations) to all route tables of the VPC.
   -  If an existing route in the VPC route tables has a destination to 10.0.0.0/8, 172.16.0.0/12, or 192.168.0.0/16, the routes will fail to be added. In this case, do not enable **Auto Add Routes**. After the attachment is created, manually add routes.
   -  Do not set the destination of a route (with an enterprise router as the next hop) to 0.0.0.0/0 in the VPC route table. If an ECS in the VPC has an EIP bound, the VPC route table will have a policy-based route with 0.0.0.0/0 as the destination, which has a higher priority than the route with the enterprise router as the next hop. In this case, traffic is forwarded to the EIP and cannot reach the enterprise router.

.. _er_01_0063__table4211920161010:

.. table:: **Table 4** Enterprise router route table

   +----------------------------------+--------------------------------+------------------+
   | Destination                      | Next Hop                       | Route Type       |
   +==================================+================================+==================+
   | VPC 1 CIDR block: 192.168.0.0/16 | VPC 1 attachment: er-attach-01 | Propagated route |
   +----------------------------------+--------------------------------+------------------+
   | VPC 2 CIDR block: 172.16.0.0/16  | VPC 2 attachment: er-attach-02 | Propagated route |
   +----------------------------------+--------------------------------+------------------+
   | VPC 3 CIDR block: 10.1.0.0/16    | VPC 3 attachment: er-attach-03 | Propagated route |
   +----------------------------------+--------------------------------+------------------+
   | VPC 4 CIDR block: 10.2.0.0/16    | VPC 4 attachment: er-attach-04 | Propagated route |
   +----------------------------------+--------------------------------+------------------+

.. _er_01_0063__section94881859164511:

Resource Planning
-----------------

The enterprise router, VPCs, and ECSs must be in the same region. You can select any AZ within the region.

.. note::

   The following resource details are only examples. You can modify them as required.

-  One enterprise router

   .. table:: **Table 5** Enterprise router details

      +------------------------+-------+---------------------------------+---------------------------------+-------------------------+-------------------------+--------------+
      | Enterprise Router Name | ASN   | Default Route Table Association | Default Route Table Propagation | Association Route Table | Propagation Route Table | Attachment   |
      +========================+=======+=================================+=================================+=========================+=========================+==============+
      | er-test-01             | 64800 | Enable                          | Enable                          | Default route table     | Default route table     | er-attach-01 |
      +------------------------+-------+---------------------------------+---------------------------------+-------------------------+-------------------------+--------------+
      |                        |       |                                 |                                 |                         |                         | er-attach-02 |
      +------------------------+-------+---------------------------------+---------------------------------+-------------------------+-------------------------+--------------+
      |                        |       |                                 |                                 |                         |                         | er-attach-03 |
      +------------------------+-------+---------------------------------+---------------------------------+-------------------------+-------------------------+--------------+
      |                        |       |                                 |                                 |                         |                         | er-attach-04 |
      +------------------------+-------+---------------------------------+---------------------------------+-------------------------+-------------------------+--------------+

-  Four VPCs, each with a unique CIDR block

   .. _er_01_0063__table195012516413:

   .. table:: **Table 6** VPC details

      +-------------+----------------+----------------+-------------------+-------------------------+
      | VPC Name    | VPC CIDR Block | Subnet Name    | Subnet CIDR Block | Association Route Table |
      +=============+================+================+===================+=========================+
      | vpc-demo-01 | 192.168.0.0/16 | subnet-demo-01 | 192.168.1.0/24    | Default route table     |
      +-------------+----------------+----------------+-------------------+-------------------------+
      | vpc-demo-02 | 172.16.0.0/16  | subnet-demo-02 | 172.16.1.0/24     | Default route table     |
      +-------------+----------------+----------------+-------------------+-------------------------+
      | vpc-demo-03 | 10.1.0.0/16    | subnet-demo-03 | 10.1.1.0/24       | Default route table     |
      +-------------+----------------+----------------+-------------------+-------------------------+
      | vpc-demo-04 | 10.2.0.0/16    | subnet-demo-04 | 10.2.1.0/24       | Default route table     |
      +-------------+----------------+----------------+-------------------+-------------------------+

-  An ECS in each VPC, a total of four ECSs

   .. _er_01_0063__table154151647412:

   .. table:: **Table 7** ECS details

      +-------------+---------------+-------------+----------------+--------------------------------------+--------------------+
      | ECS         | Image         | VPC         | Subnet         | Security Group                       | Private IP Address |
      +=============+===============+=============+================+======================================+====================+
      | ecs-demo-01 | Public image: | vpc-demo-01 | subnet-demo-01 | sg-demo (general-purpose web server) | 192.168.1.12       |
      |             |               |             |                |                                      |                    |
      |             | EulerOS 2.5 6 |             |                |                                      |                    |
      +-------------+---------------+-------------+----------------+--------------------------------------+--------------------+
      | ecs-demo-02 |               | vpc-demo-02 | subnet-demo-02 |                                      | 172.16.1.189       |
      +-------------+---------------+-------------+----------------+--------------------------------------+--------------------+
      | ecs-demo-03 |               | vpc-demo-03 | subnet-demo-03 |                                      | 10.1.1.105         |
      +-------------+---------------+-------------+----------------+--------------------------------------+--------------------+
      | ecs-demo-04 |               | vpc-demo-04 | subnet-demo-04 |                                      | 10.2.1.83          |
      +-------------+---------------+-------------+----------------+--------------------------------------+--------------------+

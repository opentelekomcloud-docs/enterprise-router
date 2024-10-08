:original_name: er_01_0068.html

.. _er_01_0068:

Step 6: Verify Connectivity Among VPCs
======================================

Perform the following operations to log in to each ECS and verify the network connectivity between VPCs:

Procedure
---------

#. .. _er_01_0068__li154091419132410:

   Log in to an ECS.

#. .. _er_01_0068__li105742451915:

   Run the following command on the ECS:

   **ping** *IP address of the ECS*

   If you log in to ecs-demo-01 to verify the connectivity between vpc-demo-01 and vpc-demo-02, run the following command:

   **ping 10.1.1.105**

   If information similar to the following is displayed, the two VPCs can communicate with each other.

   |image1|

#. Repeat :ref:`1 <er_01_0068__li154091419132410>` to :ref:`2 <er_01_0068__li105742451915>` to verify the connectivity between other VPCs.

.. |image1| image:: /_static/images/en-us_image_0000001195294363.png

:original_name: er_01_0030.html

.. _er_01_0030:

Association Overview
====================

Each attachment can be associated with one route table for:

-  Packet forwarding: Packets from the attachment are forwarded through the routes specified in the associated route table.
-  Route propagation: The routes in the associated route tables are automatically propagated to the route table of the attachment.

.. _er_01_0030__fig13563243183610:

.. figure:: /_static/images/en-us_image_0000001477452077.png
   :alt: **Figure 1** Associations

   **Figure 1** Associations

.. table:: **Table 1** Association description

   +-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Attachment Type | Route Learning  | Way to Create Association                                                                                                                                                                                                          | Description                                                                                                                                                                           |
   +=================+=================+====================================================================================================================================================================================================================================+=======================================================================================================================================================================================+
   | VPC             | Not supported   | -  Auto creation: If **Default Route Table Association** is enabled and the default association route table is specified, attachments are automatically associated with the default association route table.                       | Each attachment can only be associated with one route table. Associations between attachments in :ref:`Figure 1 <er_01_0030__fig13563243183610>` are described as follows:            |
   |                 |                 |                                                                                                                                                                                                                                    |                                                                                                                                                                                       |
   |                 |                 |    -  If you want to enable this function when you create an enterprise router, refer to :ref:`Creating an Enterprise Router <er_01_0069>`.                                                                                        | -  Auto creation: The system automatically associates attachments, such as virtual gateway 1, VPC 1, and VPN gateway 1, with the default route table of the enterprise router.        |
   |                 |                 |    -  If you want to enable this function after an enterprise router is created, refer to :ref:`Modifying an Enterprise Router <er_01_0013>`.                                                                                      | -  Manual creation: You need to manually create associations in the custom route table of the enterprise router for attachments, such as VPC 2, VPN gateway 2, and virtual gateway 2. |
   |                 |                 |                                                                                                                                                                                                                                    |                                                                                                                                                                                       |
   |                 |                 | -  Manual creation: You can select a route table and create an association in it to associate an attachment with the route table. For details, see :ref:`Creating an Association for an Attachment in a Route Table <er_01_0031>`. |                                                                                                                                                                                       |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Virtual gateway | Supported       |                                                                                                                                                                                                                                    |                                                                                                                                                                                       |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPN gateway     | Supported       |                                                                                                                                                                                                                                    |                                                                                                                                                                                       |
   +-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

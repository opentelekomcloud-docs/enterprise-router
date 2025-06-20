:original_name: er_01_0095.html

.. _er_01_0095:

Sharing Overview
================

What Is Sharing?
----------------

You can share an enterprise router in your account with other accounts.

-  You are the owner of the enterprise router.
-  Other accounts are the users of the enterprise router.

After you share your enterprise router with other accounts, these other users can attach their network instances to your enterprise router, so that their network instances can access your enterprise router.

You can share an enterprise router in your account with other accounts so that these other accounts can attach their VPCs to your enterprise router.

This example uses account A, account B, and account C to describe how you can build a network using one enterprise router. :ref:`Table 1 <er_01_0095__table04706348500>` describes the resources of each account.

If account A shares enterprise router (ER-A) with account B and account C, the VPCs of accounts B and C can be attached to ER-A. :ref:`Figure 1 <er_01_0095__fig16662957112716>` shows the networking.

.. _er_01_0095__table04706348500:

.. table:: **Table 1** Accounts and their resources

   +-----------------------+-----------------------+-----------------------+
   | Account               | Enterprise Router     | VPC                   |
   +=======================+=======================+=======================+
   | A                     | ER-A                  | VPC-A-01              |
   |                       |                       |                       |
   |                       |                       | VPC-A-02              |
   +-----------------------+-----------------------+-----------------------+
   | B                     | ER-B                  | VPC-B-01              |
   +-----------------------+-----------------------+-----------------------+
   | C                     | ER-C                  | VPC-C-01              |
   +-----------------------+-----------------------+-----------------------+

.. _er_01_0095__fig16662957112716:

.. figure:: /_static/images/en-us_image_0000001399653186.png
   :alt: **Figure 1** Attaching VPCs in different accounts to the same enterprise router

   **Figure 1** Attaching VPCs in different accounts to the same enterprise router

Allowed Operations by the Owner and Other Users
-----------------------------------------------

The owner can perform all operations but these other users can perform only some of the operations. :ref:`Table 2 <er_01_0095__table168733271489>` lists the operations that other users can perform.

.. _er_01_0095__table168733271489:

.. table:: **Table 2** Allowed operations by other users

   +-----------------------------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Role                        | Allowed Operation                                                    | Description                                                                                                                                                                                       |
   +=============================+======================================================================+===================================================================================================================================================================================================+
   | Other users (user accounts) | :ref:`Viewing an Enterprise Router <er_01_0016>`                     | Other users can view:                                                                                                                                                                             |
   |                             |                                                                      |                                                                                                                                                                                                   |
   |                             |                                                                      | The name of the shared enterprise router followed by **Shared with me**.                                                                                                                          |
   +-----------------------------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                             | Adding attachments to an enterprise router                           | Other users:                                                                                                                                                                                      |
   |                             |                                                                      |                                                                                                                                                                                                   |
   |                             | :ref:`Creating a VPC Attachment <er_01_0070>`                        | -  Can only create VPC attachments.                                                                                                                                                               |
   |                             |                                                                      |                                                                                                                                                                                                   |
   |                             |                                                                      | -  Can create attachments to the shared enterprise router only after the owner account accepts the attachment requests.                                                                           |
   |                             |                                                                      |                                                                                                                                                                                                   |
   |                             |                                                                      |    If **Auto Accept Shared Attachments** is enabled, a request from a user for creating an attachment will be automatically accepted.                                                             |
   |                             |                                                                      |                                                                                                                                                                                                   |
   |                             |                                                                      | -  Cannot add tags to their created attachments to the shared enterprise router.                                                                                                                  |
   |                             |                                                                      |                                                                                                                                                                                                   |
   |                             |                                                                      | For details about the process for creating an attachment for an enterprise router in another account, see :ref:`Sharing an Enterprise Router with Other Users <er_01_0095__section169164232367>`. |
   +-----------------------------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                             | :ref:`Viewing an Attachment <er_01_0021>`                            | Other users:                                                                                                                                                                                      |
   |                             |                                                                      |                                                                                                                                                                                                   |
   |                             |                                                                      | Cannot view the tags added of their attachments.                                                                                                                                                  |
   +-----------------------------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                             | :ref:`Modifying the Basic Information of an Attachment <er_01_0093>` | Other users can change the names of their attachments created for the shared enterprise router.                                                                                                   |
   +-----------------------------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                             | :ref:`Deleting a VPC Attachment <er_01_0072>`                        | Other users can delete their attachments created for the shared enterprise router without the approval of the owner account.                                                                      |
   +-----------------------------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. note::

   Other users cannot view the **Route Tables**, **Sharing**, **Flow Logs**, and **Tags** tabs of the enterprise router.

.. _er_01_0095__section169164232367:

Sharing an Enterprise Router with Other Users
---------------------------------------------

As the owner, you can share your enterprise router with other users. These other users can create attachments for your enterprise router.

-  If **Auto Accept Shared Attachments** is not enabled on your enterprise router, you must accept the attachment creation requests from other users.


   .. figure:: /_static/images/en-us_image_0000001213710098.png
      :alt: **Figure 2** Accepting or rejecting attachment creation requests

      **Figure 2** Accepting or rejecting attachment creation requests

   .. _er_01_0095__table16962125143812:

   .. table:: **Table 3** Process description

      +-----------------+--------------------------------------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | No.             | Step                                                   | Role            | Description                                                                                                                                                                                                                                   |
      +=================+========================================================+=================+===============================================================================================================================================================================================================================================+
      | 1               | :ref:`Creating a Sharing <er_01_0096>`                 | Owner           | The owner creates a sharing to share an enterprise router with another user. This user can easily identify the shared enterprise router because its name is followed by **Shared with me**.                                                   |
      +-----------------+--------------------------------------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | 2               | :ref:`Creating a VPC Attachment <er_01_0070>`          | User            | The user creates an attachment to the shared enterprise router. The attachment will be in the **Pending acceptance** state because **Auto Accept Shared Attachments** is disabled on the enterprise router.                                   |
      +-----------------+--------------------------------------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | 3               | -  :ref:`Accepting an Attachment Request <er_01_0099>` | Owner           | -  The owner accepts the attachment request. The attachment status changes from **Pending acceptance** to **Creating**.                                                                                                                       |
      |                 | -  :ref:`Rejecting an Attachment Request <er_01_0100>` |                 |                                                                                                                                                                                                                                               |
      |                 |                                                        |                 |    -  When the attachment status changes to **Normal**, the attachment is successfully created.                                                                                                                                               |
      |                 |                                                        |                 |    -  When the attachment status changes to **Failed**, the attachment fails to be created. Contact customer service.                                                                                                                         |
      |                 |                                                        |                 |                                                                                                                                                                                                                                               |
      |                 |                                                        |                 |    After an attachment is created, you can perform :ref:`Follow-up Procedure <er_01_0070__section582517444316>`.                                                                                                                              |
      |                 |                                                        |                 |                                                                                                                                                                                                                                               |
      |                 |                                                        |                 | -  The owner can also reject the attachment request. If the owner rejects the request, the attachment status changes from **Pending acceptance** to **Rejected**, and the attachment fails to be created. If this happens, contact the owner. |
      +-----------------+--------------------------------------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  If **Auto Accept Shared Attachments** is enabled on an enterprise router, the other users' requests to create attachments to this enterprise router will be automatically accepted without the approval from the owner.


   .. figure:: /_static/images/en-us_image_0000001213710140.png
      :alt: **Figure 3** Attachment requests automatically accepted

      **Figure 3** Attachment requests automatically accepted

   .. table:: **Table 4** Process description

      +-----------------+-----------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | No.             | Step                                          | Role            | Description                                                                                                                                                                                 |
      +=================+===============================================+=================+=============================================================================================================================================================================================+
      | 1               | :ref:`Creating a Sharing <er_01_0096>`        | Owner           | The owner creates a sharing to share an enterprise router with another user. This user can easily identify the shared enterprise router because its name is followed by **Shared with me**. |
      +-----------------+-----------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | 2               | :ref:`Creating a VPC Attachment <er_01_0070>` | User account    | **Auto Accept Shared Attachments** is enabled on the enterprise router.                                                                                                                     |
      |                 |                                               |                 |                                                                                                                                                                                             |
      |                 |                                               |                 | The user creates an attachment to the shared enterprise router. The attachment will be in the **Creating** state.                                                                           |
      |                 |                                               |                 |                                                                                                                                                                                             |
      |                 |                                               |                 | -  When the attachment status changes to **Normal**, the attachment is successfully created.                                                                                                |
      |                 |                                               |                 | -  When the attachment status changes to **Failed**, the attachment fails to be created. Contact customer service.                                                                          |
      +-----------------+-----------------------------------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

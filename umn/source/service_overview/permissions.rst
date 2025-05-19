:original_name: er_01_0008.html

.. _er_01_0008:

Permissions
===========

If you need to assign different permissions to employees in your enterprise to control their access to your cloud resources, you can use Identity and Access Management (IAM) for fine-grained permissions management. IAM provides functions such as identity authentication, permissions management, and access control.

On the IAM console, you can create IAM users and assign permissions to control their access to specific resources. For example, you can create IAM users for software developers and assign permissions to allow them to use enterprise router resources but disallow them from performing any high-risk operations such as deleting such resources.

IAM is free of charge.

For more information, see `IAM Service Overview <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/what_is_iam.html#iam-01-0026>`__.

Enterprise Router Permissions
-----------------------------

By default, new IAM users do not have any permissions assigned. You need to add them to one or more groups and attach policies or roles to these groups so that these users can inherit permissions from the groups and perform specified operations on cloud services.

An enterprise router is a project-level service deployed in a specific region. You need to select a project for which the permissions will be granted. If you select **All projects**, the permissions will be granted for all the projects. You need to switch to the authorized region before accessing an enterprise router.

:ref:`Table 1 <er_01_0008__table8486434381>` lists all the system-defined policies on enterprise routers.

.. _er_01_0008__table8486434381:

.. table:: **Table 1** System-defined policies on enterprise routers

   +-------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+------------+
   | System Policy     | Description                                                                                                                            | Type                  | Dependency |
   +===================+========================================================================================================================================+=======================+============+
   | ER FullAccess     | Administrator permissions for enterprise routers. Users with such permissions can operate and use all resources on enterprise routers. | System-defined policy | None       |
   +-------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+------------+
   | ER ReadOnlyAccess | Read-only permissions for enterprise routers. Users with such permissions can only view data on enterprise routers.                    | System-defined policy | None       |
   +-------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+------------+

.. note::

   Currently, permissions cannot be configured for shared enterprise routers.

:ref:`Table 2 <er_01_0008__table12985122891519>` lists the common operations supported by each system-defined policy. You can select a proper one as required.

.. _er_01_0008__table12985122891519:

.. table:: **Table 2** Common operations supported by each system policy

   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Operation                                                    | Tenant Administrator | Tenant Guest | ER FullAccess | ER ReadOnlyAccess |
   +==============================================================+======================+==============+===============+===================+
   | Creating an enterprise router                                | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Modifying an enterprise router                               | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Viewing an enterprise router                                 | Y                    | Y            | Y             | Y                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Deleting an enterprise router                                | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Adding a Virtual Private Cloud (VPC) to an enterprise router | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Deleting a VPC attachment                                    | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Viewing attachments of all types                             | Y                    | Y            | Y             | Y                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Creating a route table                                       | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Renaming a route table                                       | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Viewing a route table                                        | Y                    | Y            | Y             | Y                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Deleting a route table                                       | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Creating an association for an attachment in a route table   | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Viewing associations in a route table                        | Y                    | Y            | Y             | Y                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Deleting an association from a route table                   | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Creating a propagation for an attachment in the route table  | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Viewing a propagation in a route table                       | Y                    | Y            | Y             | Y                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Deleting a propagation from a route table                    | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Creating a static route                                      | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Modifying a static route                                     | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Viewing a route                                              | Y                    | Y            | Y             | Y                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Deleting a static route                                      | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Creating a flow log                                          | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Viewing a VPC flow log                                       | Y                    | Y            | Y             | Y                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Disabling a flow log                                         | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Enabling a flow log                                          | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Deleting a flow log                                          | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Adding a resource tag                                        | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Modifying a resource tag                                     | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Viewing a resource tag                                       | Y                    | Y            | Y             | Y                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+
   | Deleting a resource tag                                      | Y                    | x            | Y             | x                 |
   +--------------------------------------------------------------+----------------------+--------------+---------------+-------------------+

Related Links
-------------

-  `What Is IAM? <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/what_is_iam.html#iam-01-0026>`__
-  :ref:`Creating a User and Granting Permissions <er_01_0046>`

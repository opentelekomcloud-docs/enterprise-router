:original_name: er_02_0016.html

.. _er_02_0016:

Introduction
============

This topic describes fine-grained permissions management for your Enterprise Router resources. If your account does not need individual IAM users, you may skip this topic.

By default, new IAM users do not have any permissions assigned. You need to add a user to one or more groups, and assign policies or roles to these groups. The user then inherits permissions from the groups. After authorization, the user can perform specified operations on cloud services based on the permissions.

An account has all of the permissions required to call all APIs, but IAM users must be assigned the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions can call the API successfully. For example, if an IAM user wants to query the enterprise router list using an API, the user must have been granted permissions that allow the **er:instances:list** action.

Supported Actions
-----------------

IAM provides system-defined policies that can be directly used. You can also create custom policies to work with system-defined policies for more refined access control. Actions supported by policies are specific to APIs. Common concepts related to policies include:

-  Permissions: allow or deny operations on specified resources under specific conditions.
-  APIs: REST APIs that can be called by a user who has been granted specific permissions
-  Actions: specific operations that are allowed or denied
-  Related actions: actions on which a specific action depends. When assigning permissions for the action to a user, you also need to assign permissions for the dependent actions.
-  IAM projects or enterprise projects: type of projects for which an action will take effect. For example, if you set the authorization scope of a custom policy to both IAM projects and enterprise projects, the policy takes effect for user groups in either IAM or enterprise projects. If the authorization scope is set to IAM projects only, the custom policy will take effect only for user groups in IAM projects. Administrators can check whether an action supports IAM projects or enterprise projects in the action list. "Y" indicates that the action supports the project and "x" indicates that the action does not support the project.

Enterprise Router supports the following actions that can be defined in custom policies:

-  :ref:`Enterprise Routers <er_02_0017>`
-  :ref:`VPC Attachments <er_02_0018>`
-  :ref:`Attachments <er_02_0019>`
-  :ref:`Route Tables <er_02_0020>`
-  :ref:`Associations <er_02_0021>`
-  :ref:`Propagations <er_02_0022>`
-  :ref:`Routes <er_02_0023>`
-  :ref:`Flow Logs <er_02_0024>`
-  :ref:`Tags <er_02_0033>`
-  :ref:`Quota Management <er_02_0034>`

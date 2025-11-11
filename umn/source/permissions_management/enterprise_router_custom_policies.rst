:original_name: er_01_0047.html

.. _er_01_0047:

Enterprise Router Custom Policies
=================================

Custom policies can be created to supplement system-defined policies of Enterprise Router.

You can create custom policies in either of the following ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Edit JSON policies from scratch or based on an existing policy.

For details about how to create custom policies, see `Creating a Custom Policy <https://docs.otc.t-systems.com/identity-access-management/umn/user_guide/permissions/creating_a_custom_policy.html>`__. The following are examples of common Enterprise Router custom policies.

Example Custom Policies
-----------------------

-  Example 1: Allowing users to create and delete enterprise routers

   .. code-block::

      {
              "Version": "1.1",
              "Statement": [
                      {
                              "Effect": "Allow",
                              "Action": [
                                      "er:instances:create",
                                      "er:instances:delete"
                              ]
                      }
              ]
      }

-  Example 2: Denying enterprise router deletion

   A policy with only Deny permissions must be used in conjunction with other policies to take effect. If the policies assigned to a user contain both Allow and Deny actions, the Deny actions take precedence over the Allow actions.

   The following method can be used if you need to assign the **ER FullAccess** permission to a user but also forbid the user from deleting enterprise routers. Create a custom policy for denying enterprise router deletion, and assign both policies to the group the user belongs to. Then the user can perform all operations on Enterprise Router except deleting enterprise routers. The following is an example of a deny policy:

   .. code-block::

      {
              "Version": "1.1",
              "Statement": [
                      {
                              "Effect": "Deny",
                              "Action": [
                                      "er:instances:delete"
                              ]
                      }
              ]
      }

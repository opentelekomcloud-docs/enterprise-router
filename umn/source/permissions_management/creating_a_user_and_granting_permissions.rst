:original_name: er_01_0046.html

.. _er_01_0046:

Creating a User and Granting Permissions
========================================

This section describes how to use IAM to implement fine-grained permissions control for your Enterprise Router resources. With IAM, you can:

-  Create IAM users for employees based on the organizational structure of your enterprise. Each IAM user has their own security credentials, providing access to Enterprise Router resources.
-  Grant only the minimum permissions required for users to perform a given task.
-  Entrust an account or a cloud service to perform professional and efficient O&M on your Enterprise Router resources.

If your account does not require individual IAM users, skip this topic.

:ref:`Figure 1 <er_01_0046__fig208811382017>` shows the procedure for granting permissions.

Prerequisites
-------------

You have learned about Enterprise Router permissions that can be added to the user group. For details about the system permissions supported by enterprise routers, see :ref:`Permissions <er_01_0008>`.

For the permissions of other services, see `Permission Description <https://docs.otc.t-systems.com/identity-access-management/permissions/permissions.html>`__.

Process Flow
------------

.. _er_01_0046__fig208811382017:

.. figure:: /_static/images/en-us_image_0000001208553649.png
   :alt: **Figure 1** Process for granting Enterprise Router permissions

   **Figure 1** Process for granting Enterprise Router permissions

#. .. _er_01_0046__li10176121316284:

   `Create a user group and assign permissions <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0030.html>`__.

   Create a user group on the IAM console, and assign the **ER ReadOnlyAccess** permission to the group.

#. `Create a user and add the user to the user group <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0031.html>`__.

   Create a user on the IAM console and add the user to the group created in :ref:`1 <er_01_0046__li10176121316284>`.

#. `Log in <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0032.html>`__ to the management console as the created user, switch to the authorized region, and verify that the user has only the **ER ReadOnlyAccess** permission.

   a. Click **Service List** and choose **Enterprise Router**. Then click **Create Enterprise Router** in the upper right corner. If the enterprise router fails to be created, the **ER ReadOnlyAccess** permission has taken effect.
   b. Choose any other service in the **Service List**. If a message appears indicating insufficient permissions to access the service, the **ER ReadOnlyAccess** permission has already taken effect.

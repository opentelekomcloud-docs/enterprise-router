:original_name: er_01_0049.html

.. _er_01_0049:

Overview
========

What Is a Tag?
--------------

Tags are used to identify cloud resources for purposes of easy categorization and quick search. You can add tags to enterprise routers, attachments, and route tables using either of the methods:

-  Add tags when you create an enterprise router, attachment, or route table.
-  Add tags on the details page of an existing enterprise router, attachment, or route table. You can also edit or delete tags.

Basic Knowledge About Tags
--------------------------

Tags are used to identify cloud resources. When you have many cloud resources of the same type, you can use tags to classify cloud resources by dimension (for example, use, owner, or environment).

:ref:`Figure 1 <er_01_0049__fig72351755194617>` shows how tags work. In this example, you assign two tags to each cloud resource. Each tag contains a key and a value that you define. The key of one tag is **Owner**, and the key of another tag is **Usage**. Each tag has a value.

You can quickly search for specific cloud resources based on the tags added to them. For example, you can define a set of tags for cloud resources in an account to track the owner and usage of each cloud resource, making resource management easier.

.. _er_01_0049__fig72351755194617:

.. figure:: /_static/images/en-us_image_0000001147413690.png
   :alt: **Figure 1** Example tags added for Enterprise Router

   **Figure 1** Example tags added for Enterprise Router

Constraints on Using Tags
-------------------------

-  Each tag consists of a tag key and a tag value. The rules for naming a tag key and a tag value are as follows:

   Tag key

   -  Cannot be left blank.
   -  Can contain a maximum of 36 characters.
   -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@).

   Tag value

   -  Can be left blank.
   -  Can contain a maximum of 43 characters.
   -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@).

-  Up to 20 tags can be added to a cloud resource.

-  For each resource, each tag key must be unique, and each tag key can only have one tag value.

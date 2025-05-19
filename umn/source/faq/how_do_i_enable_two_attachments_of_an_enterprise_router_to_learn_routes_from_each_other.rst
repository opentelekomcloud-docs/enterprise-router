:original_name: er_01_0123.html

.. _er_01_0123:

How Do I Enable Two Attachments of an Enterprise Router to Learn Routes from Each Other?
========================================================================================

If you want two attachments of an enterprise router to learn routes from each other, the router and each attachment must have a unique ASN. In this way, the enterprise router advertises the learned route information between the attachments.

If you want two virtual gateways attached to the same enterprise router to learn routes from each other, their ASNs must be different and can be as follows:

-  Enterprise router: 64800
-  Virtual gateway attachment A: 64513 (BGP ASN of virtual gateway A)
-  Virtual gateway attachment B: 64515 (BGP ASN of virtual gateway B)

.. note::

   VPC attachments do not support route learning.

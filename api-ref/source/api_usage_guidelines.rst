:original_name: er_02_0001.html

.. _er_02_0001:

API Usage Guidelines
====================

Public cloud APIs comply with the RESTful API design principles. REST-based web services are organized into resources. Each resource is identified by one or more Uniform Resource Identifiers (URIs). An application accesses a resource based on the resource's Unified Resource Locator (URL). A URL is usually in the following format: *https://Endpoint/uri*. In the URL, **uri** indicates the resource path, that is, the API access path.

Public cloud APIs use HTTPS as the transmission protocol. Requests/Responses are transmitted by using JSON messages, with media type represented by **application/json**.

For details about how to use APIs, see `API Usage Guidelines <https://docs.otc.t-systems.com/en-us/api/apiug/apig-en-api-180328001.html?tag=API%20Documents>`__.

Network instances can be attached to an enterprise router as its attachments. The attachment type varies depending on the network instance.


.. figure:: /_static/images/en-us_image_0000001294957952.png
   :alt: **Figure 1** Attachments

   **Figure 1** Attachments

.. table:: **Table 1** Enterprise Router attachments

   +----------------------------+-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Attachment Type            | Network Instance                  | Creating an Attachment                                                                                                                                                                                                           | Querying Attachment Details                                        | Deleting an Attachment                                                                                                                      |
   +============================+===================================+==================================================================================================================================================================================================================================+====================================================================+=============================================================================================================================================+
   | VPC attachment             | VPC                               | :ref:`Creating a VPC Attachment <createvpcattachment>`                                                                                                                                                                           | :ref:`Querying Details About a VPC Attachment <showvpcattachment>` | :ref:`Deleting a VPC Attachment <deletevpcattachment>`                                                                                      |
   +----------------------------+-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Virtual gateway attachment | Virtual gateway of Direct Connect | Create a virtual gateway by referring to `Creating a Virtual Gateway <https://docs.otc.t-systems.com/direct-connect/api-ref/apis/virtual_gateway/creating_a_virtual_gateway.html>`__ and then attach it to an enterprise router. | :ref:`Querying Details About an Attachment <showattachment>`       | `Deleting a Virtual Gateway <https://docs.otc.t-systems.com/direct-connect/api-ref/apis/virtual_gateway/deleting_a_virtual_gateway.html>`__ |
   +----------------------------+-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+

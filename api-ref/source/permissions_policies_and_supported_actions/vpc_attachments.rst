:original_name: er_02_0018.html

.. _er_02_0018:

VPC Attachments
===============

+-----------------------------------------+---------------------------------------------------------------------------------------+-----------------------+---------+--------------------+
| Permission                              | API                                                                                   | Action                | Project | Enterprise Project |
+=========================================+=======================================================================================+=======================+=========+====================+
| Creating a VPC attachment               | POST /v3/{project_id}/enterprise-router/{er_id}/vpc-attachments                       | er:attachments:create | Y       | Y                  |
+-----------------------------------------+---------------------------------------------------------------------------------------+-----------------------+---------+--------------------+
| Updating a VPC attachment               | PUT /v3/{project_id}/enterprise-router/{er_id}/vpc-attachments/{vpc_attachment_id}    | er:attachments:update | Y       | Y                  |
+-----------------------------------------+---------------------------------------------------------------------------------------+-----------------------+---------+--------------------+
| Querying details about a VPC attachment | GET /v3/{project_id}/enterprise-router/{er_id}/vpc-attachments/{vpc_attachment_id}    | er:attachments:get    | Y       | Y                  |
+-----------------------------------------+---------------------------------------------------------------------------------------+-----------------------+---------+--------------------+
| Querying the VPC attachment list        | GET /v3/{project_id}/enterprise-router/{er_id}/vpc-attachments                        | er:attachments:list   | Y       | Y                  |
+-----------------------------------------+---------------------------------------------------------------------------------------+-----------------------+---------+--------------------+
| Deleting a VPC attachment               | DELETE /v3/{project_id}/enterprise-router/{er_id}/vpc-attachments/{vpc_attachment_id} | er:attachments:delete | Y       | Y                  |
+-----------------------------------------+---------------------------------------------------------------------------------------+-----------------------+---------+--------------------+

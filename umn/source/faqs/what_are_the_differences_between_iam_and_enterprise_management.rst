:original_name: em_01_0035.html

.. _em_01_0035:

What Are the Differences Between IAM and Enterprise Management
==============================================================

Enterprise Management enables enterprises to manage cloud resources at the organization and project levels. Enterprise Management mainly provides project management, personnel management, and resource management.

Identity and Access Management (IAM) is an identity management service that provides identity authentication, permissions management, and access control.

Both IAM and Enterprise Management can be used to manage users and access permissions. However, Enterprise Management supports more fine-grained resource permissions management than IAM. Enterprise Management is recommended for medium- and large-sized enterprises.

For more information about IAM features, see *Identity and Access Management User Guide*.

Differences Between IAM and Enterprise Management
-------------------------------------------------

-  Enabling method

   -  IAM can be used free of charge immediately upon successful account registration.
   -  Enterprise Management can be used free of charge immediately upon successful account registration.

-  Resource isolation

   -  Using IAM, you can create multiple projects in a region to isolate resources and authorize users to access resources in specific projects.
   -  Using Enterprise Management, you can create enterprise projects to isolate resources across regions. Enterprise Management makes it easy to assign permissions for specific cloud resources. For example, you can add an Elastic Cloud Server (ECS) to an enterprise project, and assign permissions to a user for it to manage the ECS in the project. The user then can manage only this ECS.

Authentication Process
----------------------

When a user initiates an access request, the system authenticates the request based on the actions in the policies attached to the group to which the user belongs. The following figure shows the authentication process.


.. figure:: /_static/images/en-us_image_0000001088335405.png
   :alt: **Figure 1** Request authentication process

   **Figure 1** Request authentication process

#. A user initiates an access request.
#. The system looks for IAM project policies and then looks for matched actions in the policies.
#. If a matched Allow or Deny action is found, the system returns an authentication result (Allow or Deny). Then the authentication is finished.
#. If no matched actions are found in IAM project policies, the system continues to look for enterprise project policies and matched actions.
#. If a matched Allow or Deny action is found, the system returns an authentication result (Allow or Deny). Then the authentication is finished.
#. If no matched actions are found, the system returns a Deny. Then the authentication is finished.

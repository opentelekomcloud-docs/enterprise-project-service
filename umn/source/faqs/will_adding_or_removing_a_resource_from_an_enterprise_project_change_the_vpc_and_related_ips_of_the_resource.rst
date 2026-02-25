:original_name: em_eps_16_1100.html

.. _em_eps_16_1100:

Will Adding or Removing a Resource from an Enterprise Project Change the VPC and Related IPs of the Resource?
=============================================================================================================

No.

Transferring resources between enterprise projects may affect resource access for users that are added to the projects. It will not change the VPC or related IPs of the resource.

Transferring a resource between enterprise projects does not affect the resource itself. For example, the transferring will not cause an instance to restart, change network configurations, or change the ownership of resources.

However, if you grant resource access based on enterprise projects, users may be affected to access related resources. For example, if you grant a user only the permissions to access resources of project A, after the resources are transferred to project B, the user may fail to access the resources due to insufficient permissions.

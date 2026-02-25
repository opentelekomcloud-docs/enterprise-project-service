:original_name: em_01_0007.html

.. _em_01_0007:

Enterprise Project Permissions
==============================

**Administrator**: The administrator can perform any operations on the **Enterprise Project Management** page.

**IAM user**: An IAM user's permissions are granted by the administrator. After an IAM user logs in to the **Enterprise Project Management** page, the IAM user sees only the enterprise projects assigned by the administrator, and can only manage the resources allocated by the administrator. If the administrator assigns a permissions policy for an IAM user, the IAM user has all the permissions included in the policy.

The administrator can use the system-defined policies or custom policies to assign permissions to users. Policies related to enterprise projects include EPS Admin and EPS Viewer. You can use Identity and Access Management (IAM) to manage enterprise project permissions for IAM users. For details, see *Identity and Access Management User Guide*.

.. table:: **Table 1** Enterprise Management permissions

   +-----------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
   | Service Name          | Policy Name     | Description                                                                                                                                                                                                                                                                                                                                                                             | Typically Associated Personnel   |
   +=======================+=================+=========================================================================================================================================================================================================================================================================================================================================================================================+==================================+
   | Enterprise Management | EPS Admin       | -  The Enterprise Management administrator policy, including all the permissions related to enterprise project management and personnel management. The policy allows users to create enterprises, migrate resources, add users to user groups, remove users from user groups, and set policies for user groups. The administrator can set the policy in the **Global** service in IAM. | Enterprise asset administrators  |
   |                       |                 | -  The administrator policy of a single enterprise project. The policy has only the permissions of the specific enterprise projects, including modifying, enabling, disabling, and viewing the specified enterprise projects. The administrator or the users granted the EPS Admin policy on IAM can set the policy in Enterprise Management.                                           |                                  |
   +-----------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+
   |                       | EPS Viewer      | Read-only permissions for a specific or all enterprise projects                                                                                                                                                                                                                                                                                                                         | Enterprise asset query personnel |
   |                       |                 |                                                                                                                                                                                                                                                                                                                                                                                         |                                  |
   |                       |                 | -  Read-only permissions on Enterprise Management to view the information of all enterprise projects and users. The administrator can set the policy in the **Global** service in IAM.                                                                                                                                                                                                  |                                  |
   |                       |                 | -  The administrator or the user to whom the EPS Admin policy is attached can set the permission in Enterprise Management.                                                                                                                                                                                                                                                              |                                  |
   +-----------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------+

.. table:: **Table 2** Common operations and required permissions

   ============================================== ========= ==========
   Operation                                      EPS Admin EPS Viewer
   ============================================== ========= ==========
   Viewing resources in an enterprise project     Y         Y
   Creating an enterprise project                 Y         x
   Modifying an enterprise project                Y         x
   Enabling an enterprise project                 Y         x
   Disabling an enterprise project                Y         x
   Adding a resource to an enterprise project     Y         x
   Removing a resource from an enterprise project Y         x
   ============================================== ========= ==========

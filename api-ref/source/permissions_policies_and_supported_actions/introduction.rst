:original_name: en-us_topic_0171176552.html

.. _en-us_topic_0171176552:

Introduction
============

You can use IAM to perform refined permission management for your enterprise projects. If your account does not need individual IAM users, you can skip this chapter.

A policy is a set of permissions defined in JSON format. By default, new IAM users do not have permissions assigned. You need to add a user to one or more groups, and attach permissions policies or roles to these groups. Users inherit permissions from the groups to which they are added and can perform specified operations on cloud services based on the permissions.

An account has all the permissions required to call all APIs, but IAM users must be assigned the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully.

Supported Actions
-----------------

Operations supported by fine-grained policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: Statements in a policy that allow or deny certain operations.
-  APIs: REST APIs that can be called by a user who has been granted specific permissions.
-  Actions: Specific operations that are allowed or denied.
-  Related actions: Actions on which a specific action depends to take effect. When assigning permissions for the action to a user, you also need to assign permissions for the related actions.
-  IAM or enterprise projects: Type of projects for which an action will take effect. Policies that contain actions for both IAM and enterprise projects can be used and take effect for both IAM and Enterprise Management. Policies that only contain actions for IAM projects can be used and only take effect for IAM.

   .. note::

      The check mark (Y) and cross symbol (x) indicate that an action takes effect or does not take effect for the corresponding type of projects.

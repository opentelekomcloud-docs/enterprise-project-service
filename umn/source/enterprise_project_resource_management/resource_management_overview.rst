:original_name: em_01_0004.html

.. _em_01_0004:

Resource Management Overview
============================

You can use enterprise projects to group and manage cloud resources (for example, resources used for the same purpose).

Transferring a resource between enterprise projects does not affect the resource itself. For example, the transferring will not cause an instance to restart, change network configurations, or change the ownership of resources.

However, if you grant resource access based on enterprise projects, users may be affected to access related resources. For example, if you grant a user only the permissions to access resources of project A, after the resources are transferred to project B, the user may fail to access the resources due to insufficient permissions.

.. note::

   For details about the differences between IAM projects and enterprise projects, see :ref:`What Are the Differences Between IAM Projects and Enterprise Projects? <em_01_0036>`

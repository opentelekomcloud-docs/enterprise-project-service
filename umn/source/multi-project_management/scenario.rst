:original_name: em_eps_04_0100.html

.. _em_eps_04_0100:

Scenario
========

Company A is an enterprise user and has multiple project teams that require different resources and personnel. This topic presents the best practice for multi-project management to address company A's requirements.

Requirements
------------

-  .. _em_eps_04_0100__en-us_topic_0000001082850687_en-us_topic_0273026970_li173315117387:

   **Requirement 1**: Company A can create multiple types of resources in **region_01** and **region_02** for two project teams. Resources of the two project teams need to be isolated from each other.

-  **Requirement 2**: Each member of the project teams can access only the resources of the project team to which the member belongs, and only has the permissions required to complete tasks.

Solution
--------

-  **Solution to requirement 1**: Enterprise Management and Identity and Access Management (IAM) are two cloud services that can isolate resources between projects. However, the implementation logic and functions of the two services are different.

   -  Enterprise Management: You can create enterprise projects to group and manage resources across regions. Resources in enterprise projects are logically isolated from each other. **Each enterprise project can contain resources of multiple regions**, and resources can be added to or removed from enterprise projects.
   -  IAM: IAM projects group and physically isolate resources in a region, **and each IAM project can only contain resources in the same region.** Resources cannot be transferred between IAM projects.

In conclusion, Enterprise Management provides more flexible cross-region resource isolation between projects than IAM. Therefore, it is recommended that company A use Enterprise Management to manage project resources. The solutions to the following requirements are proposed using the Enterprise Management service. For details about the two services, see :ref:`What Are the Differences Between IAM and Enterprise Management <em_01_0035>`.

-  **Solution to requirement 2**: In IAM, company A creates IAM users for employees and adds the IAM users to different groups. In Enterprise Management, company A adds the user groups to the enterprise projects created to address :ref:`Requirement 1 <em_eps_04_0100__en-us_topic_0000001082850687_en-us_topic_0273026970_li173315117387>` and assigns required resource access permissions (see :ref:`Table 1 <em_eps_04_0100__en-us_topic_0000001082850687_en-us_topic_0273026970_table244919552228>`) to each user group.


   .. figure:: /_static/images/en-us_image_0000001137022630.png
      :alt: **Figure 1** Personnel management model of company A

      **Figure 1** Personnel management model of company A

   .. _em_eps_04_0100__en-us_topic_0000001082850687_en-us_topic_0273026970_table244919552228:

   .. table:: **Table 1** User group permissions in company A

      +---------------------------+-----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------+
      | User Group                | Responsibility                    | Permissions          | Description                                                                                                           |
      +===========================+===================================+======================+=======================================================================================================================+
      | Development team          | Project development               | ELB FullAccess       | Full permissions for Elastic Load Balance (ELB)                                                                       |
      +---------------------------+-----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------+
      |                           |                                   | OBS Administrator    | Full permissions for Object Storage Service (OBS)                                                                     |
      +---------------------------+-----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------+
      |                           |                                   | EPS Admin            | Full permissions for Enterprise Management                                                                            |
      +---------------------------+-----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------+
      | Security maintenance team | Security O&M of the project       | ECS CommonOperations | Permissions for basic ECS operations                                                                                  |
      +---------------------------+-----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------+
      | Operations team           | Overall operations of the project | EPS Admin            | Full permissions for Enterprise Management, including modifying, enabling, disabling, and viewing enterprise projects |
      +---------------------------+-----------------------------------+----------------------+-----------------------------------------------------------------------------------------------------------------------+

   .. note::

      For details about system permissions of all cloud services, see `Permission Description <https://docs.otc.t-systems.com/permissions/index.html>`__.

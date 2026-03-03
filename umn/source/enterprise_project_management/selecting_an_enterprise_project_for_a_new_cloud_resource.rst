:original_name: em_01_0013.html

.. _em_01_0013:

Selecting an Enterprise Project for a New Cloud Resource
========================================================

Scenarios
---------

To manage resources at the project level, you need to associate resources with enterprise projects when creating the resources.

You can add cloud resources to an enterprise project using either of the following methods:

-  EPS console
-  Consoles of cloud services that support EPS

Limitations and Constraints
---------------------------

New cloud resources cannot be added to a disabled enterprise project.

Using the EPS Console
---------------------

#. Sign in to the management console. In the upper right corner, hover over the account name and choose **Enterprise Management** from the drop-down list.

   The **Enterprise Project Management** page is displayed.

#. In the enterprise project list, click the name of the target enterprise project to access the enterprise project details page.

#. Click **Create Resource** or **Plan Network** in the upper right corner of the page to add required cloud resources to the enterprise project.


   .. figure:: /_static/images/en-us_image_0000001963832989.png
      :alt: **Figure 1** Creating resources and planning the network

      **Figure 1** Creating resources and planning the network

.. note::

   -  Currently, you can create only four types of cloud resources: ECSs, EVS disks, EIPs, and RDS instances.
   -  When planning the network, only the following three types of cloud resources are supported: Virtual Private Cloud, VPC Peering, and Security Group.

Using the Console of Cloud Services that Support EPS
----------------------------------------------------

You can select an enabled enterprise project when configuring **Enterprise Project** on the cloud resource creation page. New cloud resources can be managed by the selected enterprise project.

Take RDS as an example. Perform the following operations:

#. Log in to the management console.

#. Click |image1| in the upper left corner to select a region and a project.

#. Click |image2| in the upper left corner of the page and choose **Databases** > **Relational Database Service**.

#. In the upper right corner of the page, click **Create DB Instance**.

   The page for creating a DB instance is displayed.

#. Configure the database details and select the target enterprise project from the **Enterprise Project** drop-down list.


   .. figure:: /_static/images/en-us_image_0000001080662358.png
      :alt: **Figure 2** Selecting an enterprise project

      **Figure 2** Selecting an enterprise project

#. In the lower right corner, click **Create Now**.

#. Confirm the configurations and click **Submit**.

.. |image1| image:: /_static/images/en-us_image_0000001080533890.png
.. |image2| image:: /_static/images/en-us_image_0000001964330921.png

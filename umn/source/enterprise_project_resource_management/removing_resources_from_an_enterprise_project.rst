:original_name: em_01_0017.html

.. _em_01_0017:

Removing Resources from an Enterprise Project
=============================================

Scenarios
---------

If your need to group and manage resources based on your business or when resource groups need to be changed, you can reallocate resources by adding or removing them from projects.

EPS allows removal of cross-region resources from the same enterprise project for management.

Resources can be removed from an enterprise project that the resources belong to in the following two scenarios:

-  Resources are removed from one enterprise project to another project.
-  Resources are removed from one enterprise project to the **default** enterprise project.

Procedure
---------

#. Sign in to the management console. In the upper right corner, hover over the account name and choose **Enterprise Management** from the drop-down list.

   The **Enterprise Project Management** page is displayed.

#. Click **View Resource** in the **Operation** column of the row containing the target enterprise project.

   The enterprise project details page is displayed. You can view the resources in the enterprise project on the **Resources** tab.


   .. figure:: /_static/images/en-us_image_0000001936865004.png
      :alt: **Figure 1** Viewing resources

      **Figure 1** Viewing resources

#. Select the resources to be removed, and click **Remove**.

   The **Remove Resource** dialog box is displayed.

#. Select a mode.

   -  **Independent resources**: Each resource is removed as an independent resource. You can remove multiple independent resources at the same time.

      If resources other than ECSs need to be added, you must select this mode.

      You can select this mode to remove ECSs from the enterprise project, but resources associated with the ECSs, such as EIPs and EVS disks, are not removed from the enterprise project.

   -  **ECSs and ECS associated resources**: You only need to select the ECSs to be removed, and the resources associated with the ECSs will be automatically removed from the enterprise project at the same time.

      This mode is available only when the resources to be removed are ECSs. Currently, only ECSs and their associated EVS disks and EIPs can be removed from an enterprise project at the same time.

#. Select the destination enterprise project that resources are removed to and click **OK**.

   Resources removed can be added to and managed in other enterprise projects.

   Resources can also be added into the **default** enterprise project if they do not need to be added into other projects.

   The resources are removed from the enterprise project. You can view the resources in the resource list of the destination enterprise project.


   .. figure:: /_static/images/en-us_image_0000001936952008.png
      :alt: **Figure 2** Removing resources

      **Figure 2** Removing resources

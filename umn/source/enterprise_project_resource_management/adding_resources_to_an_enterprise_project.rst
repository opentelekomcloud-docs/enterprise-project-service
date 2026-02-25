:original_name: em_01_0016.html

.. _em_01_0016:

Adding Resources to an Enterprise Project
=========================================

Scenarios
---------

If your need to group and manage resources based on your business or when resource groups need to be changed, you can reallocate resources by adding or removing them from projects.

EPS supports cross-region resource movement from one enterprise project to another.

Procedure
---------

#. Sign in to the management console. In the upper right corner, hover over the account name and choose **Enterprise Management** from the drop-down list.

   The **Enterprise Project Management** page is displayed.

#. Click **View Resource** in the **Operation** column of the row containing the target enterprise project.

   The enterprise project details page is displayed. You can view the resources in the enterprise project on the **Resources** tab.


   .. figure:: /_static/images/en-us_image_0000001936865004.png
      :alt: **Figure 1** Viewing resources

      **Figure 1** Viewing resources

#. Click **Add**.

   The **Add Resource** dialog box is displayed.

#. Select a way of adding resources.

   -  **Independent resources**: Each resource is added as an independent resource. You can add multiple independent resources at the same time.

      If resources other than ECSs need to be added, you must select this mode.

      You can select this mode to add ECSs to the enterprise project, but resources associated with the ECSs, such as EIPs and EVS disks, are not added to the enterprise project.

   -  **ECSs and ECS associated resources**: You only need to select the ECSs to be added, and the resources associated with the ECSs will be automatically added to the enterprise project at the same time.

      Select this way only when the resources to be added are ECSs. Currently, only the associated EVS disks and EIPs can be added to an enterprise project along with the ECSs.

#. Filter resources by service, region, or enterprise project in the filter box above the resource list or enter resource name in the search box for resource search.

   If you select **ECSs and ECS associated resources** for **Mode**, you cannot filter resources by service or resource type.

   Resources meeting the search criteria will be displayed in the lower part of the page.


   .. figure:: /_static/images/en-us_image_0000001964490709.png
      :alt: **Figure 2** Adding resources

      **Figure 2** Adding resources

#. Select the resources to be added and click **OK**.

   After the resources are added, they appear in the resource list of the target enterprise project.

:original_name: em-pm_04_0803.html

.. _em-pm_04_0803:

Removing Users from an Enterprise Project
=========================================

Scenario
--------

You can remove users from enterprise projects as needed.

Batch operations are supported.

After a user is disassociated from an enterprise project, they can no longer manage the project.

Procedure
---------

#. Sign in to the management console. In the upper right corner, hover over the account name and choose **Enterprise Management** from the drop-down list.

   The **Enterprise Project Management** page is displayed.

#. On the **Enterprise Project Management Service** page, click the name of the enterprise project you want to view.

#. On the enterprise project details page that is displayed, click the **Permissions** tab, and click **Authorize User**.


   .. figure:: /_static/images/en-us_image_0000001964308565.png
      :alt: **Figure 1** Authorizing users

      **Figure 1** Authorizing users

#. On the IAM **Users** page that is displayed, click the user name to go to the user details page.


   .. figure:: /_static/images/en-us_image_0000001964314613.png
      :alt: **Figure 2** Users

      **Figure 2** Users

#. On the **Permissions** tab, click **By Enterprise Project**, select the target enterprise project, and click **Delete** in the **Operation** column.

   To delete enterprise projects in batches, select the enterprise projects in the list and click **Delete** above the list.


   .. figure:: /_static/images/en-us_image_0000001964318045.png
      :alt: **Figure 3** Deleting enterprise projects for a user

      **Figure 3** Deleting enterprise projects for a user

#. In the displayed dialog box, click **OK**.

   The enterprise projects that are managed by the user are deleted.

Other Operations
----------------

Users inherit permissions from their user groups. Adding or removing users from a user group allows you to efficiently manage user permissions. For details, see `Adding Users to or Removing Users from a User Group <https://docs.otc.t-systems.com/identity-access-management/umn/user_guide/user_groups_and_authorization/adding_users_to_or_removing_users_from_a_user_group.html>`__.

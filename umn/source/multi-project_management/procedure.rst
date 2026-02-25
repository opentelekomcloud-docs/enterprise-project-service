:original_name: em_eps_04_0200.html

.. _em_eps_04_0200:

Procedure
=========

The following figure illustrates the process of enterprise project management for addressing company A's requirements.


.. figure:: /_static/images/en-us_image_0000001183142611.png
   :alt: **Figure 1** Enterprise project management process

   **Figure 1** Enterprise project management process

:ref:`Step 1 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section6742547123419>`: Create enterprise projects on the **Enterprise Management console**.

:ref:`Step 2 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section564353417178>`: On the IAM console, create a user group for each functional team, create IAM users for employees, and add the users to different user groups.

:ref:`Step 3 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section117431247113414>`: On the IAM console, assign the required permissions to each user group, and add the user group to the corresponding enterprise project. Users in the group automatically inherit its permissions.

:ref:`Step 4 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section77444479341>`: Create resources on **other cloud service consoles** and add the resources to the corresponding enterprise projects.

:ref:`Follow-Up Operation: Enterprise Project Management <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section3614552161713>`: Manage users and resources on the **Enterprise Management console**.

.. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section6742547123419:

Creating an Enterprise Project
------------------------------

Perform the following procedure to create two enterprise projects (A and B) on the Enterprise Management console.

#. .. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li399283219718:

   On the **Enterprise Project Management** page, click **Create Enterprise Project**.

#. .. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li073813222814:

   Enter **EnterpriseProject_A** for **Name** and click **OK**.


   .. figure:: /_static/images/en-us_image_0000001936354110.png
      :alt: **Figure 2** Creating an enterprise project

      **Figure 2** Creating an enterprise project

#. Repeat :ref:`1 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li399283219718>` to :ref:`2 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li073813222814>` to create **EnterpriseProject_B.**

   The two enterprise projects are displayed on the **Enterprise Project Management** page.

.. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section564353417178:

Creating IAM Users and User Groups
----------------------------------

The following is an example procedure for creating a user group (**Enterprise Project A_Development**) and user (**Murphy**) and adding the user to the user group.

#. Create a user group.

   a. On the management console, click |image1| in the upper left corner and choose **Management & Deployment** > **Identity and Access Management**.

   b. .. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li1320612912244:

      On the IAM console, choose **User Groups** from the left navigation bar, and click **Create User Group** in the upper right corner.


   .. figure:: /_static/images/en-us_image_0000001936407072.png
      :alt: **Figure 3** Creating a user group

      **Figure 3** Creating a user group

   c. .. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li389874122515:

      Set the user group name to **Enterprise Project A_Development** and click **OK**.

   d. Repeat :ref:`2 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li1320612912244>` to :ref:`3 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li389874122515>` to create accounting, security maintenance, and operation teams for the two enterprise projects.

   The user groups are displayed in the user group list.

#. Create an IAM user and add the user to a user group. For details, see *Identity and Access Management User Guide*.

   a. .. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li191039159268:

      In the left navigation of the IAM console, choose **Users**. Then click **Create User**.


      .. figure:: /_static/images/en-us_image_0000001963826009.png
         :alt: **Figure 4** Creating an IAM user

         **Figure 4** Creating an IAM user

   b. On the **Create User** page, enter user information, select **Access Type**, **Credential Type**, and **Login Protection**, and click **Next**.


      .. figure:: /_static/images/en-us_image_0000001936576762.png
         :alt: **Figure 5** Setting user details

         **Figure 5** Setting user details

   c. .. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li201291344261:

      Enter the target user group to add the user. Then the user will inherit permissions from the group. Click **Create** and the IAM user Murphy is created.


      .. figure:: /_static/images/en-us_image_0000001936741978.png
         :alt: **Figure 6** Adding users to a user group

         **Figure 6** Adding users to a user group

   d. Repeat :ref:`1 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li191039159268>` to :ref:`3 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li201291344261>` to create users for all employees and add the users to corresponding user groups.

   The user is displayed in the user list. You can view the IAM users of each user group on the **Users** tab page.

.. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section117431247113414:

Adding User Groups to Enterprise Projects
-----------------------------------------

The following example shows how to associate the **Enterprise Project A_Development** user group with a project and how to add the **EPS Admin** policy to the user group. In this way, users in **Enterprise Project A_Development** can access the project.

#. On the **Enterprise Project Management Service** page, click the name of the enterprise project you want to view.

#. On the enterprise project details page that is displayed, click the **Permissions** tab, and click **Authorize User Group**.

   The IAM **User Groups** page will be displayed, and you can assign **EPS Admin**.

   For details, see `Creating a User Group and Assigning Permissions <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0030.html>`__.


   .. figure:: /_static/images/en-us_image_0000001963867729.png
      :alt: **Figure 7** Authorize User Group

      **Figure 7** Authorize User Group

.. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section77444479341:

Creating Resources and Adding Them to Enterprise Projects
---------------------------------------------------------

The following is an example procedure for creating a load balancer and adding it to enterprise project A.

#. .. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li1241418577502:

   Log in to the management console, click |image2| in the upper left corner, and choose **Network** > **Elastic Load Balance**.

#. Click **Create Elastic Load Balance** in the upper right corner of the page.


   .. figure:: /_static/images/en-us_image_0000001936593554.png
      :alt: **Figure 8** Creating a load balancer

      **Figure 8** Creating a load balancer

#. Configure the load balancer information and select enterprise project A from the **Enterprise Project** drop-down list.


   .. figure:: /_static/images/en-us_image_0000001963887181.png
      :alt: **Figure 9** Selecting an enterprise project

      **Figure 9** Selecting an enterprise project

#. Click **Create Now** in the lower right corner of the page.

#. .. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li19374176547:

   Confirm the configuration and submit your request.

#. Repeat :ref:`1 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li1241418577502>` to :ref:`5 <em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_li19374176547>` to create required resources for the two enterprise projects.

   To view the created resources, go to the Enterprise Management console and click **View Resource** in the row that contains enterprise project A or B.

   .. note::

      -  Currently, Enterprise Management only supports specific cloud services. For details, see :ref:`Supported Services <em_01_0005>`.
      -  If you have already created required resources, you can directly add them to enterprise projects. For details, see :ref:`Adding Resources to an Enterprise Project <em_01_0016>`.

.. _em_eps_04_0200__en-us_topic_0000001083044329_en-us_topic_0273026971_section3614552161713:

Follow-Up Operation: Enterprise Project Management
--------------------------------------------------

After completing the preceding steps, you can manage your enterprise projects on the **Enterprise Project Management** page.

-  **Resource management**: Click **View Resource** in the **Operation** column to view the existing resources of an enterprise project and :ref:`add more resources to the enterprise project <em_01_0016>`.
-  **Personnel management**: Choose **Permissions** to go to the IAM console to view the users and user groups associated with an enterprise project, and modify the users, user groups and their permissions for the enterprise project. For details about personnel management, see :ref:`Enterprise Personnel Management <em_01_0020>`.

.. |image1| image:: /_static/images/en-us_image_0000001963826005.png
.. |image2| image:: /_static/images/en-us_image_0000001182942651.png

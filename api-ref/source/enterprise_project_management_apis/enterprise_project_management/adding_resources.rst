:original_name: en-us_topic_0171146929.html

.. _en-us_topic_0171146929:

Adding Resources
================

Function
--------

This API is used to add resources to a target enterprise project.

URI
---

POST /v1.0/enterprise-projects/{enterprise_project_id}/resources-migrate

.. table:: **Table 1** Parameter in the URI

   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------+
   | Name                  | Mandatory       | Type            | Description                                                                                                   |
   +=======================+=================+=================+===============================================================================================================+
   | enterprise_project_id | Yes             | String          | Specifies the ID of the target enterprise project.                                                            |
   |                       |                 |                 |                                                                                                               |
   |                       |                 |                 | You can obtain the ID by using API :ref:`Querying the Enterprise Project List <en-us_topic_0121230880>`.      |
   |                       |                 |                 |                                                                                                               |
   |                       |                 |                 | If the value of **enterprise_project_id** is **0**, resources are migrated to enterprise project **default**. |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------+

Request
-------

-  Parameter description

   .. table:: **Table 2** Parameters in the request header

      +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter    | Mandatory | Type   | Description                                                                                                                                                                                                 |
      +==============+===========+========+=============================================================================================================================================================================================================+
      | X-Auth-Token | Yes       | String | Specifies the user token. EPS is a global service. When calling the IAM API to obtain a user token, set **scope** to **domain**. The value of **X-Subject-Token** in the response header is the user token. |
      +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Content-Type | Yes       | String | Default value: **application/json; charset=UTF-8**                                                                                                                                                          |
      +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 3** Parameters in the request body

      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name            | Mandatory       | Type            | Description                                                                                                                                                                                                                   |
      +=================+=================+=================+===============================================================================================================================================================================================================================+
      | project_id      | No              | string          | Specifies the project ID. This parameter is mandatory when **resource_type** is set to a region-level resource.                                                                                                               |
      |                 |                 |                 |                                                                                                                                                                                                                               |
      |                 |                 |                 | You can obtain the project ID from :ref:`Obtaining a Project ID <em_03_0909>`.                                                                                                                                                |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | resource_type   | Yes             | string          | Specifies the resource type.                                                                                                                                                                                                  |
      |                 |                 |                 |                                                                                                                                                                                                                               |
      |                 |                 |                 | To query resource types, call the :ref:`Querying Supported Services <listproviders>` API.                                                                                                                                     |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | resource_id     | Yes             | string          | Specifies the ID of the resource to be added. The ID is provided by the cloud service of the resource. For example, if you want to add an ECS resource, query the resource type on the ECS console or by calling the ECS API. |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | associated      | No              | boolean         | Specifies whether associated resources are added too.                                                                                                                                                                         |
      |                 |                 |                 |                                                                                                                                                                                                                               |
      |                 |                 |                 | The default value is **false**. Currently, only ECS associated EVS disks and EIPs can be added.                                                                                                                               |
      +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{EPS endpoint}/v1.0/enterprise-projects/{enterprise_project_id}/resources-migrate

   .. code-block::

      {
         "project_id": "0f02faab61ab497997867b2c9ef193a2",
         "associated": false,
         "resource_type": "eip",
         "resource_id": "e220166e-a6b1-4bb4-9abf-950b367212e8"
      }

Response
--------

**Status code: 204**

None

Status Codes
------------

For details, see :ref:`Status Code <en-us_topic_0171146972>`.

Error Codes
-----------

For details, see :ref:`Error Codes <en-us_topic_0121230887>`.

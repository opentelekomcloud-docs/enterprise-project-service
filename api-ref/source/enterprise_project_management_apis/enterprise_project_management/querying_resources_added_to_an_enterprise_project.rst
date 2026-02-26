:original_name: en-us_topic_0133254025.html

.. _en-us_topic_0133254025:

Querying Resources Added to an Enterprise Project
=================================================

Function
--------

This API is used to query details about resources added to an enterprise project.

URI
---

POST /v1.0/enterprise-projects/{enterprise_project_id}/resources/filter

.. table:: **Table 1** Parameter in the URI

   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------+
   | Name                  | Mandatory       | Type            | Description                                                                                              |
   +=======================+=================+=================+==========================================================================================================+
   | enterprise_project_id | Yes             | String          | Specifies the enterprise project ID.                                                                     |
   |                       |                 |                 |                                                                                                          |
   |                       |                 |                 | You can obtain the ID by using API :ref:`Querying the Enterprise Project List <en-us_topic_0121230880>`. |
   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------+

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

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name            | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                               |
      +=================+=================+=================+===========================================================================================================================================================================================================================================================================================================================+
      | limit           | No              | Integer         | Specifies the number of records to be queried. The default value is **1000**. The maximum value is **1000**, and the minimum value is **1**.                                                                                                                                                                              |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | offset          | No              | Integer         | Specifies the index position, which starts from the next data record specified by **offset**. The value must be a number and cannot be a negative number. The default value is **0**.                                                                                                                                     |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | projects        | No              | List<String>    | Specifies the project IDs. You can obtain the project IDs from :ref:`Obtaining a Project ID <em_03_0909>`. This parameter can be ignored when the transferred resource is a global resource. This parameter is mandatory when the transferred resource type is a region-specific resource type, such as ECS and EVS disk. |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | resource_types  | Yes             | List<String>    | Specifies the resource types. The value of this parameter is case-sensitive. The following shows some example values: **ecs**, **scaling_group**, **images**, **disk**, **vpcs**, **security-groups**, **shared_bandwidth**, and **eip**.                                                                                 |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                           |
      |                 |                 |                 | To query resource types, call the :ref:`Querying Supported Services <listproviders>` API.                                                                                                                                                                                                                                 |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | matches         | No              | List<match>     | Specifies the search field. **Key** indicates the field to be matched and is fixed at **resource_name**. **Value** indicates the value to be matched. If this field is not transferred, no matching condition will be used.                                                                                               |
      |                 |                 |                 |                                                                                                                                                                                                                                                                                                                           |
      |                 |                 |                 | For details, see :ref:`Table 4 <en-us_topic_0133254025__table114127551360>`.                                                                                                                                                                                                                                              |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  **Match** field data structure

   .. _en-us_topic_0133254025__table114127551360:

   .. table:: **Table 4** Match field data structure description

      +-------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name  | Mandatory | Type   | Description                                                                                                                                                                                                                   |
      +=======+===========+========+===============================================================================================================================================================================================================================+
      | key   | Yes       | String | Specifies the key. If the **matches** parameter exists, this parameter is mandatory and is fixed at **resource_name**.                                                                                                        |
      +-------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value | Yes       | String | Specifies the value. The value is the resource name. If the **matches** parameter is available, this parameter is mandatory and fuzzy search is used by default, for example, message.com. Enter a maximum of 255 characters. |
      +-------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{EPS endpoint}/v1.0/enterprise-projects/{enterprise_project_id}/resources/filter

   .. code-block::

      {
          "projects": [
              "e1eb7c40cbea4c8389cde527594a306d",
              "2345d321da864d6faf2e762647e19f96"
          ],
          "resource_types": [
              "disk"
          ],
          "offset": 0,
          "limit": 10,
          "matches": [
              {
                  "key": "resource_name",
                  "value": "lhj"
              }
          ]
      }

Response
--------

**Status code: 200**

-  Parameter description

   .. table:: **Table 5** Parameters in the response body

      +-----------------------+-----------------------+--------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                    |
      +=======================+=======================+================================================================================+
      | resources             | List<resource>        | Specifies the resource list.                                                   |
      |                       |                       |                                                                                |
      |                       |                       | For details, see :ref:`Table 6 <en-us_topic_0133254025__table15534165513610>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------+
      | errors                | List<error>           | Specifies the error list.                                                      |
      |                       |                       |                                                                                |
      |                       |                       | For details, see :ref:`Table 7 <en-us_topic_0133254025__table16666135513620>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------+
      | total_count           | Integer               | Specifies the total number of returned records meeting the requirements.       |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------+

-  **Resource** field data structure

   .. _en-us_topic_0133254025__table15534165513610:

   .. table:: **Table 6** Resource field data structure description

      ===================== ====== ======================================
      Name                  Type   Description
      ===================== ====== ======================================
      project_id            String Specifies the project ID.
      project_name          String Specifies the enterprise project name.
      resource_type         String Specifies the resource type.
      resource_id           String Specifies the resource ID.
      resource_name         String Specifies the resource name.
      resource_detail       Object Specifies the resource details.
      enterprise_project_id String Specifies the enterprise project ID.
      ===================== ====== ======================================

-  **Error** field data structure

   .. _en-us_topic_0133254025__table16666135513620:

   .. table:: **Table 7** Error field data structure description

      ============= ====== ============================
      Name          Type   Description
      ============= ====== ============================
      project_id    String Specifies the project ID.
      resource_type String Specifies the resource type.
      error_code    String Specifies the error code.
      error_msg     String Specifies the error message.
      ============= ====== ============================

-  Example response

   **Status code: 200**

   .. code-block::

      {
          "resources": [
              {
                  "project_id": "e1eb7c40cbea4c8389cde527594a306d",
                  "project_name": "XXXX",           //Project name
                  "resource_type": "disk",
                  "resource_id": "b621f5ae-b5c1-49d7-a660-752c445434b4",
                  "resource_name": "lhj1-volume-0001",
                  "resource_detail": null,
                  "enterprise_project_id": "0"
              },
              {
                  "project_id": "e1eb7c40cbea4c8389cde527594a306d",
                  "project_name": "XXXX",            //Project name
                  "resource_type": "disk",
                  "resource_id": "87c9edc9-f66c-48b8-a22f-372b2e22d579",
                  "resource_name": "lhj2-volume-0002",
                  "resource_detail": null,
                  "enterprise_project_id": "0"
              }
          ],
          "errors": [],
          "total_count": 2
      }

Status Codes
------------

For details, see :ref:`Status Code <en-us_topic_0171146972>`.

Error Codes
-----------

For details, see :ref:`Error Codes <en-us_topic_0121230887>`.

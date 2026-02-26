:original_name: en-us_topic_0121230880.html

.. _en-us_topic_0121230880:

Querying the Enterprise Project List
====================================

Function
--------

This API is used to query the list of enterprise projects that can be managed by a user. The user can add resources to an enterprise project in the list.

URI
---

GET /v1.0/enterprise-projects

.. table:: **Table 1** Query parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Name            | Mandatory       | Type            | Description                                                                                                                                                                           |
   +=================+=================+=================+=======================================================================================================================================================================================+
   | id              | No              | String          | Specifies the ID of an enterprise project. The value **0** indicates enterprise project **default**.                                                                                  |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | Interger        | Specifies the number of records to be queried. The default value is **1000**. The maximum value is **1000**, and the minimum value is **1**.                                          |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name            | No              | String          | Specifies the enterprise project name. Fuzzy search is supported.                                                                                                                     |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | No              | Interger        | Specifies the index position, which starts from the next data record specified by **offset**. The value must be a number and cannot be a negative number. The default value is **0**. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sort_dir        | No              | String          | Specifies the result sorting order. The default value is **desc**.                                                                                                                    |
   |                 |                 |                 |                                                                                                                                                                                       |
   |                 |                 |                 | -  **desc**: Results are sorted in descending order.                                                                                                                                  |
   |                 |                 |                 | -  **asc**: Results are sorted in ascending order.                                                                                                                                    |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | sort_key        | No              | String          | Specifies the keyword by which the results to return are sorted. Keywords such as **updated_at** are supported. By default, the keyword **created_at** is used.                       |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status          | No              | Integer         | Specifies the enterprise project status.                                                                                                                                              |
   |                 |                 |                 |                                                                                                                                                                                       |
   |                 |                 |                 | -  **1**: The enterprise project is enabled.                                                                                                                                          |
   |                 |                 |                 | -  **2**: The enterprise project is disabled.                                                                                                                                         |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

.. table:: **Table 2** Parameters in the request header

   +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter    | Mandatory | Type   | Description                                                                                                                                                                                                 |
   +==============+===========+========+=============================================================================================================================================================================================================+
   | X-Auth-Token | No        | String | Specifies the user token. EPS is a global service. When calling the IAM API to obtain a user token, set **scope** to **domain**. The value of **X-Subject-Token** in the response header is the user token. |
   +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      GET https://{EPS endpoint}/v1.0/enterprise-projects?name=prise_pro

Response
--------

**Status code: 200**

-  Parameter description

   .. table:: **Table 3** Parameters in the response body

      +-----------------------+--------------------------+-----------------------------------------------------------------------------------+
      | Name                  | Type                     | Description                                                                       |
      +=======================+==========================+===================================================================================+
      | enterprise_projects   | List<enterprise_project> | Specifies the enterprise project list.                                            |
      |                       |                          |                                                                                   |
      |                       |                          | For details, see :ref:`Table 4 <en-us_topic_0121230880__table66686638>`.          |
      +-----------------------+--------------------------+-----------------------------------------------------------------------------------+
      | total_count           | Integer                  | Specifies the total number of enterprise projects that meet the query conditions. |
      +-----------------------+--------------------------+-----------------------------------------------------------------------------------+

-  **enterprise_project** field data structure

   .. _en-us_topic_0121230880__table66686638:

   .. table:: **Table 4** enterprise_project field data structure description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                                                                                |
      +=======================+=======================+============================================================================================================================================+
      | id                    | String                | Specifies the enterprise project ID.                                                                                                       |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | name                  | String                | Specifies the enterprise project name.                                                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | description           | String                | Specifies the description of the enterprise project.                                                                                       |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | Integer               | Specifies the enterprise project status.                                                                                                   |
      |                       |                       |                                                                                                                                            |
      |                       |                       | -  **1**: The enterprise project is enabled.                                                                                               |
      |                       |                       | -  **2**: The enterprise project is disabled.                                                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the time (UTC) when the enterprise project was created.                                                                          |
      |                       |                       |                                                                                                                                            |
      |                       |                       | Example: 2018-05-18T06:49:06Z                                                                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | updated_at            | String                | Specifies the time (UTC) when the enterprise project was modified.                                                                         |
      |                       |                       |                                                                                                                                            |
      |                       |                       | Example: 2018-05-28T02:21:36Z                                                                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | type                  | String                | Project type. **prod**: commercial project; **poc**: test project                                                                          |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | delete_flag           | Boolean               | Deletion flag. The value **false** means that the information is not deleted and the value **true** means that the information is deleted. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   **Status code: 200**

   .. code-block::

      {
          "enterprise_projects": [
              {
                  "id": "6fbcf2f3-3164-4d32-9a3e-a8886dc38c24",
                  "name": "auto_test",
                  "description": "hello world!",
                  "type":"prod",
                  "status": 1,
                  "delete_flag" : false,
                  "created_at": "2018-05-18T06:49:06Z",
                  "updated_at": "2018-05-28T02:21:36Z"
              }
          ],
          "total_count": 1
      }

Status Codes
------------

For details, see :ref:`Status Code <en-us_topic_0171146972>`.

Error Codes
-----------

For details, see :ref:`Error Codes <en-us_topic_0121230887>`.

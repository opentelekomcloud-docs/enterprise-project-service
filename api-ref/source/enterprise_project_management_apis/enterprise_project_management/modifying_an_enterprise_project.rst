:original_name: en-us_topic_0121230884.html

.. _en-us_topic_0121230884:

Modifying an Enterprise Project
===============================

Function
--------

This API is used to modify an enterprise project.

Only the enterprise project name and description can be modified.

The enterprise project type can be only changed from **poc** to **prod**.

.. note::

   You can modify the enterprise project information only after the Enterprise Project function is enabled.

URI
---

PUT /v1.0/enterprise-projects/{enterprise_project_id}

.. table:: **Table 1** Parameter in the URI

   +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------+
   | Name                  | Mandatory       | Type            | Description                                                                                              |
   +=======================+=================+=================+==========================================================================================================+
   | enterprise_project_id | Yes             | String          | Specifies the enterprise project ID. The enterprise project whose ID is **0** cannot be modified.        |
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

      +-------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name        | Mandatory | Type   | Description                                                                                                                                                                                          |
      +=============+===========+========+======================================================================================================================================================================================================+
      | name        | Yes       | String | A name can contain 1 to 255 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed. The name must be unique in the domain and cannot include any form of the word "default". |
      +-------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | description | No        | String | A description can contain a maximum of 512 characters.                                                                                                                                               |
      +-------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | type        | No        | String | Specifies the enterprise project type. The enterprise project type can be only changed from **poc** to **prod**.                                                                                     |
      +-------------+-----------+--------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      PUT https://{EPS endpoint}/v1.0/enterprise-projects/{enterprise_project_id}

   .. code-block::

      {
         "name":"enterprise_project1",
         "description": "description"
      }

Response
--------

**Status code: 200**

-  Parameter description

   .. table:: **Table 4** Parameters in the response body

      +-----------------------+--------------------------+-------------------------------------------------------------------------+
      | Name                  | Type                     | Description                                                             |
      +=======================+==========================+=========================================================================+
      | enterprise_project    | Dict<enterprise_project> | Specifies the enterprise project.                                       |
      |                       |                          |                                                                         |
      |                       |                          | For details, see :ref:`Table 5 <en-us_topic_0121230884__table5907602>`. |
      +-----------------------+--------------------------+-------------------------------------------------------------------------+

-  **enterprise_project** data structure

   .. _en-us_topic_0121230884__table5907602:

   .. table:: **Table 5** **enterprise_project** data structure description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                                                                                |
      +=======================+=======================+============================================================================================================================================+
      | id                    | String                | Specifies the enterprise project ID.                                                                                                       |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | name                  | String                | Specifies the enterprise project name.                                                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | description           | String                | Provides supplementary information about the enterprise project.                                                                           |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | Integer               | **1** indicates **Enabled**. **2** indicates **Disabled**.                                                                                 |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                | Specifies the time (UTC) when the enterprise project was created.                                                                          |
      |                       |                       |                                                                                                                                            |
      |                       |                       | Example: 2018-05-18T06:49:06Z                                                                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | updated_at            | String                | Specifies the time (UTC) when the enterprise project was modified.                                                                         |
      |                       |                       |                                                                                                                                            |
      |                       |                       | Example: 2018-05-18T06:49:06Z                                                                                                              |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | type                  | String                | Project type. **prod**: commercial project; **poc**: test project                                                                          |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+
      | delete_flag           | Boolean               | Deletion flag. The value **false** means that the information is not deleted and the value **true** means that the information is deleted. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response

   **Status code: 200**

   .. code-block::

      {
          "enterprise_project": {
              "id": "5aa119a8-d25b-45a7-8d1b-88e127885635",
              "name": "enterprise_project1",
              "description": "description",
              "type":"prod",
              "status": 1,
              "delete_flag": false,
              "created_at": "2016-03-28T00:00:00Z",
              "updated_at": "2016-03-28T00:00:00Z"
          }
      }

Status Codes
------------

For details, see :ref:`Status Code <en-us_topic_0171146972>`.

Error Codes
-----------

For details, see :ref:`Error Codes <en-us_topic_0121230887>`.

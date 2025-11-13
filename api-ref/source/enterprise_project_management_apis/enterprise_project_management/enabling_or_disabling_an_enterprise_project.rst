:original_name: en-us_topic_0121230885.html

.. _en-us_topic_0121230885:

Enabling or Disabling an Enterprise Project
===========================================

Function
--------

This API is used to enable or disable an enterprise project.

URI
---

POST /v1.0/enterprise-projects/{enterprise_project_id}/action

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

      +-----------------+-----------------+-----------------+---------------------------------------------+
      | Name            | Mandatory       | Type            | Description                                 |
      +=================+=================+=================+=============================================+
      | action          | Yes             | String          | **enable**: Enable an enterprise project.   |
      |                 |                 |                 |                                             |
      |                 |                 |                 | **disable**: Disable an enterprise project. |
      +-----------------+-----------------+-----------------+---------------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{EPS endpoint}/v1.0/enterprise-projects/{enterprise_project_id}/action

   .. code-block::

      {
        "action":"enable"
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

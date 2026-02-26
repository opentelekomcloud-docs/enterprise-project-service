:original_name: en-us_topic_0121230886.html

.. _en-us_topic_0121230886:

Querying Enterprise Project Quota
=================================

Function
--------

This API is used to query the enterprise project quota.

URI
---

GET /v1.0/enterprise-projects/quotas

Request
-------

-  Parameter description

   .. table:: **Table 1** Parameters in the request header

      +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter    | Mandatory | Type   | Description                                                                                                                                                                                                 |
      +==============+===========+========+=============================================================================================================================================================================================================+
      | X-Auth-Token | Yes       | String | Specifies the user token. EPS is a global service. When calling the IAM API to obtain a user token, set **scope** to **domain**. The value of **X-Subject-Token** in the response header is the user token. |
      +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      GET https://{EPS endpoint}/v1.0/enterprise-projects/quotas

Response
--------

**Status code: 200**

-  Parameter description

   .. table:: **Table 2** Parameters in the response body

      +-----------------------+-----------------------+--------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                              |
      +=======================+=======================+==========================================================================+
      | quotas                | Dict<quotas>          | Enterprise project quotas.                                               |
      |                       |                       |                                                                          |
      |                       |                       | For details, see :ref:`Table 3 <en-us_topic_0121230886__table61498184>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------+

-  **quotas** field data structure

   .. _en-us_topic_0121230886__table61498184:

   .. table:: **Table 3** **quotas** field data structure description

      +-----------------------+-----------------------+--------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                              |
      +=======================+=======================+==========================================================================+
      | resources             | List<resource>        | Specifies the resource quota of EPS.                                     |
      |                       |                       |                                                                          |
      |                       |                       | For details, see :ref:`Table 4 <en-us_topic_0121230886__table55946580>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------+

-  **resource** field data structure

   .. _en-us_topic_0121230886__table55946580:

   .. table:: **Table 4** **resource** field data structure description

      +-------+--------+------------------------------------------------------------------------------+
      | Name  | Type   | Description                                                                  |
      +=======+========+==============================================================================+
      | type  | String | Specifies the resource type. Currently, it refers to **enterprise_project**. |
      +-------+--------+------------------------------------------------------------------------------+
      | used  | int    | Specifies the number of used quotas.                                         |
      +-------+--------+------------------------------------------------------------------------------+
      | quota | int    | Specifies the total amount of the quota.                                     |
      +-------+--------+------------------------------------------------------------------------------+

-  Example response

   **Status code: 200**

   .. code-block::

      {
          "quotas": {
              "resources": [
                  {
                      "type": "enterprise_project",
                      "used": 3,
                      "quota": 100
                  }
              ]
          }
      }

Status Codes
------------

For details, see :ref:`Status Code <en-us_topic_0171146972>`.

Error Codes
-----------

For details, see :ref:`Error Codes <en-us_topic_0121230887>`.

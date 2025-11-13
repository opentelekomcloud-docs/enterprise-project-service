:original_name: en-us_topic_0133254024.html

.. _en-us_topic_0133254024:

Querying Details About an API Version
=====================================

Function
--------

This API is used to query details about an API version.

URI
---

GET /{api_version}

Request
-------

-  Parameter description

   .. table:: **Table 1** Parameters in the request header

      +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter    | Mandatory | Type   | Description                                                                                                                                                                                                 |
      +==============+===========+========+=============================================================================================================================================================================================================+
      | X-Auth-Token | Yes       | String | Specifies the user token. EPS is a global service. When calling the IAM API to obtain a user token, set **scope** to **domain**. The value of **X-Subject-Token** in the response header is the user token. |
      +--------------+-----------+--------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 2** Parameters in the request

      +-------------+-----------+--------+----------------------------------------------+
      | Name        | Mandatory | Type   | Description                                  |
      +=============+===========+========+==============================================+
      | api_version | Yes       | String | Specifies the version ID, for example, v1.0. |
      +-------------+-----------+--------+----------------------------------------------+

-  Example request

   .. code-block:: text

      GET https://{EPS endpoint}/v1.0

Response
--------

**Status code: 200**

-  Parameter description

   .. table:: **Table 3** Parameters in the response body

      +-----------------------+-----------------------+-------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                   |
      +=======================+=======================+===============================================================================+
      | version               | Object                | Specifies the version details.                                                |
      |                       |                       |                                                                               |
      |                       |                       | For details, see :ref:`Table 4 <en-us_topic_0133254024__table1928194220218>`. |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------+

-  **version** field data structure

   .. _en-us_topic_0133254024__table1928194220218:

   .. table:: **Table 4** **version** field data structure description

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                                                                                                                           |
      +=======================+=======================+=======================================================================================================================================================================================+
      | id                    | String                | Specifies the version ID, for example, v1.0.                                                                                                                                          |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | links                 | List<Link>            | Specifies the API URL.                                                                                                                                                                |
      |                       |                       |                                                                                                                                                                                       |
      |                       |                       | For details, see :ref:`Table 5 <en-us_topic_0133254024__table69851542624>`.                                                                                                           |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | version               | String                | Specifies the microversion. If APIs of a version support microversions, the maximum microversion supported is returned. If microversions are not supported, this field is left empty. |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the version status. The options are as follows:                                                                                                                             |
      |                       |                       |                                                                                                                                                                                       |
      |                       |                       | -  **CURRENT**: indicates a primary version.                                                                                                                                          |
      |                       |                       | -  **SUPPORTED**: indicates an old version that is still supported.                                                                                                                   |
      |                       |                       | -  **DEPRECATED**: indicates a deprecated version that may be deleted later.                                                                                                          |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated               | String                | Specifies the version release time, which is a UTC time. For example, the release time of v1.0 is 2016-12-09T00:00:00Z.                                                               |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | min_version           | String                | Specifies the microversion. If APIs of a version support microversions, the minimum microversion supported is returned. If microversions are not supported, this field is left empty. |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  **Link** field data structure

   .. _en-us_topic_0133254024__table69851542624:

   .. table:: **Table 5** Link field data structure

      ==== ====== ======================
      Name Type   Description
      ==== ====== ======================
      href String Specifies the API URL.
      rel  String self
      ==== ====== ======================

-  Example response

   **Status code: 200**

   .. code-block::

      {
          "version": {
              "id": "v1.0",
              "links": [
                  {
                      "rel": "self",
                     "href": "https://API URL/v1.0"
                  }
              ],
              "version": "",
              "status": "CURRENT",
              "updated": "2016-12-09T00:00:00Z",
              "min_version": ""
          }
      }

Status Codes
------------

For details, see :ref:`Status Code <en-us_topic_0171146972>`.

Error Codes
-----------

For details, see :ref:`Error Codes <en-us_topic_0121230887>`.

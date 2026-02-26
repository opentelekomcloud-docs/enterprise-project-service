:original_name: en-us_topic_0133254023.html

.. _en-us_topic_0133254023:

Querying All API Versions
=========================

Function
--------

This API is used to query the versions of EPS APIs.

URI
---

GET /

Request
-------

Example request

.. code-block:: text

   GET https://{EPS endpoint}/

Response
--------

**Status code: 200**

-  Parameter description

   .. table:: **Table 1** Parameters in the response body

      +-----------------------+-----------------------+-----------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                 |
      +=======================+=======================+=============================================================================+
      | versions              | Array                 | Specifies the list of all versions.                                         |
      |                       |                       |                                                                             |
      |                       |                       | For details, see :ref:`Table 2 <en-us_topic_0133254023__table14997943587>`. |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------+

-  **versions** field data structure

   .. _en-us_topic_0133254023__table14997943587:

   .. table:: **Table 2** versions field data structure

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                                                                                                                                          |
      +=======================+=======================+======================================================================================================================================================================================================+
      | id                    | String                | Specifies the version ID, for example, v1.0.                                                                                                                                                         |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | links                 | List<Link>            | Specifies the API URL.                                                                                                                                                                               |
      |                       |                       |                                                                                                                                                                                                      |
      |                       |                       | For details, see :ref:`Table 3 <en-us_topic_0133254023__table9352054589>`.                                                                                                                           |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | version               | String                | Specifies the microversion. If the API version supports microversions, the maximum microversion supported is returned. If microversions are not supported, this field is left empty.                 |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | Specifies the version status. The options are as follows:                                                                                                                                            |
      |                       |                       |                                                                                                                                                                                                      |
      |                       |                       | -  **CURRENT**: indicates a primary version.                                                                                                                                                         |
      |                       |                       | -  **SUPPORTED**: indicates an old version that is still supported.                                                                                                                                  |
      |                       |                       | -  **DEPRECATED**: indicates a deprecated version that may be deleted later.                                                                                                                         |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated               | String                | Specifies the version release time, which is a UTC time. For example, the release time of v1.0 is 2016-12-09T00:00:00Z.                                                                              |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | min_version           | String                | Specifies the microversion. If the API version supports microversions, the system returns the supported minimum microversion. If microversions are not supported, the system returns an empty value. |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  **Link** field data structure

   .. _en-us_topic_0133254023__table9352054589:

   .. table:: **Table 3** Link field data structure

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
          "versions": [
              {
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
          ]
      }

Status Codes
------------

For details, see :ref:`Status Code <en-us_topic_0171146972>`.

Error Codes
-----------

For details, see :ref:`Error Codes <en-us_topic_0121230887>`.

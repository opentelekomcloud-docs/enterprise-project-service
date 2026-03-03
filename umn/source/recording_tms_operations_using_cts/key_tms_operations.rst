:original_name: em_01_0046.html

.. _em_01_0046:

Key TMS Operations
==================

:ref:`Table 1 <em_01_0046__en-us_topic_0141727052_t032f2bc26b86407fb436eb796b592848>` lists the enterprise project operations that will be recorded by CTS.

.. _em_01_0046__en-us_topic_0141727052_t032f2bc26b86407fb436eb796b592848:

.. table:: **Table 1** EPS operations recorded by CTS

   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Operation                                                                                                    | Resource Type             | Trace Name               |
   +==============================================================================================================+===========================+==========================+
   | Creating an enterprise project                                                                               | enterpriseProject         | createEnterpriseProject  |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Modifying an enterprise project                                                                              | enterpriseProject         | modifyEnterpriseProject  |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Disabling an enterprise project                                                                              | enterpriseProject         | disableEnterpriseProject |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Enabling an enterprise project                                                                               | enterpriseProject         | enableEnterpriseProject  |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Migrating resources                                                                                          | enterpriseProjectResource | migrate                  |
   |                                                                                                              |                           |                          |
   | .. note::                                                                                                    |                           |                          |
   |                                                                                                              |                           |                          |
   |    You can perform this operation by calling an API. Currently, EPS console does not support this operation. |                           |                          |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Removing resources and their associated resources                                                            | enterpriseProjectResource | associatedMigrateOut     |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Adding resources and their associated resources                                                              | enterpriseProjectResource | associatedMigrateIn      |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Adding resources to an enterprise project.                                                                   | enterpriseProjectResource | migrateIn                |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+
   | Removing resources                                                                                           | enterpriseProjectResource | migrateOut               |
   +--------------------------------------------------------------------------------------------------------------+---------------------------+--------------------------+

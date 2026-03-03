:original_name: em_01_0036.html

.. _em_01_0036:

What Are the Differences Between IAM Projects and Enterprise Projects?
======================================================================

IAM Projects
------------

IAM projects group and **physically isolate** resources in the same region.

Resources cannot be transferred between IAM projects, but can only be deleted and then rebuilt.

|image1|

Enterprise Projects
-------------------

Enterprise projects group, manage, and **logically isolate** resources of an enterprise in all regions.

An enterprise project can contain resources in multiple regions, and resources can be directly transferred between enterprise projects.

You cannot create projects in IAM after enabling Enterprise Management.

|image2|

.. |image1| image:: /_static/images/en-us_image_0000001088191991.png
.. |image2| image:: /_static/images/en-us_image_0000001088335419.png

schedule_get
============

The schedule API is a one way API that allows you to get information from the class schedule in OpenStudio.

get call
--------

Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you
make.

+------+--------------------------------------------------+
| json | https://<hosting location>/api/schedule_get.json |
+------+--------------------------------------------------+
| xml  | https://<hosting location>/api/schedule_get.xml  |
+------+--------------------------------------------------+

**Mandatory variables**

+------+-------------------------------------------------------+
| user | API user                                              |
+------+-------------------------------------------------------+
| key  | Key for API user                                      |
+------+-------------------------------------------------------+
| week | ISO week number of year, 1 - 52 (or 53 if applicable) |
+------+-------------------------------------------------------+
| year | year as YYYY                                          |
+------+-------------------------------------------------------+

**Optional variables**

===========  =====================================================================================================================
TeacherID     If specified, only returns classes containing the specified teacher. This works for regular and substitute teachers
ClassTypeID     If specified, only returns classes of the specified type
LocationID     If specified, only returns classes for the specified location
LevelID         If specified, only return classes with the specified level
SortBy       Accepted values: 'location' and 'time'
             - **location** Sort by location and then time 
             - **time** Sort by time and then location
===========  =====================================================================================================================

**Example calls**

.. code-block:: bash

    https://<hosting location>/api/schedule_get.json?user=test&key=test&week=1&year=2014
    https://<hosting location>/api/schedule_get.xml?user=test&key=test&week=1&year=2014&TeacherID=1&ClassTypeID=1


**Return**

The global structure for the returned values is as follows. The actual values returned differ slightly
depending on whether called as XML or JSON.

+-------------------------+---------------------------+
| data (top level) (list) | date (yyyy-mm-dd)         |
+-------------------------+---------------------------+
|                         | classes :sup:`1` (list)   |
+-------------------------+---------------------------+

1. The following data is provided for a class

=============  =======  ==================
Variable       Type     Description
=============  =======  ==================
LocationID     String   ID of location
-------------  -------  ------------------
Location       String   Name of location
-------------  -------  ------------------
Starttime      String   Start time of class
-------------  -------  ------------------
Endtime        String   End time of class
-------------  -------  ------------------
ClassTypeID    String   ID of classtype
-------------  -------  ------------------
ClassType      String   Name of classtype
-------------  -------  ------------------
TeacherID      String   ID of teacher
-------------  -------  ------------------
TeacherID2     String   ID of second teacher
-------------  -------  ------------------
Teacher        String   Name of teacher (Firstname lastname)
-------------  -------  ------------------
Teacher2       String   Name of second teacher (Firstname lastname)
-------------  -------  ------------------
LevelID        String   ID of class level
-------------  -------  ------------------
Level          String   Name of class level
-------------  -------  ------------------
Subteacher     Boolean  True if the current teacher or second teacher is a substitute teacher False when not
-------------  -------  ------------------
Cancelled      Boolean  True if the class has been cancelled False when not
-------------  -------  ------------------
Holiday        Boolean  True when a holiday is found in OpenStudio for the location of this classFalse when not
=============  =======  ==================
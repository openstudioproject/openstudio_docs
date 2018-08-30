============
schedule_get
============

The schedule API is a one way API that allows you to get information from the class schedule in OpenStudio.

1.get call:
============
Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you
make.

json
    https://<hosting location>/api/schedule_get.json
xml
    https://<hosting location>/api/schedule_get.json
    
Mandatory variables:
---------------------

user
    API user
key
    Key for API user
week
    ISO week number of year, 1 - 52 (or 53 if applicable)
year
    year as YYYY



Optional variables:
-------------------

TeacherID
    If specified, onlz returns classes containing the specified teacher. This works for regular and substitute teachers
ClassTypeID
    If specified, only returns classes of the specified type
LocationID
    If specified, only returns classes for the specified location
LevelID
    If specified, only return classes with the specified level
SortBy
    Accepted values: 'location' and 'time'
        - **location** Sort by location and then time 
        - **time** Sort by time and then location




Example calls:
--------------

.. code-block:: bash

    https://<hosting location>/api/schedule_get.json?user=test&key=test&week=1&year=2014
    https://<hosting location>/api/schedule_get.xml?user=test&key=test&week=1&year=2014&TeacherID=1&ClassTypeID=1


2.Return:
=========

The global structure for the returned values is as follows. The actual values returned differ slightly
depending on whether called as XML or JSON.

data (top level) 
    classtypes :sup:`1`

    teachers :sup:`2`

    locations :sup:`3`

    classes :sup:`4` 
        Monday - Sunday
            date (yyyy-mm-dd)


1. The folowing data is provided for classtypes:
------------------------------------------------

Type String:
    Id
        ID of classtype
    Name
        Name of classtype
    Link
        URL to classtype page on website (optional)
    Description
        Description of classtype
    LinkThumbLarge
        URL to larg thumbnail for class (400px*400px)
    LinkThumbSmall
        URL to small thumbnail for class (50px*50px)

2. The following data is provided for teachers:
-----------------------------------------------

Type String:
    Id
        ID of teacher
    Name
        Name of teacher
    Bio
        Biography of teacher
    LinkToBio
        URL to teachers' online Biography
    LinkThumbLarge
        URL to teacher picture large thumbnail

3. The following data is provided for locations:
------------------------------------------------

Type String:
    Id
        ID of location
    Name
        Name of location

4. The following data is provided for a class:
----------------------------------------------

Type String:
    LocationID  
        ID of location
    Location    
        Name of location
    Starttime
        Start time of class
    Endtime
        End time of class
    ClassTypeID
        ID of classtype
    ClassType
        Name of classtype
    TeacherID
        ID of teacher
    TeacherID2
        ID of second teacher
    Teacher
        Name of teacher (Firstname lastname)
    Teacher2
        Name of second teacher (Firstname lastname)
    LevelID
        ID of class level
    Level
        Name of class level
    CancelledDescription
        Description of why the class is cancelled (If entered)
    HolidayDescription
        Description of holiday
    MaxStudents
        Max. spaces in this class
    CountAttendance
        Number of students attending (having booked) 
    CountReservations
        Number of reservations
    CountReservationsCancelled
        Number of cancelled reservations
    BookingStatus
        Booking status
    BookingSpacesAvailable
        Available spaces for online booking 
    LinkShop
        URL to class in OpenStudio shop

Type Boolean:
    Subteacher
        True if the current teacher or second teacher is a substitute teacher 
        False when not
    Cancelled
        True if the class has been cancelled 
        False when not
    Holiday
        True when a holiday is found in OpenStudio for the location of this class
        False when not

Type Date:
    BookingOpen
        Date from which bookings for this class will be accepted (YYYY-MM-DD)
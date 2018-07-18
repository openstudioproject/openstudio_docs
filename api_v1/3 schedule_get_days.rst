=================
Schedule_Get_Days
=================
The schedule API is a one way API that allows you to get information from the schedule in OpenStudio. This chapter described the schedule_get_days endpoint which allows you get get schedule information in a selected range of dates.


1. Get Call:
============
Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you
make.

JSON
    https://<hosting location>/api/schedule_get_days.json
XML
    https://<hosting location>/api/schedule_get_days.xml

1.1. Mandatory Variables:
-------------------------

user
    API user
key
    Key for API user
date_start
    Start of day range as yyyy-mm-dd
date_end
    End of day range as yyyy-mm-dd

1.2. Optional Variables:
-------------------------

TeacherID
    If specified, only returns classes containing the specified teacher. This works for
    regular and substitute teachers
ClassTypeID
    If specified, only returns classes of the specified type
LocationID
    If specified, only returns classes for the specified location
LevelID
    If specified, only return classes with the specified level
SortBy
    Accepted values: 'location' or 'time' 

    location: Sort by location and then time

    time: Sort by time and then location
    
1.3. Example Calls:

 .. code-block:: bash

    https:///api/schedule_get_days.xml?user=test&key=test&date_start=2016-01-01&date_end=2016-01-06

    https:///api/schedule_get_days.xml?user=test&key=test&date_start=2016-01-01&date_end=2016-01-06&TeacherID=1&ClassTypeID=1
1.2. Return:
=============

The global structure for the returned values is as follows. The actual values returned differ slightly
depending on whether called as XML or JSON.

data (top level) (dict)
    schedule (list)
        date (yyyy-mm-dd)
        
        classes :sup:`1`
    classtypes (list):sup:`2`

    teachers (list):sup:`3`

    locations (list):sup:`4`

    levels (list):sup:`5`

1.The following data is provided for a class:
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

2. The folowing data is provided for classtypes:
-------------------------------------------------

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

3. The following data is provided for teachers:
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

4. The following data is provided for locations:
------------------------------------------------

Type String:
    Id
        ID of location
    Name
        Name of location

5. the following data is provided for levels:
---------------------------------------------

Type String:
    Id
        ID of level
    Name
        Name of level
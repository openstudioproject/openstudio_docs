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
--------------------

    .. code-block:: bash

        https:///api/schedule_get_days.xml?user=test&key=test&date_start=2016-01-01&date_end=2016-01-06

        https:///api/schedule_get_days.xml?user=test&key=test&date_start=2016-01-01&date_end=2016-01-06&TeacherID=1&ClassTypeID=1

2. Return:
===========

    The global structure for the returned values is as follows. The actual values returned differ slightly
    depending on whether called as XML or JSON.

    data (top level) (dict)
        schedule (list)
            date (yyyy-mm-dd)
            
            classes :sup:`1`

        classtypes (list) :sup:`2`

        teachers (list) :sup:`3`

        locations (list) :sup:`4`

        levels (list) :sup:`5`

1.The following data is provided for a class:
----------------------------------------------

    BookingOpen
        [Date] Date from which bookings for this class will be accepted (YYYY-MM-DD)
    BookingStatus
        [String] Booking status
    BookingSpacesAvailable
        [String] Available spaces for online booking
    Cancelled
        [Boolean] True if the class has been cancelled 
        False when not
    CancelledDescription
        [String] Description of why the class is cancelled (If entered)
    ClassTypeID
        [String] ID of classtype
    ClassType
        [String] Name of classtype
    CountAttendance
        [String] Number of students attending (having booked) 
    CountReservations
        [String] Number of reservations
    CountReservationsCancelled
        [String] Number of cancelled reservations 
    Endtime
        [String] End time of class
    Holiday
        [Boolean] True when a holiday is found in OpenStudio for the location of this class
        False when not
    HolidayDescription
        [String] Description of holiday
    LevelID
        [String] [String] ID of class level
    Level
        [String] Name of class level
    LinkShop
        [String] URL to class in OpenStudio shop
    LocationID  
        [String] ID of location
    Location    
        [String] Name of location
    MaxStudents
        [String] Max. spaces in this class
    Starttime
        [String] Start time of class
    Subteacher
        [Boolean] True if the current teacher or second teacher is a substitute teacher 
        False when not    
    TeacherID
        [String] ID of teacher
    TeacherID2
        [String] ID of second teacher
    Teacher
        [String] Name of teacher (Firstname lastname)
    Teacher2
        [String] Name of second teacher (Firstname lastname)    

2. The folowing data is provided for classtypes:
-------------------------------------------------

    Description
        [String] Description of classtype
    Id
        [String] ID of classtype
    Link
        [String] URL to classtype page on website (optional)
    LinkThumbLarge
        [String] URL to larg thumbnail for class (400px*400px)
    LinkThumbSmall
        [String] URL to small thumbnail for class (50px*50px)
    Name
        [String] Name of classtype
    
3. The following data is provided for teachers:
-----------------------------------------------

    Bio
        [String] Biography of teacher
    Id
        [String] ID of teacher
    LinkToBio
        [String] URL to teachers' online Biography
    LinkThumbLarge
        [String] URL to teacher picture large thumbnail
    Name
        [String] Name of teacher    

4. The following data is provided for locations:
------------------------------------------------

    Id
        [String] ID of location
    Name
        [String] Name of location

5. the following data is provided for levels:
---------------------------------------------

    Id
        [String] ID of level
    Name
        [String] Name of level
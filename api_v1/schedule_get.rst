============
schedule_get
============

    The schedule API is a one way API that allows you to get information from the class schedule in OpenStudio.

1. Call
============

    Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you
    make.

    json
        https://<hosting location>/api/schedule_get.json
    xml
        https://<hosting location>/api/schedule_get.json
    
Mandatory variables
---------------------

    user
        API user
    key
        Key for API user
    week
        ISO week number of year, 1 - 52 (or 53 if applicable)
    year
        year as YYYY

Optional variables
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

Example calls
--------------

    .. code-block:: bash

        https://<hosting location>/api/schedule_get.json?user=test&key=test&week=1&year=2014
        https://<hosting location>/api/schedule_get.xml?user=test&key=test&week=1&year=2014&TeacherID=1&ClassTypeID=1

2. Return
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

1. The folowing data is provided for classtypes
------------------------------------------------

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

2. The following data is provided for teachers
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

3. The following data is provided for locations
------------------------------------------------

    Id
        [String] ID of location
    Name
        [String] Name of location

4. The following data is provided for a class
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
        [String] ID of class level
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
    Teacher
        [String] Name of teacher (Firstname lastname)
    Teacher2
        [String] Name of second teacher (Firstname lastname)
    TeacherID
        [String] ID of teacher
    TeacherID2
        [String] ID of second teacher

    
    
    
    
        
        
        

        

        


        
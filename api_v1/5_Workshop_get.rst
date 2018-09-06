=============
Workshop_Get
=============

    The workshops API is a one way API that allows getting information from OpenStudio about a single workshop. Please note that the workshop has to be marked as visible in the shop in OpenStudio.

1.Get Call
==========

    Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you

    JSON
        https://<hosting location>/api/workshop_get.json
    XML
        https://<hosting location>/api/workshop_get.xml

1.1. Mandatory Variables:
-------------------------

    user
        API user
    key
        Key for API user
    id
        Workshop ID
    
1.2. Example Calls:
--------------------

    .. code-block:: bash

        https:///api/schedule_get_days.xml?user=test&key=test&date_start=2016-01-01&date_end=2016-01-06

        https:///api/schedule_get_days.xml?user=test&key=test&date_start=2016-01-01&date_end=2016-01-06&TeacherID=1&ClassTypeID=1


2. Return:
==========

    The global structure for the returned values is as follows. The actual values returned differ slightly
    depending on whether called as XML or JSON.

    data (top level) (list)
        workshop :sup:`1`
    
1. The following data is provided for a workshop:
-------------------------------------------------

    Activities :sup:`3`
        [List] List of activities for workshop, sorted by date and then time
    Cancelled
        [Boolean] True if the class has been cancelled 
        False when not
    Description
        [String] Workshop Description
    Enddate
        [Date] Workshop end Date
    Endtime
        [String] End time of class
    Holiday
        [Boolean] True when a holiday is found in OpenStudio for the location of this class
        False when not
    id
        [BigInt] ID of workshop
    LinkImage
        [String] URL to uploaded picture
    LinkThumbLarge
        [String] URL to large thumbnail for workshop (400px * 400px)
    LinkThumbSmall
        [String] URL to small thumbnail for workshop (50px * 50px)
    LinkShop
        [String] URL to OpenStudio shop 
    Location    
        [String] Name of location
    LocationID
        [BigInt] ID of location   
    Name    
        [String] Workshop Name
    Preview
        [String] Workshop Preview
    Price
        [Float] Workshop price (for full workshop product)
    Startdate
        [Date] Workshop start Date
    Starttime
        [String] Start time of class
    Subteacher
        [Boolean] True if the current teacher or second teacher is a substitute teacher 
        False when not
    Tagline
        [String] Workshop Tagline
    Teacher :sup:`2`
        [Dict] Dict with teacher info 
    Teacher2 :sup:`2`
        [Dict] Dict with teacher2 info    

2. Teacher fields:
------------------

    Bio
        [String] Teacher Biography
    id 
        [BigInt] ID of teacher
    LinkToBio
        [String] URL to teacher biography
    LinkThumbLarge
        [String] URL to large thumbnail for workshop (400px * 400px)
    LinkThumbSmall
        [String] URL to small thumbnail for workshop (50px * 50px)
    Name
        [String] Teacher Name
    Role
        [String] Teacher Role
    Website
        [String] URL to teacher Website
  
3. Activity:
-------------

    Date
        [Date] Date of activity
    Endtime
        [String] End time (HH:MM)
    id
        [BigInt] ID of activity
    Location
        [String] Name of location
    LocationID
        [BigInt] ID of location
    Name
        [String] Name of activity
    Starttime
        [String] Start time (HH:MM)
    Teacher
        [String] Name of teacher
    Teacher2
        [String] Name of teacher2
    TeacherID
        [BigInt] ID of teacher
    TeacherID2
        [BigInt] ID of teacher2

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
    

1.The following data is provided for a workshop:
------------------------------------------------

Type BigInt:
    id
        ID of workshop
    LocationID
        ID of location   

Type String:
    Location    
        Name of location
    Starttime
        Start time of class
    Endtime
        End time of class
    Name    
        Workshop Name
    Tagline
        Workshop Tagline
    Preview
        Workshop Preview
    Description
        Workshop Description
    LinkImage
        URL to uploaded picture
    LinkThumbLarge
        URL to large thumbnail for workshop (400px * 400px)
    LinkThumbSmall
        URL to small thumbnail for workshop (50px * 50px)
    LinkShop
        URL to OpenStudio shop 

Type Dict:
    Teacher :sup:`2`
        Dict with teacher info 
    Teacher2 :sup:`2`
        Dict with teacher2 info

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

Type Float Variables:
    Price
        Workshop price (for full workshop product)

Type Date:
    Startdate
        Workshop start Date
    Enddate
        Workshop end Date

Type List:
    Activities :sup:`3`
        List of activities for workshop, sorted by date and then time

*2.Teacher fields:
------------------

Type BigInt Variables:
    id 
        ID of teacher

Type String Variables:
    Name
        Teacher Name
    Role
        Teacher Role
    Bio
        Teacher Biography
    LinkToBio
        URL to teacher biography
    Website
        URL to teacher Website
    LinkThumbLarge
        URL to large thumbnail for workshop (400px * 400px)
    LinkThumbSmall
        URL to small thumbnail for workshop (50px * 50px)


*3. Activity:
--------------

Type BigInt Variables:
    id
        ID of activity
    LocationID
        ID of location
    TeacherID
        ID of teacher
    TeacherID2
        ID of teacher2

Type String Variables:
    Name
        Name of activity
    Location
        Name of location
    Starttime
        Start time (HH:MM)
    Endtime
        End time (HH:MM)
    Teacher
        Name of teacher
    Teacher2
        Name of teacher2

Type Date Variable:
    Date
        Date of activity

    
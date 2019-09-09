=============
workshops_get
=============

    The workshops API is a one way API that allows you to get information from OpenStudio about upcoming workshops.

1. Call
===========

    Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you make.

        JSON    
            https://<hosting location>/api/workshops_get.json

        XML     
            https://<hosting location>/api/workshops_get.xml
    
1.1 Mandatory Variables
------------------------
    user
        API user
    key
        Key for API user


1.2 Example Calls
------------------
    .. code-block:: bash

        https://<hosting location>/api/workshops_get.json?user=test&key=test


2. Return
=========

    The global structure for the returned values is as follows. The actual values returned differ slightly
    depending on whether called as XML or JSON.  

    data (top level)(list)
        workshops (list) :sup:`1`

1. The following data is provided for a workshop
------------------------------------------------

    Description
        [String] Workshop description
    Enddate
        [Date] Workshop end Date
    Endtime
        [String] End time of class
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
        [String] Workshop short description
    Price
        [Float] Workshop price (for full workshop product)
    Startdate
        [Date] Workshop start Date
    Starttime
        [String] Start time of class
    Tagline
        [String] Workshop Tagline
    Teacher :sup:`2`
        [Dict] Dict with teacher info
    Teacher2 :sup:`3`
        [Dict] Dict with teacher2 info
    
2. Teacher fields
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


=============
Workshops_Get
=============

    The workshops API is a one way API that allows you to get information from OpenStudio about upcoming workshops.
        
    1 Get Call:
    -----------

        Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you make.
        
            JSON    
                https://<hosting location>/api/schedule_get.json
        
            XML     
                https://<hosting location>/api/schedule_get.xml
        
    
    1.1 Mandatory Variables:
    ~~~~~~~~~~~~~~~~~~~~~~~~

        user
            API user
        key
            Key for API user
    
    1.2 Example Calls:
    ~~~~~~~~~~~~~~~~~~
    
        .. code-block:: bash

            https://<hosting location>/api/workshops_get.json?user=test&key=test
   
    2 return:
    ---------

        The global structure for the returned values is as follows. The actual values returned differ slightly
        depending on whether called as XML or JSON.  
        data (top level)(list)
            workshops (list) :sup:`1`
    
    1.The following data is provided for a workshops:
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    
        Type BigInt Variables:
            id
                ID of workshop
            LocationID
                ID of location
        
        Type String Variables:
            Name
                Workshop Name
            Tagline
                Workshop Tagline
            Preview
                Workshop short description
            location
                Name of location
            Starttime
                Start time of class
            Endtime
                End time of class
            Description
                Workshop description
            LinkImage
                URL to uploaded picture
            LinkThumbLarge
                URL to large thumbnail for workshop (400px * 400px)
            LinkThumbSmall
                URL to small thumbnail for workshop (50px * 50px)
            LinkShop
                URL to OpenStudio shop

        Type Date Variables:
            Startdate
                Workshop start Date
            Enddate
                Workshop end Date

        Type Dict Variables:
            Teacher :sup:`2`
                Dict with teacher info
            Teacher2 :sup:`3`
                Dict with teacher2 info
        
        Type Float Variables:
            Price
                Workshop price (for full workshop product)
        
        2.Teacher fields:
        ~~~~~~~~~~~~~~~~~

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

        
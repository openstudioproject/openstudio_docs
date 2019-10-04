=====================
school_classcards_get
=====================

    Returns information from school - subscriptions

1. Call
=============

    Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you
    make.

    JSON
        https://<hosting location>/api/school_classcards_get.json
    XML	
        https://<hosting location>/api/school_classcards_get.xml
 
1.1 Mandatory Variables
------------------------
    user	
        API user
    key
        Key for API user

1.2 Example Calls
------------------

    .. code-block:: bash

        https://<hosting location>/api/school_classcards_get.json?user=test&key=test

2. Return
==========

    The global structure for the returned values is as follows. The actual values returned differ slightly
    depending on whether called as XML or JSON.

    data (top level) (list)
        Class card1 :sup:`1`

1. The following data is provided for a class card
----------------------------------------------------

    Classes 
    	[Int] Number of classes
    Description
    	[String] Card description
    LinkShop
        [String] URL to subscription page in OpenStudio shop
    Name	
        [String] Card name
    Price
    	[Float]	Card price
    TrialCard
    	[Boolean] True if this is a trial card, else False
    Unlimited
    	[Boolean] True if unlimited classes, else False
    Validity
    	[Int] Validity number
    ValidityUnit
    	[String] 'day', 'week' or 'month' 
   
    
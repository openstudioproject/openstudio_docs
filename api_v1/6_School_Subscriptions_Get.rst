=========================
School_Subscriptions_Get
=========================

    Returns information from school - subscriptions

1 Get Call:
===========

Calls can be made as JSON and as XML. Both return the same data, just formatted according to the call you make.

    JSON    
        https://<hosting location>/api/schedule_get.json

    XML     
        https://<hosting location>/api/schedule_get.xml
    

1.1 Mandatory Variables:
------------------------

user
    API user
key
    Key for API user


1.2 Example Calls:
------------------

.. code-block:: bash

    https://<hosting location>/api/school_subscriptions_get.json?user=test&key=test


2 return:
=========

    The global structure for the returned values is as follows. The actual values returned differ slightly
    depending on whether called as XML or JSON.  

    data (top level)(list)
        Subscriptions :sup:`1`

1. The following data is provided for a subscription:
------------------------------------------------------

    Classes
        [Int] Number of Classes
    Name
        [String] Subscription Name
    Price
        [Float] Subscription Price
    SubscriptionUnit
        [String] 'week' or 'month' / unit to define number of Classes
    Unlimited
        [Boolean] True if unlimited classes, else False





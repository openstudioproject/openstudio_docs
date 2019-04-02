Manage subscription credits
===========================

This page describes how to manage credits for customers subscriptions. One subscription credit equals access to one class. 

Configuring school subscriptions
--------------------------------
The following fields for a school subscription define credit behavior

1. Classes
2. Classes per
3. Reconciliation classes
4. Credits validity (days)

**Classes & Classes per**
    Classes define the numer of classes a week or month. When classes are defined per week, OpenStudio will automatically calculate the right number of credits for a month when giving out credits.
    *Example: 1 class a week for a month with 31 days would be 4.4 credits*

**Reconciliation classes**
    Like in the example above, some months might have 5 Mondays, so 4.4 credits isn't enough. The field *Reconciliation classes* allows you to define now many negative credits a customer can accumulate on this subscription. Or in other words, how many classes customers can attend on this subscription without having credits.
    Looking at a whole year, customers will get enough credits, but might have a temporary shortage depending on the number of Mondays, Tuesdays, etc. in a month. 

**Credits validity (days)**
    Number of days subscription credits will be valid. Think of it like the minutes on your phone subscription, when they're not used within a certain period, they expire and can no longer be used.


Adding credits for all subscriptions
------------------------------------
After settings the fields above for all appropriate subscriptions under school and adding subscriptions to customers, it's possible to add credits to all subscriptions for the selected month in one go.

Go to automation in the main menu and select *Customer subscriptions*. Click the *Add credits* button. After choosing the month for which credits should be added, click the *Add credits* button in the top right and wait a short while. This operation might take a few minutes when there are a few hundred (or more) subscriptions.
The operation will continue in the background, you can continue working as usual. After a few minutes you can come back or refresh the page to get a status update.


Expiring credits
----------------
When *Credits validity* is set for one or more school subscriptions, you can expire credits. 
Go to customers in the main menu and select *Subscription credits*. Select the tab *Expired credits*. Click the *Expire* button in the top right of the page to remove all expired credits from all subscriptions.


Credit mutations for a single subscription
------------------------------------------
Go to customers - subscriptions - edit a subscription - go to the credits tab. Here you can add credit mutations (add and subtract) by using the add button.






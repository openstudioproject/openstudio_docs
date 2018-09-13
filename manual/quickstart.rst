==========
Quickstart
==========

1 Installation
==============
    Please go to readthedocs for the latest installation manual

2 Getting Started
=================

    The first things you'll want to do to get started with OpenStudio is set up your school. You can access the school properties using the school menu at the top of the screen. Below is a list of the different properties available and their purpose.

2.1 Teachers
------------

    Before classes can be added to the schedule, at least one teacher should be specified.

    In the teachers list there is a class types button for every teacher. Using this button you can set the types of classes this teacher is willing and able to teach.
    Later when adding or editing a class and selecting a teacher who is nor marked as a teacher for that class type, a notification will be shown when saving the class.

2.2 Subscriptions & Class Cards
-------------------------------

    Here you configure the different kinds of subscriptions and classcards offered by your school. 

2.3 Discovery
-------------

    Discovery is used to specify how customers found your school. Here you could for example add things like "Google", "Referral by a friend" or "Advertisement spring 2013". What you enter here will appear in a drop down list in the edit customer pages. After filling out this field for at least one customer you can go to statistics --> discovery and see a chart of the distribution of the different ways customers have found your school. This allows you to keep track of the efficacy of different kinds of advertisement and marketing.

2.4 Practice Levels
-------------------

    This creates a list of levels that can be applied to customers and classes. For example you might want to keep track of whether customers should take introduction courses or not or whether certain classes are appropriate for them. 

2.5 Class Types
---------------

    Here you can specify what types of classes are taught at your school. You should add at least one class type to be able to add classes later.

2.6 Locations
-------------
    Using locations you can specify the location of classes. You should add at least one location to be able to add classes later.

2.8 Languages
--------------

    Languages are defined here. You can link languages to customers as a reminder for yourself in which language you should communicate with them.

2.9 Holidays
------------

    Need a break? For each location you can specify when you're having a holiday and OpenStudio wil automatically cancel all classes during that period.

2.10 Keys
---------

    There is nothing to fill out here. When the field "Key Number" is filled out when adding or editing a customer, the customers appear in this list sorted by key number. This page can be used to quickly get an overview or search for keys when your school distributed keys, swipe cards or anything like that to customers so they can enter your school

3 Schedule
==========

    Use the schedule to keep track of your classes, attendance for those classes, holidays and more.

3.1 Adding Classes
------------------

    To add a new class to the schedule, click the add "Add a new class" on the right. 
    To quickly add similar classes, click the edit button (the one with the pencil icon) on the Schedule page and then use the duplicate link to duplicate the class. You'll be taken to an edit page of the duplicated class.

3.2 Managing Classes
--------------------

    For each class you can keep track of regular students using reservations, have a waitinglist for reservations, keep track of attendance and set the status of a particular class.
    These statuses are:

        - Normal
        - Subteacher
        - Cancelled
        - Open (no teacher)
        - 4 Customers

    You can store a lot of information about your customers in OpenStudio. 

4.1 Information
----------------

    - General information like name, address and comments.
    - Subscriptions
    - Class cards
    - Class attendance
    - Class reservations
    - Workshop registrations
    - Payment information
    - Documents
    - Tasks (to-do list)
    - Invoices

4.2 Pause A Subscription
------------------------

    To pause a subscription go to the edit page for a customer and then click the subscriptions link and then the "Pause" button for the subscription you wish to pause. 

5 Workshops
===========

    To add a workshop, follow these steps:

    Add a workshop
    Add at least 1 activity to the workshop agenda
    (Optional) Add a product that links to the activity you just created
    Note: All activities are automatically linked to the auto-created "Full workshop" product.

5.1 Manage
----------

5.1.1 Products
~~~~~~~~~~~~~~

    A product is a collection of activities from the agenda. By default a full workshop product is created, which can't be deleted. By adding customers to a product you can keep track of payments and automatically get an overview of expected attendance in the workshop agenda.

5.1.2 Agenda
~~~~~~~~~~~~

    The agenda page is used to manage activities for a workshop. You can schedule new activities, mange existing ones and keep track of the attendance for all activities.

5.2 Tasks
---------
    Here you can keep track of things to do or to remember for this workshop. These memos will show up on the pinboard.

5.3 Quick Stats
---------------

    This page gives a quick overview of the revenue and which cities most of the customers are from.

6 Settings
==========

    OpenStudio is configured using the settings pages

6.1 General
-----------

    General settings

    Separate customers by location 
    In case you have multiple physical locations where you teach, you might want to keep track of which customer is attending classes where. By turning this option on, an extra dropdown box appears in the customers edit pages and collection & payment export pages allowing selection of the location.
    Show welcome message 
    In case you want to turn the welcome message back on, you can do so here.
    Currency 
    This is used in the csv export for collection and payment with customers. Add the 3 letters specifying the currency, eg. EUR, USD, GBP, KRW, etc.
    Date format 
    Choose how dates are displayed.

6.2 Permissions
---------------

    Starting with OpenStudio 2.05 a group based permissions model is available in OpenStudio. This model allows you to determine who can see/edit what.
    It's basic structure is like this: 
    A user is a member of a group. A group has permissions assigned to it which determine what the members of the group can see and edit.

    First go to settings --> users & groups --> groups and add a new group.
    Once the group is added, you'll see a permissions link for that group in the groups list. By clicking that link you can set which permissions that group has.
    The next step is to add a user to that group.
    Go to preferences --> users & groups --> users and select a user. Then click the group link left of the edit button. In the menu shown now you can select a group to add the user to. 

    Please note that the group 'admin' always has full access to everything.

7 Best Practices
================

7.1 Subscriptions
-----------------

    When using the collection exports to collect payments from customers using automated software, make sure only the subscriptions for which the fees have to collected are listed in the required months. For example when collecting the fees for one subscription a month, make sure there is only one subscription active for each customer. The best way to do this is to change subscriptions at the month boundaries, so the old subscription ends at the last day of the month and the new subscription starts at the first day of the next month. This way there is no overlap between the old and new subscriptions and no duplicate collections occur.

8 License & Disclaimer
======================

    OpenStudio is licenced under the GPL version 2 or later.

Disclaimer Of Warranty
======================

    THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, WARRANTIES OF QUALITY, PERFORMANCE, NON-INFRINGEMENT, MERCHANTABILITY, OR FITNESS FOR A PARTICULAR PURPOSE. FURTHER, EDWIN VAN DE VEN DOES NOT WARRANT THAT THE SOFTWARE OR ANY RELATED SERVICE WILL ALWAYS BE AVAILABLE.

    Limitations Of Liability

    YOU ASSUME ALL RISK ASSOCIATED WITH THE INSTALLATION AND USE OF THE SOFTWARE. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS OF THE SOFTWARE BE LIABLE FOR CLAIMS, DAMAGES OR OTHER LIABILITY ARISING FROM, OUT OF, OR IN CONNECTION WITH THE SOFTWARE. USERS OF THE SOFTWARE ARE SOLELY RESPONSIBLE FOR DETERMINING THE APPROPRIATENESS OF USE AND ASSUME ALL RISKS ASSOCIATED WITH ITS USE, INCLUDING BUT NOT LIMITED TO THE RISKS OF PROGRAM ERRORS, DAMAGE TO EQUIPMENT, LOSS OF DATA OR SOFTWARE PROGRAMS, OR UNAVAILABILITY OR INTERRUPTION OF OPERATIONS.
==========
School
==========

  The school section of OpenStudio is where you will define all of your operational parameters,
  resources and products for your organization.

  *** Before continuing, a note about Profiles ***
  Customers, Teachers and Employees are all profiles that will appear as customers
  in the customer list under Customers -> Customer List.  A teacher or an employee has an
  additional flag marked in the account of the profile you create.  This is particularly useful when
  students are also Teachers or support staff (employees) to the school.
  You will not create separate records for one person who has multiple roles, but
  rather modify their user account and add check boxes to the flags for the additional
  account types, or roles, that you wish the 'customer' to have.

  OpenStudio will detect email addresses that are already in use to prevent the creation of duplicate profiles.

  You must assign an access group to each new Teacher or Employee profile if you would like their account to be
  valid for login, otherwise the profile won't have any access permissions to use the back end (non customer facing side) of the system.
  A profile does not need to have an access group assigned if you are simply defining the profile for record keeping/scheduling
  and the person does not need to login and participate on the OpenStudio system.


1. Teachers
-------------

From School -> Teachers you can manage profiles who Teach at your school.  You need to define
at least one teacher before you will be able to schedule any classes.  In order to add
a teacher, click +ADD at the top right corner of the screen.  You will be presented with
popup where you need to enter the Teachers First Name, Last Name and email address.

If your Teacher was already an employee or customer in the system, you only need to check
that additional role in the Account tab of the profile.

After you have added a Teacher, you will need to click the gray NO box to turn it
into a green YES box under the column Classes if they will teach classes and under
Events if they will be teaching at events.  The default value for both is NO.
If you do not change the status to YES, you will not be able to assign the Teacher
to a Class if this setting has not been changed.

  Actions menu

    Fixed Rate Payments
      You can define default fixed rate payments as well as custom per class payments.
        * Please note there are also per attendance schedules available *

    Travel Allowance
      You can define travel reimbursements for a Teacher per Location if you wish to
      disburse an additional payment when the instructor teaches a class at that location.

    Assign Class types
      You can assign class types that a teacher is qualified to teach.  This is helpful
      for schedulers who will receive an alert that an instructor doesn't have a particular
      class type certification associated with their profile when assigning that teacher to a class.

    Edit
      By clicking on edit you will open edit profile page.

2. Employees
-------------

From School -> Employees, you can manage profiles who are support staff at your school.

In order to add an Employee, click +ADD at the top right corner of the screen.  You will be presented with
the new Employee form.  Enter the Employee's First Name, Last Name and email address.
Click Save in order to store the new employee.

Clicking the square button to the right of the Profile name with a Pencil in it will open the Edit Profile page.
Clicking the square button to the right of the profile name with an X in it will remove the Employee flag from
the profile.


3. Memberships
----------------

    You can define memberships in OpenStudio which can be used give your customers access to
    Membership only products and benefits such as access to classes, subscriptions or class cards.
    You could, for example, make certain classes or special prices available only to customers who have an active Membership.

    To define a membership, from School -> Memberships, click +ADD at the top right corner of the screen.

    Name
      Enter the name of the membership

    Description
      You may optionally describe the membership

    Price incl VAT
      Price of membership including any applicable taxes

    Tax rate
      Optional Tax Rate

    Validity
      Define the unit number of Days, Weeks or Months that the membership will be valid.
      Select the Unit Measurement of validity time in the next field.

    Validity IN
      Select the unit measure of validity in Days, Weeks or Months.

    Terms & Conditions
      Here you can describe the terms and conditions of the membership.

      The following options are relevant for when you have accounting software
      integration enabled:

      G/L Account - General Ledger Account in your accounting software

      Cost Center - Cost Center code in your accounting software.


4. Subscriptions
-----------------

    You can define Subscriptions in OpenStudio which can be used for monthly reoccuring
    charges for access to classes.  Subscriptions are structured like Class Cards,
    but they automatically bill the customer each month for continued access to classes.

    In order to create a subscription, from School -> Subscriptions, click +ADD at the
    top right of the windows.  Fill out the form and click Save.  After clicking Save
    you will return the the list of subcriptions.  You can now define the prices for
    the subscription product.  In order to do so, click the edit button (with Pencil icon) and
    then click on the Prices tab.  then click +ADD at the top right of the screen.
    Fill out the form and click Save.

    See below for additional details about the fields in Subscriptions:

    Show In Shop
      Checking this box makes this subscription available for purchase directly using
      the online interface by your customers.
      If you clear the checkbox, only employees will be able to sell a subscription.

    Show on Website
      Checking this box makes the subscription visible to API integrated applications / websites.

    Name
      The name of the subscription is the title of the subscription products

    Description
      Describe the benefits that are included in this subscriptions

    Sort Order
      Order in which subscriptions are shown in the shop. Higher numbered items are shown first.
      Subscriptions with the same sort order number are sorted alphabetically by name.

    Classes
      Here you will define the number of classes that your customer may take per unit measure.  (week/month)

    Classes Per
      Here you define the unit measure for the number of classes defined above.
      The customer can be granted access to a number of classes per Week or Month.

    Reconciliation Classes
      Number of classes a customer can take without credits on this subscription.

    Credit validity (days)
      Here you define how many days the class credits are valid for.  If you leave the
      box empty, class credits will not expire.

    Unlimited Classes
      Checking this box grants unlimited access to classes.  The number of classes defined
      above are ignored when this box is checked.

    Terms & Conditions
      Describe the terms and conditions of the subscription here.

    Requires Membership
      Here you can set a required membership for this card. Without the membership
      defined in this field, customers won't be able to get this subscription or
      use it to attend classes.

    Quick Stats Amount

      Define an amount of money to use for Class Income Statistics.
      As for subscriptions, it's impossible to know the exact revenue for each class
      until the end of the month. This amount will be used to create rough "Quick Stats"
      estimates of class revenue.

    Registration Fee
      This Amount will be added to the first invoice for this subscription. Set to 0
      for no registration fee.

    PRICES tab
      The prices tab is where you will define the reoccuring subscription charge per date period.

    Start Date
      Define the date the defined price becomes active.

    End date
      Define the last day that this price is available.

    *** For class income calculation purposes, it is recommended to define a price for each
    month starting from the first day of the month and ending on the last day of that month. ***

    Monthly Fee (Including (VAT/TAX))
      Define the price charged for this subscription during this price period.

    Tax Rate
      If at tax is levied for this product, select the rate here.  The rates available
      in this dropdown are defined in Settings -> Finance -> Tax Rates Tab.

    G/L Account
      General ledger account ID in your accounting software (For accounting software integration)

    Cost Center
      Cost center code in your accounting software (For accounting software integration)




5. Class Cards
---------------

6. Class Types
---------------

7. Locations
-------------

8. Shifts
-------------

9. Holidays
-------------

10. Languages
-------------

11. Practice Level
------------------

12. Discovery
-------------

13. Keys
-------------

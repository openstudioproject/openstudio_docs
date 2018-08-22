Teacher payments
============================

OpenStudio supports fixed rate and attendance based payments for teachers. Monthly credit invoices specifying the class payments and travel allowances can be generated for each teacher.

.. toctree::
    :maxdepth: 1
    :caption: Teacher payments configuration

    teacher_payments/fixed_rate
    teacher_payments/attendance_based
    teacher_payments/travel_allowance


Create credit invoices
----------------------

After configuring a payment rate system for teachers, credit invoices can be created.


#. Go to Finance - Teacher payments in the main menu
#. Go to the tab "Not verified"
#. Click Find classes and choose a range of dates to search for any classes not yet found
#. Verify all classes or verify individual classes
#. Go to the tab "Verified" 
#. By clicking process credit invoices will be created for all verfied classes or verified classes in a chosen range



Paying credit invoices
----------------------

The easiest way to pay the credit invoices for teachers is to create a payment batch. 
Navigate to Finance - Batch payments and click add. Choose Teacher payments when asked what kind of batch to create.
Here fill out the form with desired data and click *Save*.

The batch created will contain all teacher payment credit invoices with status *Sent* for the selected month.

In the batch view, click the *Export* button to export the batch. OpenStudio exports the batch items in a .csv file. This file can be transformed to different formats. For example to the PAIN format by using an application called IBANC. 

Set the batch status to *Sent to Bank* when the batch has been sent to the bank. This will automatically add payments to all invoices in the batch and set the invoice statuses to *paid*.



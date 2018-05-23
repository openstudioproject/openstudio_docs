Fixed rate
==========

Fixed rate payments allow setting a fixed rate for classes and travel allowance for classes in selected school locations.
A default rate should be set for each teacher, where class specific rates can be set to override the default rate.
Travel allowance is entered by location, if a class is given in a selected location the travel allowance is added.
Consecutive classes won't generate travel allowance twice on the invoice. A class is seen as consecutive if the start time of the next class is within 30 minutes of the previous class on the same day.

Overview
--------

Using fixed rate teacher payments has a few steps to set up and components used,

#. Store teacher bank account information
#. Setting rates and travel allowances for teachers
#. Create credit invoices
#. Paying credit invoices by creating a payment batch

Store bank account information
------------------------------

School - Teachers and click the edit button for the selected teacher and navigate to the *Payment info* tab.
Add the bank account information on this page.

Setting rates and travel allowances
-----------------------------------

Go to School - Teachers and click the Payments button for the selected teacher. Add a default rate and any class specific rates.
Travel allowances can also be added here. Travel allowances are added by location.

Create credit invoices
----------------------

Go to Finance - Teacher payments and click the *Create invoices* button. Select the month for which invoices are to be created and click the *Create invoices* button.
A credit invoice will be created for all teachers matching the following conditions,

- Has taught classes in the selected month
- A default rate has been set

*Note: When a credit invoice is already found for a teacher, no new invoice will be created. This means this function can be used safely as many times as required for a month, without any existing invoices being overwritten*

Paying credit invoices
----------------------

The easiest way to pay the credit invoices for teachers is to create a payment batch. 
Navigate to Finance - Batch payments and click add. Choose Teacher payments when asked what kind of batch to create.
Here fill out the form with desired data and click *Save*.

The batch created will contain all teacher payment credit invoices with status *Sent* for the selected month.

In the batch view, click the *Export* button to export the batch. OpenStudio exports the batch items in a .csv file. This file can be transformed to different formats. For example to the PAIN format by using an application called IBANC. 

Set the batch status to *Sent to Bank* when the batch has been sent to the bank. This will automatically add payments to all invoices in the batch and set the invoice statuses to *paid*.

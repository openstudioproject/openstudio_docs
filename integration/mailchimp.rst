MailChimp
====================

Summary
-------
Customers can manage their subscription to your MailChimp mailing lists from their personal profile using this integration. A customer is shown as subscribed based on whether the email address they used to log on to OpenStudio is found in the MailChimp mailing list.
Please be aware that it's not possible to manually subscribe customers to mailing lists, as in many parts of the world it's now required that customers opt-in for mailing lists themselves.

*In case there is a demand for this feature, please let us know by creating an issue on our github page or commenting on it when an issue has already been created.*


Prerequisites
-------------
Before setting up MailChimp integratio in OpenStudion, make sure you have the following things ready. In case you can't find them, refer to the MailChimp knowledgebase or contact MailChimp support.

*. Your MailChimp username
*. Your MailChimp API key
*. The MailChimp *list_id* of any lists you would like your customers to be able to sign up for from OpenStudion


Setup
-----

**Entering the username and API key**

    1. Log in with an user account having admin privileges in OpenStudion
    2. Go to settings - Integration - MailChimp
    3. Enter your username and API key and Save

**Linking OpenStudio lists to your MailChimp mailing lists**

    1. Go to Settings - Mail - Mailing lists
    2. Add a mailing list (the name doesn't have to match the MailChimp name) and link the list to MailChimp by setting the desired MailChimp *list_id*. The *list_id* is what determines which name in OpenStudio is matched with which list in MailChimp.
    3. When based in the EU, make sure you have set a clear description of your mailing list and defined the frequency (eg. once a month).
    4. Save

**Enable Mailing lists in customer profiles**

    1. Go to settings - Shop - Customer profiles
    2. Check the *Mailing lists* checkbox
    3. Save

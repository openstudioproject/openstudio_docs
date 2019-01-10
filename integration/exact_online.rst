Exact Online
====================

Summary
-------

The Exact Online (https://www.exact.com/us/solutions/financial-management/) integration is a one way system. It assumes all data originates from OpenStudio. The following information can be transferred from OpenStudio to Exact Online:

- Invoices
- Invoice items
- Customers
- Customers Bank accounts
- Customers Bank account mandates



Prerequisites
-------------

Before setting up Exact Online integration in OpenStudion, make sure you have the following things ready. In case you can't find them, refer to the Exact Online knowledgebase or contact Exact support. Please keep in mind that the API urls change depending on your region. The client ID and secret are obtained using the Exact Online App center. When registering an app Exact Oline will ask for a Redirect URI. This is the base URL of your OpenStudio installation, followed by */exact_online/oauth2_success*. Also make sure the url starts with https, as Exact Online doesn't accept insecure redirect URI's. *eg. https://demo.openstudioproject.com/exact_online/oauth2_success*.

#. Exact Online Server auth URL
#. Exact Online Server rest URL
#. Exact Online Server token URL
#. Client Base URL (The base URL of your OpenStudio installation)
#. Exact Online API Client ID
#. Exact Online API Client Secret


Setup
-----

**OpenStudio settings**

Complete these steps before actually linking OpenStudio to Exact Online

    #. Set the GLAaccount field for all OpenStudio sellables. Classes (prices), event tickets, class cards, subscriptions and memberships. The values of these fields should correspond to the correct General Ledger Account numbers of Exact Online.
    #. Under Settings - Financial - Invoices - Groups, set the appropriate journal ID.
    #. Under Settings - Financial - Tax rates, edit each tax rate and set the appropriate Vat Code ID, as found in Exact Online.
    #. Under settings - Financial - Payment methods - edit each payment method and set the Accounting code to the payment methods ID as found in Exact Online.

**Establish link**

    #. Log in with an user account having admin privileges in OpenStudio
    #. Go to settings - Integration - Exact Online
    #. Enter data prepared in Prerequisites and click save
    #. Click the green *Authorize* button and follow the steps until redirected back to OpenStudio
    #. Choose a default Division and click back

The link between Exact Online and OpenStudio should be established.

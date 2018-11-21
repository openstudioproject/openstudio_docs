Update OpenStudio
-----------------

Below are the steps to upgrade OpenStudio 2017 (and later), for example from version 2017.1.0 to 2017.2.0. The steps are the same for all upgrades.

#. Create a backup of your web2py folder and your openstudio database. 
#. Check your backups, do they contain data and are you able to restore them to another location. (If you're not sure you can restore it, it doesn't count as a backup)
#. Check the web2py versions section in this manual to see if the web2py version is the same for the new version. In case a newer web2py version is required, download it and set it up. For more info on setting up web2py, please see the web2py documentation.
#. In case you don't have to upgrade the web2py installation, just remove the OpenStudio app using the web2py admin interface.
#. Extract the latest OpenStudio version in the web2py applications folder.
#. Next edit the application in the admin interface and edit appconfig.ini in the private folder to connect OpenStudio to the existing database.
#. Copy the databases folder, uploads folder and custom folders in views/templates from your web2py/applications/<OpenStudio_backup> to web2py/applications/<OpenStudio updated>.
#. Visit your openstudio url and add /upgrade at the end. *eg https://demo.openstudioproject.com/upgrade*
#. Open the OpenStudio url and you should be able to log in to the new version.


*In case you need help, paid support is offered.*
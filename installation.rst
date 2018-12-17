Installation
=============

This is a short guide to get OpenStudio running as quickly as possible. This setup is not recommended for production usage. For production usage you'd want to use something like nginx together with uwsgi and make sure you have a valid SSL certificate.

General
-------

**A note about time**

OpenStudio assumes system time is set to UTC and the timezone will be configured in Settings - System - General.
All (date)times in scheduled tasks are also set in UTC.

**A note about operating systems**

OpenStudio is developed and tested on Linux. In theory Windows and MacOS should be able to serve as a hosting platform as well. On paper all components should be compatible. Though note that this is untested and unsupported, so your mileage may vary.


Database
--------

In this manual MySQL will be assumed, if you prefer it, you can also use MariaDB. Depending on which platform you are using there are different ways to install the MySQL server. On Ubuntu Linux you could use the following command: 

.. code-block:: bash

    sudo apt-get install mysql-server-5.7

For Windows or Mac OS, please see this page to download the free version http://dev.mysql.com/downloads/mysql/ . 
Install it according to the manual of your operating system.
After installing the MySQL server, make sure the MySQL service is started and connect to the database using the mysql command-line tool. 

.. code-block:: bash

    mysql -u root -p 

Then create a database for OpenStudio, in this example the database name openstudio_db will be used.

.. code-block:: bash

    mysql> create database openstudio_db;
    mysql> grant all privileges on openstudio_db.* to 'your username goes here'@'localhost' identified by 'your password goes here';
    mysql> flush privileges;
    mysql> exit

That's it, now test the database by connecting using the command-line tool.

.. code-block:: bash

    mysql -u<username> -p<password> openstudio_db

If all goes well, you'll see the mysql> prompt again. Then exit the mysql command-line tool and resume with the next step. If you got an error message, troubleshoot and solve it before moving on.

Python 2.7
------------

If you're running a Linux distribution, it's very likely that a recent python 2.7 version has already been installed. Check it by typing 'python' in the terminal. 

For Windows you can use Python 2.7.12 (or later), pip ships with this version (get it from www.python.org).

For MacOS it's likely there's already a python installation, but it might be old if you're running an older version of MacOS. So you might want to use macports (or whatevery way you prefer) to install the python27 port. (www.macports.org)
Updating the system installed python version is not recommended. 

Once python is ready to go, use pip or easy_install (or whatever way you want) to install the required python packages. Open a terminal and type "pip install <packagename>" or type "easy_install <packagename>". If you installed a new python version, make sure that you're using the pip or easy_install for the right version.


Web2py
------


Now download web2py from www.web2py.com and extract it to a directory that's suitable for you.
Now you can start web2py by opening a terminal and browsing to the directory you extracted web2py in. Then open a terminal and using python run web2py.

Linux and Mac OS

.. code-block:: bash

    python web2py.py -a <choose a password>

Windows

.. code:: 
    
    c:\python27\python.exe web2py.py -a <choose a password>


Extract the OpenStudio release archive (zip or tar.gz) to the applications folder in your web2py installation.

Open a web browser and browse to http://localhost:8000, now you should have OpenStudio in the list of Installed applications on the left of the page. Click the manage button next to OpenStudio and select Edit from the drop down list that appears. In the models section of the edit page, click Edit to the left of appconfig.ini under private. Here is a line that needs to be edited. 

.. code:: 

    uri = mysql://user:password@localhost/openstudio_db

In a previous step we created a MySQl database to hold all the information. The uri option in this file tells OpenStudio how to connect to the MySQL database.
If you installed the MySQL server on the same computer, you can use 'localhost' as the server name.
After editing the file, scroll to the top of the page and save the file (you can also use Ctrl+S). 
Web2py will need to be restarted after editing appconfig.ini, the settings are only read when the framework is started.

Starting from version 2.07 Javascript (AJAJ) is used more to make the interface more user friendly. However to make it work, you should use a routes.py file in your web2py root folder to be able to run openstudio from an url like "http://demo.openstudioproject.com". The url shouldn't have the app name in it, a url like "http://localhost:8000/OpenStudio" will cause problems.
The *routes.py* file can look like this for example:

.. code-block:: python 

    routers = dict(     # base router
        BASE = dict(
            default_application = 'OpenStudio',
            domains = {
                    'demo.openstudioproject.com' : 'OpenStudio',
                    },
            applications = ['OpenStudio','admin'],
            controllers = 'DEFAULT'
        ),
    )

After adding the routes.py file in the web2py root folder, restart web2py. Make sure your DNS records or hosts file point to the correct name.


Scheduler
---------

Starting from version 2018.82 the Web2py Scheduler is required to use all features in OpenStudio. Please refer to the Web2py book for instructions on how to set up the scheduler: `Web2py book <http://web2py.com/books/default/chapter/29/13/deployment-recipes#Start-the-scheduler-as-a-Linux-service-upstart->`_.


Logging in
----------

Go to the address where you're hosting OpenStudio. If everything went well, there will be a login screen.

Default username and password
The default username and password are admin and admin for versions lower than 2.05.
For version 2.05 and newer, the default username and password are admin@openstudioproject.com and admin.
For version 3.0 and newer, the default username and password are admin@openstudioproject.com and OSAdmin1#.

Now you're ready to start.


Troubleshooting
---------------

In case you see an error like the one below, please check that the python interpreter you're using to run OpenStudio can find the python modules mentioned in the system requirements.

.. code-block:: python 

    "Cannot import module 'applications.openstudio.modules.pytz'"



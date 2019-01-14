Installation
=============

This is a short guide to get OpenStudio running on Ubuntu 18.04.1 LTS Desktop as quickly as possible. This setup is not recommended for production usage. For production usage you'd want to use something like nginx together with uwsgi and make sure you have a valid SSL certificate.
** Using this system without HTTPS will transmit unencrypted (easily interceptable and readable) information over the networks between you and the computer hosting the application. **

General
-------

**A note about time**

OpenStudio assumes system time is set to UTC and the timezone will be configured in Settings - System - General.
All (date)times in scheduled tasks are also set in UTC.

**A note about operating systems**

OpenStudio is developed and tested on Linux. In theory Windows and MacOS should be able to serve as a hosting platform as well. On paper all components should be compatible. Though note that this is untested and unsupported, so your mileage may vary.

Operating System
----------------

This installation manual is based specifically on deployment to Ubuntu 18.04.1 LTS Desktop which can be located here: https://www.ubuntu.com/download/desktop .  The Desktop distribution is used to simplify initial administration of Web2Py server which REQUIRES a secure connection either locally, remotely over SSH tunnel or HTTPS.  SSH tunnels and HTTPS are not covered in this manual.  Install said operating system to a computer or virtual machine before proceeding to follow these instructions.

While using said OS and especially while using a different OS, you may encounter different results or barriers to installation that require additional effort to overcome before proceeding to the next step.  Experience with the use of Linux operating system is assusmed and recommended.


Database
--------

In this manual we are deploying MySQL 5.7.  You can also use another database server, such as MariaDB.  Depending on which distribution or platform you are using there are different ways to install MySQL server. On Ubuntu Linux use the following command:

.. code-block:: bash

    sudo apt-get install mysql-server-5.7

For Windows or Mac OS, please see this page to download the free version http://dev.mysql.com/downloads/mysql/ .
Install it according to the manual of your operating system.
After installing the MySQL server, make sure the MySQL service is started and connect to the database using the mysql command-line tool.

.. code-block:: bash

    sudo mysql -u root -p

Then create a database for OpenStudio, in this example the database name openstudio_db will be used.

.. code-block:: bash

    mysql> create database openstudio_db;
    mysql> grant all privileges on openstudio_db.* to 'your username goes here'@'localhost' identified by 'your password goes here';
    mysql> flush privileges;
    mysql> exit

The output should look something like this assuming your linux username is 'user':

.. code-block:: bash

    mysql> create database openstudio_db;
        Query OK, 1 row affected (0.00 sec)

    mysql> grant all privileges on openstudio_db.* to 'user'@'localhost' identified by 'password';
        Query OK, 0 rows affected, 1 warning (0.01 sec)

    mysql> flush privileges;
        Query OK, 0 rows affected (0.00 sec)

    mysql> exit
        Bye


That's it, now test the database by connecting using the command-line tool.

.. code-block:: bash

    mysql -u<username> -p<password> openstudio_db

If all goes well, you'll see the mysql> prompt again. Then exit the mysql command-line tool and resume with the next step. If you got an error message, troubleshoot and solve it before moving on.


Redis Server
------------

We need to install the database cashing server.  This can be done in Ubuntu Linux by typing the following command:

.. code-block:: bash

    sudo apt-get install redis-server


For Windows or Mac OS, you can download Redis Server from https://redis.io/download  Follow the application vendors instsructions for installing and running Redis on Windows or Mac.


Python 2.7
------------

For Windows you can use Python 2.7.12 (or later), pip ships with this version (get it from www.python.org).

For MacOS it's likely there's already a python installation, but it might be old if you're running an older version of MacOS. So you might want to use macports (or whatever way you prefer) to install the python27 port. (www.macports.org)
Updating the system installed python version is not recommended and you are doing so at your own risk.

Install Python 2.7 on Ubuntu Linux by issuing the following commands:

.. code-block:: bash

    sudo apt-get install python
    sudo apt-get install python-pip

Install the following Python Modules:

openpyxl, html2text, pytz, redis (2.10.6), mollie-api-python (2.x), weasyprint (0.42.3), Pillow, pybarcode, qrcode, mailchimp3

In order to install said modules in Ubuntu Linux, issue the following commands:

.. code-block:: bash

    sudo -H pip install openpyxl
    sudo -H pip install html2text
    sudo -H pip install pytz
    sudo -H pip install redis==2.10.6
    sudo -H pip install mollie-api-python==2.0.6
    sudo -H pip install weasyprint==0.42.3
    sudo -H pip install Pillow
    sudo -H pip install pybarcode
    sudo -H pip install qrcode
    sudo -H pip install mailchimp3


Web2py
------

Now download web2py from www.web2py.com and extract it to a directory that's suitable for you.  In this example I'll use a seperate folder in the Home Directory called www-dev

.. code-block:: bash

    sudo mkdir /home/www-dev
    sudo chmod 777 /home/www-dev
    cd /home/www-dev
    wget https://mdipierro.pythonanywhere.com/examples/static/web2py_src.zip
    unzip web2py_src.zip


**Please note that setting directory permissions to 777 should never be done in production**

Now we need to download and extract the latest OpenStudio release archive (zip or tar.gz) to the applications folder in your web2py installation.  The latest release van be found here: https://github.com/openstudioproject/openstudio/releases

In this manual version 2018.84.2 will be assumed.
After extraction we need to rename the extracted folder to 'openstudio'  If you neglect to rename the extracted folders, the special characters will prevent the application from being detected by web2py.  In order to do so in Ubuntu Linux, issue the following commands:


.. code-block:: bash

    cd /home/www-dev/web2py/applications
    wget https://github.com/openstudioproject/openstudio/archive/v2018.84.2.zip
    unzip v2018.84.2.zip
    mv openstudio-2018.84.2 openstudio


Now you can start web2py by opening a terminal and browsing to the directory you extracted web2py in and then using python run web2py.

To start web2py on Ubuntu Linux, issue the following commands:

.. code-block:: bash

    cd /home/www-dev/web2py
    python web2py.py -a <choose a password>

Windows

.. code::

    c:\python27\python.exe web2py.py -a <choose a password>


Open a web browser ON THE HOST COMPUTER (this is why we've installed desktop gui in this guide) and browse to http://localhost:8000  Now click on the hamburger button (The three horizontle lines for menu) on the top right of the page and click 'My Sites'.  You should have openstudio in the list of Installed applications on the left of the page.  If you don't, check that the directory name of the openstudio folder under /web2py/applications/ doesn't have any special characters in it and restart web2py.

Click the manage button next to OpenStudio and select Edit from the drop down list that appears. Near the bottom of the list in the Private Files section of the edit page, click Edit to the left of appconfig.ini  - Here is a line that needs to be edited.

.. code::

    uri = mysql://user:password@localhost/openstudio_db

In a previous step we created a MySQl database to hold all the information. The uri option in this file tells OpenStudio how to connect to the MySQL database.  You need to replace 'user:password' with the username and password you authorized during the create database step.

If you installed the MySQL server on the same computer, you can use 'localhost' as the server name.
After editing the file, scroll to the top of the page and save the file (you can click the floppy disk icon or also use Ctrl+S).
If already started, Web2py will need to be restarted after editing appconfig.ini, the settings are only read when the framework is started.

At this stage the application is available for login from the host computer at http://localhost:8000/openstudio - HOWEVER, it is liable to malfunction unpredictably until you configure a routes.py file.  By default, when web2py runs, it binds to 127.0.0.1.  If you want to be able to access the application remotely from the host computer, you need to start web2py with additional argument -i {ip address}.  You can define the binding port with -p {port number}.  You cannot administrate your sites in web2py admin unless you are running it localhost and access from same computer or remote computer via SSH tunnel OR bind to a routeable IP and access using HTTPS.

Starting from version 2.07 Javascript (AJAJ) is used more to make the interface more user friendly. However to make it work, you should use a routes.py file in your web2py root folder to be able to run openstudio from an url like "http://demo.openstudioproject.com". The url shouldn't have the app name in it, a url like "http://localhost:8000/OpenStudio" will cause problems.
The *routes.py* file can look like this for example:

.. code-block:: python

    routers = dict(     # base router
        BASE = dict(
            default_application = 'openstudio',
            domains = {
                    'demo.openstudioproject.com' : 'openstudio',
                    },
            applications = ['openstudio','admin'],
            controllers = 'DEFAULT'
        ),
    )

After adding the routes.py file in the web2py root folder, restart web2py. Make sure your DNS records or hosts file point to the correct name.

E-Mail
---------

In order for OpenStudio to send emails for activities such as Invoices & Payments,
you'll need to configure you email server settings.
Click the manage button next to OpenStudio and select Edit
from the drop down list that appears. Near the bottom of the list in the Private
Files section of the edit page, click Edit to the left of appconfig.ini
  - Here are the lines that need to be edited:

  ; smtp address and credentials
[smtp]
server = localhost:2525
sender = OpenStudio | Dev <your@emailaddress.com>
;login  = username:password
tls    = false
ssl    = false



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

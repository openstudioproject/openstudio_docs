System requirements
====================

Please keep in mind that OpenStudio is a web application which needs more resources then a standard website.

Hardware
-----------------

**Minimum**

- 2 (v)CPU cores*
- 2 GB of RAM
- 1 GB of free storage


**Recommended**

- 2 (v)CPU cores*
- 4 GB of RAM
- 10 GB of free storage
- SSD storage

\* With performance comparable to at least a second generation Intel Core i5 @ 2.0 Ghz


Hosting platform
-----------------

While in theory everything used to build OpenStudio should run on Windows and MacOS as well, it's only tested on Linux.
For a production system, this is probably the best choice.

**General**

* Python 3.4 or later (Python 2.7 for any release before 2019.08)
* MySQL 5.5 or later database
* Redis server (Tested using version shipped with Ubuntu 18.04 - 4.0.9-1)
* Web2py (http://www.web2py.com)


**Optional but recommended for a production setup**

* Nginx
* uWSGI
* SSL Certificate

You might want to have a look at `Let's Encrypt <https://letsencrypt.org/>`_ and support the project if you can.

**Python Mododules v2019.08 and later**

Install requirements using 

*pip install -r requirements.txt*

requirements.txt is found in the root of the OpenStudio application folder. Using a virtual environment is highly recommended.
Virtualenvwrapper is a big help when managing your virtual envs. https://virtualenvwrapper.readthedocs.io/en/latest/

**Python Modules v2019.01 and later**

* openpyxl
* html2text
* pytz
* redis (3.2.1)
* mollie-api-python (2.x)
* weasyprint (0.42.3)
* Pillow
* pybarcode
* pyqrcode
* qrcode
* mailchimp3


**Python Modules v2018.82 and later**

* openpyxl
* html2text
* pytz
* redis (2.10.6)
* mollie-api-python (2.x)
* weasyprint (0.42.3)
* Pillow
* pybarcode
* pyqrcode
* qrcode
* mailchimp3


**Python Modules v2018.81 and earlier**

* openpyxl
* html2text
* pytz
* redis (2.10.6)
* mollie-api-python 1.4.2 (not compatible with 2.x)
* weasyprint (0.42.3)
* Pillow
* pybarcode
* pyqrcode
* mailchimp3

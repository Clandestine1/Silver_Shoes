# Setting up a basic Django application
###### by LaShauna Walker and Dashiell Lumas
## Overview
Django (/ˈdʒæŋɡoʊ/ jang-goh) is a free and open source web application framework, written in Python. A web framework is a set of components that helps you to develop websites faster and easier. Released 21 July 2005.
### Django Reinhardt
<a href="http://imgur.com/njkQ85h"><img src="http://i.imgur.com/njkQ85h.jpg" title="source: imgur.com" /></a>
####Pioneer of 'Hot' Jazz guitar
## Django ORM
ORMs provide a high-level abstraction upon a relational database that allows a developer to write Python code instead of SQL to create, read, update and delete data and schemas in their database.
 
## Installation and Setup Instructions
Let's get started by opening up our terminal and running the following command:
``
brew install python
``
This command will install Python 2.7. We decided to brew install python because it comes with a whole slew of features that will be a pain in the ass for you to go find by yourself, like ``pip``!!
For learning purposes we chose 2.7 over 3.0; due to the fact that many Django-related documentation and learning material is predicated upon python 2.7 installation. 
``
pip install django
``
OR
``
sudo pip install django
``
The above command will install the Django framework.
Pip is a package management system that installs software for us, kind of like ``gem install`` or ``npm install``
Generating a basic application structure
``django-admin startproject mysite`` 
generates the following file structure
``
mysite/
manage.py
    
    mysite/
        __init__.py
        settings.py
        urls.py
        wsgi.py
``
Starts your server here: http://127.0.0.1:8000/
``python manage.py runserver``
## Regex!!!!!
```
from django.conf.urls import include, url
from django.contrib import admin
```
```
urlpatterns = [
   url(r'^admin/', admin.site.urls),
   ]
```
This line means that for every URL that starts with admin/, Django will find a corresponding view.
^ for the beginning of the text
Anything else in the URL definition will be taken literally.
Another example: http://127.0.0.1:8000/post/1/
regex expression: ^post/(\d+)/$
#### Significance: 
^post/ is telling Django to take anything that has post/ at the beginning of the url (right after ^)
(\d+) means that there will be a number (one or more digits) and that we want the number captured and extracted
/ tells django that another / character should follow
$ then indicates the end of the URL meaning that only strings ending with the / will match this pattern

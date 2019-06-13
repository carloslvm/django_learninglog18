# Django Notes (First Steps)
At the time I am uploading this repo, I am giving my first steps
with django framework. The version used for this small project
was Django 1.8 when the current version at the time I am uploading
this repo is Django 2.2.

I started this project by following the tutorial found in Python
Crash Course book. Because I was getting troubles with the
differences with the syntaxes between versions 2.2 and 1.8,
I decided to use the same version of the book in order to get
familiar with the process.

The purpose of this markdown document is summarize the process
followed in the book in order to be consulted it for future projects.

## Process Summary
### Setting up the development environment
* Creating a Virtual Environment:

```
$ virtualenv my_env --python=python3
```

* Activate the Virtual Environment:

```
$ source my_env/bin/activate
```

* Create a source directory and cd into it (optional):

```
(my_env)my_env$ mkdir -v src
(my_env)my_env$ cd src
```

* Install Django:

```
(my_env)my_env/src$ pip install Django==1.8
```

* Start a Django project:

```
(my_env)my_env/src$ django-admin startproject my_project .
```

* Create the database:

```
(my_env)my_env/src$ python manage.py migrate
```

* Run the development server:

```
(my_env)my_env/src$ python manage.py runserver
```

## Starting an App
1. Creating first app:

```
(my_env)my_env/src$ python manage.py startapp my_app
```

2. You have to create your models in the models.py file located
in my\_env/src/my\_app/models.py

3. Activate your models by adding them to the settings.py file,
where **INSTALLED_APPS** list is located. You can find this file at
my\_env/src/my\_project/settings.py.

4. Every time you make changes to the models.py file and
settings.py file, you will have to apply migrations:

```
(my_env)my_env/src$ python manage.py makemigrations
(my_env)my_env/src$ python manage.py migrate
```

## Admin Site
* Create the admin user (also called superuser):

```
(my_env)my_env/src$ python manage.py createsuperuser
```

* Register your models in the admin.py file located at
my\_env/src/my\_app/admin.py

During this process, if you want to add more things to your
project you will find yourself playing with the models.py file
located whithin your app directory.Make sure you apply migrations
every time you change the content of the models.py file, 
and then register your models to the admin.py file.

You also can create more apps whithin your project, but make sure
to add them in the settings.py file in order to activate them.

Once you're done with registering your models in the admin.py
file, you will be able to get access to the admin site and see
the result of your models.

## Mapping URL
1. Here you decide what URLs are needed in the project. The home 
page is the base because this is the URL that people use
to access to the project. Before you start creating other
pages, edit the urls.py file located at 
my\_env/src/my\_project/urls.py, here is where you set up
the home page.

2. Create a second urls.py file at my\_env/src/my\_app/, the
urls.py located at the project level must match with this
file for the home page.

3. At this point, it's time to write the views. In order to
do that you have to edit the vews.py file located whithin
the app directory.

## Creating a Template
1. Inside the directory my\_env/src/my\_app/ create
directory called templates, then in templates create another
directory with the same name of the app (in this case my\_app).

2. Make a file called index.html and write the template
for the home page there. Once it's done, run the development
server to see if it's working. This was a test template in the
tutorial.

## Building Additional Pages
1. Make a file called base.html in the same directory as index.html,
this will be the parent template. You will have to apply template
inheritance in order to create more pages.

2. You may have to edit the index.html if needed to apply
the concept of inheritance.

3. You will have to write a template per view or page you want
to create.

## Important Files
In conclusion, the files you're going to play with most of the time
are:

1. ### Project Level:

    * settings.py file located at the project level for activating your apps
    and probably for modifying your databases (for example: changing sqlite
    for postgresql).

    * urls.py file, the one that is located at the project level to set up
    the home page.

2. ### App Level:

    * models.py, to define the data that your web app is going to
    contain.

    * urls.py, to set up the apps urls.

    * views.py, to show the content of the pages.

    * templates, to create the pages.

## Note on pages
Making web pages with Django consists of three stages:

1. Defining URLs.

2. Writing views.

3. Writing templates.

## Recommended Knowledge for Django

1. Object Oriented Programming with Python.

2. HTML.

3. Bootstrap.

4. Javascript.

5. CSS.

6. Database (MySQL, PostgeSQL, Cassandra, MariaDB, etc).

## Reset Password
In case you forget your admin password, run the
following command to change it:
```
(my_env)my_env/src$ python manage.py changepassword <user_name>
```

# Basic Commands for Django Shell

## QuerySet
The QuerySet is the list of objects of a given model.
It allows you to read data from the database.

Enter the Django shell by typing the following command in terminal.

```
$ python manage.py shell
```

## List of commands

1. Displaying the objects on the web app:

```
>>> from app.models import Pizza
>>> Pizza.objects.all()
```
The word "Pizza" is a class example. You write these classes in
the models.py file.

2. Getting the ID of the object:

```
>>> Pizza.objects.get(id=1)
```

3. Creating a new object:

```
>>> Pizza.objects.create(name='Italian Pizza')
```
The arguments passed to the commands are the  same fields as the
attributes assigned in your classes.

## Important Note

Each time you modify your models, you'll need to restart the shell
to see the effects of those changes.

4. ID for users created:

```
>>> from django.contrib.auth.models import User
>>> User.objects.all()
>>> for user in User.objects.all():
....    print(user.username, user.id)

```

5. Bootstrap installation in your Django project:

```
(my_env) my_env$ pip install django-bootstrap3
```

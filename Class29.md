# Django Custum User Model

## Django Best Practices: Custom User Model

- Django ships with a built-in User model for authentication and if you'd like a basic tutorial on how to implement log in, log out, sign up and so on see the Django Login and Logout tutorial for more.

## Setup

To start, create a new Django project from the command line. We need to do several things:

- create and navigate into a dedicated directory called accounts for our code
- install Django
- make a new Django project called django_project
- make a new app accounts
- start the local web server
- Here are the commands to run:

```
# Windows
> cd onedrive\desktop\code
> mkdir pages
> cd pages
> python -m venv .venv
> .venv\Scripts\Activate.ps1
(.venv) > python -m pip install django~=4.0.0
(.venv) > django-admin startproject django_project .
(.venv) > python manage.py startapp accounts
(.venv) > python manage.py runserver

# macOS
% cd ~/desktop/code
% mkdir pages
% cd pages
% python3 -m venv .venv
% source .venv/bin/activate
(.venv) % python3 -m pip install django~=4.0.0
(.venv) % django-admin startproject django_project .
(.venv) % python3 manage.py startapp accounts
(.vent) % python3 manage.py runserver
```

Note that we did not run migrate to configure our database. It's important to wait until after we've created our new custom user model before doing so.

If you navigate to http://127.0.0.1:8000 you’ll see the Django welcome screen.

![django wlc](https://learndjango.com/static/images/django40_welcome.png)

## AbstractUser vs AbstractBaseUser

- There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser. In both cases we can subclass them to extend existing functionality however AbstractBaseUser requires much, much more work. Seriously, don't mess with it unless you really know what you're doing. And if you did, you wouldn't be reading this tutorial, would you?

So we'll use AbstractUser which actually subclasses AbstractBaseUser but provides more default configuration.


## Custom User Model

Creating our initial custom user model requires four steps:

- update django_project/settings.py
- create a new CustomUser model
- create new UserCreation and UserChangeForm
- update the admin

In settings.py we'll add the accounts app and use the AUTH_USER_MODEL config to tell Django to use our new custom user model in place of the built-in User model. We'll call our custom user model CustomUser.

Within INSTALLED_APPS add accounts at the bottom. Then at the bottom of the entire file, add the AUTH_USER_MODEL config.

```
# django_project/settings.py
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    "accounts",  # new
]
...
AUTH_USER_MODEL = "accounts.CustomUser"  # new
```

Now update accounts/models.py with a new User model which we'll call CustomUser.

```
# accounts/models.py
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass
    # add additional fields in here

    def __str__(self):
        return self.username
```

`(accounts) $ touch accounts/forms.py`

```
# accounts/forms.py
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm

from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")
```

Finally we update admin.py since the Admin is highly coupled to the default User model.

```
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ["email", "username",]

admin.site.register(CustomUser, CustomUserAdmin)
```

And we're done! We can now run makemigrations and migrate for the first time to create a new database that uses the custom user model.

`(.venv) > python manage.py makemigrations accounts`
`(.venv) > python manage.py migrate`
## Superuser

It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out. On the command line type the following command and go through the prompts.

`(.venv) > python manage.py createsuperuser`



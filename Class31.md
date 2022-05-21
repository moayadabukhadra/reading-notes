# Django REST Framework & Docker

## Linux Containers

Docker is really just Linux containers which are a type of virtualization.

Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm. How could multiple programmers use the same single machine? The answer was virtualization and specifically virtual machines which are complete copies of a computer system from the operating system on up.

## Containers vs Virtual Environments

Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer. Virtual environments are great.

But…virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python albeit they can refer to the proper version. So when we use Python 2.7 in a project, we’re pointing to an installation of Python 2.7 on the computer itself, not actually within the virtual environment.'

## Install Docker

To install Docker we need to download the desktop app on our computer and create a free account. The initial download of Docker might take some time to download. It’s a big file. Feel free to stretch your legs at this point!

Once Docker is done installing we can confirm the correct version is running. It should be at least version 19.

```
$ docker --version
Docker version 19.03.5, build 633a0ea
```

##  Library Website

Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework. It always must be added to a project after Django itself has been installed and configured.

Traditional Django
Navigate to the existing code directory on the Desktop and make sure you are not in a current virtual environment. You should not see (.venv) before the shell prompt. If you do, use the command deactivate to leave it. Make a new directory called library, create a new virtual environment, activate it, and install Django.

```
> cd onedrive\desktop\code
> mkdir library
> cd library
> python -m venv .venv
> .venv\Scripts\Activate.ps1
(.venv) > python -m pip install django~=4.0.0
```


```
├── django_project
│   ├── __init__.py
|   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
└── .venv/
```

The .venv directory was created with our virtual environment but Django has added a django_project directory and a manage.py file. Within django_project are five new files:

__init__.py indicates that the files in the folder are part of a Python package. Without this file, we cannot import files from another directory which we will be doing a lot of in Django!
asgi.py allows for an optional Asynchronous Server Gateway Interface to be run
settings.py controls our Django project’s overall settings
urls.py tells Django which pages to build in response to a browser or URL request
wsgi.py stands for Web Server Gateway Interface which helps Django serve our eventual web pages.
The manage.py file is not part of django_project but is used to execute various Django commands such as running the local web server or creating a new app. Let’s use it now with migrate to sync the database with Django’s default settings and start up the local Django web server with runserver.

```
(.venv) > python manage.py migrate
(.venv) > python manage.py runserver
```
```
(.venv) > python manage.py migrate
(.venv) > python manage.py runserver
```


Open a web browser to http://127.0.0.1:8000/ to confirm our project is successfully installed and running.

![web](https://djangoforapis.com/assets/images/00_welcome40.png)

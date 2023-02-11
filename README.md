
# Django Cheat Sheet Commands

This guide will provide you with the basic commands for working with Django.





## Installation

### Create virtual environment 

There are different ways to create python virtual environment, we will use python's default package
```bash
  python -m venv env_name
```
* replace env_name with your desired virtual environment name

### Activating the virtual environment
Linux / Mac Os
```bash
  source env_name/bin/activate
```
Windows
```bash
    env_name/Scripts/activate
```
* If you receive error that Windows can't run shell scripts check [this link](https://stackoverflow.com/questions/4037939/powershell-says-execution-of-scripts-is-disabled-on-this-system)

### Install django
```python
    pip install django
```


## Creating Project and Application
Creating Django Project
```bash
django-admin startprojct project_name .
```
* change project_name with the name of your project
* the . (dot) at the end is for the project to be created in the same folder

Creating Django Application
```bash
python manage.py startapp app_name
```
* change app_name with the name of your app

## Starting up the project
First we need to register the application with the project. We can do that by adding the application's name in the list INSTALLED_APPS, you can find the list in the folder project_name in the file settings.py

```python
INSTALLED_APPS = [
    ...
    'app_name',
]
```
The first time we start the project we have to make the default tables that come with django. In order to do that we need to run the migrate command.

```python 
python manage.py migrate
```
Now after all the migrations are completed we can finally start our project. We can start django project locally with the runserver command.

```python
python manage.py runserver
```
When the local server is started we can view our application on the localhost adress on port 8000. The local address are:

* localhost:8000
* 127.0.0.1:8000

If you need to stop the local server, just press CTRL + C


## Creating Super User

By default Django has two types of users, 
* user - with limited permissions
* superuser - with unlimited permissions

If you visit the Django's admin panel on the url 127.0.0.1:8000/admin/ you will be promtet to enter login credentials. In order to have those credentials and to be able to login on the admin panel we need to create superuser. We can do that with the following command.
```python 
python manage.py createsuperuser
```
After running the command you will be promted to enter credentials to create superuser. After the superuser is successfully created, run the server again and login with them in the admin panel.

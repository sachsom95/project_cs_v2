# Installing Django

- installation
- Create project
- Folder structure
- Running Server

First thing we need to do is install all the packages. We can do this in a seperate conda environment. This will be usedfull when we do the deployment.
So first create a new conda environment by typing 

```sh
conda create --name django_environment python=3.7
```
After installing the environment actiavate it. Now do a `pip install django`

To see if it installed do `python -m django --version`
Now we need to initialize a project.

```
django-admin startproject django_project
```
This should generate a project for us. So go there and open that up. This makes a project folder there. Inside that there will be another folder with same folder with project name. Along with that there is a `manage.py`. This file can be run to manage the entire website like running , migration, deployment checking.

Now the new folder created which has same name as our project has the following files

- __init__.py - tells python that this is a package
- asgi.py   
- settings.py - For managing all the settings. Contains the security keys, database settings, other django libraries which are used like crispy forms. 
- urls.py - This is used for mapping of URLS by default they have set one for admin
- wsgi.py - How web application and server communicate.

Now we can start a webserver and access the default site.
so go to location where we have `manage.py` then do 

```sh
python manage.py runserver 
```
This will run the server. Now go to localhost and port to see the website.

If we go to `/admin` this opens a new page.



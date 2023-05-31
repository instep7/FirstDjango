TECH WITH TIM TUTORIAL
------------------------------

Part I:
------------------------------
Create project with:
> django-admin startproject FirstDjango . (dot uses current directory as home directory)

The create app:
> python3 manage.py startapp main (main can be whatever you want)

Run server with:
> python3 manage.py runserver

def index in views.py

Create new file called 'urls.py' within the main folder

Add first urlpattern path 'index'

Goto urls.py in FirstDjango (add include import)
- Add second urlpattern path ''

REPEAT w/ v1 view

SUMMARY:
'urls.py' in the project folder (FirstDjango) sort down to 'urls.py' in the main app folder.  From there the route goes to views.py and calls the corresponding function
------------------------------

Part II:
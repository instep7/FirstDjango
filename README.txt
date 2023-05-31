TECH WITH TIM TUTORIAL
------------------------------

----------
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

----------
Part II:
------------------------------
settings.py >> add name of apps (main.apps...) to INSTALLED apps

Initialized DB with 'python3 manage.py migrate'

Created models in models.py

Created first migration with 'python3 manage.py makemigrations main'
Committed migration with 'python3 manage.py migrate'

Enter command line with 'python3 manage.py shell' to add items to database:
>>> from main.models import Item, ToDoList
>>> t = ToDoList(name='Anth\'s List')
>>> t.save()
>>> ToDoList.objects.all()
<QuerySet [<ToDoList: Anth's List>]>
>>> ToDoList.objects.get(id=1)
<ToDoList: Anth's List>
>>> t.item_set.all()
<QuerySet []>
>>> t.item_set.create(text='Go to mall', complete=False)
<Item: Go to mall>
>>> t.item_set.all()
<QuerySet [<Item: Go to mall>]>
>>> t.item_set.get(id=1)
<Item: Go to mall>

In main>urls.py, changed pattern to look for an integer called id

Changed views.py index function to include id and display data from that value

SUMMARY:
DB was created by adding models and performing migrations.  Items were added to the DB through the python shell.  Then the urls and views were changed to read and display info from the DB.
------------------------------

----------
Part III:
------------------------------


SUMMARY:

------------------------------

----------
Part IV:
------------------------------


SUMMARY:

------------------------------

----------
Part V:
------------------------------


SUMMARY:

------------------------------

----------
Part VI:
------------------------------


SUMMARY:

------------------------------

----------
Part VII:
------------------------------


SUMMARY:

------------------------------

----------
Part VIII:
------------------------------


SUMMARY:

------------------------------

----------
Part IX:
------------------------------


SUMMARY:

------------------------------

----------
Part X:
------------------------------


SUMMARY:

------------------------------

----------
Part XI:
------------------------------


SUMMARY:

------------------------------
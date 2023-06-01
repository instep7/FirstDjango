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
Modified DB ('python34 manage.py shell')
>>> from main.models import Item, ToDoList
>>> t = ToDoList.objects
>>> t.all()
<QuerySet [<ToDoList: Anth's List>]>
>>> t.filter(name__startswith="Anth")
<QuerySet [<ToDoList: Anth's List>]>
>>> t.filter(name__startswith="Bob")
<QuerySet []>
>>> del_object = t.get(id=1)
>>> del_object.delete()
(2, {'main.Item': 1, 'main.ToDoList': 1})
>>> t.all()
<QuerySet []>
>>> t1 = ToDoList(name="First list")
>>> t2 = ToDoList(name="Second list")
>>> t1.save()
>>> t2.save()
>>> t.all()
<QuerySet [<ToDoList: First list>, <ToDoList: Second list>]>

'python3 manage.py createsuperuser'

Ran server and logged in to url/admin

Added import of model in 'admin.py' so that it appears in admin dashboard

SUMMARY:
Learned how to access admin dashboard to navigate/edit the database.
------------------------------

----------
Part IV:
------------------------------
Added home route to urls.py and created home function in views.py

Created folder called templates under main, followed by a folder withing templates called main

Created base.html and home.html

Added name value to index and home functions to display on html pages

Added content block to base.html and used it in home.html

Removed variable name in index and home functions

Add list.html and content from list in index function

Change index to render list.html

Added items to list via 'python3 manage.py shell':
>>> from  main.models import ToDoList
>>> ls = ToDoList.objects.get(id=2)
>>> ls
<ToDoList: First list>
>>> ls.item_set.all()
<QuerySet []>
>>> ls.item_set.create(text="First Item", complete=False)
<Item: First Item>
>>> ls.item_set.create(text="Second Item", complete=False)
<Item: Second Item>
>>> ls.item_set.create(text="Third Item", complete=False)
<Item: Third Item>

Can now view list on site

Added if statement in list.html to only show incomplete items

Added completed items to list via 'python3 manage.py shell':
>>> from  main.models import ToDoList
>>> ls = ToDoList.objects.get(id=2)
>>> ls
<ToDoList: First list>
>>> ls.item_set.create(text="Not Showing", complete=True)
<Item: Not Showing>
>>> ls.item_set.all()
<QuerySet [<Item: First Item>, <Item: Second Item>, <Item: Third Item>, <Item: Not Showing>]>

Extended if statement in list.html to change color for completed items

SUMMARY:
Added items to DB via the shell and created html files as templates.  Within list.html we used blocks that are inherited from base.html and used python code to display data from the list that has an id matching the number in the url.
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
#My Django Note
##modify configurations in mysite/settings.py
By default, INSTALLED_APPS contains the following apps, all of which come with Django:
>django.contrib.admin – The admin site. You’ll use it shortly.</br>
django.contrib.auth – An authentication system.</br>
django.contrib.contenttypes – A framework for content types.</br>
django.contrib.sessions – A session framework.</br>
django.contrib.messages – A messaging framework.</br>
django.contrib.staticfiles – A framework for managing static files.</br>

###Philosophy
>create a module: define a module must follow the dry priciple.</br>
>activating models : Django apps are "pluggable", that means we can use one app in multiple projects.

####Command
>python manage.py migrate ---> looks at the INSTALLED_APPS and create any necessary database tables according to the database settings in settings.py
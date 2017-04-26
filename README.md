# Marioneta


## Steps 


==> python3 -m venv myvenv


==> source myvenv/bin/activate
(myvenv) 

==> python --version
Python 3.5.0
(myvenv) 


==> pip install django


### Create project
==> django-admin startproject marioneta

### Run
Run from the folder containing manage.py
==> python manage.py runserver 

### Create app channels
==> python manage.py startapp channels


### Add the following code in channels/views.py
```
from django.http import HttpResponse
# Create your views here.


def index(request):
	return HttpResponse("Hello. You're at the channels index.")

```


### Create a file called channels/urls.py
and add the following code in channels/urls.py

```
from django.conf.urls import urls
from . import views

urlpatterns = [
	url(r'^$', views.index, name='index'),
	
]
```

### Add the following  to marioneta/urls.py

```

    url(r'^channels/', include('channels.urls')),

```

### marioneta/urls.py should now look as follows 


```

"""
from django.conf.urls import url
from django.contrib import admin

urlpatterns = [
	url(r'^channels/', include('channels.urls')),
    url(r'^admin/', admin.site.urls),
]

```


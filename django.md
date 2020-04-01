# Data visualization Using Chartjs and Django

## install django https://www.geeksforgeeks.org/django-introduction-and-installation/
```bash
python -m pip install -U pip
pip install virtualenv
```
### set virtual envitonment
```bash
virtualenv env_site
cd env_site
cd Script 
activate
```

```bash
pip install django
cd ..

```
# https://www.geeksforgeeks.org/data-visualization-using-chartjs-and-django/?ref=rp


```bash
pip install djangorestframework
```
```bash
# Start a project name 'charts'
django-admin startproject charts

cd charts

# Start the server
python manage.py runserver
# CTRL + C

# create an app
python manage.py startapp chartjs

cd chartjs

# create a folder with index.htmlfile: templates/chartjs/index.html 
mkdir -p templates/chartjs && cd templates/chartjs && touch index.html

```

## Edit urls.py file in charts
```python
from django.contrib import admin
from django.urls import path
from chartjs import views

urlpatterns = [
  path('admin/', admin.site.urls),
  path('', views.HomeView.as_view()),
  # path('test-api', views.get_data),
  path('api', views.ChartData.as_view()),
]
```

## Edit views.py in chartjs:
```python
# from django.http import JsonResponse
from django.shortcuts import render
from django.view.generic import View

from rest_framework.views import APIView
from rest_framework.response import Response

class HomeView(View):
  def get(self, request, *args, &&kwargs):
    return render(request, 'chartjs/index.html'
```

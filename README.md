# FullStack Project Baed on Django

## What is Django?

Django is a high-level Python Web framework that encourages rapid development and clean, pragmatic design. It takes care of much of the hassle of Web development, so you can focus on writing your app without needing to reinvent the wheel.

Django is a full-featured web framework that follows the Model-View-Controller (MVC) architectural pattern. It provides a set of tools and libraries for building web applicationss, including an ORM, a templating engine, and a built-in admin interface.


## Envirement Setup :
``` 
python3 -m venv .venv
source .venv/bin/activate
# for windows
# .venv\Scripts\activate
```

```
uv pip install django
uv pip install -r requirements.txt
```

## Creating a Django Project :
```
django-admin startproject DjangoBeginners
cd DjangoBeginners
```


## Start a Project
```
python manage.py runserver
```


# Django models
Django models are the heart of the Django framework. They are used to define the structure of the database and the relationships between different models. In this section, we will explore the basics of Django models and how to create them.

## Defining a model
So far, we have created a same chai app and it’s time to add some data to it. To do this, we need to define a model. A model is a Python class that represents a table in the database. It contains fields that define the structure of the table and methods that define the behavior of the table.

To define a model, we need to use the models.py file in our Django project. Add the following code to the models.py file:
```
from django.db import models
from django.utils import timezone

# Create your models here.

class ChaiVariety(models.Model):
  CHAI_TYPE_CHOICES = [
    ('ML', 'MASALA'),
    ('GR', 'GINGER'),
    ('KL', 'KIWI'),
    ('PL', 'PLAIN'),
    ('EL', 'ELAICHI'),
  ]

  name = models.CharField(max_length=100)
  image = models.ImageField(upload_to='chais/')
  date_added = models.DateTimeField(default=timezone.now)
  type = models.CharField(max_length=2, choices=CHAI_TYPE_CHOICES, default='ML')

  def __str__(self):
    return self.name
```


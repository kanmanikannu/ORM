# Ex02 Django ORM Web Application
## Date: 

## AIM
To develop a Django application to store and retrieve data from a Book database using Object Relational Mapping(ORM).

## Entity Relationship Diagram

Include your ER diagram here

## DESIGN STEPS

### STEP 1:
Clone the problem from GitHub

### STEP 2:
Create a new app in Django project

### STEP 3:
Enter the code for admin.py and models.py

### STEP 4:
Execute Django admin and create details for 10 books

## PROGRAM

####Models.py
```
from django.db import models
from django.contrib import admin

class Author(models.Model):
    name=models.CharField(max_length=20)
    birth_year=models.IntegerField()

    def __str__(self):
        return self.name


class Book(models.Model):
    title=models.CharField(max_length=20)
    author=models.ForeignKey(Author, on_delete=models.CASCADE)
    genre=models.CharField(max_length=30,default='Unknown')
    publish_date=models.DateField()
    pages=models.IntegerField()

class Book1(admin.ModelAdmin):
    list_display=('title','author','genre','publish_date','pages')
```
####admin.py
```
from django.contrib import admin

from .models import Author,Book


class AuthorAdmin(admin.ModelAdmin):
    list_display = ('name',  'birth_year')  # Fields to display in the list view
    

class BookAdmin(admin.ModelAdmin):
    list_display = ('title', 'author', 'genre', 'publish_date', 'pages')  # Fields to display in the list view


admin.site.register(Author,AuthorAdmin)
admin.site.register(Book,BookAdmin)

```

## OUTPUT

![Uploading Screenshot (19).png…]()
![Uploading Screenshot (18).png…]()



## RESULT
Thus the program for creating a database using ORM hass been executed successfully

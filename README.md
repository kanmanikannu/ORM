####Name : Kanmani U
####Reg no : 212221040070

# Ex02 Django ORM Web Application
## Date: 04.04.2024

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

![Screenshot (19)](https://github.com/kanmanikannu/ORM/assets/114866367/032897a8-fc24-4db6-9234-6a1c548d65e9)
![Screenshot (18)](https://github.com/kanmanikannu/ORM/assets/114866367/6a550c10-4976-41a6-b37b-3e67894c90c0)




## RESULT
Thus the program for creating a database using ORM hass been executed successfully

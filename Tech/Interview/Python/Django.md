
# Python interview preparation

## Table of content
- [What is a django](#What-is-django?)
- [Django ORM](#django-orm)
- [CSRF Token](#csrf-token)
- [Authentication](#authentication)
- [Middleware](#middleware)

##  What is django? 
Python djangp backend web fremwork

## Which companies use djanog?
   Pinterest, ...

## What is the different between app and project?
   Project is configuration a website where app is where the logic sits and 
   is a compontent of which is build project.

4. What are url?
   Navigation, router to templates

   
6. Why do wee add names to URL's and how do we acces them dynamically?
   Allows to link access urls by name and make providing changes easier 
   also pretty handy during testing.

7. Django temlates Jinji, condition in templates, extending and implementing 
   templates?



## Authentication
### Definition
The Django authentication system handles both authentication and authorization.
Briefly, authentication verifies a user is who they claim to be,
and authorization determines what an authenticated user is allowed to do.
Here the term authentication is used to refer to both tasks.


Same as in other project with flasj by decorator
---

## Middleware
### Definition
Middleware is a framework of hooks into Django’s request/response processing.
It’s a light, low-level “plugin” system for globally altering Django’s input 
or output.


Each middleware component is responsible for doing some specific function.
For example, Django includes a middleware component, AuthenticationMiddleware,
that associates users with requests using sessions.


## Own
Are decorator that adds extra functionality during handling every request

```py
class SimpleMiddleware:
    def __init__(self, get_response):
        self.get_response = get_response
        # One-time configuration and initialization.

    def __call__(self, request):
        # Code to be executed for each request before
        # the view (and later middleware) are called.

        response = self.get_response(request)

        # Code to be executed for each request/response after
        # the view is called.

        return response
```
---
## Session
---
## Class Based Views vs Function Based Vies 
Class are better for DRY concept
---
## Error handling
---
## Handling file upload
---
## Static files (dev and prod)
    - collectstatic
    - Django white noisess
    - aws s3 bucket
---
## Django ORM
### Query related objects 

#### Query related object FORWARD
```bash
>>> e = Entry.objects.get(id=2)
>>> e.blog # Returns the related Blog object.
```
#### Query from related object - BACKWARDS -  child model object - down
```py
class Company(models.Model):
    name = models.CharField(max_length=50)


class Person(models.Model):

    name = models.CharField(max_length=50)
    surname = models.CharField(max_length=50)
    company = models.ForeignKey(Company, on_delete=models.CASCADE)
```
Result:
```bash
>>> company = Company.objects.get(pk=2)
>>> company.person_set.all()
```
```xml
<QuerySet [
    <Person: Konrad-Wieczorek-Netguru S.A.-Poznań-ul. Małe Garbary 9>,
    <Person: Jakub-Protasiewicz-Netguru S.A.-Poznań-ul. Małe Garbary 9>
]>
```
Works also with create eg.
```bash
>>> company.person_set.create(name='Test', surname='Test', recruiter=False)
<Person: Test-Test-Netguru S.A.-Poznań-ul. Małe Garbary 9>
>>> company.person_set.all()
<QuerySet [<Person: Konrad-Wieczorek-Netguru S.A.-Poznań-ul. Małe Garbary 9>,
<Person: Jakub-Protasiewicz-Netguru S.A.-Poznań-ul. Małe Garbary 9>,
<Person: Test-Test-Netguru S.A.-Poznań-ul. Małe Garbary 9>]>
```
    - linking sum, and 
    - quiery up on object
    - query owdn on oblect 
    - _set
    - 
### Annotate
Allows to annotate the query set by custom field.
>>> Company.objects.all().annotate(persons=Count(F('person__name'))).filter(persons__gt=1)

### Query expressions F()


---
## CSRF Token
### CSRF definition
The CSRF middleware and template tag provides easy-to-use protection against 
Cross Site Request Forgeries. This type of attack occurs when a malicious 
website contains a link, a form button or some JavaScript that is intended to
perform some action on your website, using the credentials of a logged-in user
who visits the malicious site in their browser. A related type of attack,
‘login CSRF’, where an attacking site tricks a user’s browser into logging 
into a site with someone else’s credentials, is also covered.


A Cross-site request forgery hole is when a malicious site can cause a visitor's
browser to make a request to your server that causes a change on the server.
The server thinks that because the request comes with the user's cookies, 
the user wanted to submit that form.

### How to protect your website against it? 
Django automatically enables **django.middleware.csrf.CsrfViewMiddleware**
middleware, that protects sites against csrf requests.

### Hot to use it?
- Insert in form
```py
<form method="post"\\{\\% csrf_token \\%\\}
```
- Get the token and save it in cookie or session
---


## Django Database
Django ins not suitable for non-sql databases

## Django signals


## Serializers
- What is it for?
- what does it do?
- 
2 scoups of django
single page application
genrec view sets 


## Gunicorn
It's a type of WSGI (webserver gateway interface) connects python app with
web server(NGINX)

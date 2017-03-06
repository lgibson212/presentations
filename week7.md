# How does middleware work in Django?
## Provide an example and explanation.

### What is middleware?
a framework that hooks into django's response/request processing.

snags the http request, alters it, and then sends the response.

happens in the middle.


### Deafult middleware that comes with ```django-admin startproject``` command in settings.py

```python 
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]
```

During the REQUEST cycle, the Middleware classes are executed top-down.

Then Django will do all the work on your view function.

After the work is done (e.g. querying the database, paginating results, processing information, etc),

it will return a RESPONSE for the client.

During the response cycle, the Middleware classes are executed bottom-up


![midware](https://simpleisbetterthancomplex.com/media/2016-07-18-how-to-create-a-custom-django-middleware/middleware.svg)


You can create your own custom middleware:

The folder 'middleware' should be placed in the same folder as settings.py, urls, templates...

> yourproject/yourapp/middleware

(Don't forget to create the __init__.py empty file inside the middleware folder so your app recognize this folder)

Can be written as a function or as a class. Add it into the settings.py file.


references
- https://simpleisbetterthancomplex.com/tutorial/2016/07/18/how-to-create-a-custom-django-middleware.html
- http://agiliq.com/blog/2015/07/understanding-django-middlewares/
- https://docs.djangoproject.com/en/1.10/ref/middleware/
- http://stackoverflow.com/questions/18322262/how-to-setup-custom-middleware-in-django


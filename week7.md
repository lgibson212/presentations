# How does middleware work in Django?
## Provide an example and explanation.

### What is middleware?
a framework that hooks into django's response/request processing.

snags the http request, alters it, and then sends the response.

happens in the middle.


### Deafult middleware that comes in ```django-admin startproject```

```python 
MIDDLEWARE_CLASSES = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.auth.middleware.SessionAuthenticationMiddleware',
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


references
- https://simpleisbetterthancomplex.com/tutorial/2016/07/18/how-to-create-a-custom-django-middleware.html
- http://agiliq.com/blog/2015/07/understanding-django-middlewares/
- 

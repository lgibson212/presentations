# How does middleware work in Django?
## Provide an example and explanation.

### What is middleware?
a framework that hooks into django's response/request processing.

snags the http request, alters it, and then sends the response.

happens in the middle.


### Deafult middleware that comes in ```django-admin startproject```

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

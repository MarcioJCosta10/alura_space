# Iniciar o projeto alura space
>>> iniciar venv
>>> pip list
>>> pip install --upgrade pip
>>> pip install django
>>> pip freeze > requirements.txt
>>> django-admin help --> lista todos comandos do django
>>> django-admin startproject setup .

### Configure timezone in settings.py

```py
LANGUAGE_CODE = 'pt-BR'

TIME_ZONE = 'America/Sao_Paulo'
```
# Configure python-dotenv
>>> pip install python-dotenv
### Criar new file .env
### Criar .gitignore
>>> https://www.toptal.com/developers/gitignore/ --> site para criar gitignore

### Criar o app galeria
>>> python manage.py startapp galeria
### registrar esse app em settings.py

### isolar as urls 
# criar o arquivo urls.py em galeria
```py
from django.urls import path
from galeria.views import index

urlpatterns = [
    path('',index)
]
```
# configurar urls.py de setup
```python
from django.contrib import admin
from django.urls import path
from django.urls import include


urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('galeria.urls')),
]

```
### configurar templates
# em settings.py configurar DIR templates
```py
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR,'templates')],
```

## configure static files
```py
STATIC_URL = 'static/'
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'setup/static')]
STATIC_ROOT = os.path.join((BASE_DIR,'static'))
```

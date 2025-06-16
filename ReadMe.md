# Current root directory
The root directory should look like:
```
django-rest-framework-projects\
    backend\
        ...
    requirements.txt    
```
## Steps:
1. Create a virtual environment
```
python -m venv django-venv
```
2. Activate the virtual environment
```
# For Windows:
django-venv\Scripts\activate.bat

# For Mac/Linux:
source django-venv/bin/activate
```
3. Deactivate the virtual environment (optional)
```
# For Windows:
deactivate

# For Mac/Linux:
deactivate
```
4. The following packages required and contained in the requirements.txt file.
```
asgiref==3.5.2
Django==4.1.3
django-extensions==3.2.1
django-filter==22.1
djangorestframework==3.14.0
djangorestframework-jsonapi==6.0.0
inflection==0.5.1
python-dotenv==0.21.0
pytz==2022.6
sqlparse==0.4.3
tzdata==2022.6
```
Install above python packages using the command:
```
pip3 install -r backend/requirements.txt
```
5. Start a new Django project. Installing Django has given you access to a handy ```startproject``` command. Use the following command to start our new project.
```
django-admin startproject drf_project1 backend
```
6. Copy out the environment variables and secrets from the env.template into a .env file
```
copy env.template .env
```
7. Create first Django app, name it ```core```
> Note: Change directory into the ```backend``` folder where the ```drf_project1``` lives and run the command
```
python manage.py startapp core
```
The root directory should look like:
```
django-rest-framework-projects\
    backend\
        core\
        drf_project1\
        manage.py
        requirements.txt   
    django-venv\
    .env
    env.template
    ReadMe.md 
```
8. Make some changes in the django settings file

```
# Imports: replace the imports with all of these
from pathlib import Path
from dotenv import load_dotenv
import os
load_dotenv()

# Variables: Replace ALLOWED_HOSTS, SECRET_KEY and DEBUG with the following snippet.
SECRET_KEY = os.environ.get("SECRET_KEY")
DEBUG = int(os.environ.get("DEBUG", default=0))
ALLOWED_HOSTS = os.environ.get("DJANGO_ALLOWED_HOSTS").split(" ")

# Installed apps: Django will include our new app in the project when we register it. Replace the current settings with the following snippet.
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'django_extensions', #Great packaged to access abstract models
    'django_filters', #Used with DRF
    'rest_framework', #DRF package
    'core', # New app
]
```
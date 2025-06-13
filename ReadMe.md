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
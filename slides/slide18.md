## 4.0 Getting Started

- To view your project locally in a web browser - you have to execute the following commands:
    - `$ python manage.py makemigrations` - Is responsible for creating new migrations for new models or changes you have made to existing models
    - `$ python manage.py migrate`- The migrate command looks at the INSTALLED_APPS in settings and applies to the disk any necessary database tables.
    - `$ python manage.py runserver` - Starts your Django development server, a lightweight Web server written purely in Python.
    - You could now go to `http://127.0.0.1:8000/` with your web browser and view your site.
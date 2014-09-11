## 3.3 Django Settings

- Your settings file contains a bunch of variables declaring the configuration for your project
    - e.g. static file location & Time Zone
- Two Essential Setting Variables:
    -  DEBUG - A boolean value that you set to True or False
        - When debug is on (DEBUG = True), Django will display a detailed traceback on your error page, including metadata about your environment. This allows you to easily debug your error.
    - INSTALLED_APPS - A tuple of python packages that your project can use.
        - Whenever you install a new python package (e.g. django-braces, django-rest-framework) you need to add it to your installed apps tuple to access it within your project.
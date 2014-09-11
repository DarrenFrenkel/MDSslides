### Django App File Structure

- **&lt;app name&gt;/** - Your root app directory. It should sit in your project workspace directory.
- **\_\_init\_\_.py** - Marks your app as a python package.
- **admin.py** - Where you register your models to be viewed in the admin panel and customised how they will be displayed.
- **migrations/** - Stores a history of all your model migrations. It's a type of version control for changes to your models (ORM).
- **models.py** - Where you write your the models for your application.
- **tests.py** - Where you write tests for your app.
- **views.py** - Controls how your server displays content to your client (browser or web service)

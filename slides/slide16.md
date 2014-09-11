## 3.4 Django Project vs. App

- Project - is a collection of configuration and apps for a particular website.
- App - An app is a Web application that provides functionality to the project - e.g. a Weblog system, user authentication, session management, or a simple poll app.
- A project can contain multiple apps and app can be in multiple projects.
- Create an app by executing - `python manage.py startapp <app name>`
- Whenever you add a new app to your project you need to add it your `INSTALLED_APPS` tuple to access it within your project.

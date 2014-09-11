
title: Melb Django School Slides
style: style.css
output: slides.html

-- extraxtsm
-- xtsm hd6 custom1
-- xtsm hd6 custom1
-- xtsm hd6 custom1
-- xtsm hd6 custom1

### Server Side Scripting - CGI Protocol

![Server Side Script](static/CGI-request-response-cycle.png)

* CGI protocol is a way for a script to communicate with a web server.
* Server side scripts allow developers to add content dynamically to a file.
* Html pages could now show database information & logic.

-- md

### Application servers - The Modern Web (Django)

* Now we have dedication Application servers that decouples the processes of getting a resource via URI.
* Our application server has different files for URLs, views, templates & models.
* We could now route our URI to a view which could render a template to be viewed by a user or generate context data to be consumed by an API.

-- sm wd

![Django App](static/request-response.png)

The Modern Server Environment
-- sm


# 2.0 Let's Get Started!

## 2.1 Installing Python 2.7
- Linux:
  - Typically already installed
- Mac:
  - Already installed
- Windows:
  - https://www.python.org/downloads/


## 2.2 Python/Package Manager
- Installing Pip - Pip is a package manager used to install & manage Python programs. Pip allows us to easily install Django and other Python packages.
- Download get-pip.py `https://bootstrap.pypa.io/get-pip.py`
- Run `python get-pip.py`

--

## 2.3a Virtualenv - keeping things tidy
- Helps avoid version clashes
- Separate package environment per env
- Helps with consistancy: same package versions in development, testing, and production.
- Every time you have a new django project, you want to create it in a new VirtualEnv.


-- xtsm hd6 custom1

## 2.3b Installing VirtualEnv

- Linux:
 - `sudo pip install virtualenv`
- Mac:
 - `sudo pip install virtualenv`
- Windows:
 - `pip install virtualenv`

### 2.3c Create/Activate Virtualenv

- Create Virtualenv:
    - Mac & Linux:
        - `$ virtualenv foo`
    - Windows:
        - `virtualenv.exe venvname`
- Activate Virtualenv:
    - Windows:
        - `\foo\Scripts\activate`
    - Linux & Mac:
        - `$ source bin/activate`

- You are now within your virtual environment. Anything you install with Pip will be contained within this environment.

## 2.4 Install Django

- Install Django: - `$ pip install Django`

-- xtsm hd6 custom1

# 3. Django File Structure

## 3.1 Start Project/Structure

- To create a new django project - `$ django-admin.py startproject <project name>`
- This command gives you the following out-of-the-box django file structure:

![Django Project Structure](static/django-project-structure.png)

-- sm

## 3.2a Django Project File Overview

- __Project Workspace: &lt;project name&gt;/__  - is just a container for your project. Its name doesn't matter to Django; you can rename it to anything you like. All Python imports for code in your project and apps are relative to here.
- __manage.py__ - A handy wrapper for django-admin.py for this project.
- __Projet Module: &lt;project name&gt;/&lt;project name&gt;/__ - This is the Python module of your app.

--

## 3.2b Django Project Module Files Overview

### Inside your project module:

- __\_\_init\_\_.py__ - An empty file that tells Python that this directory should be considered a Python package
- __settings.py__ - Settings/configuration for this Django project.
- __urls.py__ - The URL declarations for this Django project; a 'table of contents' of your Django-powered site.
- __wsgi.py__ - An entry-point for WSGI-compatible web servers to serve your project.


-- sm

## 3.3 Django Settings

- Your settings file contains a bunch of variables declaring the configuration for your project
    - e.g. static file location & Time Zone
- Two Essential Setting Variables:
    -  DEBUG - A boolean value that you set to True or False
        - When debug is on (DEBUG = True), Django will display a detailed traceback on your error page, including metadata about your environment. This allows you to easily debug your error.
    - INSTALLED_APPS - A tuple of python packages that your project can use.
        - Whenever you install a new python package (e.g. django-braces, django-rest-framework) you need to add it to your installed apps tuple to access it within your project.

-- md

## 3.4 Django Project vs. App

- Project - is a collection of configuration and apps for a particular website.
- App - An app is a Web application that does something – e.g. a Weblog system, a database of public records or a simple poll app.
- A project can contain multiple apps and app can be in multiple projects.
- Create an app by executing - `python manage.py startapp <app name>`
- Whenever you add a new app to your project you need to add it your `INSTALLED_APPS` tuple to access it within your project.

-- sm  custom2 hd6-custom

## 3.5 App File Structure/File overview

![Django App Structure](static/django-app-structure.png)
######Django App File Structure

- **&lt;app name&gt;/** - Your root app directory. It should sit in the same directory as your project root.
- **\_\_init\_\_.py** - Makes your app into a python package.
- **admin.py** - Where you register your models to be viewed in your admin panel and customised how they will be displayed.
- **migrations/** - Stores a history of all your model migrations. It's a type of version control for changes to your models (ORM).
- **models.py** - Where you write your the models for your application.
- **tests.py** - Where you write tests for your app.
- **views.py** - Controls how your server displays content to your client (browser or web service)

-- md

## 4.0 Getting Started

- To view your project locally in a web browser - you have to execute the following commands:
    - `$ python manage.py makemigrations` - Is responsible for creating new migrations for new models or changes you have made to existing models
    - `$ python manage.py migrate`- The migrate command looks at the INSTALLED_APPS in settings and applies to the disk any necessary database tables.
    - `$ python manage.py runserver` - Starts your Django development server, a lightweight Web server written purely in Python.
    - You could now go to `http://127.0.0.1:8000/` with your web browser and view your site.

-- sm


# 5 Creating a basic HTTP request/response via Django

## 5.1  The URL

### Create a url
![urlconfig](static/urlconfig.png)

* Create the above file in `project-name/urls.py`

### Django accessing that URL

* Django determines the root URLconf module to use - `<project_name>.urls.py`
* Django loads that Python module and looks for the variable urlpatterns. This should be a Python list of django.conf.urls.url() instances.
* Django runs through each URL pattern, in order, and stops at the first one that matches the requested URL.
* Once one of the regexes matches, Django imports and calls the given view, which is a simple Python function (or a class based view).

-- sm

## 5.2 The View

![views](static/views.png)

### Create a View

* Create the above file in `app-name/views.py`

### Consuming an HTTP Request and Sending a Response

* The HttpRequest argument gets passed into the request parameter of the view function.
* The HttpRequest instance has multiple properties associated with it. One is `method` which returns the HTTP method (GET, HEAD, POST, PUT, DELETE, OPTIONS, TRACE).
* We then could send our response back to our browser using the Django builtin function `HttpResponse`

-- extraxtsm

## 5.3 How it comes together

![Django Basic Request Response Structure](static/basic-request-response.png)

- The browser via HTTP makes a request to your server, using your input URL as a resource.
- The server then looks for a matching URL in your urlconfigs file (urls.py).
- The matched URL then calls a function or a class in the views.py file.
- The view then displays a response to the browser.


--
# 6 Version Control

- Why?  Because we make mistakes.

- Using Git
    - Git is a version control program.
    - Download Git - `http://git-scm.com/downloads`

- Add Git into your project directory
    - git init

-- sm

## 6.1 Git Add/Commit Overview

- Git allows you to choose how to wrap your file changes - basically allowing you to control your change history.
- For example, you've changed three files:
    - A url (urls.py),
    - Its relevant view (views.py)
    - An unrelated change to your index.html.
- Ideally you would like to commit the urls.py & views.py changes together and index.html as a separate commit.
- Git facilitates this behaviour by first requiring you to place each change on a staging level. Here you could choose which file to set to staging (The urls.py & views.py). Then you could wrap all the staged files as one commit. Next you could stage and commit your change to the index.html.

-- hd6 custom1 xtsm

## 6.2 Git Add/Commit/Status Commands

![git status](static/git-status.gif)

######Git Status Message

- To see a list of all changed files that haven't been committed - `$git status`
- To set a file to staged - `$git add <file name> ` or `$git add .` - adds all changed files to staged
- To commit staged files - `$git commit -m <commit message>`

-- sm hd6 custom1 xtsm


## 6.3 Git Log

![git Log](static/git-log.jpg)
######Git Log Message

- You could see a history of all your changes through the git log command - `$git log`
- This command shows a list of all your commits starting with the most recent.


-- xtsm hd6 custom1

## 6.4 Git Branches

![git Log](static/git-branches.png)
######Git Branches

- One way to view your git commit history is as a list of linear nodes on a master branch. Where each node represents a successful change (commit) to your code base.
- Often you want to add a new feature to your app but want to retain the integrity of the master branch. We do this by branching off from the master branch, adding the new feature and then merging back in.
- To create a branch - `$git checkout -b <branch name>`
- To merge your branch back into master:
    - first checkout master - `$git checkout master`
    - then merge your branch into the master branch - `$git merge <branch name>`

--

## 6.5 Github/Git Clone

- Github is a website that allows you to remotely store your code base and change history. You code base is stored in a Github repository (repo). On Github you to easily view your files & commit history and share your code base. [Go to github](https://github.com/)
- You could share you code base that is stored on Github with the Git clone command.Git clone copies projects sitting on a Github repository (repo) to your local computer (sharing your code base). The Git clone command is  - `$ git clone <project url>`
- You could then get any new changes from the remote repo by executing - `$git pull`. In addition, you could post any committed local changes to the remote repo using - `$git push`

-- xtsm hd6 custom2 custom1 wd

## 6.6 Github - Fork/Pull Request


- When working on a remote repository (repo) often the repo's owner would like to review your code before adding it to the code base. To implement this type of workflow, you would fork the remote repo from Github, add your code and then make a pull request.

![Github Fork](static/github-fork.png)

- Fork - Allows you to clone a remote repo as a separate repo under your github account

![Github Pull Request](static/github-pullRequest.png)

- Pull request - Sends a request to the repo owner to merge the changes from your clone to the owner’s repo.

- The repo owner could then accept your pull request.

--

# Appendix - Project Creation Steps

## 2.1 - Installing Python 2.7

- windows:
    - https://www.python.org/downloads/
- Mac & Linux:
    - Already installed

## 2.2 - Python/Package Manager

- windows:
    - Download get-pip.py - `https://bootstrap.pypa.io/get-pip.py`
    - Run `python get-pip.py`
    - Add `C:\Python27\Scripts` to your environment variables
- Mac:
    - sudo easy_install pip
- linux:
    - sudo apt-get install python-pip

## 2.3b Installing VirtualEnv

- Mac & Linux:
    - `sudo pip install virtualenv`
- Windows:
    - `pip install virtualenv`

## 2.3c Creating/Activate Virtualevn

- Create Virtualenv:
    - Mac & Linux:
        - `$ virtualenv foo`
    - Windows:
        - `virtualenv.exe foo`
- Activate Virtualenv
    - Windows:
        - `\foo\Scripts\activate`
    - Linux & Mac:
        - `$ source bin/activate`

## 2.4 Install Django

- `pip install Django`

## 3.1 Start Project

- `$ django-admin.py startproject <project name>`

## 3.4 Django Project vs. App

- `python manage.py startapp <app name>`
- Add your app to your INSTALLED_APPS tuple in your settings file

## 4. Getting Started

- `$ python manage.py makemigrations`
- `$ python manage.py migrate`
- `$ python manage.py runserver`
- Go to `http://127.0.0.1:8000/` to see your Django powered site.

## 5.1 The URL

- Create the below file in `project-name/urls.py`

![urlconfig](static/urlconfig.png)

## 5.2 The View

- Create the below file in `app-name/views.py`

![views](static/views.png)

- Go to `http://127.0.0.1:8000/` to see the output of your HTTP response.

## 6. Version Control

- Download Git - `http://git-scm.com/downloads`
- Add Git to your project directory - `git init`

## 6.2 Git Add/Commit/Status Commands

- View all your changed/added files - `git status`
- Add all your files to Git - `git add <file name>`
- Commit all your files `git commit -m "initial commit"`

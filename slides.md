
title: Melb Django School Slides
style: style.css
output: slides.html

-- sm

## How do web Apps work

- HTTP - is the protocol that we use to communicate between client and server
	- basically how our browser communicates with a server.
- HTTP protocol - by protocol, I mean there is specific information that a client has to send to a server and vice versa to communicate properly
- On the client side, the browser initiates communication to the server via a url with a request (http request) and sends over 3 main components:
	-  HTTP Request line
	-  HTTP Request Headers 
	-  HTTP Request Body
-  On the Server side, the server receives the request and then responds (http response) by sending back 3 main components to the client:
	-  HTTP Response Status-Line
	-  HTTP Response Headers
	-  HTTP Response Body
-- md

## The Request

- HTTP Request line - contains the following: 
	- Method - 5 main methods - GET, HEAD, POST, PUT, DELETE 
	- URI - is the specific page you're requesting (e.g. index.html) 
	- Protocol Version - is the version of HTTP (e.g. HTTP/1.1)
- HTTP Request Header: - is a list of key/value pairs that is mainly about the client's environment
	- host - is the main key/value pair of the Request Header - It gives us our server location (e.g. example.com)
- HTTP Request Body: - an option body message

-- md

## The Response

- HTTP Response Status-Line:
	- Protocol Version - is the version of HTTP (e.g. HTTP/1.1)
	- Status Code - (e.g. 200, 404)
	- Description - a brief description of the status code (e.g. ok, file now found)
- HTTP Response Header:
	-  is a list of key/value pairs that tells us about our server environment (e.g.Server: Apache/1.3.3.7 (Unix) (Red-Hat/Linux))
- HTTP Response Body:
	- The actual response which is rendered in the client's window (The browser). The content of the body will be HTML code.   

-- md

## Application servers vs web servers

* A web server typically returns static web pages, ie we place an http request for a specific file name on a server (the url) and the web server returns that file 
* However, An application server allows us to use business logic to return content dynamically. 
	* ie we could route a url to a view and then that view could return a template or a json object.
	* or we could easily change the template that the view renders or change the type of data it returns
* Essentially the main difference is an app server allows us to dynamically change the http response instead of being connected to a page. 

--


##Python/Package Manager
- For all mac/linux users python comes pre-installed, for windows users time to upgrade (use vagrant)
- Installing Pip - Pip is a package manager used to install & manage python programs. Pip allows us to install Django and other python packages
- Download get-pip.py
- run python get-pip.py

--

##Environment
- Every time you have a new django project, you want  to create it in a new environment. This Allows for local & production environment compatibility (ie same version of python, django and same dependencies). Which will be helpful in the future especially for debugging.
- VirtualEnv allows us to control our environment - it essentially puts your projects into a virtual silo

-- md

##Installing VirtualEnv/Django
- Pip install virtualenv
- Then to create a virtualenv it's - `$virtualenv env`
- To activate the env it's - `$source env/bin/activate`
- You are now within your virtual environment. Anything you install will be contained within this environment
- Install Django: - `$pip install https://www.djangoproject.com/download/1.7c2/tarball/`

--

##Git - Version Control

- Git is a version control program. It allows you to track changes you’ve made to your project/app.
- You could install it by executing - `$sudo apt-get install git`
- Make changes to your project and you could see a list of file changes with - `$git status`
- You could see the actual changes to the files with - `$git diff <file-name>`

-- sm

##Git Add/Commit

- Git allows you to choose how to wrap your file changes.
- For example, you’ve changed three files:
	- a url (urls.py),
	- it’s relevant view (views.py)
	- an unrelated change to your index.html.
- Ideally you would like to commit the urls.py & views.py changes together and index.html as a separate commit.
- Git facilitates this behaviour by first requiring you to place each change on a staging level. Here you could choose which file to set to staging (The urls.py & views.py). Then you could wrap all the files you’ve set to staging as one commit. Next you could stage and commit your change to the index.html. This change will be seen as a separate commit - `$git log`
- To set a file to staged - `$git add <file name> ` or `$git add .` - adds all changes to staged
- To commit staged files - `$git commit -m “<commit message>”`

--

## Github/Git Continued

- Github is a remote repository where you could store your code base. Github allows you to easily view your files & commit history and share your code base.
- Git allows you to copy projects sitting on Github to your local computer (essentially sharing your code base) by using the git clone command. - `$ git clone <project url>`
- You could then get any new changes from the remote repo by executing - `$git pull`. In addition, you could post any committed local changes to the remote repo using - `$git push`

-- sm

##Git Branches & Forks

- Git Branches - a way to view your git commit history is as a list of linear nodes on a master branch. Where each node represents a successful change (commit) to your code base. Often you want to add a new feature to your app but want to retain the integrity of the master branch. We do this by branching off from the master branch, adding the new feature and then merging back in.
- To create a branch - `$git checkout -b <branch name>`
- To merge your branch back into master:
	- first checkout master - `$git checkout master`
	- then merge your branch into the master branch - `$git merge <branch name>`
- When working on a remote repo often the repo owner would like to review your code before adding it to the code base. To implement this type of workflow, you would first fork the remote repo, add your code and then make a pull request.
	- Fork - allows you to clone the public repo as a separate repo under your github account
	- Pull request - sends a request to the repo owner to merge the changes from the clone on your account to the owner’s repo.
	- The repo owner could then accept your pull request.

-- md

## Django - Start Project/Structure

- To create a new django project - `$django-admin.py startproject <mysite>`
- This command gives you the following out-of-the-box django file structure:
	- mysite/
		- manage.py
		- mysite/
			- __init__.py
			- settings.py
			- urls.py
			- wsgi.py

-- sm

## Django Project File Overview

- __Outer mysite/__  - is just a container for your project. Its name doesn’t matter to Django; you can rename it to anything you like.
- __requirements.txt__ -  doesn’t come out of the box, you need to create the file yourself.
	- place the name of all your third party python libraries inside this file and pip will install them - `$pip -R requirements.txt`
- __manage.py__ -  A command-line utility that lets you interact with this Django project in various ways. Its two main activities are:
	- starting your local server - `$./manage.py runserver`
	- Accessing your python shell - `$./manage.py shell`

--

## Django Project File Overview Continued

- __inner mysite/__ - is the actual Python package for your project. Its name is the Python package name you’ll need to use to import anything inside it (e.g. mysite.urls).
- __mysite/__init__.py__ - An empty file that tells Python that this directory should be considered a Python package
- __mysite/settings.py__ - Settings/configuration for this Django project
- __mysite/urls.py__ - The URL declarations for this Django project; a “table of contents” of your Django-powered site.
- __mysite/wsgi.py__ - An entry-point for WSGI-compatible web servers to serve your project.


-- sm

##Django Settings

- Your settings file contains a bunch of variables declaring the configuration of your project
	- e.g. static file location & Time Zone  
- Two Essential Setting Variables
	-  DEBUG - a boolean value that you set to True or False
		- When Debug is on (DEBUG = True), Django will display a detailed traceback on your error page, including metadata about your environment. This allows you to easily debugged your error. 
	- Installed Apps - a tuple of python packages that your project can use.
		- Whenever you install a new python package (e.g. django-braces, django-rest-framework) you need to add it to your Installed Apps tuple to access it within your project.  

-- md

## Django Project vs. App

- Project - is a collection of configuration and apps for a particular website
- App - An app is a Web application that does something – e.g. a Weblog system, a database of public records or a simple poll app
- A project can contain multiple apps and app can be in multiple projects.
- create an app by executing `python manage.py startapp <app name>`
- Whenever you add a new app to your project you need to add it your `INSTALLED_APPS` tuple to access it within your project.

-- sm

## App File Structure/File overview

- myapp/ - your root app directory should sit in the same directory as your project root
- myapp/\_\_init\_\_.py - makes your app into a python package
- mpyapp/admin.py - where you register your models to be viewed in your admin panel and customised how they will be displayed.
- migrations/ - stores a history of all your model migrations - it's a type of version control for changes to your model.
- models.py - where you write your the models for your application
- tests.py - where you write tests for your app
- views.py - controls how your server displays content to your client (browser or web service)

-- md

## Getting Started 

- To run your projects/See it in a web browser - you have to execute the following commands:
	- `$ python manage.py migrate`- The migrate command looks at the INSTALLED_APPS setting and creates any necessary database tables according to the database settings in your mysite/settings.py file and the database migrations shipped with the app.
	- `$ python manage.py runserver` - Starts your Django development server, a lightweight Web server written purely in Python.
	- You could now go to `http://127.0.0.1:8000/` with your web browser and view your site.

--

## How it comes together

- The browser via http makes a request to your server, using your input url as a resource
- The server then looks for a matching url in your urlconfigs file (urls.py)
- The matched url then calls a function or a class in the views.py file
- The view then displays a template with context variables to a browser or a json object to an API 

http request -> url -> view -> http response








 







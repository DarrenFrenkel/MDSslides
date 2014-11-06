
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



-- sm


--




-- sm



-- md



-- sm  custom2 hd6-custom



-- md



-- sm



-- sm



-- extraxtsm




--



-- hd6 custom1 xtsm



-- sm hd6 custom1 xtsm





-- xtsm hd6 custom1


--


-- xtsm hd6 custom2 custom1 wd



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

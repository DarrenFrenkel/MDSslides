
title: Melb Django School Slides
style: style.css
output: slides.html

-- extraxtsm
-- xtsm hd6 custom1
-- xtsm hd6 custom1
-- xtsm hd6 custom1
-- xtsm hd6 custom1


-- md

### Application servers - The Modern Web (Django)

* Now we have dedication Application servers that decouples the processes of getting a resource via URI.
* Our application server has different files for URLs, views, templates & models.
* We could now route our URI to a view which could render a template to be viewed by a user or generate context data to be consumed by an API.

-- sm wd

![Django App](images/request-response.png)

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

## 5.2 The View

![views](images/views.png)

### Create a View

* Create the above file in `app-name/views.py`

### Consuming an HTTP Request and Sending a Response

* The HttpRequest argument gets passed into the request parameter of the view function.
* The HttpRequest instance has multiple properties associated with it. One is `method` which returns the HTTP method (GET, HEAD, POST, PUT, DELETE, OPTIONS, TRACE).
* We then could send our response back to our browser using the Django builtin function `HttpResponse`

-- extraxtsm

## 5.3 How it comes together

![Django Basic Request Response Structure](images/basic-request-response.png)

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

![git status](images/git-status.gif)

######Git Status Message

- To see a list of all changed files that haven't been committed - `$git status`
- To set a file to staged - `$git add <file name> ` or `$git add .` - adds all changed files to staged
- To commit staged files - `$git commit -m <commit message>`

-- sm hd6 custom1 xtsm


## 6.3 Git Log

![git Log](images/git-log.jpg)
######Git Log Message

- You could see a history of all your changes through the git log command - `$git log`
- This command shows a list of all your commits starting with the most recent.


-- xtsm hd6 custom1

## 6.4 Git Branches

![git Log](images/git-branches.png)
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

![Github Fork](images/github-fork.png)

- Fork - Allows you to clone a remote repo as a separate repo under your github account

![Github Pull Request](images/github-pullRequest.png)

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

![urlconfig](images/urlconfig.png)

## 5.2 The View

- Create the below file in `app-name/views.py`

![views](images/views.png)

- Go to `http://127.0.0.1:8000/` to see the output of your HTTP response.

## 6. Version Control

- Download Git - `http://git-scm.com/downloads`
- Add Git to your project directory - `git init`

## 6.2 Git Add/Commit/Status Commands

- View all your changed/added files - `git status`
- Add all your files to Git - `git add <file name>`
- Commit all your files `git commit -m "initial commit"`

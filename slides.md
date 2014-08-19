
title: Melb Django School Slides
style: style.css
output: slides.html

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

--

##Installing VirtualEnv/Django
- Pip install virtualenv
- Then to create a virtualenv it's - `$virtualenv env`
- To activate the env it's - `$source env/bin/activate`
- You are now within your virtual environment. Anything you install will be contained within this environment
- Install Django - `$pip install https://www.djangoproject.com/download/1.7c2/tarball/`

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

-- md

## Django Project File Overview

- __Outer mysite/__  - is just a container for your project. Its name doesn’t matter to Django; you can rename it to anything you like.
- __requirements.txt__ -  doesn’t come out of the box, you need to create the file yourself.
	- place the name of all your third party python libraries inside this file and pip will install them - `$pip -R requirements.txt`
- __manage.py__ -  A command-line utility that lets you interact with this Django project in various ways.
	- Its two main activities are:
		- starting your local server - `$./manage.py runserver`
		- Accessing your python shell - `$./manage.py shell`

--

## Django Project File Overview Continued

- __inner mysite/__ - is the actual Python package for your project. Its name is the Python package name you’ll need to use to import anything inside it (e.g. mysite.urls).
- __mysite/__init__.py__ - An empty file that tells Python that this directory should be considered a Python package
- __mysite/settings.py__ - Settings/configuration for this Django project
- __mysite/urls.py__ - The URL declarations for this Django project; a “table of contents” of your Django-powered site.
- __mysite/wsgi.py__ - An entry-point for WSGI-compatible web servers to serve your project.










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





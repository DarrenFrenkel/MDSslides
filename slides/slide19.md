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

### Django accessing that URL

* Django starts with the root URL conf specified in `settings.ROOT_URLCONF`
* Django loads that Python module and looks for the variable urlpatterns
* Django runs through each URL pattern, in order, and stops at the first one that matches the requested URL
* Once one of the regexes matches, Django imports and calls the given view, which is simply a Python function

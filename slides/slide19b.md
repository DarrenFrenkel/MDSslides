## 5.1  The URL

### Create a url


```python
    from django.conf.urls import patterns, url

    urlpatterns = patterns('',
        url(r'^$', 'testhttp.views.get_request', name='get' ),
    )

    # urls.py file
```


* Create the above file in `project-name/urls.py`


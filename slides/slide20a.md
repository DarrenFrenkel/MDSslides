## 5.2 The View

```python
    from django.http import HttpResponse

    def get_request(request):
        content = "This is my httpresponse"
        return HttpResponse(content)

    # views.py file
```

* Create the above file in `app-name/views.py`


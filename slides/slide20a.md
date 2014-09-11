## 5.2 The View

```python
    from django.http import HttpResponse

    def get_request(request):
        if request.method == 'GET':
            html = "This is my httpresponse"
            return HttpResponse(html)

    # views.py file
```

* Create the above file in `app-name/views.py`


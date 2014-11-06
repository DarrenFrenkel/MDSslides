### Accesing the data on our view

- We could access the html form input data and save it to the model as follows

```python
def name_data(request):
    if request.method == "POST":
        first_name = request.POST['first_name']
        middle_name = request.POST['middle_name']
        last_name = request.POST['last_name']
        email = request.POST['email']
        new_name = UserInfo.objects.create(first_name=first_name,
                                           middle_name=middle_name,
                                           last_name=last_name,
                                           email=email
                                           )
        new_name.save()

# views.py
```

### Our View

- Our is_valid method checks if our data is appropriate for our form. It checks:
    - That our email field contains and @ and a full stop
    - That our data is less than 100 characters
    - That our middle name input could be blank

```python
from django.shortcuts import render
from django.http import HttpResponseRedirect

def get_name(request):
    # if this is a POST request we need to process the form data
    if request.method == 'POST':
        # create a form instance and populate it with data from the request:
        form = NameForm(request.POST)
        # check whether it's valid:
        if form.is_valid():
            # process the data in form.cleaned_data as required
            first_name = request.POST['first_name']
            middle_name = request.POST['middle_name']
            last_name = request.POST['last_name']
            email = request.POST['email']
            new_name = UserInfo.objects.create(first_name=first_name,
                                               middle_name=middle_name,
                                               last_name=last_name,
                                               email=email
                                               )
            # redirect to a new URL:
            return HttpResponseRedirect('/thanks/')
    # if a GET (or any other method) we'll create a blank form
    else:
        form = NameForm()
    return render(request, 'name.html', {'form': form})

# views.py
```

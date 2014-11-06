### Our View

```python
from django.shortcuts import render
from django.http import HttpResponseRedirect

def get_name(request):
    if request.method == 'POST':
        form = NameForm(request.POST)
        if form.is_valid():
            # Saves all our input data as an instance of our UserInfo model
            form.save()
            return HttpResponseRedirect('/thanks/')
    else:
        form = NameForm()
    return render(request, 'name.html', {'form': form})

# views.py
```

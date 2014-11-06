### Using Django Forms

- We could add the following form fields to our forms.py file

```python
from django import form

class UserInfoForm(forms.Form):
    first_name = forms.CharField(max_length=100)
    middle_name = forms.CharField(max_length=100, required=False)
    last_name = forms.CharField(max_length=100)
    email = forms.EmailField()


# forms.py
```


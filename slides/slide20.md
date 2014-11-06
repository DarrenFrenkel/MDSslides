## Field Validator

- Let say we want to use a Field Validator to make sure our names are Capitalised

```python
from django.core.exceptions import ValidationError

def validate_first_letter_uppercase(value):
    if not value[0].isupper():
        msg = u"The first letter in your name must be capitalized"
        raise ValidationError(msg)

# validators.py
```

- In our forms.py we would call the validator on our fields as follows:

```python
from django import form
from .validators import validate_first_letter_uppercase

class UserInfoForm(forms.Form):
    first_name = forms.CharField(max_length=100, validators=[validate_first_letter_uppercase])
    middle_name = forms.CharField(max_length=100, required=False, validators=[validate_first_letter_uppercase])
    last_name = forms.CharField(max_length=100, validators=[validate_first_letter_uppercase])
    email = forms.EmailField()

# forms.py
```




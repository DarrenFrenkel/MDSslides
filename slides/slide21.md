## Calling Validators on ModelForms

```python
from django.forms import ModelForm
from .models import UserInfo
from .validators import validate_first_letter_uppercase

class UserInfoForm(ModelForm):

    def __init__(self):
        super(UserInfoForm, self).__init__(*args, **kwargs)
        self.fields["first_name"].validators.append(validate_first_letter_uppercase)
        self.fields["middle_name"].validators.append(validate_first_letter_uppercase)
        self.fields["last_name"].validators.append(validate_first_letter_uppercase)

    class Meta:
        model = UserInfo
        fields = ['first_name', 'middle_name', 'last_name', 'email']

# forms.py
```

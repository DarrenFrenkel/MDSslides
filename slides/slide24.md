## Validating fields against each other continued

```python
from django.forms import ModelForm
from .models import UserInfo

class UserInfoForm(ModelForm):
    class Meta:
        model = UserInfo
        fields = ['first_name', 'middle_name', 'last_name', 'email', 'verify_email']

    def clean(self):
        if self.cleaned_data['email'] != self.cleaned_data['verify_email']:
            msg = u"Please make sure you've entered the correct email"
            raise ValidationError(msg)

# forms.py
```

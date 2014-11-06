## Manually Rendering Forms

- You could also rendering each form field individually

- Your code will look as follows:

```html
{{ form.non_field_errors }}
<div class="fieldWrapper">
    {{ form.first_name.errors }}
    <label for="id_first_name">First Name:</label>
    {{ form.first_name }}
</div>
<div class="fieldWrapper">
    {{ form.middle_name.errors }}
    <label for="id_middle_name">Middle Name:</label>
    {{ form.middle_name }}
</div>
<div class="fieldWrapper">
    {{ form.last_name.errors }}
    <label for="id_last_name">Last Name:</label>
    {{ form.last_name }}
</div>
<div class="fieldWrapper">
    {{ form.email.errors }}
    <label for="id_email">Email</label>
    {{ form.email }}
</div>

# index.html
```

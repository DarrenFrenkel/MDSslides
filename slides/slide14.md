## Automatically Rendering your form

- You could automatically render your forms as different html markup
    - {{ form.as_table }} will render them as table cells wrapped in <tr> tags
    - {{ form.as_p }} will render them wrapped in <p> tags
    - {{ form.as_ul }} will render them wrapped in <li> tags

- To render your form with p tags your html template would look as follows:

```html
<form action="" method="post">
    {% csrf_token %}
    {{ form.as_table }}
    <input type="submit" value="Submit" />
</form>
<!-- index.html -->
```

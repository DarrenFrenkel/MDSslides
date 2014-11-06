### Our HTML

- Instead of rewriting our forms we coud just use the form context variable inside our html

```html
<form action="" method="post">
    {% csrf_token %}
    {{ form }}
    <input type="submit" value="Submit" />
</form>

<!-- index.html -->
```

- This will render all the fields on our form
- We will show you how to render individual fields later
- note the csrf_token protects agains Cross Site Request Forgery



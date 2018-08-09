# jquery-formset
Javascript library to handle the Django's formset

# How to use it

Add the library at the end of your html page. Don't forget to include jQuery lib before.

```html
<script src="jquery.formset.js"></script>
```

Initialize the script

```html
<script>
    $('#formset-wrapper').formset({
        templateId: '__TEMPLATE_ID__',
        prefix: 'form',
        addButtonId: 'add-row',
        deleteButtonClassname: 'delete-row'
    });
</script>
```

Create a template

```html
<script type="text/template" id="__TEMPLATE_ID__">
    {{ formset.empty_form.as_p }}
    <p><a href="#" id="delete-item" data-row-id="id_{{ formset.empty_form.prefix }}">delete</a></p>
</script>
```

Define wrapper and a items list

```html
<div id="formset-wrapper">
    <div class="items">
    {% for form in formset.forms %}
        <div class="item" id="id_{{ opt_form.prefix }}">
            {{ form.as_p }}
        </div>
    {% endfor %}
    </div>
    <a href="#" id="add-item">Add row</a>
</div>
```


# Adding the template

Now we need the template where the Geocollection detail will be rendered.
Let's create a `geocollections` folder inside the `my_geonode/templates` folder with a file named `geocollection_detail.html`:

```bash
mkdir -p my_geonode/templates/geocollections/
vim my_geonode/templates/geocollections/geocollection_detail.html
```

{% raw %}
```html
{% extends "geonode_base.html" %}

{% block body %}
    <h2>Geocollection {{ object.name }}</h2>
    <p>Group: {{ object.group.title }}</p>
    <p>Resources:</p>
    <ul>
        {% for resource in object.resources.all %}
            <li>{{ resource.title }}</li>
        {% endfor %}
    </ul>
{% endblock %}
```
{% endraw %}

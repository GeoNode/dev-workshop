# Site wide customization

Now we can make some changes that will apply to the whole site.
We can add a `Geocollections`entry in the top menu bar.

Edit the `site_base.html`file in the templates folder and uncomment the list item adapting the text as well.

```html
{% comment %}
Add Tab for Third Party Apps
<li>
 <a href="{{ PROJECT_ROOT }}app">App</a>
</li>
{% endcomment %}
```

into:

```html
<li>
 <a href="{{ PROJECT_ROOT }}">Geocollections</a>
</li>
```

On browser refresh you will see a new entry in the nav bar which is persistent to the whole site.

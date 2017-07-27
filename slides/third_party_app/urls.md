# Add url configuration

In our urls.py add the following:

```python
from wagtail.wagtailadmin import urls as wagtailadmin_urls
from wagtail.wagtaildocs import urls as wagtaildocs_urls
from wagtail.wagtailcore import urls as wagtail_urls
```

and in the url patterns:
```python
url(r'^cms/', include(wagtailadmin_urls)),
url(r'', include('puput.urls')),
url(r'', include(wagtail_urls)),
```

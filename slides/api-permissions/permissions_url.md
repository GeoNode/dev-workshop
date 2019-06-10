# Permissions logic (url)

Lastly we need a url to map our client to our view, in `urls.py`
```bash
vim geocollections/urls.py
```

```python
from django.conf.urls import url
  
from .views import GeocollectionDetail, geocollection_permissions

urlpatterns = [
    url(r'^(?P<slug>[-\w]+)/$',
        GeocollectionDetail.as_view(),
        name='geocollection-detail'),

    url(r'^permissions/(?P<collection_id>\d+)$',
        geocollection_permissions,
        name='geocollection_permissions'),
]
```

This url will be called with the id of the geocollection, the id will be passed to the view in order to det the permissions.

# Add url configuration

In order to access our view we also need an url mapping,

We can create a `urls.py` file containing a url mapping to our generic view:
```bash
vim geocollections/urls.py
```

```python
from django.conf.urls import url
  
from .views import GeocollectionDetail

urlpatterns = [
    url(r'^(?P<slug>[-\w]+)/$',
        GeocollectionDetail.as_view(),
        name='geocollection-detail'),
]
```
We also need to register the app urls in the project urls.
So let's modify the *my_geonode* `urls.py` file adding the following:
```bash
vim my_geonode/urls.py
```

```python
...
urlpatterns += [
## include your urls here
    url(r'^geocollections/', include('geocollections.urls')),
]
...
```

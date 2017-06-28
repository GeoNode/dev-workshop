# Add url configuration

In order to access our view we also nee a url mapping,

We can create a urls.py file containing a url mapping to our generic view:

```python
from django.conf.urls import patterns, url

from .views import GeocollectionDetail

urlpatterns = patterns('views',
    url(r'^(?P<slug>[-\w]+)/$', GeocollectionDetail.as_view(), name='geocollection-detail'),
)

```
We also need to register the app urls in the project urls.
Modify the `my_geonode`url adding the following:
```python
url(r'^geocollections/', include('geocollections.urls')),
```

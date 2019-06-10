# Add a url for our API

In order to publish our API we need a url and we want that url to appear under the GeoNode's `/api` domain.

The final url for our API has to be `/api/geocollections`.

We can inject the url into the GeoNode API by adding the following in our `my_geonode/urls.py` file:
```bash
vim my_geonode/urls.py
```

```python
from geonode.api.urls import api
from geocollections.api import GeocollectionResource

api.register(GeocollectionResource())
```
And add the follofing in the urlpatterns:

```python
url(r'', include(api.urls)),
```

The final result will be:
```python
from django.conf.urls import url, include
from django.views.generic import TemplateView

from geonode.urls import urlpatterns

from geonode.api.urls import api
from geocollections.api import GeocollectionResource

api.register(GeocollectionResource())

urlpatterns += [
## include your urls here
    url(r'', include(api.urls)),
    url(r'^geocollections/', include('geocollections.urls')),
]

urlpatterns = [
   url(r'^/?$',
       TemplateView.as_view(template_name='site_index.html'),
       name='home'),
 ] + urlpatterns
```
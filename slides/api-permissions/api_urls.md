# Add a url for our API

In order to publish our API we need a url and we want that url to appear under the GeoNode's `/api` domain.

The final url for our API has to be `/api/geocollections`.

We can inject the url into the GeoNode API by adding the following in our `my_geonode/urls.py` file:

```python
from geonode.api.urls import api
from geocollections.api import GeocollectionResource

api.register(GeocollectionResource())
```
And add the follofing in the urlpatterns:

```python
url(r'', include(api.urls)),
```

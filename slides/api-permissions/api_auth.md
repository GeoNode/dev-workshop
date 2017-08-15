# API authorization

We want the API to respect our custom permissions, we can easily achieve this by adding the following to the beginning of api.py:

```python
from tastypie.authorization import DjangoAuthorization
from guardian.shortcuts import get_objects_for_user


class GeocollectionAuth(DjangoAuthorization):
    def read_list(self, object_list, bundle):
        permitted_ids = get_objects_for_user(
            bundle.request.user,
            'geocollection.view_geocollection').values('id')

        return object_list.filter(id__in=permitted_ids)

    def read_detail(self, object_list, bundle):
        return bundle.request.user.has_perm(
            'view_geocollection',
            bundle.obj)
```

and this to the GeocollectionResource Meta class:

```python
authorization = GeocollectionAuth()
```

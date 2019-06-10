# Let's test permissions on API

We can test the permissions on API by manually set a permission from the command line and check that the API respects it.

With `python manage.py shell` in our my_geonode folder we open a geonode shell.

A perm spec could look like this:

```python
perms = {
  'users': {
    'AnonymousUser': ['view_geocollection'],
    'alessio': ['view_geocollection']
  }
}
```

and we can assign the permissions with:

```python
from geocollections.models import Geocollection
Geocollection.objects.first().set_permissions(perms)
```

our http://localhost:8000/api/geocollections should now list the geocollection.

If you remove the 'AnonymousUser' line from `perms` and assign again the permissions ti will disappear.
```python
perms = {
  'users': {
    'alessio': ['view_geocollection']
  }
}
```
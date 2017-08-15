# Permissions logic (permissions objects)

We need to add the permissions object to the database. We can do this by adding the following meta class to our Geocollection model, guardian will take care of creating the objects for us.

```python
class Meta:
        permissions = (
            ('view_geocollection', 'Can view geocollection'),
        )
```
the run a `python manage.py migrate` to install them

# Permissions logic (permissions objects)

We need to add the permissions object to the database.

We can do this by adding the following meta class to our Geocollection model, guardian will take care of creating the objects for us.
```bash
vim geocollections/models.py
```

```python
    class Meta:
        permissions = (
            ('view_geocollection', 'Can view geocollection'),
        )
```
Then run `python manage.py makemigrations` and `python manage.py migrate` to install them.

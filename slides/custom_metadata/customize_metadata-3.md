# Customize Metadata (3)

**Updating the Model**

You will need to `run migrations` again and restart the server...

```shell
workon my_geonode
python manage.py makemigrations
python manage.py migrate
```

Now we have patched the DB. 

It is not yet sufficient. We need to display the new field also.

Let's extend the default templates.
# Customize Metadata (3)

**Resource Base Patching**

You will need to run migrations again and restart the server...

```bash
workon geonode

DJANGO_SETTINGS_MODULE=my_geonode.local_settings python manage.py makemigrations

DJANGO_SETTINGS_MODULE=my_geonode.local_settings python manage.py migrate

sudo service apache2 restart

```

Now we have patched the DB. It is not yet sufficient. We need to display the new field also.
Let's extend the default templates.
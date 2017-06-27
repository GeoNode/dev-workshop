# Create the django app

Django gives us an handy command to create apps.
We already used `startproject` to create our geonode-project, now we can use `startapp` to create the app.

`python manage.py startapp geocollections`

This will create a folder named `geocollections` that contains empty models and views.

We need to add the new app to the `INSTALLED_APPS` of our project.
in `my_geonode/settings.py` line 56 change:

`INSTALLED_APPS = INSTALLED_APPS + ('my_geonode',)` to
`INSTALLED_APPS = INSTALLED_APPS + ('my_geonode', 'geocollections',)`

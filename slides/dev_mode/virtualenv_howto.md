# Python virtualenv

How to:
* `mkvirtualenv my_geonode`
* `git clone -b 2.8.0 --single-branch https://github.com/GeoNode/geonode`
* `pip install -r geonode/requirements.txt && pip install -e geonode`
* `pip install gdal`
* `cd geonode && paver setup`
* `python manage.py migrate`
* `python manage.py createsuperuser` (there must be a superuser named 'admin' when in dev mode)
* `python manage.py loaddata geonode/base/fixtures/initial_data.json`
* `python manage.py loaddata geonode/base/fixtures/default_oauth_apps.json`
* `paver start_geoserver && python manage.py runserver`

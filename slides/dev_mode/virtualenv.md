# Python virtualenv

requirements:
* [virtualenv](https://github.com/pypa/virtualenv) + [virtualenvwrapper](https://bitbucket.org/virtualenvwrapper/virtualenvwrapper/)
* [git](https://git-scm.com/)
* [Java](https://www.java.com/en/) Virtual Machine

How to:
* `mkvirtualenv my_geonode`
* `git clone -b 2.6.x https://github.com/GeoNode/geonode`
* `pip install -e geonode && pip install -r geonode/requirements.txt`
* `cd geonode && paver setup`
* `python manage.py migrate`
* `python manage.py createsuperuser` (there must be a superuser named 'admin' when in dev mode)
* `python manage.py loaddata geonode/base/fixtures/initial_data.json`
* `python manage.py loaddata geonode/base/fixtures/default_oauth_apps.json`
* `paver start_geoserver && python manage.py runserver`

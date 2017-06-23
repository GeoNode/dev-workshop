# How to run it in development mode

A normal GeoNode dev mode installation can be run by 'paver start'
Paver will start geoserver and the run django. In our case we want to run django with 'my_geonode' settings so we need to run geoserver and django separately.

* `cd geonode && paver start_geoserver`
* `cd ../my_geonode && python manage.py runserver`

You can wrap this in a simple executable .sh script

### Access geonode at http://localhost:8000

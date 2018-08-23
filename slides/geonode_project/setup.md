# Let's create our own geonode-project

#### Make sure to run it just outside the geonode folder as we will keep them completely separate

`$ django-admin.py startproject my_geonode --template=https://github.com/GeoNode/geonode-project/archive/master.zip -e py,rst,json,yml,ini,env,sample -n Dockerfile my_geonode`

Now make sure to have your virtualenv enabled and run:

`$ pip install -e my_geonode`

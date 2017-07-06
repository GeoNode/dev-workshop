# Setup the server

There are different options for deploying:

* on a dedicated Ubuntu 16.04 server installing GeoNode with apt-get (sistemwide installation)
* on a server with other services installing GeoNode and my_geonode in a python virtualenv
* on a dedicated server using a python sistemwide installation (`sudo pip install ..` )

For this workshop we assume the first option so that apache and tomcat as well as postgres are all set up.
Follow the quick install doc at http://docs.geonode.org/en/master/tutorials/install_and_admin/quick_install.html
The other installations require a full manual setup as described in the docs at http://docs.geonode.org/en/master/tutorials/install_and_admin/geonode_install/index.html

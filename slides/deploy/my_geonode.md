# Setup our my_geonode

We need now to install our `my_geonode` project following these steps:

* git clone from your repository (in the folder of your preference)
* sudo pip install -e my_geonode
* edit the settings where needed
* edit `/etc/apache2/sites-enabled/geonode.conf` replacing the wsgi path to the `my_geonode/my_geonode/wsgi.py` file
* add the apache rights to the my_geonode folder with a directory like
```conf
<Directory "/path/to/my_geonode/">
       Order allow,deny
       Require all granted
</Directory>
```
* Test your server.

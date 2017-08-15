# Data container volume

- Essentially it is a docker image that defines storage space for the GeoServer data directory
- The container doesn’t run a process and in fact stops immediately after `docker run` is called but it still exists in a stopped state
- Can be easily added to a container with the `--volumes-from` option

```
docker run -d --volumes-from geoserver_data_dir --name geoserver geonode/geoserver
```

- The above command run a GeoServer container with the external volume from our data container which acts as **GeoServer Data Directory** where all configurations for the layers in GeoNode reside

- You can verify the directory content with the command below:

```
docker exec -it geoserver ls -lart /geoserver_data/data/
```

```
drwxr-xr-x  3 root root 4096 Aug 27 16:51 workspaces
-rw-r--r--  1 root root 1547 Aug 27 16:51 wms.xml
-rw-r--r--  1 root root 2013 Aug 27 16:51 wfs.xml
-rw-r--r--  1 root root 1285 Aug 27 16:51 wcs.xml
drwxr-xr-x  2 root root 4096 Aug 27 16:51 styles
drwxr-xr-x  8 root root 4096 Aug 27 16:51 security
drwxr-xr-x  2 root root 4096 Aug 27 16:51 printing
drwxr-xr-x  2 root root 4096 Aug 27 16:51 plugIns
drwxr-xr-x  2 root root 4096 Aug 27 16:51 palettes
drwxr-xr-x  2 root root 4096 Aug 27 16:51 logs
-rw-r--r--  1 root root  144 Aug 27 16:51 logging.xml
drwxr-xr-x  2 root root 4096 Aug 27 16:51 images
-rw-r--r--  1 root root 1111 Aug 27 16:51 gwc-gs.xml
-rw-r--r--  1 root root 1374 Aug 27 16:51 global.xml
drwxr-xr-x  2 root root 4096 Aug 27 16:51 geonode
drwxr-xr-x  2 root root 4096 Aug 27 16:51 demo
-rw-r--r--  1 root root  184 Aug 27 16:51 README.rst
drwxr-xr-x 12 root root 4096 Aug 27 16:51 .
drwxr-xr-x  7 root root 4096 Aug 27 17:08 ..
```

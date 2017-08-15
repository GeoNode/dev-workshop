# Compose orchestration

```yml
    django:
      image: geonode/django
      links:
        - postgres
        - elasticsearch
        - rabbitmq
      command: django-admin.py runserver 0.0.0.0:8000 --settings=geonode.settings
      env_file:
        - ./scripts/docker/env/production/django.env

    geoserver:
      image: geonode/geoserver:latest
      links:
        - postgres
      ports:
        - "8080"
      volumes:
        - /var/run/docker.sock:/var/run/docker.sock
      volumes_from:
        - data_dir_conf
      env_file:
        - ./scripts/docker/env/production/geoserver.env

    geonode:
      image: geonode/nginx:geoserver
      links:
        - django
        - geoserver
      ports:
        - "80:80"

    data_dir_conf:
      image: geonode/geoserver_data:2.10.x
      container_name: geoserver_data_dir
      command: /bin/true
      volumes:
        - /geoserver_data/data

volumes:

  geoserver_data_dir:
```

* Part of the GeoNode source code
* Full support of any OS (Linux, Mac Os, Windows) and Cloud provider almost finished!
* As simple as possible to have GeoNode up and running

```
docker-compose up -d
```

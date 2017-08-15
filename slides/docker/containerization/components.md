# GeoNode containerization

![diagram](css/img/components.svg)

| IMAGE             | PORTS             |
| :---------------- | :---------------- |
| geonode/nginx:geoserver       | 0.0.0.0:80->80/tcp, 443/tcp       |
| geonode/django                | 8000/tcp                          |
| geonode/geoserver:latest      | 0.0.0.0:32770->8080/tcp           |
| postgres                      | 5432/tcp                          |
| geonode/geoserver_data:2.10.x |                                   |
| elasticsearch                 | 9200/tcp, 9300/tcp                |
| rabbitmq                      | 4369/tcp, 5671-5672/tcp, 25672/tcp|

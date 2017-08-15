# Docker compose

* The easiest possible path for developers who are not required to know [Docker](https://www.docker.com/)
* SO independent and **Docker for * ** invariant
* Data persistence
* Shortcuts for any docker command

```bash
make up # ===> docker-compose up -d and all environment variables
```

```bash
make sync:up # ===> Apply migration and all needed fixtures to work with 
```

```bash
docker-compose exec django django-admin.py migrate --noinput
docker-compose exec django django-admin.py loaddata sample_admin
docker-compose exec django django-admin.py loaddata geonode/base/fixtures/default_oauth_apps_docker.json
docker-compose exec django django-admin.py loaddata geonode/base/fixtures/initial_data.json
```

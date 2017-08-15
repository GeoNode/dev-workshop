# Shortcuts

**Makefile** that automatically run mostly django-admin commands and set all required environment variables for the Host machine

```makefile
up:
	# bring up the services
	docker-compose up -d

build:
	docker-compose build django
	docker-compose build celery

sync: up
	# set up the database tablea
	docker-compose exec django django-admin.py migrate --noinput
	docker-compose exec django django-admin.py loaddata sample_admin
	docker-compose exec django django-admin.py loaddata geonode/base/fixtures/default_oauth_apps_docker.json
	docker-compose exec django django-admin.py loaddata geonode/base/fixtures/initial_data.json

migrate:
	django-admin.py migrate --noinput

migrate_setup: migrate
	django-admin.py loaddata sample_admin
...
```

Let's have GeoNode ready to use from master branch

```
make up && make sync up
```

**Often master branch is broken! Please don't raise tickets for that, do it for the stable :)**

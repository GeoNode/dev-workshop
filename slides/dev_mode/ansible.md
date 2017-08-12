# Ansible

**Automation at your fingertips**

The [Ansible](https://www.ansible.com/) Role will install GeoNode and required dependencies onto an Ubuntu 16.04 (Xenial) host

Tasks included:
- PostgreSQL+PostGIS
- GeoServer
- GeoNode django application
- Nginx
- Uwsgi
- AWS RDS databases (optionally)

Use cases:
- You already have a GeoNode template published on GitHub (**For production**)
- You do not have a GeoNode template published on GitHub and wish to create one
- You do not have a GeoNode template and you do not want to create one (*demonstration-only setup*)

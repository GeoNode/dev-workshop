# Challenges (more)

Another solution:

- Python [SDK Docker API]() (formerly [docker-py]()) from inside the container

```python
import docker

BOOTSTRAP_IMAGE_CHEIP = 'codenvy/che-ip:nightly'

client = docker.from_env()
print client.info()
client.containers.run(BOOTSTRAP_IMAGE_CHEIP, network_mode='host')
```

Compose with:

```bash
export DOCKERHOST=${DOCKER_HOST} \
&& export GEONODE_HOST_IP=$(docker run --net=host codenvy/che-ip:nightly) \
&& docker-compose up --build
```

- It can also be used to get the **internal NGINX** address for the configuration of GeoNode *accessTokenUri* and *checkTokenEndpointUrl* of GeoServer. See more on our [documentation](http://docs.geonode.org/en/master/tutorials/admin/geoserver_geonode_security/index.html#geoserver-geonode-aa)

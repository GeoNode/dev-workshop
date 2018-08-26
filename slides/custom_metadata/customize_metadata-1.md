# Customize Metadata (1)

**Resource Base Patching**

This is a way to add fields directly to the ResourceBase Class without actually modifying it.
Can be done from my_geonode.apps
The ready method is invoked ad initialization time and can be currently used to tweak your app in several ways.

```python
...
class AppConfig(BaseAppConfig):

    name = "my_geonode"
    label = "my_geonode"

    def ready(self):
        super(AppConfig, self).ready()
        run_setup_hooks()
```

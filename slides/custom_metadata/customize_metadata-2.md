# Customize Metadata (2)

**Resource Base Patching**

Add the patch_resource_base method to the AppConfig and run it from the ready method.

```python
...
from django.db import models
from django.utils.translation import ugettext_lazy as _

...
class AppConfig(BaseAppConfig):

    name = "my_geonode"
    label = "my_geonode"

    def _get_logger(self):
        import logging
        return logging.getLogger(self.__class__.__module__)

    def patch_resource_base(self, cls):
        self._get_logger().info("Patching Resource Base")
        doi_help_text = _(
            'a DOI will be added by Admin before publication.')
        doi = models.TextField(
            _('DOI'),
            blank=True,
            null=True,
            help_text=doi_help_text)
        cls.add_to_class('doi', doi)

    def ready(self):
        super(AppConfig, self).ready()
        run_setup_hooks()
        
        from geonode.base.models import ResourceBase
        self.patch_resource_base(ResourceBase)
```
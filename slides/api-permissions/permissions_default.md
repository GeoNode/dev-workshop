# Permissions logic (set_default)

Let's add a method that will be used to set the default permissions on the Geocollections.
We can add this logic to the Geocollection model but could also be a generic Mixin like it is in GeoNode.

```python
from django.contrib.auth.models import Group
from django.contrib.auth import get_user_model
from django.contrib.contenttypes.models import ContentType
from django.conf import settings
from guardian.shortcuts import assign_perm, remove_perm
```
```python
def set_default_permissions(self):
        """
        Set default permissions.
        """

        # default permissions for anonymous users
        anonymous_group, created = Group.objects.get_or_create(name='anonymous')

        if settings.DEFAULT_ANONYMOUS_VIEW_PERMISSION:
            assign_perm('view_geocollection', anonymous_group, self)
        else:
            remove_perm('view_geocollection', anonymous_group, self)

        # default permissions for group members
        assign_perm('view_geocollection', self.group, self)
```

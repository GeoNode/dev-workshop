# Add permissions methods

Let's add a method that will be used to set the default permissions on the Geocollections
```python
from django.contrib.auth.models import Group
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
        assign_perm('view_geocollection', self.group.group, self)

```

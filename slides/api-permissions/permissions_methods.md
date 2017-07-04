# Permissions logic (methods)

Now we need a method to add generic permissions, we want to be able to assign view permissions to groups and single users.
We can add this to our Geocollection model

```python
def set_permissions(self, perm_spec):
  anonymous_group = Group.objects.get(name='anonymous')
  remove_object_permissions(self)

  if 'users' in perm_spec and "AnonymousUser" in perm_spec['users']:
    assign_perm('view_geocollection', anonymous_group, self)

  if 'users' in perm_spec:
    for user, perms in perm_spec['users'].items():
      user = get_user_model().objects.get(username=user)
      assign_perm('view_geocollection', user, self)

  if 'groups' in perm_spec:
    for group, perms in perm_spec['groups'].items():
      group = Group.objects.get(name=group)
      assign_perm('view_geocollection', group, self)
```
```python
def remove_object_permissions(self):
  from guardian.models import UserObjectPermission, GroupObjectPermission
  UserObjectPermission.objects.filter(content_type=ContentType.objects.get_for_model(self),
                                        object_pk=self.id).delete()
  GroupObjectPermission.objects.filter(content_type=ContentType.objects.get_for_model(self),
                                         object_pk=self.id).delete()
```

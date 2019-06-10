# Permissions logic (view)

We can add now a view to receive and set our permissions, in `views.py`:
```bash
vim geocollections/views.py
```

```python
import json
from django.core.exceptions import PermissionDenied
from django.http import HttpResponse
```
```python
def geocollection_permissions(request, collection_id):

    collection = Geocollection.objects.get(id=collection_id)

    if not user.has_perm('view_geocollection', collection):
      return HttpResponse(
          'You are not allowed to change permissions for this resource',
          status=401,
          content_type='text/plain')

    if request.method == 'POST':
        success = True
        message = "Permissions successfully updated!"
        try:
            permission_spec = json.loads(request.body)
            collection.set_permissions(permission_spec)

            return HttpResponse(
                json.dumps({'success': success, 'message': message}),
                status=200,
                content_type='text/plain'
            )
        except:
            success = False
            message = "Error updating permissions :("
            return HttpResponse(
                json.dumps({'success': success, 'message': message}),
                status=500,
                content_type='text/plain'
            )
```

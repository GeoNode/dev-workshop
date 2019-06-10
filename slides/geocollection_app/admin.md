# Enable the admin panel

We need a user interface where we can create geocollections.

Django makes this very easy, we just need the `admin.py` file as follows:
```bash
vim geocollections/admin.py
```

```python
from django.contrib import admin

from .models import Geocollection


class GeocollectionAdmin(admin.ModelAdmin):
     prepopulated_fields = {"slug": ("name",)}
     filter_horizontal = ('resources',)


admin.site.register(Geocollection, GeocollectionAdmin)
```

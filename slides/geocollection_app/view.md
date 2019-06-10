# Adding a view

We can use a django generic view to show the collections detail.

Add the following in the `views.py` file:
```bash
vim geocollections/views.py
```

```python
from django.views.generic import DetailView

from .models import Geocollection


class GeocollectionDetail(DetailView):

    model = Geocollection
```

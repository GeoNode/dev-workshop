# A note on inheritance in python/django

Python modules and objects are first searched in the most local path and in cascade up to the python system installation folder.

Django use the same approach, for example templates and apps are first searched locally and, if found, the others with the same name are not executed.

The GeoNode-project is a django project template that takes advantage of this behavior to use GeoNode as a library and add its own customized templates and apps.

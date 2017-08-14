# Permissions and APIs

In this chapter we will add some more advanced logic like permissions and APIs.

The permissions in GeoNode are managed with django-guardian, a library which allow to set object level permissions (django has table level authorization).

The APIs are implemented through django-tastypie.

* Permissions on who can view the geocollection
* How to add templated and js to embed a permission ui in our geocollection detail page
* API to serve json serialized searchable endpoint

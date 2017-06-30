# A note on the client part

Server side logic is just one part necessary to implement permissions.

Due to the time restrictions of this workshop we'll not go through the client part but here's a checklist of what is necessary:

* a template snippet that can be embedded in the
geocollection_detail.html, you can copy and simplify _permissions_form.html and _permissions.html (in geonode/templates)
* a javascript file that will collect permissions settings and send them to the server,
you can copy and simplify: _permissions_form_js.html (in geonode/templates)

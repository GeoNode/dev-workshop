# How to customize a generic page

As you can see in the templates folder there are only the `site_index.html` and the `site_base.html` files.
In order to customize another GeoNode page, for example the layers list page, you need to recreate the same folder structure of the GeoNode templates folder and add a file with the same name.

For the layers list page we can add a folder named `layers`into the template folder and a file named `layer_list.html`in there.
The changes made in this file will only affect the layer list page.

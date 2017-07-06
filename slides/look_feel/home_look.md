# Home page look and feel
To change the theme of our geonode-project we can act on the `site_base.css` file available in the `my_geonode/my_geonode/static/css` folder.

The file is empty so we can inspect elements of the home page with the browser's developer tools and define css rules in there.

For example if we want to change the background of the `jumbotron`, we can add

`.home .jumbotron { background: yellow }`

Adding the `.home`class is necessary in order to let the rule have precedence over the GeoNode's one. We see this by inspecting the element in the console.

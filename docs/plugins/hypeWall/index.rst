hypeWall
========

Rich user interface for sharing status updates, links and content via user walls.

- URL-parsing with embeddable content view
- Geotagging (based on browser location)
- Inline multi-file upload
- Friend tagging
- Content attachments

Gotchas
~~~~~~~

* Reverse geocoding is performed via Nominatim http://wiki.openstreetmap.org/wiki/Nominatim.
Reverse geocoding (i.e. browser position coordinates to human readable address)
will not work in https. Implement a custom solution using a paid/free/proprietary
service that does the same

* Icons are not included with the plugin. You will need to load FontAwesome CSS,
either by registering it in your theme, or using one of the available Elgg plugins.

* You can add wall tabs and forms by extending the ```'framework/wall/container/extend'``` view

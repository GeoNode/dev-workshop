# Edit my_geonode settings

Let's add the correct django app in our settings.py.

```python
'wagtail.wagtailforms',
'wagtail.wagtailredirects',
'wagtail.wagtailembeds',
'wagtail.wagtailsites',
'wagtail.wagtailusers',
'wagtail.wagtailsnippets',
'wagtail.wagtaildocs',
'wagtail.wagtailimages',
'wagtail.wagtailsearch',
'wagtail.wagtailadmin',
'wagtail.wagtailcore',
'puput',
'modelcluster',
'wagtail.contrib.wagtailroutablepage',
'wagtail.contrib.wagtailsitemaps',
'compressor'
```
then run:
```shell
python manage.py migrate
```

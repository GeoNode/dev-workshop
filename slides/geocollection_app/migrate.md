# Migrations

At this point we need to ask django to create the database table.
Django since version [1.8](https://docs.djangoproject.com/en/1.8/) has embedded [migrations](https://docs.djangoproject.com/en/1.8/topics/migrations/) mechanism and we need to use them in order to change the state of the db.

Make sure to be in the `my_geonode` folder

```python
python manage.py makemigrations
python manage.py migrate
```

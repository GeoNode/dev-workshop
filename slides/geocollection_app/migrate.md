# Migrations

At this point we can ask django to create the database table.
Django since version 1.8 has embedded migrations mechanism and we need to use migrations in order to change the state of the db.

Make sure to be in the my_geonode folder

```python
python manage.py makemigrations geocollections
python manage.py migrate
```

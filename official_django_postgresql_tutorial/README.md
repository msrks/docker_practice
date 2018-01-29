## official docker-compose tutorial (django+postgresql)

https://docs.docker.com/compose/django/

django projectの作成

```
$ docker-compose run web django-admin startproject composeexample .
```

django `settings.py/DATABASES` の編集

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}
```

```
$ docker-compose up
```

#### コメント

ベースイメージが `python:3.6.2-alpine` だと `psycopg2` がpipで入らなかったが、 `python:3` に変えたらうまくいった。

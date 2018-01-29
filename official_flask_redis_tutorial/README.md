## official docker-compose tutorial (flask+redis)

https://docs.docker.com/compose/gettingstarted/

```
$ docker-compose up
```

```
$ docker-compose ps
               Name                             Command               State           Ports         
----------------------------------------------------------------------------------------------------
officialflaskredistutorial_redis_1   docker-entrypoint.sh redis ...   Up      6379/tcp              
officialflaskredistutorial_web_1     python app.py                    Up      0.0.0.0:5000->5000/tcp
```

run one-off commands

```
$ docker-compose --help
$ docker-compose run web env
```

run background

```
$ docker-compose up -d
$ docker-compose stop
```

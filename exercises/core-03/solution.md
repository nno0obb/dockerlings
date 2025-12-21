```
$ docker build . -t logging-app
$ docker images logging-app
$ docker run -d --name my-logger logging-app
$ docker logs my-logger
$ docker logs my-logger > logs.txt
```

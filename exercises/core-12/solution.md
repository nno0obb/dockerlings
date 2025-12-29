```
$ vim docker-compose.yml
$ cat docker-compose.yml
services:
  redis-server:
    image: redis:alpine
    container_name: c12-redis
    ports:
      - "6379:6379"
$ docker compose up
$ brew install redis
$ redis-cli ping
```

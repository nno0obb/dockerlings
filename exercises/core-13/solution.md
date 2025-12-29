```
$ vim docker-compose.yml
$ cat docker-compose.yml
services:
  web:
    build: ./app
    container_name: c13-web
    ports:
      - "8013:5000"
    environment:
      - REDIS_HOST=redis
    depends_on:
      - redis

  redis:
    image: redis:alpine
    container_name: c13-redis
    ports:
      - "6379:6379"
$ docker compose up --build
$ for i in {1..5}; do echo $(curl localhost:8013); done
```

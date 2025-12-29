```
$ vim docker-compose.yml
$ cat docker-compose.yml
services:
  web:
    build: ./app
    container_name: c14-web
    ports:
      - "8014:5000"
    networks:
      - c14-app-net
    environment:
      - REDIS_HOST=redis
    depends_on:
      - redis

  redis:
    image: redis:alpine
    container_name: c14-redis
    ports:
      - "6379:6379"
    volumes:
      - redis-data:/data
    networks:
      - c14-app-net

volumes:
  - redis-data

networks:
  - c14-app-net
$ docker compose up --build
$ for i in {1..5}; do echo $(curl -s localhost:8014); done  # 1~5
$ <Ctrl+C>
$ docker compose up --build
$ for i in {1..5}; do echo $(curl -s localhost:8014); done  # 6~10
$ docker cp c14-redis:/data/dump.rdb .
$ <Ctrl+C>
$ docker volume ls
$ docker volume inspect core-14_redis-data
$ redis-server --dbfilename dump.rdb
$ redis-cli get hits
```

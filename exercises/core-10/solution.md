```
$ docker network create c10-network
$ docker network ls
$ docker pull postgres:14-alpine
$ docker pull busybox
$ vim run-containers.sh
...
$ cat run-containers.sh
...
docker run \
  --detach \
  --name c10-db \
  --network c10-network \
  --env POSTGRES_PASSWORD=mysecretpassword \
  postgres:14-alpine
...
docker run \
  --detach \
  --name c10-app \
  --network c10-network \
  busybox sleep 3600
```

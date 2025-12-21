```
$ docker run --detach --name c4-container nginx
$ docker cp ./run-inside-container.sh c4-container:/tmp
$ docker exec c4-container chmod +x /tmp/run-inside-container.sh
$ docker exec c4-container /tmp/run-inside-container.sh
$ docker cp c4-container:/tmp/container-info.txt ./
$ docker stop c4-container && docker rm c4-container
```

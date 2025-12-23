```
$ docker run \
  --name c9-dev-server \
  --publish 8009:80 \
  --mount type=bind,source=./app,target=/usr/share/nginx/html,readonly \
  --detach \
  nginx
$ curl localhost:8009
$ gsed -i 's/Version 1/Version 2/g' ./app/index.html
$ curl localhost:8009
$ docker stop c9-dev-server && docker rm c9-dev-server
```

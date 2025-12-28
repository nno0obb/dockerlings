```
$ vim Dockerfile
$ cat Dockerfile
...
EXPOSE 8080
...
$ docker build --tag c11-app .
$ docker run \
  --detach \
  --name c11-server \
  --publish 8011:8080 \
  c11-app
```

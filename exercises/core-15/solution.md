```
$ cd app
$ go build
$ ./dockerlings-go-app
$ curl localhost:8080
$ <Ctrl+C>
$ docker build . --tag core-15
$ docker run --rm core-15 stat /server
$ vim Dockerfile
$ cat Dockerfile
...
FROM golang:1.21-alpine AS builder
FROM scratch
COPY --from=builder /server /server
...
$ docker run --rm --publish "8080:8080" core-15
$ curl localhost:8080
```

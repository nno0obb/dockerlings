```
$ mkdir pgdata
$ docker pull postgres:16
$ docker images postgres
$ docker run --detach --name c8-postgres --volume ./pgdata:/var/lib/postgresql/data postgres:16
$ docker logs c8-postgres
$ docker run \
  --detach \
  --name c8-postgres \
  --volume ./pgdata:/var/lib/postgresql/data \
  --env POSTGRES_PASSWORD=password \
  postgres:16
$ docker exec --interactive --tty c8-postgres psql -U postgres
postgres=# CREATE TABLE dvd_rentals (title TEXT);
postgres=# INSERT INTO dvd_rentals (title) VALUES ('The Grand Budapest Hotel');
postgres=# SELECT * FROM dvd_rentals;
postgres=# \q
$ docker stop c8-postgres && docker rm c8-postgres
$ docker run \
  --detach \
  --name c8-postgres \
  --volume ./pgdata:/var/lib/postgresql/data \
  --env POSTGRES_PASSWORD=password \
  postgres:16
$ docker exec --interactive --tty c8-postgres psql -U postgres
postgres=# SELECT * FROM dvd_rentals;
postgres=# \q
$ docker stop c8-postgres && docker rm c8-postgre
```

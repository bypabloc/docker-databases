# Para Resturar y Respaldar necesitamos obtener el CONTAINER ID:
``` bash
sudo docker ps
```

Example output:

``` bash
CONTAINER ID   IMAGE                  COMMAND                  CREATED        STATUS       PORTS                                                            NAMES
ae38154bc560   mysql:8.0.28           "docker-entrypoint.s…"   15 hours ago   Up 3 hours   3306/tcp, 33060/tcp, 0.0.0.0:3308->3307/tcp, :::3308->3307/tcp   mysql
4287dae4e916   mariadb:10.3.16        "docker-entrypoint.s…"   15 hours ago   Up 3 hours   0.0.0.0:3307->3306/tcp, :::3307->3306/tcp                        mariadb
f807cae10fd5   postgres:13.0-alpine   "docker-entrypoint.s…"   15 hours ago   Up 3 hours   0.0.0.0:5433->5432/tcp, :::5433->5432/tcp                        postgres
```

Ejemplo de la de mysql:
``` bash
ae38154bc560
```

## Resturar
``` bash
cat <path-file-sql>.sql | sudo docker exec -i <container-id> mysql -u <user> --password=<password> <db-name>
```

``` bash
cat database.sql | sudo docker exec -i ae38154bc560 mysql -u root --password=123456 database-db
```

## Backup

``` bash
sudo docker exec <container-id> mysqldump -u <user> --password=<password> <db-name> > <path-file-sql>.sql
```

``` bash
sudo docker exec ae38154bc560 mysqldump -u root --password=123456 database-db > database.sql
```


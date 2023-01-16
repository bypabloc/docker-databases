## Para obtener la info de todas las imagenes:
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

## Para obtener la IP de un contenedor ejecutamos el siguiente comando:
``` bash
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <CONTAINER ID>
```

## Obtenemos algo como lo siguiente:
``` bash
172.20.0.7
```

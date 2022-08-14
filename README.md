## Entorno de desarrollo
- Ubuntu 21.10
- Docker version 20.10.14, build a224086
- Docker Compose version 1.26.0, build d4451659

### Requisitos previos:
1. Docker instalado en su servidor conforme a los pasos 1 y 2 de [Cómo instalar y usar Docker en Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
2. Docker Compose instalado en su servidor conforme el paso 1 de [Cómo instalar Docker Compose en Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

## Comandos para arrancar el contenedor:
``` bash
sudo docker-compose up -d --build --remove-orphans --force-recreate
```

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

## Para realizar un backup o restore en la db:
[MySql](/README-MYSQL.md)


## Nota, comandos docker:

### Comandos para bajar todos los contenedores:
``` bash
sudo docker-compose down
```
### Comandos para bajar todos los contenedores:
``` bash
sudo docker rm -f $(docker ps -a -q)
```
### Comandos para bajar todas las imagenes:
``` bash
sudo docker rmi -f $(docker images -aq)
```

### Comandos para bajar todos los volumenes:
``` bash
sudo docker volume rm $(docker volume ls -q)
```
### Para eliminar todas las imagenes que no estan usadas por contenedores existentes, usa la opcion -a:
``` bash
docker image prune -a
```

## Si aparece un error como el siguiente:
``` bash
ERROR: Pool overlaps with other one on this address space
```
## Se puede solucionar con el comando:
``` bash
docker-compose down
docker network prune -f
```

## Configurar archivo template:
``` bash
git config --global ./.gitmessage ~/.gitmessage
```
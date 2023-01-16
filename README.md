## Entorno de desarrollo
- Ubuntu 21.10
- Docker version 20.10.14, build a224086
- Docker Compose version 1.26.0, build d4451659

### Requisitos previos:
1. Docker instalado en su servidor conforme a los pasos 1 y 2 de [Cómo instalar y usar Docker en Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
2. Docker Compose instalado en su servidor conforme el paso 1 de [Cómo instalar Docker Compose en Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

### Comandos para arrancar el contenedor:
``` bash
sudo docker-compose up -d --build --remove-orphans --force-recreate
```

- [Guia para obtener info de las imagenes y obtener la API de la DB de tu preferencia](/readme/images-ip.md)
- [Guia para realizar un backup o restore en mysql](/readme/db/mysql.md)
- [Guia para realizar un backup o restore en postgresql](/readme/db/postgresql.md)

- [Comandos para limpiar imagenes de docker](/readme/down-container.md)

- [Si te trabas, posibles soluciones](/readme/troubleshooting.md)

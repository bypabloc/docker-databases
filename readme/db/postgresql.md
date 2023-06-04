# Para Resturar y Respaldar necesitamos obtener el CONTAINER ID:

## Resturar
``` bash
cat <path-file-sql>.sql | docker exec -i <container-id> mysql -u <user> --password=<password> <db-name>
```

``` bash
cat financier.sql | docker exec -i ab75321b02a1 psql -U postgres financial_dock
```

## Entrar a la terminal:
``` bash
docker exec -it <container-id> psql -U <user>
```

``` bash
docker exec -it ab75321b02a1 psql -U <user>
```
# Para Resturar y Respaldar necesitamos obtener el CONTAINER ID:

## Resturar
``` bash
cat <path-file-sql>.sql | docker exec -i <container-id> mysql -u <user> --password=<password> <db-name>
```

``` bash
cat pandora.sql | docker exec -i 7bec7263f3cc mysql -u root --password=123456
```

## Backup
``` bash
docker exec <container-id> mysqldump -u <user> --password=<password> <db-name> > <path-file-sql>.sql
```

``` bash
docker exec ae38154bc560 mysqldump -u root --password=123456 database-db > database.sql
```

## Entrar a la terminal:
``` bash
docker exec -it <container-id> mysql -uroot --password=<password>
```

``` bash
docker exec -it 7bec7263f3cc mysql -uroot --password=123456
```

git config --global user.name "Pablo Contreras"

git config --global user.email "pacg1991@gmail.com"
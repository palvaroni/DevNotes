## Mariadb service
```bash
docker run --name mariadb_1 -p 4306:3306 -v /home/ropa/mariadb/mysql:/var/lib/mysql \
  --restart unless-stopped -e MYSQL_ROOT_PASSWORD=root -d mariadb
```

## Database backups
Backup: 
```bash
  docker exec CONTAINER /usr/bin/mysqldump -u root --password=root DATABASE > backup.sql
```

Restore: 
```bash
  cat backup.sql | docker exec -i CONTAINER /usr/bin/mysql -u root --password=root DATABASE
```

Windows: 
```bash
  docker exec CONTAINER /usr/bin/mysqldump -u root --password=root -r DATABASE | Set-Content backup.sql
```

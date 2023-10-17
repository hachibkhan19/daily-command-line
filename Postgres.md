# daily-command-line
## How to restore sql file in postgres db
```
pg_restore -O -x -h localhost -U postgres -p 5434 -d trmisdb trmis_backend_backup_16_October_2023_11_00__AM.sql
```

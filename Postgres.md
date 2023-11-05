# How to enter Postgres using terminal
```
sudo su postgres
then psql
```

## How to restore sql file in postgres db
```
pg_restore -O -x -h localhost -U postgres -p 5434 -d trmisdb trmis_backend_backup_16_October_2023_11_00__AM.sql
```
## There is 1 other session using the database.database "exception_db" is being accessed by other users
### 1st step
```
SELECT pg_terminate_backend(pg_stat_activity.pid)
    FROM pg_stat_activity
    WHERE pg_stat_activity.datname = 'exception_db'(db_name);
```
### 2nd step
```
DROP DATABASE exception_db;
```

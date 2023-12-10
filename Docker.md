### Check if PostgreSQL is running: Verify if there is a PostgreSQL database running on your host machine that is already using port 5432. You can check this using the following command:
```
  sudo lsof -i :5432
```
### To enter a PostgreSQL container, you can use the docker exec command. Here's how you can do it:
```
docker exec -it eap_db_1 bash
or
docker exec -it a3f(container id) bash
```
### After running this command, you will be inside the PostgreSQL container, and you can run PostgreSQL commands as needed. If your container is running a PostgreSQL server, you can access the PostgreSQL command-line interface (CLI) by typing:
```
psql -U your_username -d your_database_name
```

### How to Install pgAdmin on Ubuntu 22.04
 [How to Install pgAdmin on Ubuntu 22.04](https://linuxgenie.net/how-to-install-pgadmin-on-ubuntu-22-04/)

  - Step 1: Install Curl
    ```
    sudo apt install curl
    ```
  - Step 2: Add Public Key Using Curl
      ```
      sudo curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add
      ```
  - Step 3: Add pgAdmin Repository
      ```
      sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list'
      ```
  - Step 4: Update Server’s Packages
      ```
      sudo apt update
      ```
  - Step 5: Install pgAdmin
      ```
      sudo apt install pgadmin4 -y
      ```
  


### How To Install PostgreSQL on Ubuntu 22.04
  [How To Install PostgreSQL on Ubuntu 22.04](https://www.digitalocean.com/community/tutorials/how-to-install-postgresql-on-ubuntu-22-04-quickstart)
   - 1st To install PostgreSQL, first refresh your server’s local package index:
      ```
       sudo apt update
      ```
   - 2nd Then, install the Postgres package along with a -contrib package that adds some additional utilities and functionality:
       ```
       sudo apt install postgresql postgresql-contrib
       ```
   - 3rd run this command
      ```
      sudo -i -u postgres
      ```
   - 4th Then you can access the Postgres prompt by running:
      ```
      psql
      ```
  - 5th setup password for postgres User and Log in into the psql promt:
      ```
       sudo -u postgres psql
      ```
  - 6th Then in the psql console, change the password and quit
      ```
      postgres=# \password postgres
      Enter new password: <new-password>
      postgres=# \q
      ```
  - 7th run this command for showing pg_hba.conf file
      ```
      postgres=# SHOW hba_file;
      ```
  - 8th open a new terminal and paste this sudo nano /etc/postgresql/14/main/pg_hba.conf
      ```
      sudo nano /etc/postgresql/14/main/pg_hba.conf
      ```
  - 9th we find this type of value under a file
      ```
          default:
         local   all             postgres                             peer
      
         Change it: 
      
         local   all             postgres                             md5
      ```
  - 10th Then restarted the postgres service with the command
      ```
      sudo service postgresql restart
      ```
    
# How to enter Postgres using terminal
```
sudo su postgres
then psql
```

### How to check postgres is running
```
systemctl status postgresql
```

## How to restore sql file in postgres db Use pg_restore when you have a backup created using pg_dump
 ```
  pg_restore -O -x -h localhost -U postgres -p 5434 -d trmisdb trmis_backend_backup_16_October_2023_11_00__AM.sql
 ```

## How to restore sql file in postgres db Use psql when you have a plain SQL file
 ```
  psql -h localhost -U postgres -p 5432 -d trmis_prod_db -f trmis_prod_backup_20240919_184456.sql
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
### Here is the command to pull the PostgreSQL Docker image:
 ```
  docker pull postgres
 ```
### You can set up a PostgreSQL Docker container with the name postgres_docker and expose it on port 5433. Here's an example command:
```
 docker run --name postgres_docker -e POSTGRES_PASSWORD=mysecretpassword -p 5433:5432 -d postgres:latest
```
### you can connect to PostgreSQL using the host localhost and port 5433:
```
 psql -h localhost -p 5433 -U postgres -d postgres
```
### Enter Docker postgres
```
 psql -U postgres
```

### How to run Postgres in Docker
  [How to run Postgres in Docker](https://www.docker.com/blog/how-to-use-the-postgres-docker-official-image/)
  
### How to run Postgres in Docker with specific version
 ```
 docker pull postgres:16.4
 ```
### How to run Postgres in Docker with latest version
 ```
 docker pull postgres:latest
 ```

### How to run Postgres Docker image with mapping localhost port 5432 and password setup and with container name and Runs the container in detached mode 
 ```
 docker run --name postgres-container -e POSTGRES_PASSWORD=inneed8294 -d -p 5433:5432 postgres:16.4
 ```
### or if has no postgres in local machine
 ```
 docker run --name postgres-container -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres:16.4
 ```
### To connect to the PostgreSQL instance in the Docker container, use:
 ```
  psql -h localhost -p 5433 -U postgres
 ```
### Use psql to find the configuration directory:
  ```
   psql -U postgres -c 'SHOW config_file;'  
  ```
### SHOW Port
 ```
 SHOW port;
 ```

### To transfer data from one table to another table such as (option_settings) table in one PostgreSQL database to another database's option_settings table using pgAdmin and PostgreSQL, you can follow these steps:

### Step 1: Export the Data from the Source Database
  1. Open pgAdmin and connect to the source database (where the data is stored).
  2. Navigate to the option_settings table in the Object Browser.
  3. Right-click on the option_settings table and choose Export from the context menu.
  4. Choose a file format like CSV
  5. Click OK to export the data.

![Screenshot from 2024-10-22 19-48-15](https://github.com/user-attachments/assets/084be612-024a-41cb-9fc0-4000b5867f34)


![Screenshot from 2024-10-22 19-49-00](https://github.com/user-attachments/assets/6691e6b9-1831-4ddb-8895-bac9abd146ae)

### Step 2: Import the Data into the Target Database
  1. Now, connect to the target database (the new database) in pgAdmin.
  2. Right-click on the option_settings table and choose Import/Export.
  3. Under Filename, select the CSV file exported earlier.
  4. Set Format to CSV.
  5. Click OK to start importing.

![Screenshot from 2024-10-22 19-51-01](https://github.com/user-attachments/assets/f7213735-0eb8-4e26-ac87-485b7154b2f9)

![Screenshot from 2024-10-22 19-49-13](https://github.com/user-attachments/assets/ee0e5756-a2b5-4538-926a-7e1fc52dffa2)






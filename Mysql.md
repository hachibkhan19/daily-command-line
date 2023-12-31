### Restoring a MySQL Database using command line:
  - 1st step: 
    - Open a Terminal:
        ```Open a terminal or command prompt on your system.
        ```
  - 2nd step:
    - Navigate to the Directory Containing the Backup and Use the cd command to navigate to the directory where your backup file is located. For :
        ```shell
            cd /path/to/backup/directory
        ```
  - 3rd step:
    - Use mysql Command, Use the mysql command along with the appropriate options to restore the database::
        ``` shell
              mysql -u username -p database_name < backup_file.sql
        ```
    - Replace username with your MySQL username.
    - Replace database_name with the name of the database you want to restore.
    - Replace backup_file.sql with the name of your backup file.
      
###  How to Backup MySQL DB using command line

  - 1st step: 
    - Open a Terminal:
        ```Open a terminal or command prompt on your system.
        ```
  - 2nd step:
    - Use mysqldump Command and Use the mysqldump command followed by the database name to create a backup:
        ```shell
            mysqldump -u username -p database_name > backup_file.sql
        ```
    - Replace username with your MySQL username.
    - Replace database_name with the name of the database you want to back up.
    - backup_file.sql is the name of the file where the backup will be saved.


### How to enter inside mysql server in command line.
```
mysql -u (username) -p (password)
```
### How to connect database
```
use database_name;
```
### How to show all tables
```
show tables;
```
### How to Check the Status of mysql Service?
```
sudo systemctl status mysql
```
### How to restart MariaDB
```
sudo systemctl restart mariadb
```
### How to show database Log File in Docker mariadb
- First Execute this line to check its working or not for docker database DB
```
  SET GLOBAL general_log = 'ON';
  SET GLOBAL general_log_file = '/var/log/mysql/sql_log1.log';
```
- Secondly enter a mariadb database container using this command
```
docker exec -it (container id) bash
```
- Thirdly enter this location
```
root@a3f371b6277c:/var/log/mysql#
```
- Fourthly create file using this command
```
touch sql_log1.log (your log file name)
```
- Fifth show this file using this command
```
cat sql_log1.log (your log file name)
```
- Delete all data from log file using this command
```
echo "" > /var/log/mysql/sql_log1.log
```

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

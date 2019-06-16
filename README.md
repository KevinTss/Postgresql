# Postgresql

[Tuto](https://www.robinwieruch.de/postgres-sql-macos-setup/)  
[Video tuto](https://www.youtube.com/watch?v=IbVPbF7HTL4)  
  
If you have installed postgresql on your machine look here : `/usr/local/var/postgre`  
  
Or run:  
  
```
postgres --version
```
  
Run postgres:  
```
pg_ctl -D /usr/local/var/postgres start
```
To stop it, run:  
```
pg_ctl -D /usr/local/var/postgres stop
```
  
After that, you need to login into postgres:  
```
psql postgres
```
  
From here you can start to use postgres.  

## Settings
  
We want to create a user and a databse to sqtart working with.  
  
- First create a user `test_user` with as password `test_password`  
  
```
CREATE ROLE test_user WITH LOGIN PASSWORD 'test_password';
```
  
- Give permission to this user to use create database  
  
```
ALTER ROLE test_user CREATEDB;
```
  
If you want to list user du:  
```
\du
```
To exit press `ctrl + d`  
  
## Login as user that you created
  
```
psql postgres -U test_user
```
  
## Create database
  
```
CREATE DATABASE test_database;
```
  
Check if you are connected to a database:  
  
```
\connect test_database
``` 
  
See content of database  
  
```
\dl
```
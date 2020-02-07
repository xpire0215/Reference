# MySQL

Version: 8.0

### Show Current Status

```
mysql> STATUS
```

## Database Operation

### Show Databases

```
mysql> SHOW DATABASES;
```

### Create Database
```
# Grant specific privileges to a user account
# Account Operation -> Set Privilege
mysql> CREATE DATABASE database_name;
```

### Select Database

```
mysql> USE database_name;
```

### Show Tables

```
mysql> SHOW TABLES;
```

# Account Operation

### Show Users

```
# Show the architecture of mysql.user
mysql> desc mysql.user;

# Select the keys from mysql.user
mysql> select host, user from mysql.user;
```

### Create User

```
> CREATE USER 'user_name'@'localhost' IDENTIFIED BY 'user_password';
```

### Set Privilege

```
mysql> GRANT permission1, permission2 ON database_name.table_name TO 'user_name'@'localhost';

# Example 
mysql> GRANT ALL PRIVILEGES ON database_name.* TO 'user_name'@'localhost';
```

* ALL PRIVILEGES - Grants all privileges to a user account.
* CREATE - The user account is allowed to create databases and tables.
* DROP - The user account is allowed to drop databases and tables.
* DELETE - The user account is allowed to delete rows from a specific table.
* INSERT - The user account is allowed to insert rows into a specific table.
* SELECT - The user account is allowed to read a database.
* UPDATE - The user account is allowed to update table rows.
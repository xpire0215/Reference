# MySQL

Version: 8.0



## Initial MySQL Server for Chinese

#### Show Current Status

```
mysql> STATUS
```



#### Show Character

```
mysql> SHOW VARIABLES LIKE "%character%";
```



#### Show Collation

```
mysql> SHOW VARIABLES LIKE "%collation%";
```



#### Show Database Character and Collation

```
mysql> SELECT SCHEMA_NAME 'database', default_character_set_name 'charset', DEFAULT_COLLATION_NAME 'collation' FROM information_schema.SCHEMATA;
```



### Only Once

#### Modify MySQL Server Character

```
mysql> SET character_set_server=utf8;
```



#### Modify MySQL Database Character

```
mysql> SET character_set_database=utf8;
```



#### Modify MySQL Database Collation

```
mysql> SET collation_database=utf8_general_ci;
```



### Permanent

#### Modify /etc/mysql/my.cnf

```
[mysqld]
character-set-server=utf8

[client]
default-character-set=utf8

[mysql]
default-character-set=utf8
```



## Database Operation

#### Show Databases

```
mysql> SHOW DATABASES;
```



#### Create Database

```
# Grant specific privileges to a user account
# Account Operation -> Set Privilege
mysql> CREATE DATABASE database_name;
```



#### Select Database

```
mysql> USE database_name;
```



#### Delete Database

```
mysql> DROP DATABASE database_name;
```



## Table Operation

#### Show Tables

```
mysql> SHOW TABLES;
```



#### Create Table

```
Example:
mysql> CREATE TABLE IF NOT EXISTS table_name (
	     id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
	     title VARCHAR(255) NOT NULL,
         start_date DATE,
         due_date DATE,
         status TINYINT NOT NULL,
         description TEXT,
         created_at TIMESTAMP,
	   );
```



#### Add Column to Table

```
mysql> ALTER TABLE table_name ADD COLUMN new_column TYPES AFTER column_name;

Example:
mysql> ALTER TABLE username ADD COLUMN student_ID INT NOT NULL AFTER student_name;
```



#### Delete Column from Table

```
mysql> ALTER TABLE table_name DROP COLUMN column_name;
```



#### Show the structure of the table

```
mysql> desc table_name;
```



#### Delete Table

```
mysql> DROP TABLE table_name;
```



## Account Operation

#### Show Users

```
# Show the architecture of mysql.user
mysql> desc mysql.user;

# Select the keys from mysql.user
mysql> select host, user from mysql.user;
```



#### Create User

```
> CREATE USER 'user_name'@'localhost' IDENTIFIED BY 'user_password';
```



#### Set Privilege

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
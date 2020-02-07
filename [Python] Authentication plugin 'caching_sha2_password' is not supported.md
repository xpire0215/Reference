# [Python] Authentication plugin 'caching_sha2_password' is not supported

In MySQL 8.0, caching_sha2_password is the default authentication plugin rather than mysql_native_password.

## Solution

### Add auth_plugin='mysql_native_password' in  parameters 

```
db = mysql.connector.connect(
	user='user_name',
	password='password',
	host='127.0.0.1',
	database='test', # Optional
	auth_plugin='mysql_native_password'
)
```

### If auth_plugin='mysql_native_password' doesn't work

```
# Install mysql-connector-python instead of mysql-connector

> pip uninstall mysql-connector
> pip install mysql-connector-python
```
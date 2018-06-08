# Run docker 
```
$ docker run -p 3366:3306 -e MYSQL_ALLOW_EMPTY_PASSWORD=yes -d rodoxx:sqitch
```

# Alter mysql user authentication

```
$ mysql -urooot`
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '';
```

# Sqitch configuration

```
$ sqitch init test --uri https://github.com/rodoxx/sqitch.git --engine mysql
$ sqitch config --user user.name 'Name'
$ sqitch config --user user.email 'usernmae@domain.com'
$ sqitch config --user engine.mysql.client /usr/bin/mysql
$ sqitch target add localhost db:mysql://root@localhost/databasename
```

# Create databases

```
$ mysql -u root --execute 'CREATE DATABASE sqitch'
$ mysql -u root --execute 'CREATE DATABASE databasename'
```

# Create first commit 

```
sqitch add appuser -n 'Create a an application user'
```



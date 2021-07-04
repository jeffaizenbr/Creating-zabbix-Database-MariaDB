# Creating-zabbix-Database-MariaDB


# 1 - Install MariaDB server

```bash
yum install mariadb* -y
```

# 2 - configure mariaDB

```bash
mysql_secure_instalation
```

# 3 - configure database

```bash
create database zabbix character set utf8 collate utf8_bin;
```
```bash
CREATE USER 'zabbix'@'localhost' IDENTIFIED BY '123';
```
```bash
GRANT ALL PRIVILEGES ON *.* TO 'zabbix'@'localhost' WITH GRANT OPTION;
```
```bash
CREATE USER 'zabbix'@'%' IDENTIFIED BY '123';
```
```bash
GRANT ALL PRIVILEGES ON *.* TO 'zabbix'@'%' WITH GRANT OPTION;
```
```bash
zcat /usr/share/doc/zabbix-server-mysql*/create.sql.gz | mysql -uzabbix -p zabbix
```


## Creating user with PostgreSQL 

```bash
sudo -u postgres createuser --pwprompt zabbix
```
```bash
sudo -u postgres createdb -O zabbix -E Unicode -T template0 zabbix
```


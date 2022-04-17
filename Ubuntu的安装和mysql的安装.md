### 1.安装Ubuntu

```java
1.安装过程
2.sudo password root #设置root用户密码
```

### 2.安装Ubuntu Desktop

```java
[1]sudo apt-get update
[2]sudo apt-get upgrade
[3]sudo su root
[4]sudo apt-get install tasksel
[5]tasksel
[6]选择ubuntu desktop
[7]reboot
```

### 3.安装mysql

```java
[1]apt-get update
[2]sudo apt-get install mysql-server
[3]sudo mysql_secure_installation
[4]进行配置操作
[5]mysql -uroot -p
[6]mysql>CREATE USER 'username'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
[7]mysql>GRANT ALL PRIVILEGES ON *.* TO 'username'@'%' WITH GRANT OPTION;
[8]flush privileges;
[9]mysql>quit
[10]sudo ufw allow 3306 #开启端口
[11]sudo ufw enable
[12]gedit /etc/mysql/mysql.conf.d/mysqld.cnf
[13]把bind-address = 127.0.0.1 改为 bind-address = 0.0.0.0
[14]service mysql restart
[15]service mysql status
```


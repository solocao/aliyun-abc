# navicat 1130-host ... is not allowed to connect to this MySql server  

可能是你的帐号不允许从远程登陆，只能在localhost。这个时候只要在localhost的那台电脑，登入`MySQL`后，更改 `MySQL`里的 "user" 表里的 "host" 项，从"localhost"改称"%"

```
mysql -u root -pvmwaremysql>use mysql;
mysql>update user set host = '%' where user = 'root';
mysql>select host, user from user;
```

重启MySQL，即可访问。
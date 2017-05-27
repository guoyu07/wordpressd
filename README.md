# WordPress

> WordPress运行环境

基于 php:7.1.5-apache版本建构，开启rewrite。

## 使用

### Pull

```shell
$ sudo docker pull hub.c.163.com/jabber/wordpress
```

### Run

```shell
$ docker run --name wordpress -dp 80:80 -v `pwd`:/var/www/html hub.c.163.com/jabber/wordpress
```

## Xdebug 使用

```shell
$ sudo docker pull hub.c.163.com/jabber/wordpress:xdebug
```

### Run

```shell
$ sudo docker run --name wordpress -dp 80:80 -v `pwd`:/var/www/html hub.c.163.com/jabber/wordpress:xdebug
```

### 进入xdebug容器

```shell
$ sudo docker exec -it wordpress /bin/bash
```

### 修改xdebug配置

```shell
$ sed -i '$a xdebug.remote_host = 192.168.1.105' /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini 
$ sed -i '$a xdebug.remote_enable = On' /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
```

### 重启xdebug容器

```shell
$ sudo docker restart wordpress
```

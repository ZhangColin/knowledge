# Redmine docker 安装

### docker 地址

```url
https://github.com/sameersbn/docker-redmine
```



### 初始化数据库

```mysql
CREATE USER 'redmine'@'%.%.%.%' IDENTIFIED BY 'Z$gcm_c0m';
CREATE DATABASE IF NOT EXISTS `redmine` DEFAULT CHARACTER SET `utf8mb4` COLLATE `utf8mb4_unicode_ci`;
GRANT SELECT, LOCK TABLES, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER ON `redmine`.* TO 'redmine'@'%.%.%.%';
```



### 启动 docker 容器

```shell
docker run --name redmine -d -it \
  -p 10083:80 \
  -e REDMINE_PORT=10083 \
  -e DB_ADAPTER=mysql2 \
  -e DB_HOST=172.17.0.4 \
  -e DB_NAME=redmine \
  -e DB_USER=redmine \
  -e DB_PASS='Z$gcm_c0m' \
  -e SMTP_DOMAIN='exmail.qq.com' \
  -e SMTP_HOST='smtp.exmail.qq.com' \
  -e SMTP_PORT=465 \
  -e SMTP_USER='git@zsgcm.com' \
  -e SMTP_PASS='dLBSccH6HYgkfs8x' \
  -e SMTP_TLS=true \
  -e NGINX_MAX_UPLOAD_SIZE='200M' \
  -v /root/redmine/redmine:/home/redmine/data \
  -v /root/redmine/redmine-logs:/var/log/redmine/ \
  sameersbn/redmine:4.1.1-7
```


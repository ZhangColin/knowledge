# Gitlab docker 安装

```shell
docker run -d -p 8443:443 -p 8090:80 -p 8022:22 --restart always --name gitlab -v /Users/colin/gitlab/etc:/etc/gitlab -v /Users/colin/gitlab/log:/var/log/gitlab -v /Users/colin/gitlab/data:/var/opt/gitlab --privileged=true twang2218/gitlab-ce-zh:8.13.5


```


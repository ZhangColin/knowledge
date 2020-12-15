



```shell
docker update -m 1500M --memory-swap 1500M  897a6a09807a
```



```shell
docker container update --restart=always 容器名字
```



### 日志

```shell
# 查看指定时间后的日志，只显示最后100行
docker logs -f -t --since="2018-02-08" --tail=100 CONTAINER_ID

# 查看最近30分钟的日志
docker logs --since 30m CONTAINER_ID

# 查看某时间之后的日志
docker logs -t --since="2018-02-08T13:23:37" CONTAINER_ID

# 查看某时间段日志
docker logs -t --since="2018-02-08T13:23:37" --until "2018-02-09T12:23:37" CONTAINER_ID
```


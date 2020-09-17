## Redis Cluster 集群部署 (docker-compose 版本)

#### 首次部署前须知
想要成功的部署出redis cluster 大致分2步。

- 准备工作
    修改 `config/redis-cluster/node1/redis.conf` 中 `cluster-announce-ip 172.16.121.247` 修改为自己需要部署的ip

- 第一：`docker-compose` 构建 redis 服务

    docker-compose up -d

- 第二：`redis-cli` 创建 cluster 服务

    redis-cli --cluster create 172.16.121.247:6061 172.16.121.247:6062 172.16.121.247:6063 172.16.121.247:6064 172.16.121.247:6065 172.16.121.247:6066 --cluster-replicas 1


#### 有问题需要重新部署时可能需要

每台都

    cluster reset
    flushall




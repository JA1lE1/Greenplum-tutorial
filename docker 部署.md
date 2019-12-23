# docker 部署

```bash
apt-get update
sudo apt install docker.io
sudo service docker start
```

- [Ubuntu 18.04 装Docker](https://blog.csdn.net/u010889616/article/details/80170767)
- [docker greenplum](https://my.oschina.net/u/876354/blog/1606419)

- 端口的配置？？



## docker 知识点补习

- 镜像

  - 拉取镜像

- 容器

  - 创建容器

- 相应的命令

  - ```bash
    -it 
    ```

  - 



## docker-compuse方式

### Docker

```bash
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
    
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo apt-key fingerprint 0EBFCD88

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"


sudo apt-get install docker-ce docker-ce-cli containerd.io
```





### 安装docker-compuse

```bash
sudo curl -L https://github.com/docker/compose/releases/download/1.17.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
```





### **greenplum-oss-docker**

- run_ossdocker.sh

  - ```bash
    docker run -it –hostname=gpdbsne \
    –name gpdb5oss \
    –publish 5432:5432 \
    –publish 88:22 \
    –volume `pwd`:/code \
    kochanpivotal/gpdb5oss bin/bash`
    ```

#### 注意的点

- 如何保持docker在后台的运行

  - 修改run_ossdocker.sh 文件

    - ```
      #加个d？
      # 加d 后没有直接进入对应的容器 应该是在后台运行 然后需要再重新进入
      # 当前的build_docker.sh 是退出的时候直接删除对应的容器？
```
      
    - 



## further

- **what is Spark**

- [pivotal 大佬的快速部署GP 和Spark的方式](https://github.com/kongyew)

- [docker快速入门与实践](https://yeasy.gitbooks.io/docker_practice/container/import_export.html)
  - 现阶段主要看**基本概念** ， **使用镜像** ，和**操作容器**


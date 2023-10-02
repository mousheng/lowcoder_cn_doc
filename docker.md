# Docker

您可以选择使用 Docker-Compose  (推荐）或者 Docker 私有化部署Lowcoder。

## 准备

* [Docker](https://docs.docker.com/get-docker/)（最低版本：20.10.7）
* [Docker-Compose](https://docs.docker.com/compose/install/)（最低版本：1.29.2）

> #### 💡 说明
>
> * 服务器最低要求：2 核 CPU 和 4 GB RAM
> * Windows 推荐使用 PowerShell 来执行以下命令

创建一个名为 majiang 的目录，用于存放Lowcoder实例数据。

```text
mkdir majiang
cd majiang
```

## 使用 Docker-Compose 部署（推荐）

#### 部署

##### 步骤 1：下载配置文件

可以使用 curl 命令进行下载：

```text
curl https://majiang-files.oss-cn-hangzhou.aliyuncs.com/docker-compose.yml -o $PWD/docker-compose.yml
```

或者通过点击 [docker-compose.yml](https://majiang.co/fe74d81d6b261c4efce7a56492cfd7ce/docker-compose.yml) 进行下载。

##### 步骤 2：启动 docker 容器

运行命令启动 docker 容器：

```text
docker-compose up -d
```

初次启动会自动下载 docker 镜像，镜像约 400 MB。

​![](assets/1-20231002181225-bpznpuo.jpeg)​

镜像下载完毕后，服务会在 30 秒内完成启动，请耐心等待。

> #### 💡 说明
>
> 如果遇到镜像下载速度慢或下载失败的问题，请参阅 Docker [镜像加速器](https://yeasy.gitbook.io/docker_practice/install/mirror)文档配置国内的镜像加速源。

##### 步骤 3：查看 docker 状态

通过以下命令来查看日志：

```text
docker logs -f majiang
```

当看到`frontend、backend、redis、mongo entered RUNNING state`​时，Lowcoder服务已经正式启动，如下图：

​![](assets/3-20231002181225-wlm8wy8.png)​

#### 更新

执行以下命令来更新Lowcoder服务：

```text
docker-compose pull
docker-compose rm -fsv majiang
docker-compose up -d
```

#### 部署

执行以下命令来私有化部署Lowcoder服务：

```text
docker run -d --name majiang -p 3000:3000 -v "$PWD/stacks:/majiang-stacks" iocmajiang/majiang
```

#### 更新

执行以下命令来更新Lowcoder服务：

```text
docker pull iocmajiang/majiang
docker rm -fv majiang
docker run -d --name majiang -p 3000:3000 -v "$PWD/stacks:/majiang-stacks" iocmajiang/majiang
```

## 部署完毕后

访问 http://localhost:3000，选择​**立即注册**​，注册后将自动创建企业，之后您可以邀请成员进入该企业。

​![](assets/2-20231002181225-34pfxhn.png)​

## 常见问题

* [在Lowcoder镜像中，如何如何访问宿主机 API/DB？](https://majiang.co/docs/visit-host-api-or-db)

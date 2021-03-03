# 🚢 asm-wrapper

## 使用方法

1.Linux 环境需要安装一下依赖

- Debian

  `apt update && apt install -y git wget curl perl`

- Centos

  `yum update && yum install git wget curl perl`

  2.任意目录下创建一个新文件夹,执行命令

`wget --no-check-certificate https://raw.githubusercontent.com/bzh1371462781/docker5/main/docker-compose.yml`

3.编辑配置`docker-compose.yml`将需要字段自行填写替换完整,需要多容器的可以多复制一条 service 出来

4.使用 `docker-compose up -d` 拉取 image 并且启动容器环境

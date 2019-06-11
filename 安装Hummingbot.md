## 安装Hummingbot

#### 系统要求？

Hummingbot已经测试并支持以下64位系统：

- Ubuntu 16.04 or later
- macOS 10.12.6 (Sierra) or later
- Windows 10 or later (see Windows section below)

#### 安装选择

[通过Docker镜像安装](https://docs.hummingbot.io/installation/docker)

Hummingbot Docker镜像包含所有依赖项，并可以在任何操作系统的虚拟环境中运行。

预计安装时间:5分钟

[通过源代码安装](https://docs.hummingbot.io/installation/source)

从源代码安装使您可以完全访问代码，并允许您动态编辑策略和连接器文件。

预计安装时间:10分钟

#### 1: Docker安装

使用Docker预编译版本的hummingbot，可以用一行命令运行hummingbot。

Docker Hub上可以找到hummingbot的Docker镜像[coinalpha/hummingbot](https://hub.docker.com/r/coinalpha/hummingbot)。


##### 创建一个hummingbot实例

终端： 用docker启动hummingbot

#1) Create a label for your container and specify which docker 
#image of hummingbot to use
export NAME=myhummingbot && \
export TAG=latest

#2) Specify the path to folders where you would like to save
#your config and log files
export CONF_PATH=$(pwd)/hummingbot_conf && \
export LOGS_PATH=$(pwd)/hummingbot_logs

#3) If the folders do not exist, create them:
mkdir $CONF_PATH && \
mkdir $LOGS_PATH

#4) Launch hummingbot with the parameters you specified
docker run -it \
--name $NAME \
--mount "type=bind,source=$CONF_PATH,destination=/conf/" \
--mount "type=bind,source=$LOGS_PATH,destination=/logs/" \
coinalpha/hummingbot:$TAG


**命令参数**
- 在4个export命令中，用你自定义的值替换对应的值
- NAME:  容器的名称，例: myhummingbot
- TAG: 当前使用的镜像版本，例：latest，development或者指定版本0.7.0
- CONF_PATH：本地电脑的conf/ 路径
- LOG_PATH：本地电脑的logs/路径

##### 配置和日志文件

上述方法要求您显式地指定要在本地计算机上挂载conf/和logs/文件夹的路径。

**注意:必须在运行docker run命令之前创建文件夹。**

电脑上所需的文件夹包括:

- hummingbot_conf/：映射到容器中的conf/文件夹，存储配置文件。
- hummingbot_log/：  映射到容器中的logs文件夹，存储日志文件。


**挂载已经存在的config和log文件夹**

如果已经有hummingbot_conf/和hummingbot_logs/文件夹，运行上面的命令将把现有的hummingbot_conf/和hummingbot_logs/文件夹挂载到新创建的docker容器实例中，并允许您继续使用这些文件。

##### 参考:有用的Docker命令

命令	描述

docker ps	列出已经存在并且正在运行的容器

docker start $NAME	启动一个已经存在的，之前创建的容器

docker attach $NAME	连接到一个已经存在并正在运行的容器

##### 更新Hummingbot版本

下面的命令将使用指定的新版本更新hummingbot的现有实例:

docker rm $NAME && \
docker image rm coinalpha/hummingbot:$OLD_TAG && \
docker run -it \
--name $NAME \
-v "$PWD"/conf/:/conf/ \
-v "$PWD"/logs/:/logs/ \
coinalpha/hummingbot:$NEW_TAG

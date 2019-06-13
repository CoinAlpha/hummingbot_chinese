## 在云平台上安装

在Google Cloud Platform、Amazon Web Services和Microsoft Azure等云平台，可以将hummingbot作为长期运行的服务来运行。


### 在Google Cloud Platform创建一个新的VM实例

- 进入到Google Cloud Platform控制台
- 创建一个Compute实例
- 选择“New VM Instance”，然后选择Ubuntu 18.04 LTS


![image](https://github.com/syuukawa/hummingbot_chinese/blob/master/images/Amazon-Web-Services-001.png)


- 点击“SSH”可以SSH到一个新创建的VM实例

###################图片############################


### 在Amazon Web Services创建一个新的VM实例

- 进入到AWS管理控制台
- 点击“启动虚拟机”

###################图片############################

- 选择 Ubuntu Server 18.04 LTS (HVM)

###################图片############################

- 点击 "Review and Launch", 然后点击"Launch"

###################图片############################


- 选择“新建密钥对”，命名密钥对(例如hummingbot)，下载密钥对，然后单击“启动实例”。

###################图片############################

- 点击 “View Instances”
- 要从终端连接到实例，单击“connect”，然后按照生成页面上的说明操作。


###################图片############################


### 在Microsoft Azure创建一个新的VM实例

- 进入到虚拟机控制台。
- 点击左上角的“添加”按钮。

###################图片############################


- 为资源组和VM选择一个名称。
- 选择Ubuntu 18.04 LTS作为镜像类型，选择Standard D2s v3作为大小。

###################图片############################


- 在“管理员帐户”下，选择密码并选择用户名和密码。
- 在“入站端口规则”下，选择SSH和HTTP。

###################图片############################

- 向上滚动到顶部，点击“管理”标签。
- 为诊断存储帐户选择一个有效的名称。

###################图片############################

- 进入“Review and Create”标签，点击“Create”。


###################图片############################

- 创建VM完成，下载并安装操作系统的PuTTY。

###################图片############################

- 初始化VM之后，复制公共IP地址。
- 打开PuTTY应用程序，将IP地址粘贴到主机名中，然后打开。

###################图片############################


### 在Ubuntu上安装Docker(或参考Docker官方说明)

**更新apt包索引**
> sudo apt-get update

**安装允许apt通过HTTPS使用存储库的文件**
>   sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

**添加Docker的官方GPG密钥**
> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable edge test"
    
**进行另一个apt-get更新**
>sudo apt-get update

**安装Docker**
>sudo apt-get install docker-ce docker-ce-cli containerd.io

**更改docker的sudo权限**
>sudo usermod -a -G docker $USER

### 使用Docker安装Hummingbot
**执行下面的命令**
>export NAME=myhummingbot
export TAG=latest
sudo docker run -it \
--name $NAME \
-v "$PWD"/conf/:/conf/ \
-v "$PWD"/logs/:/logs/ \
coinalpha/hummingbot:$TAG

###################图片############################


- 安装docker 之后，您将看到下面的屏幕，Hummingbot在这里成功启动

###################图片############################

- 开始做市!

## 在云服务器上运行机器人


**Tip**

阅读我们关于在不同云提供商上运行Hummingbot的[博客](https://www.hummingbot.io/blog/2019-06-cloud-providers/)。

### 在后台运行机器人

**防止云实例休眠**

要在云的后台运行实例，可以运行以下命令之一:screen或screen -S $NAME。如果希望运行多个机器人，可以使用后者。然后像往常一样启动机器人。
要退出屏幕，请按Ctrl-A-D。

要重新登录到屏幕，可以使用screen或screen -r $NAME打开屏幕的特定实例。要列出所有正在运行的实例，请使用screen -ls。

我们建议用户为希望运行的每个客户机下载单独的docker映像。

感谢discord的用户@matha提出的这个问题和@pfj提供的解决方案。

### 从您的手机访问云实例

使用Hummingbot的Telegram集成在没有计算机的情况下连接到云实例。

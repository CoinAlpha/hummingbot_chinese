## Hummingbot客户端

Hummingbot使用命令行界面(CLI)帮助用户配置和运行该bot，并生成所执行交易的日志。

### 开始Hummingbot

### 用Docker安装

使用docker运行创建一个新的hummingbot实例将自动启动hummingbot客户端(参见[docker -创建hummingbot的新实例](https://docs.hummingbot.io/installation/docker#create-new-instance-of-hummingbot))。

要运行以前创建的、已停止的容器:

> docker start $NAME && docker attach $NAME

- 注： $NAME 为创建并停止的容器的名称

### 用源代码安装

⚠️
在运行hummingbot之前，确保您使用conda激活了Anaconda环境。

打开一个终端窗口，进入到包含Hummingbot的目录的根目录。运行:
> bin/hummingbot.py

### 用户接口
### 布局

***************************图片*********************************

CLI分为三个窗格:

- 输入窗格(左下角):用户在其中输入命令
- Output窗格(左上角):打印用户命令的输出
- 日志窗格(右):日志消息

### 命令

命令               功能
help              打印可用命令列表。
start             启动机器人。如果缺少任何配置设置，它将自动提示您进行这些设置。
config            配置机器人。第一次运行时，初始化机器人。如果机器人已经初始化,解锁Ethereum钱包。
status            获取关于两家交易所之间的价格差异以及当前订单的状态报告。
list              列出钱包、交易所、配置和完成的交易。
                    例子：list [wallets|exchanges|configs|trades]
describe          获取关于钱包、交换和订单的详细信息。
                  示例用法:描述[-w|-e binance|-e ddex]，分别显示钱包、binance位置和钱包余额(可用于ddex)的详细信息。
get_balance       获取外汇或钱包的余额，或获取外汇或钱包中特定货币的余额。
                    示例用法:get_balance [-c uses -w|-c ETH -e binance]分别显示Ethereum钱包中的可用余额和binance中的可用余额。
 exit | CTRL + C  取消所有订单，保存日志，退出Hummingbot。
 exit -f          强制退出而不取消订单。
 stop             取消所有未完成的订单并停止机器人。
 export_private_key  打印出以太钱包私钥。
 history          打印bot过去的交易和性能分析。
 export_trades    导出您的交易到csv文件。


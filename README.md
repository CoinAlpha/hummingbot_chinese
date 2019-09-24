![Hummingbot](https://i.ibb.co/X5zNkKw/blacklogo-with-text.png)
# hummingbot中文资源 （不断完善中）

*请注意：hummingbot是一款实验性软件，您需要自行承担使用风险。请检查Apache 2.0许可。本repo内所有文件及内容均非金融投资理财建议。*

> ***👏欢迎在“Issues”区讨论及提问题***

## 目录
- [hummingbot是什么](#hummingbot是什么)
- [做市概念入门](#做市概念入门) 
- [跨交易所套利概念入门](#跨交易所套利概念入门)
- [常见问题](#常见问题)
- [使用hummingbot的前期准备](#使用hummingbot的前期准备)
- [安装hummingbot](#安装hummingbot)
- [使用hummingbot](#使用hummingbot)
- [hummingbot博客](#hummingbot博客)
- [hummingbot互动](#hummingbot互动)
- [致谢](#致谢)


## hummingbot是什么？
![hummingbot command line user interface](https://hummingbot.io/static/4997d415d34711a686f26d7ba359d8ff/ed7b0/hummingbot-cli.png)

[Hummingbot](https://github.com/coinalpha/hummingbot)(点击查看源代码及下载hummingbot)是一个**开源且免费**的数字货币量化策略交易软件，是让任何人都可以创造和使用高频交易机器人的一款交易工具，用以实现跨交易所或单交易所做市及套利。Hummingbot可以为散户、中小型交易公司或基金提供量化高频交易策略，亦可以为区块链项目发行的数字货币以及交易所本身提供流动性。

Hummingbot现在支持的交易所有：币安、火币\DDEX、Radar Relay、Coinbase Pro、Bamboo Relay、IDEX等，即将支持的交易所有Bittrex, Bitfinex, Kraken, Bitmex, Binance DEX等。

Hummingbot现在提供以下几种策略：
- [跨交易所做市](https://docs.hummingbot.io/strategies/cross-exchange-market-making/)
- [单交易所做市](https://docs.hummingbot.io/strategies/pure-market-making/)
- [跨交易所套利](https://docs.hummingbot.io/strategies/arbitrage/)
- [发现跨交易所套利盈利机会](https://docs.hummingbot.io/strategies/discovery/)

[Hummingbot英文网站](https://www.hummingbot.io)为hummingbot**官方网站**，一切信息请以官方网站为准。
[Hummingbot中文网站](http://hummingbot.cn)由社区成员[syuukawa](https://github.com/syuukawa)个人创建及维护。

**相关阅读**
- [《不要牌照，不会编程，我一个人就是一支量化基金》](https://www.chainnews.com/articles/092938875124.htm)

<br>

## 做市概念入门
“做市”简单来讲就是不断报出特定买卖价格（就是在交易是出limit order而不是直接接受market order），卖价当然比买价要高，自行设定，这样当对方接单时，你就可以实现低买高卖了。做市为金融市场提供了宝贵的**流动性**，流动性越高的市场或资产交易效率越高、买卖价差越低、市场参与者对此的信心也就越高，参与者数量越多。

在传统金融市场比如纳斯达克和新三板中，做市商十分普遍，但门槛很高，数字货币交易所因为数据透明以及API公开等原因为入场做市提供了较低的门槛，人人都可以进行做市套利交易。

对做市商来说，做市是一种逻辑相对简单、风向相对较低的盈利方式。对区块链项目和数字资产交易所来说，做市商的加入可以提高数字资产**流动性**，帮助数字资产形成合理价格，为更多的交易者提供交易机会。

Hummingbot现在提供两种做市交易策略，图解如下所示： 

### 单交易所做市策略图解

点击[单交易所做市](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/%E4%BA%A4%E6%98%93%E7%AD%96%E7%95%A5/%E5%8D%95%E4%BA%A4%E6%98%93%E6%89%80%E5%81%9A%E5%B8%82.md)了解更多。
![](https://docs.hummingbot.io/assets/img/pure-mm.png)


### 跨交易所做市策略图解

点击[跨交易所做市](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/%E4%BA%A4%E6%98%93%E7%AD%96%E7%95%A5/%E8%B7%A8%E4%BA%A4%E6%98%93%E6%89%80%E5%81%9A%E5%B8%82.md)了解更多。
![](https://docs.hummingbot.io/assets/img/xemm-1.png)
![](https://docs.hummingbot.io/assets/img/xemm-2.png)

<br>

## 跨交易所套利概念入门

跨交易所套利图解如下所示： 
![](https://docs.hummingbot.io/assets/img/arbitrage.png)

跨市套利是在两个交易所之间买进和卖出相同的数字资产交易对，并利用交易所之间的差价来赚取利润，也是一种低买高卖的做法。为了帮助用户更好的发现跨市套利的机会，hummingbot亦推出了[“发现”功能](https://docs.hummingbot.io/strategies/discovery/)。点击[跨交易所套利](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/%E4%BA%A4%E6%98%93%E7%AD%96%E7%95%A5/%E5%A5%97%E5%88%A9.md)了解更多。

<br>

## 常见问题
- [FAQ](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/FAQ.md)

<br>

## 使用hummingbot的前期准备
- 足够数量的交易对存货
- 中心化交易所账户及API（如果你的策略涉及中心化交易所）
  - [如何获取Binance API](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/%E6%94%AF%E6%8C%81%E7%9A%84%E4%BA%A4%E6%98%93%E6%89%80/Binance%E6%8E%A5%E5%8F%A3.md) 
  - [如何获取Coinbase Pro API](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/%E6%94%AF%E6%8C%81%E7%9A%84%E4%BA%A4%E6%98%93%E6%89%80/Coinbase%20Pro%E6%8E%A5%E5%8F%A3.md)
- 以太坊钱包（如果你的策略涉及去中心化交易所）
  - [了解以太坊钱包更多](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/Ethereum%E9%92%B1%E5%8C%85.md)
  - 例如：Metamask
- 以太坊节点（如果你的策略涉及去中心化交易所）
  - [了解以太坊节点更多](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/Ethereum%E8%8A%82%E7%82%B9.md)
  - 如何免费获得一个以太坊节点 coming soon
- 运行系统要求：
  - Ubuntu 16.04或以后版本
  - macOS 10.12.6 (Sierra)或以后版本
  - Windows 10或以后版本

<br>

## 安装hummingbot

### 快速安装指南
#### 步骤1：安装Docker

如果您还没有Docker，我们将向您展示如何在不同平台安装Docker。Docker是一种开源容器化产品，可将所有依赖项预先打包到一个容器中，从而大大简化了安装过程。

**Linux的/Cloud**
安装tmux，使您可以轻松地远程运行Hummingbot：

```
sudo apt-get update
sudo apt-get install -y tmux
```
安装Docker:
```
# 1) Download Docker install script
wget https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/install-docker/install-docker-ubuntu.sh

# 2) Enable script permissions
chmod a+x install-docker-ubuntu.sh

# 3) Run installation
./install-docker-ubuntu.sh

# Note: The script will close the terminal window
```

> ***重启Terminal***
上面的命令将关闭您的终端/ bash窗口，以便为docker命令启用正确的权限。 如果bash /终端窗口没有自动关闭，请关闭并重新启动。

**MAC系统**
您可以通过从官方页面下载安装程序来安装Docker。 下载并安装Docker之后，如有必要，请重新启动系统。

**Windows系统**
通过以下链接下载最新版本的Docker Toolbox .exe文件：Docker Toolbox版本。
![](https://docs.hummingbot.io/assets/img/docker_toolbox_download.PNG)

在downloads文件夹中找到安装程序，并使用随附的VirtualBox和Git for Windows运行完整安装。 （Git是Docker使用的默认shell）
![](https://docs.hummingbot.io/assets/img/docker_toolbox_install.PNG)

默认情况下，将在您的桌面上创建Docker Quickstart终端的快捷方式。 您可以使用此快捷方式打开Docker Toolbox。
![](https://docs.hummingbot.io/assets/img/docker_toolbox_startup.PNG)

#### 步骤2：安装Hummingbot

**使用自动化Docker脚本**

我们创建了帮助程序脚本，简化了使用Docker安装和运行Hummingbot的过程：

create.sh：创建Hummingbot的新实例
start.sh：启动Hummingbot
update.sh：更新Hummingbot

这些脚本可帮助您安装Hummingbot实例并设置文件夹以容纳日志和配置文件：
```
hummingbot_files       # Top level folder for hummingbot-related files
├── hummingbot_conf    # Maps to hummingbot's conf/ folder, which stores configuration files
└── hummingbot_logs    # Maps to hummingbot's logs/ folder, which stores log files
```

> ***注意***
更新Hummingbot时，请使用update.sh帮助程序脚本。 不要删除这些文件夹； 否则，您的配置信息可能会丢失。

**Linux系统/云**
打开一个新的Bash窗口并运行tmux以创建一个新进程：
```
tmux
```
然后运行以下命令：
```
# 1) Download Hummingbot helper scripts
wget https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/create.sh
wget https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/start.sh
wget https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/update.sh

# 2) Enable script permissions
chmod a+x *.sh

# 3) Run install script
./create.sh
```
之后，您应该看到Hummingbot客户端界面，可以开始配置Bot。

**MAC系统**
打开一个终端窗口并运行以下命令：
```
# 1) Download Hummingbot helper scripts
curl https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/create.sh -o create.sh
curl https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/start.sh -o start.sh
curl https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/update.sh -o update.sh

# 2) Enable script permissions
chmod a+x *.sh

# 3) Run install script
./create.sh
```
之后，您应该看到Hummingbot客户端界面，可以开始配置Bot。

**Windows系统**
使用Docker Quickstart桌面快捷方式打开Docker Toolbox。 您应该看到以下屏幕：
![](https://docs.hummingbot.io/assets/img/docker_toolbox_cmdline.PNG)

在Docker Toolbox窗口中，运行以下命令：
```
# 1) Navigate to root folder
cd ~

# 2) Download Hummingbot helper scripts
curl https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/create.sh -o create.sh
curl https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/start.sh -o start.sh
curl https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/update.sh -o update.sh

# 3) Enable script permissions
chmod a+x *.sh

# 4) Run install script
./create.sh
```
之后，您应该看到Hummingbot客户端界面，可以开始配置Bot。


**相关阅读**
- [《如何安装hummingbot》(中文翻译)](https://github.com/CoinAlpha/hummingbot_chinese/tree/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90)
- [《如何安装hummingbot(完全版)》(英文原文)](https://docs.hummingbot.io/installation/)

<br>

## 使用hummingbot

### 快速配置指南
如果您已经使用我们的安装脚本成功安装了Hummingbot，则应该在下面看到基于命令行的Hummingbot界面。
![](https://docs.hummingbot.io/assets/img/hummingbot-cli.png)

#### 步骤1：认识客户端界面
首先，让我们逐步介绍Hummingbot客户端界面的设计：

左上窗格：打印对命令的响应的位置
左下窗格：在此处输入命令以控制机器人
右窗格：打印实时交易机器人活动日志的位置

输入帮助以查看命令列表：
```
>>> help
help    Print a list of commands
start   Start market making with Hummingbot
config  Add your personal credentials e.g. exchange API keys
status  Get current bot status
bounty  Participate in hummingbot's liquidity bounty programs

etc...
```

#### 步骤2：启用纸币交易模式（可选)
您可以运行Hummingbot并模拟交易策略，而无需执行和进行实际交易。 在开始时运行命令paper_trade以启用此功能。
```
Enable paper trading mode (y/n) ? >>> y

New config saved:
paper_trade_enabled: y

Your configuration is incomplete. Would you like to proceed and finish all necessary configurations? (y/n) >>> n
```

#### 步骤3：注册流动性奖励（可选）
流动资金赏金允许您通过运行针对特定代币和/或交易所的做市机器人来获得奖励。

Hummingbot与代币发行者和交易所建立合作伙伴关系，以管理赏金计划，该计划将根据Hummingbot用户的已成交做市商订单量对其进行奖励。 有关更多信息，请参见赏金常见问题。

输入bounty --register开始注册过程：

1. 同意条款和条件
2. 允许我们收集您的交易数据以进行验证
3. 输入您的以太坊钱包地址
4. 输入您的电子邮件地址
5. 确认信息并完成

#### 步骤4：配置机器人
a）输入config开始配置
我们将为单一市场做市策略创建一个配置，该策略为一个交易对做市。

> ***注意***
此处的参数值仅用于说明目的，并不是财务建议。

```
What is your market making strategy >>>
pure_market_making

Import previous configs or create a new config file? (import/create) >>>
create
```

b）选择交易对
接下来，选择要使用的交易所和交易对。 请注意，您可能需要交易所帐户和存放在交易所的加密资产清单。 您可以在此处查看有关Hummingbot当前支持的交流的更多信息。

您可以选择像Binance这样的集中式交易所：
```
Enter your maker exchange name >>>
binance

Enter the token symbol you would like to trade on binance (e.g. ZRXETH) >>>
ETHUSDT
```

或者，您可以选择像Radar Relay这样的去中心化交易所（DEX）：
```
Enter your maker exchange name >>>
radar_relay

Enter the token symbol you would like to trade on radar_relay (e.g. ZRX-WETH) >>>
ZRX-WETH
```

c）输入做市参数
参数通过设置所使用的点差，每个订单的大小，下达多少订单以及刷新订单的频率来控制机器人的行为。 [《用户手册》](https://docs.hummingbot.io/manual/)中对每种纯做市策略提示进行了更详细的说明。

```
Enter quantity of orders per side [bid/ask] (single/multiple) >>>
single

How far away from the mid price do you want to place the first bid order (Enter 0.01 to indicate 1%)? >>>
0.01

How far away from the mid price do you want to place the first ask order (Enter 0.01 to indicate 1%)? >>>
0.01

How often do you want to cancel and replace bids and asks (in seconds). (Default is 60 seconds) ? >>>
60

What is your preferred quantity per order (denominated in the base asset, default is 1) ? >>>
0.2
```

d）启用库存偏斜
此功能使您可以设置目标基准/报价库存比率。 例如，您正在交易ZRX-WETH对，而您的当前资产库存由80％ZRX和20％WETH组成。 将此值设置为0.5将使机器人自动调整双方的订单量，卖出更多而少买ZRX，直到获得50％-50％的比率。

```
Would you like to enable inventory skew? (y/n) >>>
y

What is your target base asset inventory percentage (Enter 0.01 to indicate 1%). Default is 0.5 (50%) ? >>>
0.5
```

e）输入您的交换API密钥或以太坊钱包/节点信息
现在您已经设置了做市机器人的行为方式，是时候为它提供操作所需的必要API密钥（用于集中式交易）或钱包/节点信息（用于分散式交易).

f）输入终止开关参数
Hummingbot随附可帮助您运行bot的实用程序，例如：

终止开关Kill switch：在达到一定的性能阈值（可能为正值或负值）后自动停止漫游器
汇率：设置稳定币和其他加密资产之间的汇率，以便您可以在不同交易所的不相同交易对上运行漫游器
Telegram整合：通过连接可以发出命令的Telegram机器人，从任何地方只用Telegram手机应用控制您的交易机器人

有关这些实用程序的更多信息，请参见[《用户手册》中的“实用功能”部分](https://docs.hummingbot.io/utilities/kill-switch/)。 默认情况下，仅通过演练配置kill开关。

激活终止开关功能，并告诉它在达到特定百分比损失时使机器人停止运行：
```
Would you like to enable the kill switch? (y/n) >>>  
y

At what profit/loss rate would you like the bot to stop? (e.g. -0.05 equals 5% loss) >>>
-0.05
```

#### 步骤5：调试参数
如果要从头开始重新配置机器人，请键入config并回答y，是否要重新配置机器人？ （y / n）>>>?。 这将在初始设置过程中提示所有问题。

另外，命令列表配置将显示您当前的机器人参数，包括全局和策略配置。
```
>>> list configs

global configs:
...

pure_market_making strategy configs:
...
mode                      single
bid_place_threshold       0.01
ask_place_threshold       0.01
cancel_order_wait_time    60
order_amount              0.2
...
```

您可以通过执行config $ parameter_name来指定要配置的参数。 例如，我们想将bid_place_threshold扩大到0.02。 这告诉机器人下订单比中间价格低2％，而不是1％。
```
>>> config bid_place_threshold

Please follow the prompt to complete configurations:

How far away from the mid price do you want to place the first bid order (Enter 0.01 to indicate 1%)? >>>
0.02

New config saved:
bid_place_threshold: 0.02
```
您还可以通过退出退出bot并编辑自动生成的配置文件conf_pure_market_making_0.yml。 该文件保存在根目录下的hummingbot_files / hummingbot_conf /目录中。 

如果您成功完成了上述步骤，则应该看到以下消息：
```
Config process complete. Enter "start" to start market making.

>>> start
```

**相关阅读**

- [《快速配置hummingbot指南》(英文原文)](https://docs.hummingbot.io/quickstart/3-configure-bot/)
- [《如何配置hummingbot》(英文原文)](https://docs.hummingbot.io/operation/configuration/)
- [《如何配置hummingbot》(中文翻译)](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/Hummingbot%E9%85%8D%E7%BD%AE.md)
- [《简易运行hummingbot指南》(英文原文)](https://docs.hummingbot.io/quickstart/4-run-bot/)
- [《如何运行hummingbot》(英文原文)](https://docs.hummingbot.io/operation/running-bots/)
- [《如何运行hummingbot》(中文翻译)](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/%E8%BF%90%E8%A1%8CBots.md)
- [《如何在云上运行hummingbot》(中文翻译)](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/%E8%BF%90%E8%A1%8Cbots-%E5%9C%A8%E4%BA%91%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%8A.md)
- [认识hummingbot客户端](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/Hummingbot%E5%AE%A2%E6%88%B7%E7%AB%AF.md)

<br>

## hummingbot博客

- [交易所類型說明：CLOB，RFQ和Automated](https://0xcj.com/2019/05/24/%E4%BA%A4%E6%98%93%E6%89%80%E9%A1%9E%E5%9E%8B%E8%AA%AA%E6%98%8E%EF%BC%9Aclob%EF%BC%8Crfq%E5%92%8Cautomated/)

<br>

## hummingbot互动

- 想问问题？欢迎在github “Issues”区讨论及提出你的问题
- 想即时联系hummingbot团队？欢迎点击加入[hummingbot discord聊天室](https://discord.hummingbot.io)
- 想为hummingbot出份力？欢迎帮助[**翻译hummingbot文档**](https://docs.hummingbot.io)并在github提交Pull Request(合并请求)，我们阅读和修改后会尽快通过。感谢大家支持！
- 发现bug？报告bug也可以获得赏金哟！每报告一个我们决定解决的bug便可以获得0.1ETH赏金，[点击了解详情](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/Bug%E8%B5%8F%E9%87%91%E8%AE%A1%E5%88%92.md)。

<br>

## 致谢
感谢本repo的第一个来自社区的贡献者[syuukawa](https://github.com/syuukawa)！💐

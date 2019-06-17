## 运行机器人

**Note**

下面的命令假设您已经在Hummingbot CLI中。如果您需要安装和启动CLI的帮助，请参阅[安装](https://docs.hummingbot.io/installation)和[客户端](https://docs.hummingbot.io/operation/client)。

### 开始一个机器人

使用start命令初始化一个做市机器人。

如果缺少任何配置设置，将提示您添加它们(参见:[configuration](https://docs.hummingbot.io/operation/configuration/))。

如果您以前使用config配置过Hummingbot，但现在处于CLI的新会话中，则需要再次运行config来解锁您的Ethereum钱包。

### 自动审批

**为了在基于以太坊的去中心化交易所(DEX)上进行交易，如果您是第一次交易该令牌，您可能需要发送一个以太坊事务来批准您在该交易所进行交易的令牌。**
Hummingbot检查令牌是否被批准，并在开始运行前自动处理批准事务。

**Note**

**虽然Hummingbot会自动处理批准，但它不会自动打包ETH或反打包WETH。**

### 库存需求

Hummingbot使用您的令牌余额来确定每个订单的大小。对于去中心化的交易所，如DDEX和Radar Relay，它使用您的以太钱包中的令牌余额。对于像Binance这样的中心化交易所，它使用您的令牌余额在各自的交换中。Hummingbot的交易规模将永远低于任何一方的最低资产余额。

![image](https://docs.hummingbot.io/assets/img/inventory1.png)

对于跨交易所做市，我们建议用户从每个交易所的基本资产和报价资产的大致相等余额开始。因此，有四个平衡要跟踪:

- 以做单为基础的资产
- 以做单为报价资产
- 以主动卖单为基础资产
- 以主动买单报价资产
**以上的翻译感觉有点奇怪，希望大神能给更好的改进意见**

**Tip**

在不久的将来，我们计划添加一个自动再平衡模块来自动化传输和交换令牌的过程。目前，用户需要手动重新平衡这些帐户。


### 命令

请参阅[客户端:命令](https://docs.hummingbot.io/operation/client#commands)。

### 日志

Hummingbot的右窗格包含了它所采取的所有行动的日志，包括批准、加注、填充等等。当用户退出Hummingbot时，它将包含该节所有活动的日志文件保存到logs/文件夹。

### 运行多个机器人

要运行多个机器人，需要在bash/Terminal的新实例中启动Hummingbot，如果使用Docker，则需要在新容器中启动Hummingbot。

如果您正在使用Docker，您仍然需要单独的文件夹来存储配置文件，并使用Docker run命令从每个文件夹创建Docker容器。要重新启动这些容器，可以使用命令docker start[您的容器名称]和docker attach[您的容器名称]。


## Hummingbot配置

⚠️以下的命令假定你已经安装了Hummingbot的客户端，如果需要安装和加载客户端，请参考[安装](https://docs.hummingbot.io/installation)和[客户端](https://docs.hummingbot.io/operation/client)。

更多的策略信息请参考[Hummingbot白皮书](https://www.hummingbot.io/whitepaper.pdf)。

### 开始

config命令帮助你初始化和配置运行Bot所需的全局信息和策略，在conf/文件夹将创建以下文件。

文件                                                     描述
conf_global.yml                                       全局的配置设定，例如：binance的Api keys和以太节点。
conf_cross_exchange_market_making_strategy_[#].yml    cross-exchange market making strategy设定。
conf_arbitrage_strategy_[#].yml                       arbitrage策略的设定
conf_pure_market_making_[#].yml                       pure market making 策略的设定
conf_discovery_strategy_[#].yml                       discovery策略的设定

**编辑conf/中的文件**

配置文件创建完成后，可以在conf/文件中编辑配置文件。

### 流程

输入config，你将被要求选择一中策略并输入策略相关的配置参数，我们已经开发了对于每中策略的流程。

- [Cross-exchange market making](https://docs.hummingbot.io/strategies/cross-exchange-market-making#configuration-walkthrough)
- [Arbitrage](https://docs.hummingbot.io/strategies/arbitrage#configuration-walkthrough)

### 配置文件模版

Hummingbot使用的配置文件创建并被保存在conf/文件夹中。你可以对文件直接进行编辑。

模版配置文件例子：[config templates](https://github.com/CoinAlpha/hummingbot/tree/master/hummingbot/templates)

⚠️

当你修改配置文件的时候，首先要退出Hummingbot并且确定不在运行的状态，配置信息的改变将在下一次Hummingbot启动的时候起作用。

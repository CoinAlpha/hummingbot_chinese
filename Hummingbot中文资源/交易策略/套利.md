
## Arbitrage

### 它是如何工作的?

套利在[策略](https://docs.hummingbot.io/strategies/)中进行了描述，并在Hummingbot[白皮书](https://hummingbot.io/whitepaper.pdf)中进行了进一步的讨论。


### 示意图

下图说明了套利是如何进行的。交易涉及两个交易所:交易所A和交易所B；Hummingbot监控交易所的价格，并在盈利机会出现时进行交易。

当Hummingbot可以在一个交易所以较低的价格买进，在另一个交易所以较高的价格卖出时，机会就出现了。

![image](https://docs.hummingbot.io/assets/img/arbitrage.png)


### 先决条件:库存

1.类似于跨市场交易，您将需要在两个交易所(主交易所和次交易所)持有库存，以便能够进行交易并捕捉价格差异(即在一个交易所低买，在另一个交易所高卖)。
2.您还将需要一些以太支付在去中心化交易所中的gas费用。


### 配置预排

以下是第一次运行config时的所有步骤。

**提示:配置期间自动完成输入**

在执行命令行配置过程时，在提示符处按<TAB>将显示有效的可用输入。


提示                                      描述

    What is your market making strategy >>>:  输入 arbitrage
                                              目前可用的选项:cross_exchange_market_making或pure_market_making(区分大小写)
    
    Import previous configs or                第一次运行机器人时，输入create。
    create a new config file?                 如果您之前已经初始化，输入import，它将要求您指定配置文件的位置。
    (import/create) >>>:  
                                              
    
    Enter your primary exchange name >>>:     进入一个你想交易的交易所。
                                              当前可用的选项:binance、radar_relay、coinbase_pro或ddex(区分大小写)
                                              
    Enter your secondary exchange name >>>:   进入另一个你想交易的交易所。
                                              当前可用的选项:binance、radar_relay、coinbase_pro或ddex(区分大小写)
                                              
    Enter the token symbol you would like     输入主交易所交易的令牌符号。示例输入:ZRX-WETH
    to trade on [primary exchange name] >>>:
                                             
    
    Enter the token symbol you would like     输入次交易所交易的令牌符号。示例输入:ZRX-WETH
    to trade on [secondary exchange name] >>>:
    
    
    
    What is the minimum profitability for     设置min_profitability(参见[定义](https://docs.hummingbot.io/strategies/arbitrage/#configuration-parameters))。
    your to make a trade?                     : 交易的最小盈利的设定
     (Enter 0.01 to indicate 1%) >>>:
     
    Enter your Binance API key >>>:           您必须创建一个启用交易的Binance API key key(选择“启用交易”)。
    
    Enter your Binance API secret >>>:
    
    
    
    Would you like to import an existing wallet    导入或创建一个Ethereum钱包，用于在DDEX上进行交易。
    or create a new wallet? (import / create) >>>: 输入一个有效的输入:
                                                   
                                                   import:从输入私钥导入钱包。
                                                       如果您选择导入，您将被要求输入您的私钥以及一个密码来锁定/解锁用于Hummingbot的钱包
                                                    - 您的钱包私钥>>>
                                                    - 一个密码，以保护您的钱包密钥>>>
                                                    
                                                   create: 创建一个带有新私钥的新钱包。 
                                                   - 如果您选择create，您将只需要输入一个密码来保护您新创建的钱包
                                                   - 一个密码，以保护您的钱包密钥>>>
                                                   
                                                   **提示**
                                                   使用Metamask中提供的钱包(即从Metamask导入钱包)，您可以查看Hummingbot在去中心化交易所网站上创建的订单和完成的交易。
                                                   
    Which Ethereum node would you like             输入一个Ethereum节点URL，以便Hummingbot在基于Ethereum的去中心化交易所进行交易时使用。
    your client to connect to? >>>:                有关更多信息，请参见安装:[设置Ethereum节点](https://docs.hummingbot.io/installation/node)。
                                                   
                                                   **提示**
                                                   如果您正在使用Infura端点，请确保在URL之前添加https://。
                                                   
 
### 配置参数

以下参数是Hummingbot配置文件中的字段(位于/conf文件夹中，例如conf/conf_arbitrage_strategy_ _[#].yml)。

   
    术语                                          定义
    min_profitability                            以小数表示的量(即输入0.01对应1%)。
                                                 Hummingbot在交易所下订单的最低盈利能力。
                                                    
                                                 例如:假设最低盈利能力阈值为0.01，并且在take exchange (binance)上有一个投标价格为100的令牌符号，
                                                 Hummingbot将向制造商交易所(ddex)发出99美元(或更低)的竞价指令，以确保1%(或更高)的利润;
                                                 Hummingbot只有在交易所出价最高的情况下才会下这个订单。
                                                 
    
    trade_size_override                          以最大允许订单大小的报价货币表示的金额。
                                                 **这个实在翻译不出来汗，，，汗，，，汗，，，**
                                                 
                                                 示例:假设交易大小超过为100，并且令牌符号为ETH/DAI，那么允许的最大订单大小是值为100 DAI的订单大小。
                                                 
                                                 

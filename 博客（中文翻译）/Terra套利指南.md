在这篇文章中，我们将介绍如何在Terra和其他交易所之间套利。你也可以点击[这里](https://www.youtube.com/watch?v=JsSNi9PUdVQ)查看演示视频。

# Terra 是什么？

>[Terra](https://terra.money/)协议是 Luna 代币、Terra Core 生成器以及区块链支付解决方案 CHAI 的开发基础。Terra 协议的设计有两大基础：稳定性和电子商务平台的采用。其运行在 Tendermint 委托权益证明算法和 Cosmos SDK 上。它旨在成为一个新的全球金融基础架构，可以在其上创建不同的 DApp（去中心化应用）。（[资料来源](https://medium.com/stakin/what-is-terra-money-8eb1dcb314d2)）

Terra协议的目标是成为一个专注于稳定币的区块链，LUNA代币作为系统的核心。 如果你想知道它是如何工作的，可以看看他们的[介绍视频](https://www.youtube.com/watch?v=KqpGMoYZMhY)。  

# 选择市场

除了 LUNA 代币，Terra 协议已经在其区块链上发行了以下稳定币：

- UST（美元）
- KRT（韩元） 
- SDT（新加坡元） 
- MNT（蒙古图格里克）

使用 Hummingbot *amm-arb* 策略，可以连接到 Terra 区块链并使用 Terra Swap 和其他交易所（中心化或去中心化）进行套利交易

我们首先需要找到可以进行 Terra 代币交易的场所。

从某个提供市场信息汇总的网站（例如，[Coingecko](https://www.coingecko.com/pt/moedas/terra-luna#markets)、[Coinpaprika](https://coinpaprika.com/coin/luna-terra/#!exchanges) 或 [Coinmarketcap](https://coinmarketcap.com/currencies/terra-luna/)）开始入门是一种理想的方式。

掌握了这些信息之后，只需与 Hummingbot 支持的当前交易所和协议进行交叉检查，然后选择您想要运行的自动程序即可。

在本指南中，我们将使用 Terra 链上的 LUNA-UST 交易对和 Bittrex 交易所上的 LUNA-USDT 交易对作为示例。

# 创建您的 Terra 钱包

如果要创建 Terra 钱包，您需要从 [Terra 官方页面](https://terra.money/)下载 Terra Station 应用程序。

如何创建Terra链钱包:

1. 从网站下载并安装Terra Station钱包;
2. 启动Terra Station，点击顶部的Connect按钮;
3. 选择New wallet创建新钱包;
4. 填好所有表格，确保你的seed短语存放在一个安全的地方;
5. 确认你的seed完成注册;
6. 向您的新Terra钱包添加资金;
7. Terra钱包地址可在Terra Station窗口顶部找到。

Terra Station 让您可以管理您的钱包、交换代币以及将 LUNA 委托给 Terra 区块链上的验证者。我们可以使用 Terra 钱包连接到 Hummingbot 以执行 AMM 策略。

>注意：稍后我们将使用 Terra 钱包地址和seeds在 Hummingbot 中连接钱包

>注意 2：如果您的 Terra 钱包没有您正在交易的任何代币，Hummingbot 将显示 markets are not ready（市场尚未准备就绪）的警告消息。

  ![](https://images.ctfassets.net/h07e7qaokuyy/6orWCzYiCrhLaxo0vjn7ZO/46cda1e5118dc2f2140ce9496565831a/terrawallet.jpg?w=1300&h=744&q=50&fm=webp)
 
# 在 Hummingbot 中连接您的 Terra 钱包

>重要提示：如果要使 Hummingbot 与 Terra 链进行通信，您必须安装并运行Gateway。如果您尚未安装网关，请按照本指南进行操作。

通过连接到 Hummingbot 客户端上的 Terra 钱包，检查您的网关是否已正确连接。

1.	运行命令 *connect terra*；
2.	输入您的 Terra 钱包地址；
3.	输入您的 Terra 钱包seed，包括每个字符之间的空格。

  ![](https://images.ctfassets.net/h07e7qaokuyy/21obi0LQgc19UI8S2iYh8i/57294429c01bff6b403feeae87cc4851/terraconnect.png?w=496&h=116&q=50&fm=webp)
 
# 连接到交易所

在安装并启动 Hummingbot 之后（如果您还没有这样操作），就可以连接到您将要进行套利操作的交易所了。

您可以在[这里](https://docs.hummingbot.io/exchange-connectors/overview/)查看Hummingbot上可用的连接器的更新列表及其状态，以及与每个连接器连接的说明。  

# 创建 amm-arb 策略

在两个市场已连接的情况下，您需要做的就是创建套利策略。在 Hummingbot 上，执行 *create*（创建）命令，并回答以下问题：

![](https://images.ctfassets.net/h07e7qaokuyy/1MCtraHFnlV0NIGhMATBkd/1946d79b1155bd9a6907c7212fb0a07b/terracreate.png?w=650&h=550&q=50&fm=webp)
 
- *What is your market making strategy?* (您的做市策略是什么？) 输入 amm-arb。

- *Enter your first connector (exchange/AMM)* (输入您的第一个连接器（交易所/AMM）): 您可以输入其中任何一个，但我的建议是选择 AMM 协议作为第一个连接器，因为AMM订单执行速度比中心化交易所慢。

- *Enter the token trading pair you would like to trade on terra* (输入您想在 Terra 上交易的代币交易对) 例如：LUNA-UST

>重要提示：每个代币在两个连接器上的必须都有仓位，否则程序可能无法执行正确的计算

- *Enter your second connector (exchange/AMM)* (输入您的第二个连接器（交易所/AMM）): 输入程序将连接到的第二个交易所。例如，*Bittrex*

- *Enter the token trading pair you would like to trade on bittrex* (输入您想在 Bittrex 上交易的代币交易对): 在我们的示例中，我们将以 LUNA-USDT 为例。请注意，您可以选择一个不同于第一个交易所的交易对。

- *What is the amount of LUNA per order?* (每笔订单的 LUNA 数额是多少？): 确保此值大于两个交易所要求的最小值，否则您可能无法正确执行策略。

- *What is the minimum profitability for you to make a trade?* (您进行交易的盈利目标下限是多少？): Hummingbot 已经在盈利目标计算中考虑了交易成本，因此您将在此处输入的值是您期望的利润率下限。

- How much buffer do you want to add to the price account for slippage for orders on the first (and second) market? (对于第一（和第二）市场上的订单出现滑点，您希望为价格账户添加多少缓冲？): 由于市场是动态变化的，在自动程序检测到套利机会到创建订单之间的时间差内，资产价格可能会发生变化。下滑缓冲区将使自动程序能够在订单价格的基础上加上（或减去）此处指示的百分比，从而确保订单得到执行。

- Do you want to submit both arb orders concurrently?(您是否想同时提交两笔套利订单？) 如果是，程序将同时向两个市场发送订单。如果否，程序将等待在第一个市场上完成订单，然后再向第二个市场发送订单。

- Enter a new file name for your configuration (为您的配置输入一个新文件名): 选择配置文件的名称，以便您可以在下次启动自动程序时使用 import（导入）命令再次对其进行加载。开始使用吧！只需点击 start（开始），自动程序就会开始寻找套利机会！

# 结论

区块链和加密货币都是新兴技术，在创建新系统和对现有系统进行迭代改进方面有很大的空间。

由于每个新市场的差异，每个新项目都为交易者，尤其是套利者提供了新的机会。

稳定币还为这个市场动态增加了另一层含义，因为套利者最终填补了这些系统中的一个重要角色，帮助不同的稳定币的价格变得稳定。


## 如有任何问题获想参与讨论，请加入我们的社区

我们的社区有众多的做市商和套利者，他们愿意互相帮助，充分利用 Hummingbot。 您可以加入我们的 [Discord 中文频道](https://discord.gg/HgDExTAcWF)，讨论 Hummingbot、策略、流动性挖坑以及与加密货币世界有关的任何其他内容，并获得我们团队的直接支持。

加入中文微信群，请添加ID：amtf202004

更多教学互动视频，请订阅[bilibili频道](https://space.bilibili.com/2010395218/channel/detail?cid=178340)
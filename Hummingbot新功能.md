我们仍然在不断完善Hummingbot，并且不断开发使用户交易更便捷、安全和稳定的新功能。本篇内容旨在介绍最近Hummingbot推出的各项新功能。

- [纸上交易](#纸上交易)
- [加密功能](#加密功能)
- [库存偏斜](#库存偏斜)
- [悬挂订单](#悬挂订单)
- [最佳竞价跳跃模式](#最佳竞价跳跃模式)

## 纸上交易

纸上交易模式是一种模拟的市场环境，用户可以在其中做出购买和出售决策并测试Hummingbot性能，而不需在实际交易所中下达实际订单。

此功能使用户可以测试Hummingbot并模拟交易策略，而不会产生任何财务风险。它使用虚拟余额，您可以使用文本编辑器在```conf_global.yml```文件中设置虚拟余额。进行纸质交易时，也不需要交易所账户，以太坊钱包和以太坊地址。截至2019年11月20日，此功能已支持Binance，Coinbase Pro，Huobi，DDEX，Bamboo Relay和Radar Relay。

可以使用```paper_trade```命令在Hummingbot中启用/禁用纸面交易模式。 Hummingbot客户端的顶部栏应该被激活：```paper_trade_mode：ON```。要调整模拟交易模式下使用的虚拟令牌余额，请编辑位于客户端```conf```目录中的```conf_global.yml```文件。

纸上交易是查看特定策略在一段时间内表现如何的好方法。它为您提供了大致的性能基准。

**注意：纸上交易模式可能夸大了您从某种策略中获得的回报，因为当您在现实世界中下订单时，其他做市商和交易者将对您的操作做出响应，并可能影响交易的可盈利性。**

因此，纸上交易只有在有对比的情况下才更有用。例如，您可能要运行两个纸上交易机器人-一个具有更大的点差和非常长的取消订单等待时间，而另一个则具有更小的点差和较短的取消订单等待时间。随着时间的流逝，您将能够找出与实际资产进行交易时想要设置的最佳参数。

#### 更多资源
- 在[此处](https://www.youtube.com/watch?v=Zxq6S317pfw&feature=youtu.be&t=385)观看完整的演示视频。
- 在[此处](https://docs.hummingbot.io/utilities/paper-trade/)阅读纸面交易模式的文档。

---
## 加密功能

以前，您的Exchange API密钥以纯文本格式保存在```conf_global.yml```全局配置文件中。即使Hummingbot是本地客户端软件，这也存在潜在的安全风险，因为如果某人能够访问您的计算机或云虚拟机，他们可能会看到您的API密钥并对其执行恶意交易。

首次启动配置过程时，新的Hummingbot客户端将提示您输入新密码。
![](https://hummingbot.io/static/93651605b3369201fbe631d1da142cca/ed7b0/image1.png)

您设置的此密码将用于加密以太坊钱包私钥和Exchange API密钥。现在，每次启动Hummingbot客户端时，都必须在客户端中输入此密码。请注意，出于安全原因，系统不会在任何地方存储此密码。这意味着如果忘记或丢失了密码，将无法恢复。

现在，一旦设置了密码，便可以在```conf```文件夹中看到一些加密文件，并且全局配置文件将不再包含私钥并交换API信息。

![](https://hummingbot.io/static/ffcbeee88ff3b52b852a012cb49193ef/ed7b0/image2.png)

对于从Hummingbot的早期版本升级的用户，v0.20.0和更高版本会自动将现有API密钥从```conf_global.yml```转移出，并转换为这种新的加密格式。这还将替换您之前用于加密以太坊钱包私钥的密码。

重新打开Hummingbot客户端时，必须重新输入设置的密码才能继续。正确输入密码后，您也可以更改或编辑敏感信息。

我们希望这项新的加密功能将帮助我们所有的用户更加安全地运行高频交易机器人！

#### 更多资源
- 阅读[快速入门指南中的步骤4：配置做市机器人](https://docs.hummingbot.io/quickstart/3-configure-bot/#step-4-configure-a-market-making-bot)。
- 阅读[v0.20.0发布说明](https://docs.hummingbot.io/release-notes/0.20.0/)

---
## 库存偏斜

库存风险是做市商面临的主要风险之一。当市场趋势向上时，做市商往往会卖出更多的股票，而持有的增值资产则更少。相反，当市场趋势下降时，做市商往往会购买多于出售，并持有更多价值下降的资产。

库存偏斜参数旨在根据库存变化来调整订单大小，以便您维持目标基本/报价库存比率。例如，假设您正在交易```ZRX-WETH```对，而您的当前资产库存由80％ZRX和20％WETH组成。将您的```ventory_target_base_percent```设置为0.5将使机器人自动调整双方的订单金额，卖出更多而少买入ZRX，直到获得50％-50％的比率。

要启用它，请将```stocker_skew_enabled```参数设置为```true```，然后设置您的```inventory_target_base_percent```。

#### 更多资源
- 在[此处](https://docs.hummingbot.io/strategies/pure-market-making/#inventory-based-dynamic-order-sizing)阅读有关库存偏斜的文档。
- 请在[此处](https://docs.google.com/spreadsheets/d/16oCExZyM8Wo8d0aRPmT_j7oXCzea3knQ5mmm0LlPGbU/edit#gid=690135600)查看库存偏差计算器。

---
## 悬挂订单

![](https://hummingbot.io/static/4d2a3f80d7b4541fe0cc955207e96b3a/ed7b0/demo2_2.png)
悬挂订单可让您更好地控制Hummingbot调整订单的方式。作为做市商，您想在定单的两侧设置点差。默认情况下，我们总是在每个固定的时间间隔取消和补充订单，但是悬挂订单可以让您调整此行为。

通过将```enable_order_filled_stop_cancellation```设置为```true```，Hummingbot会在一侧（买入或卖出）被填充时将另一侧的订单“挂起”（不取消），以便在市场上下波动时始终可以低买高卖。

---
## 最佳竞价跳跃模式

此功能以前称为“便士跳（Penny Jumping）”，是在流动性不佳，点差较大的市场中交易的理想选择。它使您能够最大程度地扩大订单的价差，同时仍确保您的订单是市场上最好的订单。

此功能来自专业做市商和加密货币对冲基金的实际操作方式。专业的做市商不会天真的设置点差，而是考虑到订单状态并对其他交易者的行为做出判断和反应。

通过将```jump_orders_enabled```设置为```TRUE```，您的机器人将自动调整设置的订单，其价格比最高出价高出1格，并询问市场中的订单。如果另一个做市商取消您的订单，Hummingbot将自动跳出另一个做市商的订单，直到达到您的价差参数（```bid_place_threshold```，```ask_place_threshold```）为止。

您还可以使用```jump_orders_depth```指定进入订单簿的深度，以计算最高买入价和最高买入价。

让我们看看实际情况。在下面的订单簿中，最佳出价和要价订单以红色突出显示。
![](https://hummingbot.io/static/72243a277da7ec0bee8cbd354ce31ee4/ed7b0/demo6.png)

启用```jump_orders_enabled```时，Hummingbot的订单（以红色突出显示）下达的订单比以前的最佳订单高出1格。如果其他交易者跳了您的订单，机器人将通过跳过它们来自动响应竞争订单。
![](https://hummingbot.io/static/a600e949a705853afc94ce118db0b3bf/ed7b0/demo7.png)

#### 更多资源
- 在[此处](https://www.youtube.com/watch?v=7fnAUXRLF4g&feature=youtu.be&t=1491)观看完整的演示视频。
- 在[此处](https://docs.hummingbot.io/strategies/pure-market-making/#penny-jumping-mode)阅读文档。

---
更多最新功能，请阅读[博客](https://hummingbot.io/blog/2019-11-advanced-market-making/)及参考最近版本的[发布说明](https://docs.hummingbot.io/release-notes/)。

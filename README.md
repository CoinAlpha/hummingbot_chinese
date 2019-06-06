![Hummingbot](https://i.ibb.co/X5zNkKw/blacklogo-with-text.png)
# hummingbot中文资源 （完成中）

*请注意：本篇内容并非金融投资理财建议*

> ***👏欢迎在“Issues”区讨论及提问题***

### hummingbot是什么？
![hummingbot command line user interface](https://www.hummingbot.io/blog/2019-04-announcing-hummingbot/hummingbot-cli.png)
[Hummingbot](https://github.com/coinalpha/hummingbot)(点击查看源代码及下载hummingbot)是一个**开源且免费**的数字货币量化策略交易软件，是让任何人都可以创造和使用高频交易机器人的一款交易工具，用以实现跨交易所或单交易所做市及套利。Hummingbot可以为散户、中小型交易公司或基金提供量化高频交易策略，亦可以为区块链项目发行的数字货币以及交易所本身提供流动性。

Hummingbot现在支持的交易所有：币安、DDEX、Radar Relay、Coinbase Pro、Bamboo Relay等，即将支持的交易所有IDEX、Uniswap、Binance DEX等。

Hummingbot现在提供以下几种策略：
[跨交易所做市](https://docs.hummingbot.io/strategies/cross-exchange-market-making/)
[单交易所做市](https://docs.hummingbot.io/strategies/pure-market-making/)
[跨交易所套利](https://docs.hummingbot.io/strategies/arbitrage/)
[发现跨交易所套利盈利机会](https://docs.hummingbot.io/strategies/discovery/)

**相关阅读**
[《不要牌照，不会编程，我一个人就是一支量化基金》](https://www.chainnews.com/articles/092938875124.htm)
<br>
<br>
### 做市概念入门
“做市”简单来讲就是不断报出特定买卖价格（就是在交易是出limit order而不是直接接受market order），卖价当然比买价要高，自行设定，这样当对方接单时，你就可以实现低买高卖了。在传统金融市场比如纳斯达克和新三板中，做市商十分普遍，但门槛很高，数字货币交易所因为数据透明以及API公开等原因为入场做市提供了较低的门槛，人人都可以进行做市套利交易。

对做市商来说，做市是一种盈利方式。对区块链项目和数字资产交易所来说，做市商的加入可以提高数字资产**流动性**，帮助数字资产形成合理价格，为更多的交易者提供交易机会。

Hummingbot提供两种做市交易策略，如下图所示： 
![](https://docs.hummingbot.io/assets/img/pure-mm.png)
*单交易所做市策略图解*
<br>
<br>
![](https://docs.hummingbot.io/assets/img/xemm-1.png)
![](https://docs.hummingbot.io/assets/img/xemm-2.png)
*跨交易所做市策略图解*
<br>
<br>
### 跨交易所套利概念入门
![](https://docs.hummingbot.io/assets/img/arbitrage.png)
跨市套利是在两个交易所之间买进和卖出相同的数字资产交易对，并利用交易所之间的差价来赚取利润，也是一种低买高卖的做法。为了帮助用户更好的发现跨市套利的机会，hummingbot亦推出了[“发现”功能](https://docs.hummingbot.io/strategies/discovery/)。
<br>
<br>
### 使用hummingbot的前期准备
- 足够数量的交易对存货
- 中心化交易所账户及API（如果你的策略涉及中心化交易所）
  [如何获取Binance API](https://docs.hummingbot.io/connectors/binance/) 
  [如何获取Coinbase Pro API](https://docs.hummingbot.io/connectors/coinbase/)
- 以太坊钱包（如果你的策略涉及去中心化交易所）
  例如：Metamask
- 以太坊节点（如果你的策略涉及去中心化交易所）
  [关于以太坊节点](https://docs.hummingbot.io/installation/node/#option-2-third-party-providers)
  [如何免费获得一个以太坊节点](https://docs.hummingbot.io/installation/node/#option-2-third-party-providers)
- 运行系统要求：
  Ubuntu 16.04或以后版本
  macOS 10.12.6 (Sierra)或以后版本
  Windows 10或以后版本
<br>
<br>
### 安装hummingbot
**相关阅读**
[《如何安装hummingbot》](https://docs.hummingbot.io/installation/)
<br>
<br>
### 使用hummingbot
**相关阅读**
[《如何配置hummingbot》](https://docs.hummingbot.io/operation/configuration/)
[《如何运行hummingbot》](https://docs.hummingbot.io/operation/running-bots/)
<br>
<br>
### hummingbot博客
[交易所類型說明：CLOB，RFQ和Automated](https://0xcj.com/2019/05/24/%E4%BA%A4%E6%98%93%E6%89%80%E9%A1%9E%E5%9E%8B%E8%AA%AA%E6%98%8E%EF%BC%9Aclob%EF%BC%8Crfq%E5%92%8Cautomated/)

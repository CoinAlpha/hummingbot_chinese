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

Hummingbot现在支持的交易所有：币安、DDEX、Radar Relay、Coinbase Pro、Bamboo Relay等，即将支持的交易所有IDEX、Uniswap、Binance DEX等。

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

**相关阅读**
- [《如何安装hummingbot》(中文翻译)](https://github.com/CoinAlpha/hummingbot_chinese/tree/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90)
- [《如何安装hummingbot》(英文原文)](https://docs.hummingbot.io/installation/)

<br>

## 使用hummingbot

**相关阅读**
- [《如何配置hummingbot》(英文原文)](https://docs.hummingbot.io/operation/configuration/)
- [《如何配置hummingbot》(中文翻译)](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/Hummingbot%E9%85%8D%E7%BD%AE.md)
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
- 想即时联系hummingbot团队？欢迎点击加入[hummingbot discord聊天室](discord.hummingbot.io)
- 想为hummingbot出份力？欢迎帮助[**翻译hummingbot文档**](https://docs.hummingbot.io)并在github提交Pull Request(合并请求)，我们阅读和修改后会尽快通过。感谢大家支持！
- 发现bug？报告bug也可以获得赏金哟！每报告一个我们决定解决的bug便可以获得0.1ETH赏金，[点击了解详情](https://github.com/CoinAlpha/hummingbot_chinese/blob/master/Hummingbot%E4%B8%AD%E6%96%87%E8%B5%84%E6%BA%90/Bug%E8%B5%8F%E9%87%91%E8%AE%A1%E5%88%92.md)。

<br>

## 致谢
感谢本repo的第一个来自社区的贡献者[syuukawa](https://github.com/syuukawa)！💐

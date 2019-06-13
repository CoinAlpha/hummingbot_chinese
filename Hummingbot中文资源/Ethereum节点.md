## 设置你的以太节点

### 需要以太节点吗？

您需要一个Ethereum节点来处理基于Ethereum的去中心化交易所的策略，比如0x 设置一个订单在 Radar Relay 或者 DDEX上。


### Option 1. 运行你自己的本地节点

最好和最可靠的方法，是运行您自己的Ethereum节点!

运行您自己的节点可能需要专用的存储和计算，以及一些技术技能。这是两个最广泛使用的以太坊客户端:

- [Geth (go-ethereum)](https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum)
- [Parity](https://github.com/paritytech/parity-ethereum)

**备注**

这些可能需要几个小时到几天的时间来同步，并且可能需要在首次运行时进行一些故障排除。

### Option 2. 第三方提供的节点

- 1.[Infura](https://infura.io/)提供免费和最广泛使用的以太节点。
- 2.[Alchemy Insights](https://alchemyinsights.io/)提供专业级以太节点,我们已经与Alchemy合作，为Hummingbot用户提供免费试用-请联系我们获取更多信息。
- 3.[Quiknode](https://quiknode.io/)

**Infura用户的重要提示**

如果使用Infura端点，请确保在Hummingbot中使用URL时将https://附加到URL后面。否则，您可能会看到一个糟糕的ethereum rpc url错误。

![image](https://github.com/syuukawa/hummingbot_chinese/blob/master/images/do-i-need-an-ethereum-node-001.png)


### Option 3. 专用区块链硬件

为您的Ethereum节点获得专用硬件。Ethereum节点意味着24/7持续运行，并消耗大量计算资源(CPU、RAM和存储)。对于更专业的用户，使用专用硬件可能是有意义的。

### 软件

[DAppNode](https://dappnode.io/)是在专用硬件上自动安装和操作Ethereum(以及其他区块链)的软件，更容易启动和操作Ethereum节点，并可以运行其他区块链。

### 硬件


- [IntelⓇ NUC mini PC](https://www.intel.com/content/www/us/en/products/boards-kits/nuc.html): DIY，自定义和配置自己的硬件。
- [Avado](https://ava.do/):使用DAppNode预加载的专用硬件。

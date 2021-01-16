本指南向您展示如何显示如何安装和运行新的```amm_arb```策略。我们在此博文中介绍的```amm_arb```策略使您可以套利AMM协议（例如Uniswap以及Balancer）和订单簿交换之间的价格差异。

## 适用Docker安装Hummingbot

由于```amm_arb```需要Hummingbot Gateway（一个单独的存储库），因此您必须使用Docker或从源代码安装Hummingbot才能运行它。如果使用Windows或macOS安装程序安装Hummingbot，则此策略将不起作用。

首先，让我们安装Hummingbot的Docker版本。我们为每个操作系统提供指南：

- [Windows](https://docs.hummingbot.io/installation/windows/)
- [苹果MAC系统](https://docs.hummingbot.io/installation/mac/)
- [Linux /云](https://docs.hummingbot.io/installation/linux/)
- [树莓派](https://docs.hummingbot.io/installation/raspberry/)

如果安装成功，您将看到Hummingbot客户端界面。

## 设置Hummingbot

接下来，我们需要将凭证添加到Hummingbot客户端，以便它可以在AMM协议和订单簿交换上进行交易。

我们还将配置Hummingbot与Hummingbot Gateway配合使用，Hummingbot Gateway是一个促进与区块链协议通信的独立模块。由于Gateway是与Hummingbot驻留在同一本地计算机中的单独的Web服务器，因此我们需要确保两者之间的所有通信均已安全加密。

### 创建一个安全密码

如果您是第一次在此计算机上使用Hummingbot，系统将提示您创建密码。此密码将用于加密敏感的配置设置，例如API密钥，秘密密钥和钱包私钥。

### 输入交易所API密钥
由于```amm_arb```套利AMM协议和集中式交易所之间的价格差异，因此您必须先输入两种凭据，然后才能开始交易。首先输入交换API密钥。

Hummingbot需要启用交易的API密钥才能访问您的交易所帐户。有关如何查找API密钥的特定于交易所的信息，请参见Hummingbot文档中的“连接器”页面。

输入命令```connect```查看可用的交易所。然后，输入```connect [exchange]```通过添加API密钥将您的交换帐户连接到Hummingbot，其中```[exchange]```是Hummingbot支持的交易所之一。

```
>>> connect binance
Enter your Binance API key
>>> ****************************

Enter your Binance API secret
>>> ****************************

You are now connected to binance.
```

### 建立ETH钱包和节点

接下来，我们将添加我们的以太坊钱包并连接到以太坊节点，这是在以太坊区块链上提交交易所需的。

!!注意：如果您在非以太坊协议上运行amm_arb，则以下说明可能不适用。

输入命令connect ethereum并添加与您的以太坊钱包关联的私钥。 Hummingbot以加密形式存储您的私钥和交换API密钥。
```
>>> connect ethereum
Enter your wallet private key
>>> ****************************

Wallet 0x...xxxx connected to hummingbot.
```

接下来，输入```config ethereum_rpc_url```并输入Infura节点的URL。
```
>>> config ethereum_rpc_url
Which Ethereum node would you like your client to connect to?
>>> https://mainnet.infura.io/v3/XXXX
```

**请注意，稍后设置Hummingbot Gateway时，我们将再次需要此URL。**

注意：要了解如何设置自己的以太坊节点或除Infura之外的其他提供商，请参阅[高级配置-以太坊节点](https://docs.hummingbot.io/operation/adv-command-ref/#setup-ethereum-nodes)。

### 添加ETH加油站API密钥
[ETH加油站](https://ethgasstation.info/)是一个免费的网站，可实时跟踪以太坊的汽油价格。由于以太坊汽油价格波动很大，我们建议添加一个API密钥，以便客户端在运行机器人时可以结合实时汽油价格。

要获得ETH加油站的免费API密钥，请访问DefiPulse Data并创建一个帐户。然后，保存API密钥以在Hummingbot中使用：
![](https://hummingbot.io/static/c5a65eb6ecc73b7602d6feb1de645505/a73f6/defipulse.png)

接下来，运行以下命令以输入您的ETH加油站API密钥，并告诉Hummingbot将其用于汽油价格查询：
```
>>> config ethgasstation_gas_enabled
Do you want to enable Ethereum gas station price lookup?
>>> Yes

>>> config ethgasstation_api_key
Enter API key for defipulse.com gas station API
>>> **************

>>> config ethgasstation_gas_level
Enter gas level you want to use for Ethereum transactions (fast, fastest, safeLow, average)
>>> fast (or another option)
```

注意：你也可以通过```config manual_gas_price```来设置汽油价格 

### 在Hummingbot中建立SSL证书


最后，我们将生成一个SSL证书，以保护Hummingbot客户端和Hummingbot Gateway之间的通信。

输入```generate_certs```以创建SSL证书：
```
>>>  generate_certs
Enter passphrase to generate Gateway SSL certification
>>> [your secret passphrase]

Gateway SSL certification files are created in /Users/[USERNAME]/hummingbot/certs
```
写下您的密码和认证路径，因为我们很快就会需要它。

获取证书路径：如果以后需要获取证书路径，请转到存储Hummingbot文件的目录。如果在安装Hummingbot的Docker版本时接受了默认选项，则计算机上将存在/ hummingbot_files目录。转到它并运行cd certs进入certs文件夹。然后，您可以从certs目录内部运行pwd以获得绝对路径。

## 安装和配置Hummingbot Gateway

Hummingbot Gateway是一个轻量级的Web服务器，具有连接到各种区块链的连接器。它允许基于Python的Hummingbot客户端与利用Javascript模块的Balancer等协议进行交互。

### 安装Gateway

在终端或Bash中，运行以下命令以下载并执行安装脚本：
```
# Download Hummingbot Gateway install
curl https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/create-gateway.sh -o create-gateway.sh
curl https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/update-gateway.sh -o update-gateway.sh

# Enable script permissions
chmod a+x create-gateway.sh

# Create a gateway instance
./create-gateway.sh
```

### 配置Gateway


该脚本会询问您一些问题以完成安装过程：
```
===============  CREATE A NEW GATEWAY INSTANCE ===============

ℹ️  Press [ENTER] for default values:
```

对于前三个问题，您可以按Enter接受默认值：
```
Enter Gateway version you want to use [latest/development] (default = "latest") >>>
Enter a name for your new Gateway instance (default = "gateway-instance") >>>
Enter Balancer network you want to use [mainnet/kovan] (default = "mainnet") >>>
```

输入您在步骤2中写下的certs文件夹的绝对路径：
```
Enter the full location path where your Hummingbot cert files are located
>>> /Users/[USERNAME]/hummingbot/certs
```

输入您在步骤2中添加的Infura节点URL：
```
Enter the Ethereum RPC URL set in your Hummingbot instance
>>> https://mainnet.infura.io/v3/XXXX
```

在第2步中输入用于生成SSL证书的密码：
```
Enter your Gateway cert passphrase configured in Hummingbot
>>> [your secret passphrase]
```

之后，查看信息并输入“是”以完成Gateway配置：

![](https://hummingbot.io/static/aa3a632397c42276d02bc98a28b648d0/320b1/gateway-summary.png)


更改端口：默认情况下，网关将安装在Hummingbot用于连接到的端口5000上。如果端口5000不可用，网关将增加端口号并使用端口5001。如果端口为5001，请在Hummingbot中运行```config gateway_api_port```设置正确的端口。

## 运行```amm-arb```机器人

现在，我们终于可以配置一个在AMM协议和订单簿交换之间套利的```amm_arb```机器人！

### 配置机器人

使用```create```命令来构建策略配置文件：
```

What is your market making strategy?
>>> amm_arb

Enter your first connector (exchange/AMM)?
>>> balancer

Enter the token trading pair you would like to trade on balancer (e.g. WETH-DAI)
>>> WETH-DAI

Enter your second connector (exchange/AMM)?
>>> binance

Enter the token trading pair you would like to trade on binance (e.g. ZRX-ETH)
>>> ETH-USDT

What is the amount of WETH per order?
>>> [order_amount]

What is the minimum profitability for you to make a trade (Enter 1 to indicate 1%)?
>>> 1

# Buffer added to the price to account for price movement before trade execution
How much buffer do you want to add to the price to account for slippage for orders on the first market (Enter 1 for 1%)?
>>> 0.1

How much buffer do you want to add to the price to account for slippage for orders on the second market (Enter 1 for 1%)?
>>> 0.1

# If true the bot submits both arbitrage taker orders (buy and sell) simultaneously.
# If false, the bot will wait for first exchange order filled before submitting the other order.
Do you want to submit both arb order concurrently (Yes/No)?
>>> Yes
```


有关以上每个参数的详细信息，请参阅策略-AMM Arb。

添加以太坊令牌：要将令牌地址添加到Hummingbot维护的以太坊令牌列表中，请在Hummingbot目录中编辑以下文件（如果从源安装）：```/hummingbot/hummingbot/wallet/ethereum/erc20_tokens.json```。我们打算在Hummingbot的未来版本中简化此过程。

### 运行机器人


输入```start```以运行该机器人。

表演者将执行检查，以确保它可以同时连接到协议和交换机。之后，机器人会自动对需要批准的任何令牌调用```approve```功能。

然后，机器人将连续扫描套利机会并执行交易以捕获它们。

输入```status```以查看每个套利分支的当前获利能力。

输入```history```以查看您的机器人在当前时段进行了哪些交易。

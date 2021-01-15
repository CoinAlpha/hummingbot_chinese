## celo-arb套利策略：在celo和其他交易所之间交易cGLD或cUSD来套利

### 事先准备

由于Celo是一种区块链协议，因此除了正常的库存要求外，您还需要在运行Hummingbot客户端的同一台计算机上访问Celo节点和celo-cli命令行工具。

与普通套利策略类似，您将需要在Celo钱包和您想要用来套利的二级交易所中保存Celo代币的库存（即Celo Gold（cGLD）或cUSD），以便能够交易和获取价差（即购买在一个交易所低价卖出，在另一个交易所高价卖出）。
您还需要在Celo钱包中添加一些CELO代币，才能支付Celo区块链上的交易费用。

### Celo节点

Celo节点允许Hummingbot客户端通过连接到对等方，发送交易和获取链状态来与Celo区块链进行交互。由于客户端只需要访问链和最近的区块，因此您可以运行Celo完整节点或超轻型节点。请遵循Celo文档来安装和运行完整节点。**请注意，必须同步节点才能运行celo-arb策略。**

***提示：超轻同步模式— celo-arb策略适用于以“超轻”模式运行的Celo节点，同步速度要快得多。有关如何以超轻模式启动节点的说明，请参见我们的[快速入门](https://hummingbot.io/academy/celo-arb/)。***

### ```celo-cli``` CLI工具

为了与Celo节点进行交互，Hummingbot客户端依赖于celo-cli命令行工具。请按照Celo文档中的以下说明安装celo-cli。

### 配置

**1. 建立一个AWS云实例**

此配置为在AWS上安装Hummingbot的Docker构建。请注意，除了AWS以外，您还可以使用其他云提供商，并且除了Docker之外，还可以从源代码或二进制安装Hummingbot。

- 实例类型
  尽管免费的t2.micro层可能足以运行celo-arb，但我们建议使用t2.medium实例作为最小实例类型，以提高性能。

- 存储
  默认情况下，AWS实例具有8 GB的存储空间。我们建议您将存储增加到至少16 GB，以便与Celo节点一起安装Docker版本。

**2. 安装Docker**
```# 1) Download Docker install script
wget https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/install-docker/install-docker-ubuntu.sh

# 2) Enable script permissions
chmod a+x install-docker-ubuntu.sh

# 3) Run installation
./install-docker-ubuntu.sh
```

**3. 运行Celo超轻型节点**
按照Celo文档获取Celo Docker映像并安装/配置节点，但是在“配置节点”步骤之后和“启动节点”步骤之前立即停止：

而是运行以下命令来启动超轻型节点而不是完整节点：
```docker run --name celo-ultralight-node -d --restart unless-stopped -p 127.0.0.1:8545:8545 -v $PWD:/root/.celo $CELO_IMAGE --verbosity 3 --networkid $NETWORK_ID --syncmode lightest --rpc --rpcaddr 0.0.0.0 --rpcapi eth,net,web3,debug,admin,personal --etherbase $CELO_ACCOUNT_ADDRESS --bootnodes $BOOTNODE_ENODES --allow-insecure-unlock```

***确保保存创建的新Celo帐户的地址和密码。您稍后将需要它。***

**4. 安装和运行Hummingbot**
```# 1) Download Hummingbot install, start, and update script
cd ~
wget https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/create.sh
wget https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/start.sh
wget https://raw.githubusercontent.com/CoinAlpha/hummingbot/development/installation/docker-commands/update.sh

# 2) Enable script permissions
chmod a+x *.sh

# 3) Create a hummingbot instance
./create.sh
```

之后，Hummingbot将自动启动并提示您设置密码。退出后，可以使用```./start.sh```和```./update.sh```命令分别运行和更新Hummingbot。

**5. 连接Celo区块链**
运行命令```connect celo```

在步骤3中创建Celo帐户时，输入Celo地址和密码。

现在，您应该已连接到Celo。要进行检查，请运行```balance```命令并检查CELo和cUSD的余额是否与您在Celo钱包中持有的余额匹配。

**6. 配置**

以下是运行```create```命令时的所有步骤。这些参数是Hummingbot配置文件中的字段（位于```/ conf```文件夹中，例如```conf / celo_arb _ [＃].yml```）。

- secondary_market：输入你想要进行套利的另一个交易所
- secondary_market_trading_pair：输入你想要套利的交易对
- min_profitability：你想获得的最低收益率
- order_amount：套利交易每部分的订单金额
- celo_slippage_buffer（How much buffer do you want to add to the Celo price to account for slippage (Enter 1 for 1%)?）：在Celo交易价格中添加缓冲百分比以缓解交易执行之前的价格变动/滑点

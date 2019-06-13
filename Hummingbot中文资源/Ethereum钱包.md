## 设置你的以太钱包

### 为什么Hummingbot需要以太钱包私钥

在去中心化交易平台(如Radar Relay和DDEX)上进行交易策略直接与Ethereum区块链上的智能合约交互。因此，交易必须经过签名和授权，这需要您的私钥。

## 创建钱包

启动Hummingbot并运行配置过程后，会问您:是导入现有的钱包还是创建一个新钱包?

回复创建一个新的钱包。注意，为了运行交易机器人，您需要将ETH和令牌发送到这个钱包地址。

之后，系统会提示您输入一个保护钱包的密码。每次启动hummingbot时，都需要使用此密码解锁钱包，以便在去中心化的交易所上运行交易机器人。

### 导入钱包

从Metamask和MyCrypto等钱包中导入Hummingbot钱包有两种方法:

- 1.导入钱包的密钥文件(推荐)
- 2.导入钱包的私钥

**Warning**

我们建议使用keyfile方法而不是复制和粘贴私钥。如果您的私钥仍然保存在剪贴板中，那么您访问的恶意网站可能会使用Javascript访问剪贴板并复制其中的内容。

### Keyfile(推荐)

使用JSON密钥文件导入钱包:

- 1.从其他钱包(如Metamask、MyCrypto或MyEtherWallet)导出JSON密钥文件
- 2.将文件保存在/conf目录中
- 3.将文件重命名为key_file_[address]。json，其中[address]是格式0xabc…def的Ethereum地址。
- 4.启动Hummingbot
- 5.回答导入问题:您是想导入一个现有的钱包还是创建一个新的钱包?
- 6.你的钱包应该在选项列表中可用。

### 私钥

- 1.启动Hummingbot并运行配置过程后，会问您:是导入现有的钱包还是创建一个新钱包?
- 2.回复import，系统会提示您输入与钱包关联的私钥
- 3.用密码保护你的钱包

### 导出钱包

有两种方法可以将你的Hummingbot钱包导出到其他钱包，比如Metamask和MyCrypto:

- 1.导出钱包的密钥文件(推荐)
- 2.导出钱包的私钥

**Warning**

我们建议使用keyfile方法而不是复制和粘贴私钥。如果您的私钥仍然保存在剪贴板中，那么您访问的恶意网站可能会使用Javascript访问剪贴板并复制其中的内容。

### Keyfile (推荐)

当您使用Hummingbot导入或创建钱包时，一个名为key_file_[address]的JSON文件在/conf目录中创建的。这个JSON密钥文件包含您钱包的加密私钥，可以导入到其他dApps中。

### 私钥

在hummingbot CLI中，您可以使用export_private_key命令来显示与钱包地址关联的私钥。您也可以使用这个私钥将您的钱包导入到像Metamask和MyCrypto这样的dApps中。

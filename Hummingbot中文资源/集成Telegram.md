## 集成Telegram

![image](https://docs.hummingbot.io/assets/img/telegram.png)

将Hummingbot与Telegram Messenger集成在一起，你就可以从任何安装了Telegram的设备上获得实时更新，并向你的交易机器人发出指令。

无论您是在云中运行Hummingbot，还是在本地机器上运行Hummingbot，您都可以使用Telegram从任何位置监视和控制Hummingbot !

### 设置你的电报机器人

下面，我们将展示如何创建与Hummingbot部署集成的Telegram机器人。

### 1.创建一个机器人

- 单击此链接启动正式的BotFather bot，这是一个帮助您创建和管理Telegram bots的Telegram bot: https://telegram.me/BotFather。
- 在Telegram中，转到新创建的BotFather聊天窗格，单击Start或type / Start。
- 输入/newbot创建一个机器人。

![image](https://docs.hummingbot.io/assets/img/botfather-1.png)

- 为您的机器人输入一个名称，在Telegram中输入该机器人的名称(例如hummingbot)。

![https://docs.hummingbot.io/assets/img/botfather-2.png](https://docs.hummingbot.io/assets/img/botfather-2.png)

- 输入一个以单词bot结尾的惟一ID(例如my_awesome_hummingbot)。

![https://docs.hummingbot.io/assets/img/botfather-3.png](https://docs.hummingbot.io/assets/img/botfather-3.png)

- 单击机器人的名称启动它:t.me/<YOUR BOT NAME> 在上面的消息。
- 请注意上面响应中的电报令牌。您将在稍后的配置步骤中用到它。


### 2.获取Telegram ID

- 单击此链接启动userinfobot，这是一个帮助您检索电报ID的电报机器人:https://telegram.me/userinfobot。
- 在Telegram中，转到新创建的userinfobot聊天窗格，并单击Start或输入 / Start。
- 请注意提供的Id参数。您将在稍后的配置步骤中用到它。

### 3.在Hummingbot中配置Telegram设置

- 在安装Hummingbot的目录中，转到全局配置文件:conf/ con_global .yml。
- 在文件末尾输入以下参数:

      telegram_enabled: true
      telegram_token: <TELEGRAM TOKEN FROM STEP 1>
      telegram_chat_id: <TELEGRAM ID FROM STEP 2>
      
### 使用电报机器人

- 在开始使用Hummingbot之前，请确保Telegram机器人是实时的。如果是这样，您应该在Telegram中看到一个带有您的机器人名字的聊天窗格。
- 现在你可以像往常一样启动Hummingbot了。当您进入hummingbot CLI窗口启动时，Telegram将立即连接。
- Telegram bot和实际运行的Hummingbot实例之间的消息是实时同步的。例如，可以使用status和history等命令来监视机器人的性能，还可以使用start和stop来控制机器人。

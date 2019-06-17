## Debug控制台

调试控制台是Hummingbot开发人员在运行时检查和修改Hummingbot中活动状态的强大工具。它允许访问与Hummingbot进程相同的实时Python控制台。
它可以被认为与大多数浏览器中的开发人员控制台类似。

### 激活调试控制台

调试控制台在默认情况下是禁用的。您需要通过在conf/ con_global .yml中设置debug_console: true来启用它。

![image](https://docs.hummingbot.io/assets/img/debug1.png)

### 进入调试控制台

当您启动Hummingbot并启用调试控制台时，它将在启动时打印出一条“已启动调试控制台”日志消息。

![image](https://docs.hummingbot.io/assets/img/debug2.png)

注意调试消息中打印的端口号(上面示例中的端口8211)，您可以使用telnet或nc通过连接到日志消息中描述的TCP端口来访问调试控制台。

![image](https://docs.hummingbot.io/assets/img/debug3.png)

### 访问Python模块和公开对象

一旦您进入调试控制台，就可以访问Hummingbot进程中功能齐全的Python解释器。

您可以通过hb对象访问HummingbotApplication类下的所有公开属性。

下面是一些您可以从调试控制台访问的公开属性:

- hb.strategy:当前活动的策略对象
- hb.markets:一个活跃的市场连接器字典
- hb.acct: 当前活动的Ethereum钱包对象
- hb.clock: 驱动所有Hummingbot组件的时钟对象

![image](https://docs.hummingbot.io/assets/img/debug4.png)

### 一些例子

下面是一个开发人员查询策略下当前活动的出价/要价以及DDEX上当前的最佳要价的例子。

![image](https://docs.hummingbot.io/assets/img/debug5.png)

您应该参考公开对象的源代码，以查看可以在调试控制台中检查和修改哪些属性。

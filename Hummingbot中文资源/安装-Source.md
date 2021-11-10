## 用源文件安装

### 系统特定依赖

我们为用户提供针对每个操作系统编译的二进制文件。下面，我们列出了特定于os的依赖关系和建议。

操作系统          备注

Mac OSX	        可能需要安装Xcode或Xcode命令行工具。

Linux               我们推荐Ubuntu 18.04，虽然Hummingbot也可以在其他版本的Linux上运                        行。如果您正在一个新的Linux虚拟机上安装Hummingbot，我们建议先安                        装build-essential包，因为Hummingbot使用gcc编译器和它包含的其他                          库:（安装命令如下）
                       sudo apt-get update
                       sudo apt-get install build-essential
                       
 Windows         Hummingbot是为macOS和Linux设计和优化的。虽然Windows二进制文件                       是可用的，但它不能很好的支持。相反，我们建议Windows用户安装用于                           Linux的[Windows子系统](https://docs.microsoft.com/en-us/windows/wsl/faq)，它允许您运行Linux版本。


### 1. 安装Anaconda

Hummingbot需要python3和其他Python库。为了管理这些依赖关系，Hummingbot使用了Anaconda，这是Python的开源环境和包管理器，是当前数据科学家和数据工程师的行业标准。

要安装Anaconda，请访问[Anaconda网站](https://www.anaconda.com/distribution/)并下载操作系统的Python 3.7安装程序。图形安装程序和命令行安装程序都可以工作。运行安装程序，它将指导您完成安装过程。

然后，打开终端窗口并尝试conda命令。如果该命令有效，那么Anaconda已经成功安装，即使图形安装程序说它失败了。

- Warning

如果使用ZSH或其他Unix shell，请将下面的代码段复制到.zshrc或类似的文件中。默认情况下，Anaconda只将其添加到.bash_profile文件中。这使得conda命令在根路径中可用。

>__conda_setup="$(CONDA_REPORT_ERRORS=false '/anaconda3/bin/conda' shell.bash hook 2> /dev/null)"
if [ $? -eq 0 ]; then
    \eval "$__conda_setup"
else
    if [ -f "/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/anaconda3/etc/profile.d/conda.sh"
        CONDA_CHANGEPS1=false conda activate base
    else
        \export PATH="/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup


### 2. 下载Hummingbot客户端

克隆或下载[Github repository](https://github.com/coinalpha/hummingbot)。

### 3. 运行安装脚本

在终端或bash窗口中，进入到根目录:

>cd hummingbot

运行install脚本，它创建一个自定义的Anaconda环境，并安装Python库和机器人所需的其他依赖项:

>./install

### 4. 激活环境

安装脚本创建一个自定义的Anaconda环境，用于管理Hummingbot使用的依赖项。激活环境:

>conda activate hummingbot

当您在终端命令提示符前看到(hummingbot)前缀时，环境已被激活:

- 备注1

确保您使用的是最新的conda版本。您可以通过键入conda—version来检查。此外，如果您看到一条消息说您的shell没有配置为使用conda activate，那么您可能必须输入conda init bash命令。

- 备注2

在编译或运行该机器人之前，确保您已经激活了hummingbot环境。

### 5. 编译

编译并且Cythonize的源代码到可执行的二进制:

>./compile

### 6. 运行Hummingbot

输入以下命令开始运行Hummingbot:

>bin/hummingbot.py


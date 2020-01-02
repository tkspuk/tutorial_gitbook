# Gitbook系统安装

## Node.js安装

![Node.js](../imgs/node.js.png)

> gitbook需要依赖于node.js

> Node.js是一个基于Chrome Javascript运行时建立的一个平台，用来方便的搭建快速的，易于扩展的网络应用。

> Node.js借助事件驱动，非阻塞I/O模型变得轻量和高效，非常适合run across distributed devices的data-intensivede 的实时应用。

Node.js的安装，请参考：

[nodejs官网](https://nodejs.org/en/download/)下载然后傻瓜安装即可

[在 Linux 中安装 Nodejs](https://einverne.github.io/post/2017/10/linux-install-nodejs.html)

安装完成之后，可以通过下面的命令来验证一下Node.js是否安装成功。

```zsh
$ node -v
v12.1.0
```



## Gitbook应用安装

Gitbook是使用NPM来进行安装的，可以在命令行中输入下面的命令进行安装：

```bash
$ npm install gitbook-cli -g
```

安装完成之后，你可以使用下面的命令来检验是否安装成功

```bash
$ gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

如果你看到了上面类似的版本信息，则表示你已经安装成功了。


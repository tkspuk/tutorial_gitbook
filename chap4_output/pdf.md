# 输出为PDF

输出为PDF文件，需要先安装`gitbook pdf`

```bash
$ npm install gitbook-pdf -g
```

> 如果在安装gitbook-pdf时，觉得下载`phantomjs`包太慢的话，你可以到`phantomjs`的官方网站上去下载。

> http://phantomjs.org/

> 这个包的安装方式，参考其官网的说明文档。

然后，用下面的命令就可以生成PDF文件了。

```bash
$ gitbook pdf
```

如果，你已经在编写的gitbook当前目录，也可以使用相对路径。

```bash
$ gitbook pdf .
```

然后，你就会发现，你的目录中多了一个名为```book.pdf```的文件。

# 安装calibre插件

玩过kindle的都知道，calibre是一款非常方便的开源电子书转换软件。在这里，我们也是用到ebook-convert这个插件。

首先在calibre官网下载插件，下载链接：[Calibre_download](https://calibre-ebook.com/download)。下载适合自己系统的版本。

下载到电脑之后我做了很多尝试，刚下载之后我兴冲冲的去使用gitbook pdf . mypdf.pdf指令，结果发现提示ebook-convert未安装。

将安装的calibre放在系统应用中，然后将app添加到path中。

执行一个命令
```
sudo ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/local/bin
```

执行完成之后，重新进入书籍目录。

```
$ cd jianli
$ gitbook pdf . jianli.pdf
info: 7 plugins are installed 
info: 6 explicitly listed 
info: loading plugin "highlight"... OK 
info: loading plugin "search"... OK 
info: loading plugin "lunr"... OK 
info: loading plugin "sharing"... OK 
info: loading plugin "fontsettings"... OK 
info: loading plugin "theme-default"... OK 
info: found 1 pages 
info: found 7 asset files 
info: >> generation finished with success in 7.5s ! 
info: >> 1 file(s) generated
```

执行完以上代码，进入书籍目录，即可看到已经转换完成的PDF了。大功告成！






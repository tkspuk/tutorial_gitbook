# Gitbook初始化一本书

Gitbook可以通过命令行工具，进行书籍的管理，使用方法如下：

## Book的目录结构
新写一本书的时候，需要从**模板中**复制以下文件，
```
├── FOOTER.md   底标文件
├── README.md   书籍说明
├── SUMMARY.md  书籍目录与结构
└── book.json   书籍的配置文件
```

## 初始化
首先安装**book.json**中定义的插件与配置。

```
gitbook install 
```

其次，在使用 `gitbook init` 之后本地会生成两个文件 `README.md` 和 `SUMMARY.md` ，这两个文件都是必须的，一个为介绍，一个为目录结构。

```
gitbook init
```

如何编写`SUMMARY.md`和`README.md` 将在后续章节详细介绍[README.md 与 SUMMARY编写](../chap2_content/basic.md)


## 本地预览
当内容书写完毕后，可以在终端中输入如下命令，实现实时预览

```bash
gitbook serve
gitbook serve ./ {book_name}
```

`gitbook serve` 命令实际会先调用 `gitbook build` 编译书籍，完成后打开 web 服务器，默认监听本地 4000 端口，在浏览器打开 <http://localhost:4000> 即可浏览电子书。

## 发布电子书

```bash
gitbook build
gitbook build ./ {book_name} --output=./{outputFolde}
gitbook build ./ --log=debug --debug
```

当电子书内容制作好之后，可以使用如下命令来生成 HTML 静态网页版电子书。该命令会在当前文件夹中生成 `_book` 文件夹，这个文件夹中的内容就是静态网页版电子书。

使用 `--log=debug --debug` 可以用来调试，会打印出 stack trace。

## 查看帮助

```bash
$ gitbook -h

  Usage: gitbook [options] [command]

  Commands:

    build [options] [source_dir] Build a gitbook from a directory
    serve [options] [source_dir] Build then serve a gitbook from a directory
    install [options] [source_dir] Install plugins for a book
    pdf [options] [source_dir] Build a gitbook as a PDF
    epub [options] [source_dir] Build a gitbook as a ePub book
    mobi [options] [source_dir] Build a gitbook as a Mobi book
    init [source_dir]      Create files and folders based on contents of SUMMARY.md
    publish [source_dir]   Publish content to the associated gitbook.io book
    git:remote [source_dir] [book_id] Adds a git remote to a book repository

  Options:

    -h, --help     output usage information
    -V, --version  output the version number
```


## 一键发布到github脚本
执行gitbookpush命令进行gitbook发布
```
#!/bin/sh
gitbook build ./ docs
git add --all
git commit -m "book update"
git push -u origin master
```

前提需要做好github的的初始化工作[github初始化](../chap5_publish/gitpages.md)

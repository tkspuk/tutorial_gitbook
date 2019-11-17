# 发布到Github Pages

## 发布方式
将gitbook书籍发布到github有以下两种方法：
* **方法一**: md源文件与html文件放在同一个仓库，并且都存储在master分支，html发布在docs文件夹下，然后在github上进行设置
* **方法二**: 将md文件与Github Pages静态文件存放在一个仓库中。md文件为master分支，而html文件为 gh-pages分支。

## 方法一：使用项目docs目录提供服务

1. 登陆到Github，创建一个新的仓库，名称我们就命名为`tutorial_gitbook`，这样我就得到一个`tutorial_gitbook`仓库。
2. gitbook书籍本地文件夹执行`git init`初始化git 
3. 添加远端分支`git remote add origin https://github.com/tkspuk/tutorial_gitbook.git`
4. 将本地资料push到仓库：

    ```
    git config  user.name "John Doe"
    git config  user.email johndoe@example.com
    git add --all
    git commit -m "first commit"
    git push -u origin master
    ```
5. 点击这个仓库的**Settings**，找到**GitHub Pages**配置选项，在**Source**配置中选择`master branch/docs folder`选项，大功告成。

经过上述步骤，Github会自动为你分配一个网址。

> http://USERNAME.github.io/tutorial_gitbook

未来修改书籍发布仅需要以下两个命令

```
gitbook build ./ docs
git add --all
git commit -m "some update"
git push -u origin master
```



## 方法二：使用项目gh-pages分支提供服务

除了上面的直接发布静态文件到Github Pages的方法以外，还可以使用一个单独的项目的Github Pages功能。

###  手动创建仓库与分支

1. 登陆到Github，创建一个新的仓库，名称我们就命名为`tutorial_gitbook`，这样我就得到一个`tutorial_gitbook`仓库。
2. 克隆仓库到本地： `git clone git@github.com:/USER_NAME/tutorial_gitbook.git`
3. 创建一个新分支： `git checkout -b gh-pages`，注意，分支名必须为`gh-pages`。
4. 将分支push到仓库： `git push -u origin gh-pages`。
5. 切换到主分支：`git checkout master`。

经过这一步处理，我们已经创建了`gh-pages`分支了，有了这个分支，Github会自动为你分配一个网址。

> http://USERNAME.github.io/tutorial_gitbook

你可以在项目页面右下角```setting```中看到：

![Github Pages](../imgs/gh-pages-setting.png)


### 基于Travis的自动化发布Github Pages

下面将介绍使用一个仓库托管源码，而使用 Travis 自动将静态网站发布到 `gh-pages` 分支中。这样就可以避免提交源码的同时，还需要同步一遍 `gh-pages` 分支。

[domenic](https://gist.github.com/domenic/ec8b0fc8ab45f39403dd) 制作了一个脚本，当 master 分支更新时，自动使用 CI Travis 拉取更新，然后和 `gh-pages` 分支做比较，如果有差异了，自动将 master 分支的修改提交到 `gh-pages` 分支。
# GitBook

[https://www.gitbook.com](https://www.gitbook.com)

GitBook 又是什么，和 Git 的关系？

GitBook 是一个基于 Node.js 的命令行工具，专注于管理和编辑电子书，采用了时下最流行的 MarkDown 语法来编写书籍，目前很多开源电子书基本都是用 MarkDown 编写的，还有很多 Blog、论坛，也都推出了支持 MarkDown 的编辑工具。本教程即是用 GitBook + MarkDown 语法编撰的。

关于 MarkDown，不展开了，参加附录教程。

## 安装

首先我们需要安装 Node.js

### 安装 Node

去 https://nodejs.org/en/ 下载 LTS 版本安装对应的操作系统版本即可

check

```
npm -verison
```

### 安装 GitBook

```
npm install gitbook-cli -g
```

## 初始化

### 初始化仓库

在一个本地空目录执行

```
gitbook init
```

会产生2个文件：

README.md

SUMMARY.md

### 设置大纲

编辑 SUMMARY.md，如本教程的：

```markdown
# 目录

* [简介](README.md)
* [Git 的历史](git-history.md)
* [Git 的概念](git-theory.md)
* [Git 操作本地库](git-local.md)
* [Git 操作远程库](git-remote.md)
* [Git 分支管理](git-flow.md)
* [GitHub](github.md)
* [GitLab](gitlab.md)
* [GitBook](gitbook.md)
* [附录](appendix.md)
```

然后重新 init，就会生成好所有章节的 md 文档

### 启动本地服务

```
gitbook serve
```

然后就可以访问 http://localhost:4000 查看书籍了

![2017-09-11_153530](images\2017-09-11_153530.png)

## 编辑书籍

这里开始就八仙过海了，你可以上文本工具，可以用 VS Code，可以用 IDEA，这些都是不错的 MarkDown的编辑器，但是使用最好的工具更有助于我们更好的完成我们的工作，这里推荐 Typora，免费、强大、专注写作

![](images\2017-09-11_154324.png)

## 发布书籍

最后，初始化好就可以和某个 Git 仓库进行集成，如果你的书籍是开源的，推荐和 GitHub 集成，GitBook 官方提供了和 GitHub 集成的方式，这样就不用再到 GitBook 上去做一次提交了。


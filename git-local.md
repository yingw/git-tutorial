# Git 操作本地库

本地库的操作是 Git 最重要的功能，包含一堆常用命令，如 init, add, commit, checkout 等。

## 安装 Git 客户端

首先，得安装 Git

### 在 Windows 上安装

下载 [Git-SCM](https://git-scm.com) 或 [git-for-windows](https://git-for-windows.github.io/) 并安装即可，安装完成后用：

```shell
git --version
```

来检查是否成功

### 在 Linux 上安装

Debian, Ubuntu, Deepin, Mint

```shell
sudo apt-get install -y git
```

RHEL, CentOS, Fedora

```shell
yum install -y git
```

### 在 Mac 上安装

```shell
brew isntall git
```

或，安装 XCode 就内置了 Git。

## 初始设置

我们需要给 Git 设置使用者的信息

```shell
git config --global user.name "Gary Yin Guo Wei"
git config --global user.email "yinguowei@cn.wilmar-intl.com"
```

查看现有的设置

```shell
git config --list
```

好了，准备工作完毕，接下来可以开始操作我们的第一个库了。

## 项目1：Hello, Git!

创建一个空目录，如 hello-git，在目录中，创建本地仓库

```shell
git init
```

新建一个 README.txt （以下非 git 命令都以 windows 为例）

```shell
echo Hello, Git!>README.txt
type README.txt
```

添加到本地

```shell
git add README.txt
```

提交

```shell
git commit -m "初次提交！"
```

这样第一个库就创建好了，并完成了一次提交，下面来分析当中的几个关键命令。

## 命令解析

### 创建版本库 git init

```shell
git init
```

创建仓库的命令，所有仓库的第一个命令。执行后会创建 .git 目录。

如果要指定创建文件夹：

```shell
git init directory
```

### 查看状态 git status

我们**经常**要查看 status 来实时了解当前库的状态

```shell
git status
```

常见的一些状态

```shell
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   INFO.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md
        deleted:    README.txt
        
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        modified:   git-history.md
```

分别是：

- Staged，未提交：INFO.txt
- 变更，未 Staged：README.md
- 删除，未 Staged：README.txt
- 新文件，未 Staged：git-history.md

### 添加文件 git add

```shell
# 添加单个文件
git add file
# 添加多个文件
git add file2.txt file3.txt
# 添加指定后缀名，注意引号一定要
git add '*.txt'
```

当然，也可以添加目录

### 提交变更 git commit

```shell
git commit -m "First commit"
```

重要：不能省略注释！

### 查看提交日志 git log

```shell
git log
```

或查看简洁版本

```shell
git log --pretty=oneline
```

### 设置忽略 .gitignore

add 的时候，我们会碰到一些不想加入到 git 仓库中去的文件，比如 windows 的略缩图 Thumbs.db，java 的编译类 *.class，我们可以把它加入项目下 .gitignore 文件来自动忽略（类似 SVN）。（注意要用文本工具另存为创建）

一个典型的 Java 项目 .gitignore 如：

```properties
target/
!.mvn/wrapper/maven-wrapper.jar

### STS ###
.apt_generated
.classpath
.factorypath
.project
.settings
.springBeans

### IntelliJ IDEA ###
.idea
*.iws
*.iml
*.ipr

### NetBeans ###
nbproject/private/
build/
nbbuild/
dist/
nbdist/
.nb-gradle/

/.mvn
mvnw
mvnw.cmd

```

同时，看全局配置，还可以在 USER_HOME/documents 下面设置 gitignore_global.txt 来做全局设置。

对于不同语法的 gitignore，大家可以参考 GitHub 提供的这个仓库：

https://github.com/github/gitignore

## 其他命令

### 查看差异 git diff

待 stage 的文件，可以用 diff 工具来查看差异（但是更推荐用外部工具如 SourceTree、Beyond Compare、Tortoise Merge）

```shell
git diff readme.txt
```

### 删除文件 git rm

```shell
git rm file

git commit
```

## 项目2：版本回退

工作中难免存在错误，错误的修改、错误的提交，而且 git 的数据储存区比较复杂，所以回退这一块是稍微复杂点，但是必须得了解清楚，否则各种操作失误、丢失文件一定会让整个项目组崩溃。

### git 的版本号

是一大串字母+数字组合的 SHA1 加密串，指定版本时候，一般只要写其前 7 位就够了

### 回退工作区 git checkout

可以丢弃工作区的修改，回退到最后一次暂存区的状态：

```shell
git checkout -- file
```

### 回退暂存区 git reset

暂存区的修改撤销掉（unstage），先 reset HEAD file，再 checkout 回退工作区修改：

```shell
git reset HEAD file
git checkout -- file
```

## 工作区、暂存区、分支

工作区、暂存区、分支的概念是 Git 里最核心的概念之一，这里介绍一下工作区和暂存区，分支将在后面章节介绍

add 将文件放到暂存区 stage，head 指向 master 分支

commit，stage 到 分支 ![image](http://wiki.jikexueyuan.com/project/git-tutorial/images/git10.jpg)



## 附：暂存区的操作

切去其他分支前，没提交的变更可以

```
git stash
```

回来后

```
git stash list
```

恢复

```
git stash apply
```

删除

```
git stash drop
```

或，恢复且删除：

```
git stash pop
```


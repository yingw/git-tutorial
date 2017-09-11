# Git 操作远程库

Git 分布式已经够强了，但是为了大家交换文件方便，还可以再设置一台虚拟中心的远程服务器作为远程仓库，比较知名的搭建远程仓库的工具有：

- GitHub
- GitLab
- BitKeeper
- 共享文件夹……

除了最后一种，其他的 Git 远程库工具额外提供了：认证、授权、SSO、社区、第三方团队工具等等等等丰富多彩的世界，可以参考 GitHub 章节。

GitHub 是一个推崇开源、在线 SaaS 的平台，GitLab 是可以本地创建私有仓库的 Linux 工具。

## 添加远程库 git remote

对于一个现有项目，管理远程仓库使用 remote 命令：

```shell
git remote add origin git@github.com:michaelliao/learngit.git
```

远程库的名字就是 origin

## 克隆 git clone

参加一个现有项目，从无到有，可以使用 clone：

到每个 Git 远程库管理软件（如 GitHub、GitLab），都有一个叫做 Clone 的选项，可以辅助其远程地址（注意是不需要权限的），一般我们加入一个现有项目也是从这条命令开始从远程库创建本地项目的。

```shell
git clone http://yinguowei@git.wilmartest.cn/yinguowei/cas-client-demo.git
```

接下来，你就可以在本地仓库上尽情 commit，并关联到自己的远程库或发起 pull request了。

## 推送 git push

已 clone，推送本地 commit：

```shell
git push -u origin master
```

-u 是把本地分支和远程分支关联
以后提交只要

```shell
git push origin master
```

## 拉取 git pull

已 clone，同步远程服务器上到本地的方式成为拉取

```shell
git pull origin master
```

## 查看区别 git diff

```shell
git diff  HEAD
```




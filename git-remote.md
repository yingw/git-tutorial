# Git 操作远程库

Git 分布式已经够强了，但是为了大家交换文件方便，还可以再设置一台虚拟中心的远程服务器作为远程仓库，比较知名的搭建远程仓库的工具有：

- GitHub
- GitLab
- BitKeeper
- 共享文件夹……

除了最后一种，其他的 Git 远程库工具额外提供了：认证、授权、SSO、社区、第三方团队工具等等等等丰富多彩的世界，当今世界上，不论个人开发组，还是一些大型企业，都开始倾向于将自己的一些工具完全开源，并 po 到 GitHub 上，会有许许多多志同道合的开发组一起参与进来优化产品，使得我们的 IT 世界变得越来越好，也是的 GitHub 成了全球最大的社交编程和代码托管平台，估值在 17 年初已达 20 亿美金！

GitHub 是一个推崇开源、在线 SaaS 的平台，GitLab 是可以本地





## 添加远程库



```
git remote add origin git@github.com:michaelliao/learngit.git
```

远程库的名字就是 origin

## 推送



```
git push -u origin master
```

-u 是把本地分支和远程分支关联
以后提交只要
git push origin master

### 拉取

```
git pull origin master
```



查看区别

git diff  HEAD



## 克隆

git clone http://...


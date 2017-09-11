# Git 的概念

## 集中式 VS 分布式

Git 是分布式版本控制系统。区别于 SVN 和 CVS 等早期集中式版本控制系统。

集中式版本控制系统最大的毛病就是必须联网才能工作；

分布式版本控制系统根本没有“中央服务器”。但在实际使用分布式版本控制系统的时候，通常也有一台充当“中央服务器”的电脑，但这个服务器的作用仅仅是用来方便“交换”大家的修改。

和 SVN 的详细比对参考：[GitSvnComparison](https://git.wiki.kernel.org/index.php/GitSvnComparsion)

## 一些区别

A summary of differences

- Git is much faster than Subversion，快
- Subversion allows you to check out just a subtree of a repository; Git requires you to clone the entire repository (including history) and create a working copy that mirrors at least a subset of the items under version control. 完整
- Git's repositories are much smaller than Subversions (for the Mozilla project, 30x smaller) 小
- Git was designed to be fully distributed from the start, allowing each developer to have full local control 完整权限
- Git branches are simpler and less resource heavy than Subversion's 轻
- Git branches carry their entire history 完整历史
- ~~Merging in Git does not require you to remember the revision you merged from (this benefit was obviated with the release of Subversion 1.5)~~
- Git provides better auditing of branch and merge events 审计
- Git's repo file formats are simple, so repair is easy and corruption is rare. 文件格式简单
- Backing up Subversion repositories centrally is potentially simpler - since you can choose to distributed folders within a repo in git 备份
- Git repository clones act as full repository backups 完整
- Subversion's UI is more mature than Git's 界面
- Walking through versions is simpler in Subversion because it uses sequential revision numbers (1,2,3,..); Git uses unpredictable SHA-1 hashes. Walking backwards in Git is easy using the "^" syntax, but there is no easy way to walk forward. 回退

## 分布式图解

![image](https://camo.githubusercontent.com/f66237df6febc060096bbc44ac137be244a9091b/687474703a2f2f6769742d73636d2e636f6d2f666967757265732f3138333333666967303130332d746e2e706e67)

分布式

![image](https://camo.githubusercontent.com/cad4b8f5fe2d8793c00c268749db09272e12c660/687474703a2f2f6769742d73636d2e636f6d2f666967757265732f3138333333666967303130322d746e2e706e67)

集中式

## 速度比较

由于 Git 只记录变化，很快，各操作的速度比较：

![](http://image.uczzd.cn/3832218279799585721.jpeg?id=0&from=export&width=720)

## 其他一些产品

- CVS作为最早的开源而且免费的集中式版本控制系统，直到现在还有不少人在用。由于CVS自身设计的问题，会造成提交文件不完整，版本库莫名其妙损坏的情况。同样是开源而且免费的SVN修正了CVS的一些稳定性问题，是目前用得最多的集中式版本库控制系统。
- 除了免费的外，还有收费的集中式版本控制系统，比如IBM的ClearCase（以前是Rational公司的，被IBM收购了），特点是安装比Windows还大，运行比蜗牛还慢，能用ClearCase的一般是世界500强，他们有个共同的特点是财大气粗，或者人傻钱多。
- 微软自己也有一个集中式版本控制系统叫VSS，集成在Visual Studio中。由于其反人类的设计，连微软自己都不好意思用了。
- 分布式版本控制系统除了Git以及促使Git诞生的BitKeeper外，还有类似Git的Mercurial和Bazaar等。这些分布式版本控制系统各有特点，但最快、最简单也最流行的依然是Git！


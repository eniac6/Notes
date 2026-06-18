## 便携版是什么意思 portable

不用安装，下载就用。

## .msi文件是什么？

windows专用的安装包。

和.exe 文件的区别：

.exe是可执行文件，可以是安装程序也可以是普通程序，但是.msi是专用的，更专业。

## ccswith 是什么

ccswith可以帮助你在claude code/codex等多个供应商之间 **一键切换**。

## 怎么接入deepseek

1.拿到deepseek的apikey,才能接入deepseek模型到codex.

2.取官网注册拿apikey.

## 供应商是什么东西

当然是模型的供应商， 比如codex的供应商是openai, cluade code的供应商是XX， 

然后deepseek也是一个模型供应商。



## typora 中输入 > ,表示引用

>出现这个小竖线



### 论文预印版

论文**正式投稿发布**前，或者同**行评审**前，就主动公开发布在 **预印版**平台。



![image-20260617135439426](assets/image-20260617135439426.png)



## UTF—8 和GBK 

utf-8:是一个国际通用的编码，同时支持，中文，英文，韩文等字符，

GBK： 是一个支持中文的编码。



## Git 推送到远程仓库

1 首先确保配置好git 环境（安装Git,配置用户名和邮箱、配置SSH Key方便本次远程连接github)、

测试是否登录github成功： 已经登录的用户信息

```
ssh -T git@github.com
```



### 1配置好你的本地仓库

2 进入到你的文件夹，输入：

````
git init #将本地的文件夹初始化为 git仓库
````

3 查看状态

```
git status
```

比如出现：  untracked files,   表示还未被追踪的文件

4 提交到本地仓库

```
git add .# 将当前目录下的所有文件提交到暂存区
git commit -m "messages" # 将暂存区的内容 提交到本地仓库
```

### 2新建远程仓库

直接在github 仓库中，new 一个。

### 3本地仓库和远程仓库建立关联

1添加一个远程仓库  ，并 起名为 origin.

```
git remote add origin git@github.com:eniac-ll/NOTES.git
```

参数：

git  remote : 表示 git 管理远程仓库的命令

add:  表示添加一个远程仓库

origin:  起一个别名



2 查看是否添加成功

```
git remote -v
```

参数解释：

-v  = --verbose (**详细模式**)  ：输出 详细的远程仓库信息，fetch  和 push



删除建立联系的远程仓库

```
git remote rm 别名
```



### 4推送到远程仓库



1.先查看默认分支

```
git branch
```

![image-20260618122242924](assets/image-20260618122242924.png)

\*  代表主分支 为 ：master

2.强制命名为 main

```
git branch -M main
```

因为 github 2020开始 ，将默认仓库主分支从master 改为main, 为了确保和远程仓库的分支保持一致，要改名为main.

3.推送到远程

```
git push -u origin main
```

参数：

-u ： 第一次推送时，必须要带上，代表 本地和远程 建立联系。

origin: 远程仓库

main : 远程仓库的main 分支



### 错误

(base) PS D:\桌面\Notes> git push -u origin main
remote: Permission to eniac6/Notes.git denied to eniac-ll.
fatal: unable to access 'https://github.com/eniac6/Notes.git/': The requested URL returned error: 403

记录一下：

背景： 在 

```
git push -u 
```

推送代码时，出现报错，

当前登录的用户 是eniac6, 但是他却显示是eniac-ll, 说明 https的缓存中登录的用户还是  eniac -ll, 所以我们需要清一下缓存。

或者我们添加远程仓库时，使用ssh 地址：

```
git remote add origin git@github.com:eniac-ll/NOTES.git
```

用https,会有缓存问题。

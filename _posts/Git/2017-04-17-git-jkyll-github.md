---
layout: post
title: Git Github jekyll,gem Liquid模板语言 Markdown
category: Git
tags:  Git
description: Git Github jekyll,gem Liquid模板语言 Markdown
---

Git是一款免费、开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。

字面意义：愚蠢或不开心的人

##git 常用命令清单
![](/posts/Git/git.png)

Workspace：工作区

Index / Stage：暂存区

Repository：仓库区（或本地仓库）

Remote：远程仓库

安装Git
要使用Git，第一步当然是安装Git了

新建代码库
>在当前目录新建一个Git代码库


    $ git init

>新建一个目录，将其初始化为Git代码库


    $ git init [project-name]

> 下载一个项目和它的整个代码历史


    $ git clone [url]
	//配置
>显示当前的Git配置


    $ git config --list

>编辑Git配置文件

    $ git config -e [--global]
>设置提交代码时的用户信息

	$ git config [--global] user.name "[name]"
	$ git config [--global] user.email "[email address]"
	//增加/删除文件
>添加指定文件到暂存区


    $ git add [file1] [file2] ...

>添加指定目录到暂存区，包括子目录


    $ git add [dir]

>添加当前目录的所有文件到暂存区


    $ git add .

> 添加每个变化前，都会要求确认
>对于同一个文件的多处变化，可以实现分次提交


    $ git add -p

>删除工作区文件，并且将这次删除放入暂存区


    $ git rm [file1] [file2] ...

> 停止追踪指定文件，但该文件会保留在工作区

    $ git rm --cached [file]

>改名文件，并且将这个改名放入暂存区

	$ git mv [file-original] [file-renamed]
	//代码提交

>提交暂存区到仓库区

    $ git commit -m [message]

>提交暂存区的指定文件到仓库区

    $ git commit [file1] [file2] ... -m [message]

> 提交工作区自上次commit之后的变化，直接到仓库区

    $ git commit -a

>提交时显示所有diff信息

    $ git commit -v

>使用一次新的commit，替代上一次提交
>如果代码没有任何新变化，则用来改写上一次commit的提交信息

    $ git commit --amend -m [message]

>重做上一次commit，并包括指定文件的新变化


	$ git commit --amend [file1] [file2] ...
	//远程同步

>下载远程仓库的所有变动

    $ git fetch [remote]

>显示所有远程仓库

    $ git remote -v

>显示某个远程仓库的信息

    $ git remote show [remote]

>增加一个新的远程仓库，并命名

    $ git remote add [shortname] [url]

>取回远程仓库的变化，并与本地分支合并

    $ git pull [remote] [branch]

>上传本地指定分支到远程仓库

    $ git push [remote] [branch]
>强行推送当前分支到远程仓库，即使有冲突

    $ git push [remote] --force

>推送所有分支到远程仓库

	$ git push [remote] --all     //分支管理

>列出所有本地分支

    $ git branch

>列出所有远程分支

    $ git branch -r

>列出所有本地分支和远程分支

    $ git branch -a

>新建一个分支，但依然停留在当前分支

    $ git branch [branch-name]

>新建一个分支，并切换到该分支

    $ git checkout -b [branch]

>新建一个分支，指向指定commit

    $ git branch [branch] [commit]

>新建一个分支，与指定的远程分支建立追踪关系

    $ git branch --track [branch] [remote-branch]

>切换到指定分支，并更新工作区

    $ git checkout [branch-name]

>切换到上一个分支

    $ git checkout -

>建立追踪关系，在现有分支与指定的远程分支之间

    $ git branch --set-upstream [branch] [remote-branch]

>合并指定分支到当前分支

    $ git merge [branch]

>选择一个commit，合并进当前分支

    $ git cherry-pick [commit]

>删除分支

    $ git branch -d [branch-name]

>删除远程分支

	gitpushorigin−−delete[branch−name]gitpushorigin−−delete[branch−name] git branch -dr [remote/branch]

 

远程仓库的默认名称是
	 origin

查看远程库信息，使用
	 git remote -v；

本地新建的分支如果不推送到远程，对其他人就是不可见的；

从本地推送分支，使用## git push origin branch-name ##，如果推送失败，先用## git pull ##抓取远程的新提交；

在本地创建和远程分支对应的分支，使用## git checkout -b branch-name origin/branch-name ##，本地和远程分支的名称最好一致；

建立本地分支和远程分支的关联，使用## git branch --set-upstream branch-name origin/branch-name ##；

从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。

#jekyll

搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门 

你先在本地编写符合Jekyll规范的网站源码，然后上传到github，由github生成并托管整个网站。

因此，只要你编写好符合jekyll规范的网站，上传到支持jekyll的网站，理论上都是可行的。

本地安装jekyll的意义在于：在本地就可以看到网站的效果。

 

	$ cd 文件夹名
	$ jekyll serve
cd你的目标文件夹，开启jekyll服务

 

jekyll标准的目录结构如下：
    .

    ├── _config.yml

    ├── _includes/

    |   ├── footer.html
	|   └── header.html
	├── _layouts/
	├── _posts/
	|   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
	|   └── 2014-04-26-what-is-Jekyll.md
	├── _drafts/
	|   └── begin-with-the-crazy-ideas.md
	├── _data/
	|   └── members.yml # yaml files(end with ".yml" or ".yaml")
	├── _site/
	└── index.html  


>gem

gem是ruby语言的包管理器，类似于npm之于node

    $  gem environment   // 可以查看gem ruby 的安装路径等情况

#Liquid模板语言
Liquid模板语言规定，输出内容使用两层大括号，单纯的命令使用一层大括号。

[教程文档](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers)

#Markdown

Markdown 的目标是实现「易读易写」。

兼容HTML，Markdown 的理念是，能让文档更容易读、写和随意改。HTML 是一种发布的格式，Markdown 是一种书写的格式。

[Cmd Markdown 简明语法手册](https://www.zybuluo.com/mdeditor?url=https://www.zybuluo.com/static/editor/md-help.markdown)

[Markdown 语法说明 (简体中文版)](http://wowubuntu.com/markdown/)
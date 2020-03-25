---
layout: post
title: learning notes Git
date: 2020-03-22 11:38:20 +0300
description: My learning notes of Git.
img: post-6.jpg
tags: [LearningNotes]
author: Dang Hao
---
Below is `git` learning notes of some commands:

git 设置账户
{% highlight ruby %}
git config --global user.name "gejiangwendi"
git config --global user.email "danghao0815@sina.com"
{% endhighlight %}

git 初始化
{% highlight ruby %}
git init
{% endhighlight %}

克隆一个git库
{% highlight ruby %}
git clone git@github.com:gejiangwendi/gejiangwendi.github.io.git
{% endhighlight %}

创建并切换到新的分支,并关联远程的dev分支
{% highlight ruby %}
git checkout -b dev origin/dev
{% endhighlight %}

从远程dev分支下载代码
{% highlight ruby %}
git clone -b dev http://github.com/gejiangwendi/blog.git
{% endhighlight %}

分支 其它命令
{% highlight ruby %}
git branch #查看分支
git branch <name> #创建分支
git checkout <name> #切换分支
git checkout -b <name> #创建并切换分支
git merge <name> #合并某分支到当前分支
git push <remote-name> <branch-name> #从本地推送分支
{% endhighlight %}

查看log日志
{% highlight ruby %}
git log --name-status -1
{% endhighlight %}

{% highlight ruby %}
{% endhighlight %}

{% highlight ruby %}
{% endhighlight %}

提交流程
{% highlight ruby %}
git add . #包含所有变动
git add -u #不包含未跟踪到文件
git commit -m "modify"
git commit --amend #提交失败后再次提交（公司 review）
git push origin
{% endhighlight %}

Please click [Learn Git] for more info.

[Learn Git]: https://www.runoob.com/git/git-tutorial.html

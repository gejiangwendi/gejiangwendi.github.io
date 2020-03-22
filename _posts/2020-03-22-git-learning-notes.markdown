---
layout: post
title: git learning notes
date: 2020-03-22 11:38:20 +0300
description: My learning notes of Git.
img: post-6.jpg
tags: [LearningNotes]
author: Dang Hao
---
Below is `git` learning notes of some commands:

{% highlight ruby %}
# git 设置账户
git config --global user.name "gejiangwendi"
git config --global user.email "danghao0815@sina.com"

#git 初始化
git init

#克隆一个git库
git clone git@github.com:gejiangwendi/gejiangwendi.github.io.git

#编辑后提交流程
git add .
git commit -m "modify"
git push origin
{% endhighlight %}

-End-

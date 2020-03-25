---
layout: post
title: vim learning notes
date: 2020-03-22 14:38:20 +0300
description: My learning notes of vim edit tool.
img: post-6.jpg
tags: [LearningNotes]
author: Dang Hao
---
This is my `vim` learning notes: 

{% highlight ruby %}
# 打开一个文件
vim main.c

#other commands:
i       #进入编辑模式
esc     #退出编辑模式
:wq     #保存并退出vim
15G     #跳转到第15行
v       #选择
N/n     #查找 上一处，下一处
p       #粘贴
u       #撤销
dd      #删除 光标所在行
y       #拷贝
yy      #拷贝 光标所在行
10yy    #拷贝 光标向下10行
J       #合并 当前与下一行
o       #分段
?/      #搜索

#寻找 word1 字符串，并将该字符串取代为 word2 ！(gc需要confirm)
:1,$s/word1/word2/g 或 :%s/word1/word2/g
:1,$s/word1/word2/gc 或 :%s/word1/word2/gc

home/end/pageup/pagedown
{% endhighlight %}

Please click [Learn Vim] for more info.

[Learn Vim]: https://www.runoob.com/linux/linux-vim.html

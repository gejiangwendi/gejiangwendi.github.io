---
layout: post
title: learning notes Linux
date: 2020-03-22 14:38:20 +0300
description: My learning notes of Linux.
img: post-6.jpg
tags: [LearningNotes]
author: Dang Hao
---
This is my `Linux` learning notes: 

{% highlight ruby %}
chmod 777 main.o #获取文件权限
rm -r -f test #删除文件夹
{% endhighlight %}

文件传输
{% highlight ruby %}
取文件#???
tftp -r main.o -l /home/usrdata/app/app.o -g 192.192.192.100 && sync

cd /  #将/目录内文件取出到pc本机tftp软件所在的目录
tftp -l test.txt -p 192.192.192.35 #本机ip（服务器）
{% endhighlight %}

获取文件 user=ssp 服务器ip   文件名
ftpget -u ssp 192.168.0.2 lxImage lxImage

CRT脚本
{% highlight ruby %}
[test.vbs]:
#$language = "VBScript"
#$interface = "1.0"
Sub main
  Dim connect_port
  Dim subcard_num
  Dim WshShell
  Dim result
  times = "1000000"
  crt.Screen.Synchronous = True
  Set WshShell = CreateObject("wscript.Shell")
  'do
    crt.Screen.WaitForString "hit any key to continue."
    crt.Screen.Send "0" & VbCr
    crt.Sleep 1000
  'loop while(1)
  crt.Screen.Synchronous = False
End Sub
{% endhighlight %}

{% highlight ruby %}
{% endhighlight %}

Please click [Learn Linux] for more info.

[Learn Linux]: https://www.runoob.com/linux/linux-tutorial.html

---
layout: post
title: gcc learning notes
date: 2020-03-22 10:38:20 +0300
description: My learning notes of GCC.
tags: [LearningNotes]
author: Dang Hao
---
Below is `gcc` learning notes of some commands:

{% highlight ruby %}
#gcc编译
gcc main.c -o ./out/main.o
./out/main.o

#如果没有执行权限，增加权限
sudo chmod 777 main.o
chmod +x sdk_compile.sh

#gcc编译 .a库
gcc -c test1.c 
gcc -c test2.c 
ar -r test.a test1.o test2.o

#gcc编译 包含.a库
gcc -o main main.c test.a 
./main 
{% endhighlight %}

Below is a `gcc compile example` :

编译目录结构如下：
{% highlight ruby %}
---test dir
   ---sdk
      ---*.c
   ---out
   ---main.c
   ---sdk_compile.sh
{% endhighlight %}

以下为编译脚本sdk_compile.sh内容：

{% highlight ruby %}
# 清除旧版本
rm ./out/source/*.o
rm ./out/lib.a
rm main.app
printf 'delete old output files ... ...\n\n'

i=0

# 编译sdk文件夹内的所有.c文件
for file in ./sdk/dh_*.c; do
    let "i=i+1"
    printf 'compile %s ...\n' "$file"
    gcc -c $file -o ./out/source/file_$i.o
    sleep 0.005   # 延时 5 ms
done

printf '... ...\n'
# 链接所有.o文件生成lib.a库
ar -r ./out/lib.a ./out/source/file_*.o

# 编译main.c 链接库 生成可执行文件
gcc -o main.app main.c ./out/lib.a 
printf '\nok! new main.app is created.\n\n'
{% endhighlight %}

-End-

Check out [my lib][danghao-github] for more info.

[danghao-github]: https://github.com/gejiangwendi

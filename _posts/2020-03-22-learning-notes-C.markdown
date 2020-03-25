---
layout: post
title: learning notes C
date: 2020-03-22 14:38:20 +0300
description: My learning notes of C language.
tags: [LearningNotes]
author: Dang Hao
---
This is my `C` learning notes: 

算法-间插打散
{% highlight ruby %}
tar = (ori%80)*2 + ori/80; #打散
ori = 0,1,2,3 ==> tar = 0,2,4,6
ori = (tar/2) + (tar%2)*80; #恢复
tar = 1,3,5,7 ==> ori = 80,81,82,83
{% endhighlight %}

写寄存器
{% highlight ruby %}
*((__volatile__ WORD32*)ulRegAddr) = ulRegVal;
{% endhighlight %}

&符号-变量地址
{% highlight ruby %}
void r(uint32 addr, uint32* val);
uint32 addr,data;
r(addr,&data);
{% endhighlight %}

三目运算符
{% highlight ruby %}
max=a>b?a:b;
a>b?(max=a):(max=b);
{% endhighlight %}

打印接口-宏定义
{% highlight ruby %}
#define PRINT_C(fmt,args...)\
{\
    if(g_print_ctrl_en == 1)\
    {\
         printf(fmt,##args);\
    }\
}
{% endhighlight %}

易错点
{% highlight ruby %}
判断条件尽量多用括号
if(0x1 == ((x>>(y%80))&0x1))
非判断语句，不能额外用括号，否则会当作逻辑符号计算；
{% endhighlight %}

间接读写
{% highlight ruby %}
cmd_addr=0x400 val_addr=0x403
间接地址0x1700写值0x88
w 0x403 0x88
w 0x400 0x1700
读取间接地址0x1700
w 0x400 0x1700+0x8000
r 0x403
可以封装成：
IndBitRead(base_addr,off_addr,start_bit,end_bit,*data)
IndBitWrite(base_addr,off_addr,start_bit,end_bit,data)
{% endhighlight %}

参数校验机制
{% highlight ruby %}
#define assert(condition,err_code) if(!(condition)){printf("WARNING==>0x%08x\t%s:%d\n",err_code,_FILE_,_LINE_);return err_code;}
#define err_base 0
#define invalid_para err_base+1 #无效参数
#define unknown_err err_base+2 #未知错误
#define null_ptr err_base+3 #空指针

int print_age(int age)
{
    int ret = err_base;

    assert(age>0,invalid_para);

    printf("age = %d\n",age); 

    return ret;
}
{% endhighlight %}

文件操作
{% highlight ruby %}
FILE *file_of_sth;
file_of_sth = fopen("test.txt","w+");
fclose(file_of_sth);
{% endhighlight %}

{% highlight ruby %}
{% endhighlight %}

Please click [Learn C Language] for more info.

[Learn C Language]: https://www.runoob.com/cprogramming/c-tutorial.html

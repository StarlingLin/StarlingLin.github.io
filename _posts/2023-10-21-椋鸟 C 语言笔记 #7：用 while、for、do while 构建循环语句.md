---
date: 2023-10-21 13:44:44
layout: post
title: 椋鸟C语言笔记#7
subtitle: 用 while、for、do while 构建循环语句
description: 萌新的学习笔记,写错了恳请斧正。
image: https://res.cloudinary.com/dm7h7e8xj/image/upload/v1559820489/js-code_n83m7a.jpg
optimized_image: https://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,w_380/v1559820489/js-code_n83m7a.jpg
category: code
tags:
  - blog
  - C
  - programme
  - while
  - for
  - do while
  - 循环
  - 语句
  - 笔记
author: StarlingLin
---
萌新的学习笔记,写错了恳请斧正。

#### while

C 语言中有 3 种循环语句,while 便是其中一种:

```
while (表达式)
    语句;
//如果循环体想包含更多的语句,可以加上大括号
```

当表达式为真(**非零**时)重复执行语句直到表达式为假(**0**)

具体执行方式:

![](https://img-blog.csdnimg.cn/6afade74665b46b4870795d658e5a899.png)

例子:

```
#include <stdio.h>
int main()
{
    int i = 1;  //初始化变量
 
    while(i <= 114514)    //判断循环变量
    {
        printf("%d ", i);  //循环体
        i++;   //调整循环变量
    }
    return 0;
}
```

这就能打印 1~114514 的所有数字了

但是,当我们写的代码比较长时

用 while 就会导致循环变量的**初始化 - 判断 - 调整**相隔过长

这就不方便代码的书写、查看与维护

所以引入了 for 循环

#### for

for 循环是三种循环中最常用的,结构如下:

```
for(表达式1; 表达式2; 表达式3)
    语句;
//如果循环体想包含更多的语句,可以加上大括号
```

for 循环的三个表达式是有讲究的

*   表达式 1 用于循环变量的初始化
*   表达式 2 用于循环结束条件的判断
*   表达式 3 用于循环变量的调整

![](https://img-blog.csdnimg.cn/ff1c0f2f75c64fcb9418258f14bd7507.jpeg)

整个循环过程中表达式 1 初始化部分只执行了一次

剩下来便是表达式 2、循环体、表达式 3 在不停循环

举个例子:

```
#include <stdio.h>
 
int main()
{
    int i = 0;
    
    for(i=1; i<=114514; i++)
    {
        printf("%d ", i);
    }
    
    return 0;
}
```

这同样也是打印 1~114514 的所有数字

#### do while

do while 是最少见的一种循环形式,用法如下:

```
do
    语句;
while (表达式);
```

它和上面两种循环有显著区别:

while 和 for 都是**先判断**,条件满足就进入循环

而 do while 是**先循环**,一轮结束后判断,不满足则退出循环

![](https://img-blog.csdnimg.cn/f339fa5c4b554af9a660fc512dfbf98d.png)

举例:

统计非负整数位数

```
#include <stdio.h>
 
int main()
{
    int n = 0;
    scanf("%d", &n);
    int cnt = 0;
 
    do
    {
        cnt++;
        n = n / 10;
    }
    while (n);
    
    printf("%d\n", cnt);
 
    return 0;
}
```

这里用 do while 比用另外俩好一点

因为 n 即使是 0,也应该统计一位
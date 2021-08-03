---
title: linux学习一
tags:
  - linux
categories:
  - 学习手册
abbrlink: 18881
date: 2021-07-26 18:03:15
---
# 关机重启
{% meting "3986040" "netease" "song" "theme:#555" "mutex:true" "listmaxheight:340px" "preload:auto" %}
## 1.关机命令 ： shutdown

正确的关机流程为：**sync > shutdown > reboot > halt**

**不管是重启系统还是关闭系统，首先要运行 sync 命令，把内存中的数据写到磁盘中。**

1. 将数据由内存同步到硬盘中 ： `sync`
2. 立马关机 `shutdown –h now`
3. 系统会在今天20:25关机 `shutdown –h 20:25`
4. 系统立马重启 `shutdown –r now`
5. ` `shutdown –r +10 `系统十分钟后重启 reboot 就是重启，等同于  `shutdown –r now`

---

{% codeblock lang:bash %}
sync 将数据由内存同步到硬盘中。
 
shutdown 关机指令，你可以man shutdown 来看一下帮助文档。例如你可以运行如下命令关机：
 
shutdown –h 10 ‘This server will shutdown after 10 mins’ 这个命令告诉大家，计算机将在10分钟后关机，并且会显示在登陆用户的当前屏幕中。
 
shutdown –h now 立马关机
 
shutdown –h 20:25 系统会在今天20:25关机
 
shutdown –h +10 十分钟后关机
 
shutdown –r now 系统立马重启
 
shutdown –r +10 系统十分钟后重启
 
reboot 就是重启，等同于 shutdown –r now
 
halt 关闭系统，等同于shutdown –h now 和 poweroff
{% endcodeblock %}

{% codeblock lang:c++ %}
// s[]是长文本，p[]是模式串，n是s的长度，m是p的长度

// 求模式串的Next数组：
for (int i = 2, j = 0; i <= m; i ++ )
{
    while (j && p[i] != p[j + 1]) j = ne[j];
    if (p[i] == p[j + 1]) j ++ ;
    ne[i] = j;
}

// 匹配
for (int i = 1, j = 0; i <= n; i ++ )
{
    while (j && s[i] != p[j + 1]) j = ne[j];
    if (s[i] == p[j + 1]) j ++ ;
    if (j == m)
    {
        j = ne[j];
        // 匹配成功后的逻辑
    }
}
{% endcodeblock %}
---

## 1.2 重启命令 ：reboot

---

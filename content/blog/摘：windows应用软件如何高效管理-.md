---
title: 摘：windows应用软件如何高效管理 
date: 2025-04-02T10:28:21.060Z
---

From https://ddw2019.com/190

windows C盘的目录结构：

![1743588890815.png](https://github.com/YCChan2001/tinymind-blog/blob/main/assets/images/2025-04-02/1743588911509.png?raw=true)

我们的应用程序会安装其中三个位置。

Program File（x86）：为所有用户安装的32位软件的安装目录

Program File：为所有用户安装的64位软件的安装目录

User/用户名/AppData/Roaming：为个人用户安装的软件的目录。

但是有非常多的软件不遵守操作规则，最后把我们的文件系统整理的一团乱麻。

有一次，从网络上了解到软件的管理方式（找不到来源了都）。感觉挺好，对于非常多的软件就按照这种方法来安装，具体操作如下：

第一，在C盘下建立一个“Software文件夹”

第二，将软件分为两种：一种是常规软件（如Office、Endnote、OriginLab等，修改文件夹可能会产生非常大的影响），安装到默认的目录下；一种是非常规软件（如7zip、Snipaste等，修改后影响不大，安装到“Software”中

Note: Software文件夹中的软件，使用形如“014 Youdao”这类编码，能够自然排序。而且三位数字，够我们安装999个了都。不硅谁会安装999个软件呀。（评论区的dousha99大佬指点：在路径名中引入空格是十分危险的行为，如果可以的话，大家可以不用加上面的哪个空格，直接用“014Youdao”）

![1743589304598.png](https://github.com/YCChan2001/tinymind-blog/blob/main/assets/images/2025-04-02/1743589319743.png?raw=true)

![1743589354465.png](https://github.com/YCChan2001/tinymind-blog/blob/main/assets/images/2025-04-02/1743589365453.png?raw=true)

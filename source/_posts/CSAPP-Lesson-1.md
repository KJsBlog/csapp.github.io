---
title: CSAPP Lesson 1
date: 2023-05-07 15:56:10
tags: ['CSAPP']
id: study
categories: CSAPP
---

# **Gist of Lesson 1**
---
*摘要：这是笔者正式学习CMU的CSAPP教程的过程总结，是属于<font color = #ffa500 face ="楷体" size = 5>边学边看</font>的方式进行写作。看看学完之后的自己和学之前的自己再操作系统上的理解有什么改变和提高，同时记录下初学者在进行学习时最开始的感受，以初学者的视角，记录下这门课程的真是学习经历*

## Lesson 1
今天看CSAPP的第一课，虽然中间的大部分时间是讲学术诚信，对于我个上网课的没什么启发，但其中教授抛出的一个问题还是很适合我的思考，这里写下来，希望在学成之后对这个问题能有更好的理解。
1. 问题：

```C
    void copyij(int src[2048][2048]
                int dst[2048][2048])
{
    int i,j;
    for(i = 0 ; i< 2048 ; i++)
        for(j = 0 ; j < 2048 ; j++)
            src[i][j]=dst[i][j];
} 
```
```C
    void copyij(int src[2048][2048]
                int dst[2048][2048])
{
    int i,j;
    for(j = 0 ; j< 2048 ; j++)
        for(i = 0 ; i < 2048 ; i++)
            src[i][j]=dst[i][j];
} 
```
2. 分析：

对于这两个小函数，看似在实现的逻辑上是一致的：都是把dst[i][j]值赋值给src[i][j]的值，但是在具体的代码实现上。却是相差了20倍!

![图片来自B站UP主 刘迪望 的转载视频](./pictures/Lesson%201%20question.png)

[*<font size=1>图片来自B站UP主 刘迪望 的转载视频</font>*](https://www.bilibili.com/video/BV1iW411d7hd/?spm_id_from=333.337.search-card.all.click)

---

![图片来自B站UP主 刘迪望 的转载视频](./pictures/Lesson%201%20explanation.png)

[*<font size=1>图片来自B站UP主 刘迪望 的转载视频</font>*](https://www.bilibili.com/video/BV1iW411d7hd/?spm_id_from=333.337.search-card.all.click)

---

3. 总结及个人猜想：

<font size = 2>总结：Lesson 1是开课的第一节，大概地讲授了课程的重要性以及课程的大概安排，其中的这个问题让我产生了思考，但因为写下这些的时候，笔者仅仅是刚开始的小白，而这也只是一个现在自己的猜测，同时也是写给未来的自己看的。所以在语言以及思考上都是有不足的。

<font face="楷体">~~个人的猜想：笔者个人认为之所以产生这样的差距是因为二维数组在储存方式上的特点所导致的:二维数组的储存是先固定第一位再排序第二位（即先固定array[i][j]中的i，然后再进行j的输入）。~~</font></font>

![](./pictures/Answer%20about%20array.png)
<font face ="隶书" size = 1>这个是来自我的猜想，看看学成归来会有什么新的体会以及修正</font>
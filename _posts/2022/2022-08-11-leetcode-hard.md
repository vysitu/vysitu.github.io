---
layout: post
title: LeetCode Hard 级别问题
categories: Learn
description: Thoughts
keywords: LeetCode
---

这两天开始逐渐把 LeetCode 里面 Hard 级别的问题更新到lcmax库，并且尝试逐渐解决。

说实话，大多数题目我目前的水平只能搞清楚他们要什么，做起来就很难找到着手点。

之后可能要先看别人的笔记学习一下再回头来做这些题目。

WRF-Helper 今天获得了新功能，防止设定 domain 大小的时候没有设置成 nx+1 像素。
同时我还添加了投影坐标系的设置部分，免得默认的忘记修改。中国全区域的兰伯特投影默认中央经线是 110 度，两个参照纬度线是 25 和 47 ，但是实际操作的时候这三个可能都要改，免得小区域做计算的时候图像变形幅度过大。

在把 WRF 部署到 K8S 的时候主要面临的问题是异步处理需要设置的 worker 相关问题和制定核心数量分配（都在 namelist.input）。但是解决了那些问题之后还是会出现无法指定过多 CPU 的情况。

非传统稳定同位素课程，有一个老师叫刘耘，很厉害。
[核体积效应的讲解](https://www.bilibili.com/video/BV1ni4y1M7uv)


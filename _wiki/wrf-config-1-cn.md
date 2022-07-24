---
layout: wiki
title: WRF 配置 Part 1 CN
categories: [WRF, Docker]
description: WRF Configuration
keywords: WRF, Docker
---

# 我GitHub的WRF配置相关页面
[WRF-Helper](https://github.com/vsitu/wrf-helper)

# 配置的几个部分
1. WRF 运行环境
2. WRF 和 WPS 代码
3. WRF 软件
4. WPS 软件

## WRF 运行环境
我使用的运行环境是基于 Dave Gill 配置的运行环境以及制作的 docker 镜像。   
目前使用的是第十五个版本 [fifteenth try](https://hub.docker.com/r/davegill/wrf-coop/tags)。

## WRF 和 WPS 代码
WRF 软件在 Dave Gill 的 GitHub 页面上能找到。他是也是去官方 GitHub 那边 fork 过来的。我建议去官方[官方 GitHub 页面](https://github.com/wrf-model/WRF) 获取最新的WRF。       
[WPS 官方 GitHub 页面](https://github.com/wrf-model/WPS) 也在同一个用户下面。  

基于某些地区和某些时候网络不稳定的情况，我是建议至少在制作 docker 镜像的时候直接把 WRF 和 WPS 代码拉下来放到镜像里。更进一步的话，如果只使用某些特定功能，我们可以把 WRF 和 WPS 在制作镜像的时候都编译好，这样镜像启动了就可以使用。

## WRF 软件
我使用的编译用脚本在 Dave Gill 的 [GitHub 页面](https://github.com/davegill/SCRIPTS)上可以找到。       
其实个人是可以一步步编译WRF的，步骤也不多, 但我在服务器被意外重置之后 (run level 5 -> 2) 遇到了几次 Noah-MP 错误，就暂时没有深入研究，大体上改用了 Dave Gill 的配置辅助脚本。    

## WPS 软件
WPS (WRF Pre-Processing System) 应该在 WRF 配置好之后在安装。      
WPS 的配置和编译比 WRF 更加直观简洁。用户只需要在配置的时候设置运行模式 (例如 '3' 是 gfortran-dmpar) 然后在编译的时候设置需要的处理器数量就行。 

## 注意
如要进行更复杂的配置，请参照 WRF 和 WPS 的 [官方用户手册](https://www2.mmm.ucar.edu/wrf/users/docs/user_guide_v4/contents.html).
---
layout: wiki
title: R-Tidyverse
categories: Tools, Learn, Code
description: 在R中使用Tidyverse
keywords: R
---

R 中使用 Tidyverse 可以大大方便数据的处理。Tidyverse 里面的工具对于表格类数据的辅助效果类似于 Python 的 Pandas，但是它还包含了很多其他的工具，而且互相之间兼容性比较好，所以综合使用起来可以大大节省处理和可视化数据需要的时间。

Tidyverse 常见的工具：
| 名字 | 效果 |
| ------ | ------ |
| ggplot2 | 画图 |
| dplyr | data manipulation |
| tidyr | 清理数据 |
| readr | 读取各类表格 |
| stringr | 操作字符串 |
| forcats | 操作因素（factors）类数据 |
| lubridate | datetime 日期类数据 |

 %>% 符号就是 R 里面的 pipe，把不同的步骤连起来，就可以把前一个函数的输出作为后一个的输入（第一个参数），这样可以让代码更易写易读。

 
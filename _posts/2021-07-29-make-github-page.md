---
layout: post
title: 配置github page
categories: Github
description: 大概配置情况记录
keywords: Github, Blog, Jekyll
---

今天尝试了配置Github的页面。
使用的是mzhuang的主题，挺符合预期的。

现在的难点就是添加Gitalk。按照网上的配置方法似乎应该能用，不过我自己好像测试不了。

-----
测试Gitalk成功之后，发现问题在于Github里面OAuth的配置。

Homepage URL 要设置成保存（用Issue来记录）评论的那个repository，且网址后面不要跟io之类的后缀，直接就是"https://github.com/$username/somerepo"这样的格式。   

Authorization callback URL 要设置成博客的那个网站的URL！我设置的ntsack47.github.io（https）。这么配置就没问题了。


-----
配置网址的时候有几个部分。

- 首先是在_config.yml里面添加url:...的选项。
- 然后在网站文件的根目录添加CNAME文件（无需后缀），里面写上新的网址，不需要讲https。这一步也可以在github page的配置页面完成。
- 再之后就是去DNS那里添加条目，CNAME和A都要。CNAME就是url转到博客url，没什么说的，A的话就是指定IP。我是去NameSilo搞的，添加了A用的ip地址网上能搜到现成的，也可以在本地命令提示符之类的工具里面ping博客网站的url，就可以得到一个ip了。
- - 之前就是没有添加A记录才没弄成功。没有成功的话在github page页面上能看到DNS转发设置失败之类的提示。




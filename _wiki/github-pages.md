---
layout: wiki
title: GitHub Page 做博客
categories: GitHub
description: GitHub Page
keywords: GitHub Page
---

> Ruby 3.0 默认是没有webrick的，用gem install webrick，然后再在网站的Gemfile里面添加  gem 'webrick' 即可

Github Page配置整体流程   
1. 新建“用户名.github.io”的repo，设置该repo为github page。   
2. 在本地安装jekyll套件，可以用安装包直接装Ruby，是和devkit一起装的。安装好之后界面会提示是否运行ridk install，选择“是”，运行之，之后MSYS2的安装界面选择1, base installation    
3. 如果是在墙内，需要切换安装源到https://gems.ruby-china.com/。墙外请忽略。gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/ 切换安装源 gem sources -l 查看版本   
4. 打开新的cmd窗口，切换到网站所在的目录（cmd里面切盘是E:然后再cd），运行gem install jekyll bundler，安装jekyll和bundler。完成后在cmd运行jekyll -v检查安装结果和版本。   
5. bundle config mirror.https://rubygems.org https://gems.ruby-china.com 切换bundle源   
6. 下载喜欢的主题，我最开始选的是minimal mistakes。这个主题本身是一个ruby gem，直接运行gem "minimal-mistakes-jekyll"这个命令即可。   
7. 把github上面那个repo生成的东西下载到本地（git clone）。   
8. 编辑_config.yml

    1. 声明主题（theme），然后运行bundler install，但是在上传到Github的时候不要声明主题！install之后主题文件就有了，不需要多次生成，所以之后本地调试不声明主题也没关系。
    2. 添加一系列插件plugins:
        1.   - jekyll-paginate
        2.   - jekyll-sitemap
        3.   - jekyll-gist
        4.   - #jemoji
        5.   - jekyll-feed
        6.   - jekyll-include-cache
    3. 关键是最后两个。导入jemoji会导致错误，所以我给注释掉了。
    4. 设置作者（author）信息，和默认页面排版（defaults）。
9. 大部分配置都可以参照https://mmistakes.github.io/minimal-mistakes/docs/configuration/的configuration和layouts来设置。
10. 把不同文章放在_posts/下面的不同子文件夹里，只要文章开头YAML添加了category信息，就可以在对应的category里面找到。
11. _data/文件夹要手工添加。_data/navigation.yml包含网页顶部菜单信息，英文叫做Masthead，“标头”。
12. 通往子文件夹的链接直接写成/folder/thing.html之类的就可以了


换码志的主题，直接去 http://mazhuang.org ！
那个比较简单，不过转换主题的时候需要一些调整。   
从github下载的网站文件可能版本比较旧了   
删除Gemfile.lock，然后运行：   
bundle update jekyll   
bundle install   
bundle exec jekyll serve   
之后每个命令前面都加上bundle exec   
jekyll clean清除缓存可能可以解决一些问题   
cannot load的错误可能是缺少包或者包有问题，先gem uninstall然后gem install就行   
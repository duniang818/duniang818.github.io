---
layout:     post
title:      "Windows 10 借助Jekyll + GitPage 搭建个人Blog网站"
subtitle:   "Blog主题借用huxblog-boilerplate-master"
date:       2018-10-16 15:00:00
author:     "Duniang"
header-img: "img/about_bg.jpg"
tags:
    - Blog, Jekyll, GitPage
---

# [GitHub page](https://pages.github.com/)
照着官网上的步骤，傻瓜似的安装完成
需要更加方便的编辑博客，并且具有一定的网页美观效果，还需要借助jekyll
# 安装jekyll
- [jekyll installer](https://jekyllrb.com/docs/installation/windows/)
- 点击RubyInstaller for Windows， 下载Ruby+Devkit 2.4.X 
- 双击安装，记得勾选将ruby添加到环境变量中
- 后面让选择安装mssys,任意选择，1很快，2很慢，慢慢等待安装完成
- 安装完成后从windows的开始按钮打开 *start command prompt with ruby*
- 再运行命令安装gem在ruby的命令行
```
gem install jekyll bundler
安装成功后，检查jekyll是否安装成功
jekyll -v
ruby -v
```
- 创建自己的博客
```
jekyll new myblog
- 一定要进入博客的目录，否则会报权限错误
cd myblog
bundle exec jekyll serve --incremental
or jekyll serve
```

- http://127.0.0.1:4000/ 启动成功，就可以打开浏览器查看了
- 注意有时候chromium浏览器打不开，用windows edge可以打开
# 配置config.yml 文件，形成自己的blog信息页面

```
title: Duniang
header-img:img/header.jpg
email: wangyumeiej@gmail.com
description: >- # this means to ignore newlines until "baseurl:"
  Write an awesome description for your new site here. You can edit this
  line in _config.yml. It will appear in your document head meta (for
  Google search results) and in your feed.xml site description.
baseurl: "" # the subpath of your site, e.g. /blog
url: "https://duniang818.github.io" # the base hostname & protocol for your site, e.g. http://example.com
weibo_username:     度娘818
zhihu_username:     度娘818
github_username:    duniang818
twitter_username:   duniang
```
# 编写和发布博客
Jekyll对于博文，都是要求放在_posts目录下面，同时对博文的文件名有严格的规定，必须保持格式YEAR-MONTH-DAY-title.MARKUP，通常情况下，咱们采用推荐的Markdown撰写博文，基于该格式，本博文的文件名为2017-08-15-how-to-setup-your-github-io-blog.md。

```
git add _posts/2017-08-15-how-to-setup-your-github-io-blog.md
git commit -m "Add how to setup your github.io blog"
git push mine master
```
# 查看编码
ruby -e 'puts Encoding::list.join("\n")'
# 借助[jekyll theme](https://github.com/Huxpro/huxpro.github.io#analytics) 模板创建博客
- 在运行完jekyll new duniang_blog命令后，会形成新的目录，cd到新目录
- 然后修改作者的index.md里面的home为page
- 修改_config.yml文件
- 每天修改一点开始完善自己的blog了
- gem install jekyll-paginate
- [disqus site](https://disqus.com/admin/moderate/#/pending)
- 推荐引用从https://github.com/Huxpro/huxblog-boilerplate直接copy的页面样式
将此库clone到你的github.io的repo路径下，然后修改一下_config.yml文件，在git add,commit,push到你的库，就可以远程用浏览器http://duniang818.github.io查看效果了
# jekyll use Liquid template language语法
[Liquid](https://shopify.github.io/liquid/basics/introduction/)
[Jekyll of Liquid](https://jekyllrb.com/docs/variables/)



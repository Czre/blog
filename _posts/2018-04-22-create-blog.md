---
layout: post
title:  "记：使用Jekyll在GitPages搭建博客~"
date:   2018-04-22 01:13:17 +0800
categories: 日记
---
---
> 讲在前面的话，这算是我写的第一篇博客，有很多地方都还不熟悉。<br>
这篇博客主要是记录我使用GitPages搭建Jekyll的过程，以及其中遇到的一些问题和解决办法。

` 本人环境：MacOS、brew、git、gem`
# 使用GitHub Pages搭建博客
## 1. 使用Github创建GitHub Pages项目
> 适用于没有服务器和域名的情况下 <br> 
 (如果有账号的可以跳过这一步)

[GitHub](http://www.github.com/)
1. 首先需要创建GitHub账号。

    pick a username？ 创建一个属于你的用户名<br>
    you@example.com？输入你的邮箱地址<br>
    Create a password？这个就是密码咯～
2. 使用刚注册好的账号登陆GitHub。
    * 在右上角\"+\|"点击\"New Repository\"<br>
    * 创建一个基于GitHub用户名的项目 <br>
    > 譬如我的GitHub名字是\"czre\"，所以我的github地址为\"www.github.com/Czre\" <br>
    而这个项目名字为\"blog\"，所以我的项目地址为\"www.github.com/Czre/blog\"
    
    * 一般都是创建的public（公开的，所有人都可以访问到的）项目，private（私有是收费的）<br>
    * \"Descrption\"描述。随便写点什么的介绍～<br>
    * \"Initialize this repository with a README\"大概意思：是否初始化一个README.md文件。可以勾选，也可以后期手动创建该文件。
    > PS：这个文件的内容将会在你的项目首页显示，也是本文所使用的一种书写格式，Markdown，通常以.md或.markdown结尾的文件格式。<br>
    
3. 点击\"Create Repository\"创建项目。
4. 此时会进入你的项目首页，项目地址为\"www.github.com/用户名/项目名\"
5. 点击\"Settings\"
6. 找到\"Github Pages\"，将\"Source\"中的\"None\"改为\"master branch\"并点击\"Save\"。
> 这一步是将你的项目的\"master branch\"分支设置为Github Pages，如果有问题需要创建\"gh-pages\"分支并重新指定会解决。
## 2. 安装Git并拉取分支，部署Jekyll
1. 安装Git
    > 这一步的教程略过 安装过程可以百度 关键词 git安装 git教程
2. 拉取代码

    在项目页，找到原谅色按钮\"clone or download\"复制链接，通常为\"https://github.com/用户名/项目名.git\"。<br>
    调出命令行：
    * windows为win键+R键，输入cmd<br>
    `git clone https://github.com/用户名/项目名.git`
    > 使用git命令克隆项目代码
3. 安装Ruby
    * window安装:[Ruby](https://rubyinstaller.org/)
    * mac使用brew安装<br>
    `brew install ruby`
    * linux使用相应的yum(centOS) or apt-get(ubuntu) install ruby<br>
    `yum install ruby`<br>
    `apt-get install ruby`
    
    笔者这里使用的mac系统，所以使用brew安装，附上brew安装链接
    
    `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`<br>
    
    [RubyGems](https://rubygems.org/pages/download)
    ```
     //在上面给出的链接中下载RubyGems插件 
     //在Terminal中  
     cd yourpath to RubyGems //跳转到你解压的位置，注意是在ruby-gems文件夹下
     ruby setup.rb // 执行命令
     ```
 4. 使用gem安装jekyll
    `gem install jekyll` 
 5. 配置Jekyll
 
    [Jekyll Themes](http://jekyllthemes.org/)找到自己喜欢的模板。<br>
    将下载好的模板复制到从git中clone的项目文件夹下。<br>
    修改_config.yml文件<br>
    > PS：重要，将plugins:[]修改为plugins: [\'jekyll-paginate\']
    
    具体教程:[Jekyll](https://jekyllrb.com/)<br>
    ```
    cd jekyll path // 移动到你的jekyll项目下，也就是你从git里clone下来的项目
    jekyll serve // 启动服务，默认链接地址\"http:localhost:4000\"
    ```
    期间遇到的一个问题：
    ```
    Configuration file: /Users/czre/git/blog/_config.yml
           Deprecation: The 'gems' configuration option has been renamed to 'plugins'. Please update your config file accordingly.
      Dependency Error: Yikes! It looks like you don't have jekyll-paginate or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. The full error message from Ruby is: 'cannot load such file -- jekyll-paginate' If you run into trouble, you can find helpful resources at https://jekyllrb.com/help/! 
    ```
    这个原因是因为没有jekyll-paginate，使用gem install jekyll-paginate安装一下就好了。<br>
    另外也有可能出现没有jekyll-gist错误，解决方法同上，这些错误取决模板所采用的一些服务。<br>
    所有的博客文章都在_post下,使用*.md或*.markdown来命名的文件。<br>
    ```
        ---
        layout: post
        title:  "记：使用Jekyll在GitHubPages搭建博客~"
        date:   2018-04-22 01:13:17 +0800
        categories: 日记
        ---
        ---
    ```
    每篇文章的开头都需要使用yml格式来声明。
6. 完成
    
    大概到这儿使用GitPages搭建Jekyll写博客就到此为止了，博客首发GithubPages，我的[GithubPages地址](https://czre.github.io/blog)
    
    
    
    
    
    
     
    
    
     
    
    



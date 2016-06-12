---
title: "Hello GitHub Page"
date: 2016-06-12 09:55
---

## 在GitHub上搭建个人wiki ##
#### 用到的工具 ####
- Mac OS X Yosemite(10.10.5)
- [GitHub Page][githubPage]
- [Simiki](http://simiki.org/)

#### 说明 ####
1. GitHub Page是GitHub自身的功能，它的官方介绍是：

	> Websites for you and your projects. Hosted directly from your GitHub repository. Just edit, push, and your changes are live.
 	
 	1. User & Organization Pages

 		> User & Organization Pages live in a special repository dedicated to GitHub Pages files. You will need to name this repository with the account name.
 	
 	2. Project Pages

		> Unlike User and Organization Pages, Project Pages are kept in the same repository as their project. 
	
	本文目标是建立User Page，两类Page的具体区别请参考[GitHub Page文档](https://help.github.com/articles/user-organization-and-project-pages/).

2. Simiki是一个简单的wiki框架，它是simple wiki的缩写，采用Markdown格式书写文档，simiki将markdown格式的文件发布为静态页面。
3. 本文的目的：在本地建立wiki工作环境，然后部署到GitHub上。

#### 用Simiki搭建本地wiki环境 ####
1. 安装Simiki (首先要安装python环境)

		$ pip install simiki

2. 初始化本地Simiki工作目录

		$ mkdir mywiki
		$ cd mywiki
		$ simiki init

3. 生成静态文件
	simiki自带一个说明文档，`simiki g`可以生成它的静态文件，输出到`/mywiki/output`目录中，注意output目录在执行这个命令的时候会执行删除文件操作，所以资源不要保存在这个目录下。

		$ simiki g

4. 本地预览（调试）模式，该命令打开默认的浏览器，展现simiki自带的说明文档

		$ simiki p

5. 定义自己的文档
	
		$ simiki n -t "Hello Simiki" -c first-catetory
	这个命令将在`/mywiki/content/first-catetory`目录下新建文件名为`Hello Simiki.md`的文章（后缀md表示markdown格式），如果目录名不存在，那么首先会建立这个目录。

到此，我们已经可以创建和生成wiki文章了，但需要注意的是目前simiki仅支持文章二级目录，即content目录下不允许建立二级category，category下即是对应的文章。
下面是其余几个重要的命令：
##### Help #####
	$ simiki -h
##### Update #####
	$ pip install -U simiki
	$ simiki update
##### Generate #####
	$ simiki g --draft //Include draft pages to generate
##### Preview #####
	$ simiki p -w //Auto regenerated when file changed


#### 在GitHub上部署wiki ####
1. 首先在GitHub上new repository (&lt;username&gt;.github.io)，&lt;username&gt;必须是GitHub用户名。
2. 在wiki的output目录下，git初始化，创建默认的master分支:

		$ cd output
		$ git init
		$ git add .
		$ git commit -m 'first comment'
		//将远程仓库命名为origin
		$ git remote add origin https://github.com/<username>/<username>.github.io.git
		$ git push -u origin master
	
	浏览器打开&lt;username&gt;.github.io，可以看到页面已经建立起来了，但我们只是部署了静态页面，还没有部署原始文件。

3. 部署原始文件

		//首先退回到mywiki根目录，并添加定义忽略规则
		$ cd ..
		$ echo '*.pyc\noutput' > .gitignore

		//然后创建source分支
		$ git init
		$ git checkout -b source
		$ git add .
		$ git commit -m 'add source file'
		
		$ git remote add origin https://github.com/<username>/<username>.github.io.git
		$ git push -u origin source


#### 参考文章 ####
- [Github Page Help][githubPage]
- [Simiki 文档][simikiDoc]


[githubPage]: https://help.github.com/categories/github-pages-basics/
[simikiDoc]: http://simiki.org/zh-docs/



















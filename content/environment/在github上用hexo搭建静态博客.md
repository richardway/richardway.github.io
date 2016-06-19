---
title: "在Github上用Hexo搭建静态博客"
date: 2016-06-16 14:32
---

[TOC]

## 平台
  - Windows
  - Github

## 工具
  - Hexo 3.0
  - Git Client
  - Node.js(npm)

## 综述 
  1. 这篇文章记录我在github上通过`project page`发布博客的过程。
	- 和网上的大多数教程不同，我不是通过`user page`发布博客的，因为我此前已经通过simiki在`http(s)://<username>.github.io`上搭建了个人wiki，所以我这里不可以再把该网址作为我的blog首页，所以我探索了用`project page`作为我的blog地址。最后的blog地址看起来很棒，它看上去就像是从属于我的个人wiki的页面那样，它的地址是`http(s)://<username>.github.io/blog/`
  2. 每个用户名只能创建一个`user page`，却可以创建多个`project page`（因为每个repository都可以有）。它们的详细区别见[[1]][reference]。

## 步骤
  1. 下载安装Hexo
  	不详细介绍了，按照Hexo官网的步骤做就行。
  2. 建立本地博客目录，并生成public目录
  	
	  	$ hexo init blog
	  	$ cd blog
	  	$ npm install
	  	$ npm install hexo-deployer-git --save
	  	$ hexo generate
  	
  3. 在gitbub上部署博客（过程大致参考`project page`建立的过程[[2]][reference]）
  	1. 首先在github上新建一个名为blog的repository
  	2. 在`/blog/public`目录初始化git版本库，新建孤儿分支gh-pages（注意：这是github规定的，`project page`的建立必须使用这个分支名称）并推送
	
			$ cd blog/public
			$ git init
			$ git checkout --orphan gh-pages
			$ git remote add origin https://github.com/<username>/blog.git
			$ git add .
			$ git commit -m "first commit"
			$ git push origin gh-pages
			// done，现在已经可以访问 http(s)://<username>.github.io/blog 了
	
  4. 配置_config.yml (参考[[3]][reference], [[4]][reference])，之后只需通过`hexo deploy`命令就可以将public目录下的改动push到repository了
  
		//_config.yml
		url:
		url: https://<username>.github.io/blog/
		root: /blog/

		deploy:
		type: git
		repo: https://github.com/<username>/blog.git
		branch: gh-pages
		message: [message]


		//以下三种命令效果一致
		$ hexo generate --deploy //(1)文件生成后立即部署网站
		$ hexo deploy --generate //(2)部署之前预先生成静态文件

		$ hexo generate //(3)生成文件，然后部署网站
		$ hexo deploy 
  
## 参考文章
  1. [GitHub-doc: User, Organization, and Project Pages][user-organization-and-project-pages]  
  2. [GitHub-doc: Creating Project Pages manually][creating-project-pages]  
  3. [Configurations in hexo][configuration]  
  4. [Deployment hexo through github][deployment]  
  5. [Hexo中文文档][hexo]  
  6. [用Hexo搭建github博客][shareHub]  

[reference]: #_5
[user-organization-and-project-pages]: https://help.github.com/articles/user-organization-and-project-pages/
[creating-project-pages]: https://help.github.com/articles/creating-project-pages-manually/
[configuration]: https://hexo.io/zh-cn/docs/configuration.html
[deployment]: https://hexo.io/zh-cn/docs/deployment.html
[hexo]: https://hexo.io/zh-cn/
[shareHub]: http://blog.xiaohansong.com/2015/06/17/用hexo搭建github博客/










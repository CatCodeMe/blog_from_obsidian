---
{"title":"publish workflow zh","description":"使用quartz发布obsidian到githubpage","dg-publish":true,"dg-path":null,"date":"2024-03-22 15:43:38","updated":"2024-03-22 16:05:17"}
---

> 基于[quartz](https://quartz.jzhao.xyz/)和[ccm-publisher](https://github.com/CatCodeMe/ccm-publisher)插件，发布obsidian笔记到github pages
> - 使用`submodule`，使得编译和发布博客内容完全分离，更加自由和方便

# 前置知识
- github的基本操作
- git的基本操作
# 操作步骤
1. 准备Quartz环境，参考 [Quartz: Get Started](https://quartz.jzhao.xyz/)
2. 初始化自己的Quartz编译库，这里应该是叫`yourname.github.io`, 替换`yourname`为你自己的github账号名称
	- 参考 [Quartz: Setting up your GitHub repository](https://quartz.jzhao.xyz/setting-up-your-GitHub-repository)
	- 到目前为止, 在本地运行`git remote -v `,将会得到下面的结果
		- quart_demo[^1] (其中quartz_demo是举例说明, 你自己运行的话应该是`yourname `) 
	```shell
	$ git remote -v
	origin	git@github.com:CatCodeMe/quartz_demo.git (fetch)
	origin	git@github.com:CatCodeMe/quartz_demo.git (push)
	upstream	https://github.com/jackyzha0/quartz.git (fetch)
	upstream	https://github.com/jackyzha0/quartz.git (push)
	```
3. 到这一步开始, 跟官方使用单库发布的方式区别开来, 我们使用`submodule`
4. 跟之前的步骤一样，在github初始化另一个空的仓库, 假如叫`content_demo`[^2]
	- 这里只需要初始化,不需要其他操作，像这样
	![20240322-publish_init_content.png](img/user/999_repository/20240322-publish_init_content.png)
5. 建好之后，可以直接在github, 如果喜欢git客户端工具也可以clone到本地再操作。新建一个文件（点击上图的`create a new file`蓝色链接即可）, 叫`.github/workflows/deploy.yml`
	-  **文件夹路径必须是 `.github/workflows `, 文件后缀必须是`.yml`**, 文件名没有要求，只要符合github要求即可
	- `deploy.yml` 的文件内容，可以参考这里 [deploy.yml](https://github.com/CatCodeMe/blog_from_obsidian/blob/d22e549cb735fa12f600985002ecf71e4348d1af/.github/workflows/deploy.yml)
	 ![20240322-publish_zh_yml.png](img/user/999_repository/20240322-publish_zh_yml.png)
	 - `repo` 选项替换成步骤2中名称，结构是`yourname/yourname.github.io`
	 - `token` 选项是github新的鉴权token，使用时要注意
		 1. 在[这里](https://github.com/settings/tokens?type=beta)生成token，记得在生成时选择token可以使用的仓库(更安全), 同时需要有设置`Actions`和`Contents`权限
1. 
2. Hitherto , you can use single repo like quartz site, or use `submodule`
3. For single repo, see [Quartz：Hosting](https://quartz.jzhao.xyz/hosting)
4. For **submodule**, follow me.
	1. go to github, create another empty repository like step2, for example `content_demo` [^2]
	2. in `content_demo`root path, create `.github/workflows/deploy.yml`, name to be determined,  demo [deploy.yml ](https://github.com/CatCodeMe/blog_from_obsidian/blob/d22e549cb735fa12f600985002ecf71e4348d1af/.github/workflows/deploy.yml)
		- ! 
# issues
- ctime, utime

[^1]: [quartz_demo repo](https://github.com/CatCodeMe/quartz_demo)
[^2]: [content_demo repo](https://github.com/CatCodeMe/content_demo.git)
---
{"title":"publish workflow","description":"union quartz and obsidian to publish your notes to github page","dg-publish":true,"dg-path":null,"date":"2024-03-21 16:56:09","updated":"2024-03-21 17:52:13","tags":["guide"]}
---


# steps
1. prepare quartz, see [Quartz: Get Started](https://quartz.jzhao.xyz/)
2. init an empty repository for **publishing your notes**
	- follow these steps [Quartz: Setting up your GitHub repository](https://quartz.jzhao.xyz/setting-up-your-GitHub-repository)
	- Hitherto, your git should like 
		- `quart_demo`[^1] ( **just for demo**) yourself repo for build, it's usually `your_github_name.github.io`
	```shell
	$ git remote -v
	origin	git@github.com:CatCodeMe/quartz_demo.git (fetch)
	origin	git@github.com:CatCodeMe/quartz_demo.git (push)
	upstream	https://github.com/jackyzha0/quartz.git (fetch)
	upstream	https://github.com/jackyzha0/quartz.git (push)
	```

3. Hitherto , you can use single repo like quartz site, or use `submodule`
4. For single repo, see [Quartz：Hosting](https://quartz.jzhao.xyz/hosting)
5. For **submodule**, follow me.
	1. go to github, create another empty repository like step2, for example `content_demo` [^2]

# issues
- ctime, utime
	```java {2} /void/
	public static void main(){
	  new Object() //高亮没了？
	}
	```

[^1]: [quartz_demo repo](https://github.com/CatCodeMe/quartz_demo)
[^2]: [content_demo repo](https://github.com/CatCodeMe/content_demo.git)
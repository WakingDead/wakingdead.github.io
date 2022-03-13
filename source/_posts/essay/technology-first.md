---
title: 写给自己：关于网站后续更新以及部署的参考文档
date: 2022-03-13
tags: - 技术文档
categories: - 技术文档
---

# Markdown
[Markdown语法文档](https://www.runoob.com/markdown/md-link.html)

[云游君写的Markdown语法文档](https://github.com/younghz/Markdown)

# Hexo
[云游君的教程](https://www.yunyoujun.cn/share/how-to-build-your-site/)

[云游君的主题文档教程](https://yun.yunyoujun.cn/)

[云游君的代码](https://github.com/YunYouJun/yunyoujun.github.io)

[官方文档](https://hexo.io/zh-cn/docs/)

# 一些会用到的步骤
更改主题：需要在`_config.yun.yml`文件中，按照自己的需要更改主题。更改完成后，右键`wakingdead.github.io`文件夹，点击`GIT Bash Here`,输入代码`npm i hexo-theme-yun@latest`。

写新的文档：右键`wakingdead.github.io`文件夹，点击`GIT Bash Here`,输入代码`hexo new post xxx`,即可新建`xxx.md`文件，在文档中内容即可

更新旧的文档：在旧的文档的`Front-matter`栏目，添加`update:20xx-xx-xx`，然后修改/更新即可

更新静态文件：完成更新以后，右键`wakingdead.github.io`文件夹，点击`GIT Bash Here`,输入代码`hexo clean`删除原来的静态文件，然后输入代码`hexo generate`生成新的静态文件

部署网站：`hexo deploy`

# 备份代码到GitHub
`git add -A`
`git commit -m "这次做了什么更改，简单描述下即可"`
`git push`




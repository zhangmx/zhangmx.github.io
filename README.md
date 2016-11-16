# zhangmx.github.io 这是我的个人博客仓库
beginning point ，虽然有点迟，不过总归是开始了

#部署

如果没有node环境，最好用nvm安装node

checkout 后

```bash
cd zhangmx.github.io
npm install hexo-cli -g
npm install
```

创建一篇新博文：

```bash
hexo new "New blog name"
```

去source目录下的_posts找到对应名字的md文件，编写内容。

查看效果：

```bash
hexo s --debug
```

由于采用了travis-ci部署了自动发布（坑很多），只需要把本分支提交到github就可以了。

打开浏览器，查看效果后，通过ide或者git命令直接提交改动。

鱿鱼jekyll升级导致vendors目录无法访问,本地部署环境的时候,需要在.deploy_git目录下添加一个.nojekyll的文件

内容为:

```
!vendors/*
```

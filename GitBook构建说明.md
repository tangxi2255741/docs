# Gitbook操作说明

1、通过gitbook init初始化项目，会生成SUMMARY.md[^1]文件，它是全书的目录入口。该文件会影响gitbook官网结构显示，但如果忽略掉又会影响本地生成，因此引入插件自动生成目录；

2、通过以下命令，可以安装插件，并会生成node_modules文件，不需要提交到git上，可以忽略；

```shell
$ gitbook install ./
```

3、启动服务（注意没有r，启动后可以通过：http://localhost:4000 访问）

``` shell
$ gitbook serve
```

[^1]: 可以先删除Summary文件，再使用gitbook serve命令，会自动生成，但还需再部署一次最新的目录才会生效；

**Summary插件生成目录结构说明**

1. 文件夹需要在目录下面创建README.md文件才能折叠目录；
2. 使用0-README.md，1-README.md可以自定义目录的顺序；

建议：采用手动编写，自动生成还是乱的，目前没有使用插件；



1、编写文档以后push到remote，github可以直接通过首页访问readme.md；

2、如果要部署到：https://tangxi2255741.github.io/webDoc 上，可以现在本地使用`gitbook build` 默认build到_book目录下，将整个目录下的文件copy到webDoc的文件中，再`push`webDoc就可以访问；




# 使用Git提交更新

~~~git
$ git fetch
$ git pull origin master
$ git add .
$ git commit -m "使用说明"
$ git push origin master
~~~

公司电脑路径：/d/myproject/docs

个人台式电脑文档存储路径：/d/work/myproject/docs



# Gitbook常用命令

`` npm install gitbook-cli -g ``

`gitbook ls` ：列出本地安装版本；

`gitbook current` ：列出当前使用版本；

`gitbook ls-remote` ：列出远程可使用版本；

`gitbook fetch 2.6.9` ：安装2.6.9版本；

`gitbook uninstall 2.6.9` ：卸载指定版本；

`gitbook update 2.6.9` ：更新到指定版本，没有指定版本则到最新；

`gitbook install` ：安装当前项目所需插件；

`gitbook build` ：构建成Html文件，默认在_book目录下；

`gitbook serve`：启动服务；

`gitbook pdf` ：输出pdf电子书；

`gitbook epub`：输出epub电子书；

`gitbook mobi` ：输出mobi电子书；


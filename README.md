# Gitbook操作说明

1、通过gitbook init初始化项目，会生成SUMMARY.md文件，它是全书的目录入口。该文件会影响gitbook官网结构显示，但如果忽略掉又会影响本地生成，因此引入插件自动生成目录；

2、通过以下命令，可以安装插件，并会生成node_modules文件，不需要提交到git上，可以忽略；

```shell
$ gitbook install ./
```

3、启动服务（注意没有r，启动后可以通过：http://localhost:4000 访问）

``` shell
$ gitbook serve
```



台式电脑文档存储路径：

/d/work/myproject/Document





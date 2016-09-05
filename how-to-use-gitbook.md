# 如何使用gitbook

在gitbook.com上

Create a new book

![](http://octas1bqx.bkt.clouddn.com/fb87b834b0d976fc030458cea59b4737.png)

默认得到如下仓库地址

https://git.gitbook.com/leamiko/`api-test`.git

集成到github

1 先创建一个github仓库(名称保持与gitbook上一致:`api-test`,当然不一样也无所谓)

https://github.com/leamiko/api-test.git

2 gitbook的Settings>GitHub->select a repository，选择step1创建的repo(`api-test`),点`Sync`按钮确定。
添加`add webhook`(这样github上做的修改，能够触发gitbook上文件相应的变化)

![](http://octas1bqx.bkt.clouddn.com/cf82c5777b644cb7296fc353a43563cb.png)

3 gitbook的Settings>Hooks -> `new webhook`,如下图确定后，(这样gitbook上的修改，能触发github上文件的改变)

![](http://octas1bqx.bkt.clouddn.com/321d6d7fa158679eaa849d22e53aa042.png)

![](http://octas1bqx.bkt.clouddn.com/9f88d0fcc6fb70fe6e39b73083e7feda.png)

在step1之前我会先把gitbook上的文件先手动同步到github上。

```
git clone https://github.com/leamiko/api-test.git ./api-test
cd api-test
git push https://github.com/leamiko/api-test.git master --force
```

以后只要维护https://github.com/leamiko/api-test.git上的文件即可在gitbook上预览。

或者通过gitbook editor编辑也能触发github上的文件相应变化。

再配合gitbook命令行使用

附 [Gitbook命令行](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md)使用

通过NPM安装

```
npm install gitbook-cli -g
```

其中gitbook-cli是gitbook的一个命令行工具, 通过它可以在电脑上安装和管理gitbook的多个版本.

生成一个本地预览站点

```
gitbook serve
```

生成本地_book文件,这样无需开启服务器也能查看

```
gitbook build
```

编辑好SUMMARY.md,使用如下命令会生成对应的文件
```
gitbook init
```

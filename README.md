#一、Github Pages 是什么？

如果你对编程有所了解，就一定听说过github。它号称程序员的Facebook，有着极高的人气，许多重要的项目都托管在上面。简单说，它是一个具有版本管理功能的代码仓库，每个项目都有一个主页，列出项目的源文件。

但是对于一个新手来说，看到一大堆源码，只会让人头晕脑涨，不知何处入手。他希望看到的是，一个简明易懂的网页，说明每一步应该怎么做。因此，github就设计了Pages功能，允许用户自定义项目首页，用来替代默认的源码列表。所以，github Pages可以被认为是用户编写的、托管在github上的静态网页。

##第一步，创建项目
在你的电脑上，建立一个目录，作为项目的主目录。我们假定，它的名称为jekyll_demo。
```
　$ mkdir jekyll_demo
```

对该目录进行git初始化
```
$ cd jekyll_demo
　　$ git init
```

然后，创建一个没有父节点的分支gh-pages。因为github规定，只有该分支中的页面，才会生成网页文件
```
$ git checkout --orphan gh-pages
```
以下所有动作，都在该分支下完成

##第二步，创建设置文件
在项目根目录下，建立一个名为_config.yml的文本文件。它是jekyll的设置文件，我们在里面填入如下内容，其他设置都可以用默认选项，具体解释参见官方网页
```
seurl: /jekyll_demo
```

目录结构变成：
```
/jekyll_demo
　　　　|--　_config.yml
```

##第三步，创建模板文件
在项目根目录下，创建一个_layouts目录，用于存放模板文件
```
$ mkdir _layouts
```

进入该目录，创建一个default.html文件，作为Blog的默认模板。并在该文件中填入以下内容
```
<!DOCTYPE html>
<html>
<head>
	<meta http-equiv="content-type" content="text/html; charset=utf-8" />
	<title>{{ page.title }}</title>
</head>
<body>
	{{ content }}
</body>
</html>
```
Jekyll使用Liquid模板语言，{{ page.title }}表示文章标题，{{ content }}表示文章内容，更多模板变量请参考官方文档。

目录结构变成：
```
/jekyll_demo
　　　　|--　_config.yml
　　　　|--　_layouts
　　　　|　　　|--　default.html
```

##第四步，创建文章
回到项目根目录，创建一个_posts目录，用于存放blog文章


##第五步，创建首页
##第六步，发布内容

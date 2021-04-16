打造易阅读的电子书-GitBook

作为一名合格的程序媛，阅读博客，观看视频是必不可少的一个环节，输入知识的同时，还要输出所观所感，持续输出自己的原创，快速提高能力，加快自我成长。

那么，问题来了？我们应该使用什么工具创作？怎么阅读起来舒服、美观？

下面都是满满的干货，Let'go，一起往下看吧！

## 文本编辑工具-`Typora`

编辑文本的工具，我在这里给大家推荐`Typora`，这款工具最大的好处就是所写即所见，还支持数学公式的插入，对算法工程师来讲真的不要太方便哦~Typora的安装有也是十分方便的，直接给大家上链接：https://www.typora.io/ (注：其他便捷工具下载链接[点击](./算法工程师软件工具推荐.md))

## 电子书生成工具-`GitBook`

`GitBook`是一个基于`Node.js`的命令行工具，支持Markdown和AsciiDoc两种语法格式，可以输出html、pdf、ebook等格式的电子书。通过使用GitBook管理文档、预览、制作电子书，他也支持写入数学公式，不用很麻烦的插入数学公式图片，省了很大的时间开销。

### 生成电子书的流程

+ **必要工具安装**

1. Git(链接：https://pan.baidu.com/s/1GWivepH7KbWaY9OFAOq_oQ  提取码：pq3b)
2. Node.js(链接：https://pan.baidu.com/s/1EeEdTqQhVj9mqIZQ1EyUIA  提取码：7mds；或在官网下载：https://nodejs.org/en/download/)
3. Typora(或者自己喜欢的Markdown编辑器)

+ **安装`cnpm`**(非必要步骤)

安装`Node.js`后，会默认安装`npm`，由于node安装插件是从国外服务器下载，受网络影响很大，速度慢可以会出现异常，我们可以使用国内的镜像源-淘宝镜像源，同步频率目前为10分钟一次。

我们可以使用阿里定制的`cnpm`命令行工具代替默认的`npm`，打开cmd，敲入以下代码进行

```shell
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

检测`cnpm`版本，若安装成功，则会有`cnpm`的基本信息。

```shell
cnpm -v
```

结果如下，出现类似信息，说明已安装成功，以后安装插件只需要使用`cnpm isntall`即可。

```
cnpm@6.1.1 (C:\Users\Administrator\AppData\Roaming\npm\node_modules\cnpm\lib\par
se_argv.js)
npm@6.14.5 (C:\Users\Administrator\AppData\Roaming\npm\node_modules\cnpm\node_mo
dules\npm\lib\npm.js)
node@11.10.0 (D:\nodejs\node.exe)
npminstall@3.27.0 (C:\Users\Administrator\AppData\Roaming\npm\node_modules\cnpm\
node_modules\npminstall\lib\index.js)
prefix=C:\Users\Administrator\AppData\Roaming\npm
win32 x64 6.1.7601
registry=https://r.npm.taobao.org
```

**注：该命令并非必要命令，主要作用是加快插件的安装速度。**

+ **安装`GitBook`**

然后执行以下命令安装`GitBook`:

```shell
cnpm install -g gitbook-cli
```

**注：如果没有使用淘宝镜像源，请把命令中的`cnpm`改为`npm`，下面使用到`cnpm`命令同上。**

检查是否安装成功

```shell
gitbook -V
```

结果如下，出现类似信息，说明已安装成功，如果报错，请确认上面的命令是否加了`-g`。

```
CLI version: 2.3.2
GitBook version: 3.2.3
```

+ **`GitBook`使用**

初始化

```shell
gitbook init
```

初始化后会生成`SUMMARY.md`和`READ.md`文件，信息如下：

```
info: create README.md
info: create SUMMARY.md
info: initialization is finied
```

两个文件的作用如下：

 `README.md` —— 书籍的介绍写在这个文件里

`SUMMARY.md`—— 书籍的目录结构在这里配置

+ **通过Typora编辑`SUMMARY.md`**

内容修改：

```markdown
# 结构
[文章名](文章路径)

# for example
+ [Introduction](README.md)
+ 深度学习
	+ [深度学习概述](./chapters/DL/深度学习概述.md)
```



+ 构建书籍

```shell
gitbook build [书籍路径] [输出路径]
```


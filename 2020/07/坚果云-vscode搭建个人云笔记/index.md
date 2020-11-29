# 坚果云 + VSCode搭建个人云笔记


# 坚果云 + VSCode搭建个人云笔记

之前使用的是有道云笔记，有两个问题：

1. Mac版的有道云笔记越来越卡了，不知道以后会不会改善
2. 免费账户Markdown不能上传图片（没错，我的会员到期，我本可以继续付费，但我不愿意哈哈哈哈哈🤣）

当初使用有道云笔记是因为界面十分美观而且它的目录结构是类似于文件夹的，所以没有使用印象笔记。但是上述问题（主要还是第1个）让我十分不能忍，俗话说：`自己动手，丰衣足食`，所以果断上网查找解决办法，并且将其记录下来。

## 0. 选型

- ***为什么使用坚果云（个人免费账户）？***

1. 存储文件速度快、稳定
2. 可以多端同步不受限制
3. 对于笔记来说，每个月的上传下载流量是绰绰有余的
4. 最重要的是，可以多人协同办公，可以说是十分方便了

![坚果云免费账户](https://cdn.jsdelivr.net/gh/SuperGch/picgo/note-imgs/坚果云免费账户.png "坚果云免费账户")

- ***为什么使用VSCode?***

因为我之前是搞Java的，工作中需要写一点前端（负责公司工作流的前后端维护和开发）和各种文档，VSCode轻量、跨平台、扩展丰富（可玩性极高）并且界面还很酷，一下子就爱上了。所以使用VSCode我是十分愿意的，安装插件之后，写Markdown也是很爽，一些常用功能都有。

## 1. 创建Github仓库

进入Github创建一个仓库，配置如下图所示，该仓库用于存储笔记中的图片。

> 仓库必须要是public的，否则上传会失败!

![进入Github创建一个仓库，用于存放图片](https://cdn.jsdelivr.net/gh/SuperGch/picgo/note-imgs/20200630173918.png "Github创建仓库")

## 2. 获取Github Token

进入Github的`Settings`->`Developer Settings`->`Personal access tokens`->`Generate new token`，然后按照如下步骤，完成之后记住token。

![生成Token，这样PicGo可以使用token将图片上传到仓库](https://cdn.jsdelivr.net/gh/SuperGch/picgo/note-imgs/20200630171630.png "Github生成Token")

## 3. 安装PicGo并设置

如果只是依赖坚果云来存储所有笔记及其附属文件的话，那么会出现问题：在电脑上使用VSCode编辑了笔记，然后在手机上使用坚果云查看这个文档，图片就会显示不出来。

`解决办法`: 使用Github仓库作为图床，将图片放到Github仓库中，然后生成一个该图片的连接，在Markdown文档中使用这个图片链接即可显示图片。

在网上发现了有人使用`PicGo`这个VSCode插件，发现十分不错，安装插件之后可以直接使用快捷键将本地文件系统的图片或者剪贴板的图片直接上传到图片仓库中。

打开VSCode，安装插件`PicGo`，完成之后，点开`Settings`，找到如下位置开始配置

![按照如图所示的配置项配置，其他选项按需配置](https://cdn.jsdelivr.net/gh/SuperGch/picgo/note-imgs/PicGo配置.png "配置PicGo")

总共6个步骤，这里解释一下步骤3，因为github的服务器不在中国大陆，所以直接使用github做图床非常慢，这里通过使用jsDelivr这个网站中的CDN的url进行自定义加速，格式是`https://cdn.jsdelivr.net/gh/你的Github用户名/图床仓库`。

## 4. PicGo使用方法

使用阶段，在markdown文档当中，使用如下快捷键，即可将图片上传到上述创建的Github仓库的指定路径下，并且获取到图片的地址（会按照文档的类型自动写好的）。

`option + command + u`: 将剪贴板中的图片上传，如果剪贴板中没有图片，那么会报错。上传成功后，剪贴板内容变为该图片的仓库地址，直接粘贴即可。

`option + command + e`: 将文件系统中的图片上传。

## 5. 文档分享解决方案

由于坚果云限制了付费用户才可以分享文档，所以为了可以分享文档，需要在VSCode中安装插件`Markdown Preview Enhance`。

使用方法：首先在markdown源文件当中点击右键，选择`Markdown Preview Enhance:...`选项，那么会在当前源文件右边出现一个预览窗口，这个预览窗口当中右键，即可实现导出为各种格式。

目前支持的格式有：`HTML`,`PDF`,`PNG`,`JPEG`,`ePub`,`mobi`,`Pandoc`，足以支持日常使用了。



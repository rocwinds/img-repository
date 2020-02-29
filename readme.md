# Github仓库当图床 + PicGo快速上传 + jsDelivr加速

# 创建自己的GitHub图床

## 1. 创建GitHub图床之前，需要注册/登陆GitHub账号

> 申请GitHub账号很简单，我就不演示了

## 2. 创建Repository

![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b439125b024?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *点击"New repository"按钮* ![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b43d211747d?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *最后1234步骤执行*

> - 我已经建立过一个同名的repository的，所以第一步会显示红色
> - 第三步，为repository初始化一个README.md文件可以根据需求选择，非必选

## 3.生成一个Token用于操作GitHub repository

![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b43f3c6ccb3?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *回到主页，点击"Settings"按钮* ![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b43f97bc563?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *进入页面后，点击"Developer settings"按钮* ![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b43faa50788?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *点击"Personal access tokens"按钮* ![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b4403817332?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *创建新的Token* ![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b44115f2ee3?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *填写描述，选择"repo",然后点击"Generate token"按钮*

> 注：创建成功后，会生成一串token，这串token之后不会再显示，所以第一次看到的时候，就要好好保存

# 配置PicGo

## 1. 下载运行PicGo

![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b4427ee17cd?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *下载zip包后，解压，运行可执行文件*

## 2. 配置图床-使用默认github访问链接

![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b44282f8187?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *如图配置*

> - 设定仓库名的时候，是按照“账户名/仓库名的格式填写”
> - 分支名统一填写“master”
> - 将之前的Token黏贴在这里
> - 存储的路径可以按照我这样子写，就会在repository下创建一个“img”文件夹
> - 自定义域名的作用是，在上传图片后成功后，PicGo会将“自定义域名+上传的图片名”生成的访问链接，放到剪切板上`https://raw.githubusercontent.com/用户名/RepositoryName/分支名`，自定义域名需要按照这样去填写

## 3.快捷键及相关配置

![img](https://user-gold-cdn.xitu.io/2019/1/28/16893b4431798992?imageView2/0/w/1280/h/960/format/webp/ignore-error/1) *可以按照这样配置*

> 注：可以将快捷键设置为`ctrl+shift+c`

## 4.给图片显示加速-jsDelivr 配置

其实就是上一节 PicGo 配置的最后一条——设定自定义域名。我的设定是：

```html
https://cdn.jsdelivr.net/gh/用户名/仓库名@分支名
```

其中：

- `gh` 表示来自 Github 的仓库
- `joeyliu6/Blogger` 仓库的具体位置
- `master` 仓库的分支

好的，在此就配置完成。图片链接形式如下：

```html
https://cdn.jsdelivr.net/gh/rocwinds/img-repository@master/img/图片文件
```

![img](https://cdn.jsdelivr.net/gh/joeyliu6/Blogger@master/static_files/iljw/img/large/20190512155938.png)

可以通过 PicGo 方便地上传图片了，它支持拖拽、点击、剪贴板上传，上传后，图片链接直接复制的你的剪贴板中。

当然，你也可以通过 Git 命令，将本地图片批量上传到 Github 上，再替换成原文中的图片链接地址，以完成图片迁移的工作。
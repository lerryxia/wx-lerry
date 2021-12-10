# wx-lerry
基于halo网站后台和GBlog-wx小程序
### 文初lerry www.lerry.xyz
### 介绍
> .. 基于halo的后台，主题halo-joe2.0;以及GBlog-wx的小程序源代码搭建的服务器，网站和微信小程序。此仓库仅仅用于个人备份. ..
> halo https://halo.run
> GBlog-wx : https://gitee.com/fuzui/GBlog-wx.git

> 软件架构
> 软件架构说明

### 安装教程
#### 1. 搭建Linux系统后台
> Linux 环境部署请访问halo文档 可以搭配宝塔面板使用操作方式

#### 2. ( 搭建网站主题 )[https://halo.run]
#### 3。个性化小程序
### 配置

> 将miniprogram/config中api-tmp.js文件复制并重命名为api.js。

#### 修改api.js如下配置：
```
const ApiBaseUrl = '';//生产上
const Config = {
  AccessKey: '',
  guestbookSheetId: 2
}
```
> 1.ApiBaseUrl为halo后台地址，上线必须为域名，在开发者工具中可点击右上角详情——本地设置，将不校验合法域名打勾。
> 2.AccessKey为halo api的AccessKey。进入halo后台管理系统，在系统——博客设置——高级选项——API设置中，将API 服务开启，并设置Access key。将此Access key填入上述js文件中对应位置。
> 3.guestbookSheetId该值是留言板页面id，默认为关于页的评论，可自行前往表结构中查看。（使用官方主题id默认2）

### 海报分享功能

#### 1，在config/api.js文件中，修改如下代码
```
const CloudConfig = {
  isOpen: true,
  env: 'fuzui',  //云环境ID
  shareOpen: true,  // 海报分享开启
}
```
#### 2，上传云函数

> 右击cloudfunctions下get_qrcode文件夹，点击“创建并部署：云端安装依赖(不上传node_moudles)”，等待完成。

#### 3，右击cloudfunctions，同步云函数列表

#### 4，设置downloadFile合法域名

> 在微信后台需将博客图片地址域名（halo附件地址）和微信头像域名添加到downloadFile合法域名，例如cdn.fuzui.net与wx.qlogo.cn、thirdwx.qlogo.cn。（在开发者工具中可勾选不校验合法域名运行）

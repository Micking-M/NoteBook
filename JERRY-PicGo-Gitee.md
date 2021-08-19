---
title: 《JERRY PicGo & Gitee 网站图床搭建说明》
date: 2020-11-29 02:54:24
categories:
- [README]
tags: 
- README
- 图床搭建
- PicGo
cover: https://img-blog.csdnimg.cn/2021030114474345.jpg
---

# JERRY-PicGo-Gitee

**《JERRY PicGo & Gitee 网站图床搭建说明》**

> 原创内容，转载请注明出处！

# 一、前言

## 1.1 什么是网站图床？

图床一般是指储存图片的服务器，有国内和国外之分。国外的图床由于存在空间距离等因素，导致访问速度很慢，影响图片显示速度。国内也分为单线空间、多线空间和 CDN 加速三种。

图床的意义在于专门用来存放图片，同时允许你把图片对外链接的网上空间。

## 1.2 为什么需要图床？

- 减轻网站服务器存储压力，同时负担流量
- CDN 服务提高图片加载速度，从而加快网站访问速度
- CDN 服务提高图片加载速度，从而节省流量
- 利于后续网站迁移扩容

## 1.3 什么是 PicGo？

**PicGo**：一个用于快速上传图片并获取图片 `URL` 链接的工具。

- 开源免费
- 支持多种图床
- 支持插件可扩展
- 支持多种图片上传方式
- 支持多种自定义设置
- 简单、稳定、易用

## 1.4 什么是 Gitee？

**Gitee**：[开源中国](https://baike.baidu.com/item/开源中国/5462428)（OSChina）推出的基于 `Git` 的代码托管服务和研发协作平台 。

## 1.5 PicGo 与 Gitee 搭配作为图床的优缺点

**（1）优点**

- 免费稳定
- 简单易用

**（2）缺点**

- 只支持单张 1 MB 以内大小的图片
- 单个免费图床大小上限为 500 MB
- 图片安全性较差
- 图床存在一定的失效风险

# 二、Gitee 的配置

## 2.1 注册用户

[Gitee官网](https://gitee.com/)

点击右上角注册即可。

## 2.2 创建图床仓库

- 点击右上角的 `+` 选择 `新建仓库`
- 仓库名称建议设为 `image-bed`
- 是否开源选择 `公开`
- 勾选使用 Readme 文件初始化这个仓库
- 默认选择单分支模型（只创建 master 分支）

## 2.3 Gitee 的设置

- 在个人主页点击 `个人设置`
- 选择安全设置里的 `私人令牌`
- 点击 `生成新令牌`
- 勾选 `user_info` 及 `projects`
- 进行密码验证
- 保存私人令牌

# 三、PicGo 的配置

## 3.1 PicGo 的下载安装

**（1）下载**

[PicGo官网](https://molunerfinn.com/PicGo/)

- 点击免费下载
- 选择稳定版本
- 选择系统版本
- 点击链接下载

**（2）安装**

- 打开安装程序
- 默认执行下一步
- 点击启动 PicGo

## 3.2 PicGo Gitee 插件安装

- 在 PicGo 菜单栏中选择 `插件设置`
- 搜索 gitee
- 下载 `gitee-uploader` 插件
- 重启 PicGo

# 四、PicGo 的使用

## 4.1 配置 Gitee 插件

- 在 PicGo 菜单栏中选择 `图床设置`
- 选择 gitee 选项
- `repo` 填写图床仓库名（用户名/仓库名）
- `branch` 默认为 master
- `token` 填写 Gitee 私人令牌
- 点击确定（同时建议设为默认图床）

## 4.2 自定义 PicGo

- 在 PicGo 菜单栏中选择 `PicGo 设置`
- 打开日志文件添加 `错误-Error` 及 `提醒-Warn`
- 开启 `开机自启`
- 开启 `时间截重命名`
- 开启 `上传自动复制 url`

## 4.3 上传图片到图床

**（1）拖拽图片上传**

将图片直接拖拽到 PicGo `上传区` 图片便会自动上传至图床，并自动复制指定格式的链接。

**（2）剪贴板首图上传**

点击 PicGo `上传区` 中的 `剪贴板图片上传`，会自动上传剪贴板上存在的第一张图片，并自动复制指定格式的链接。

## 4.4 使用技巧

可以使用截图工具配合 `PicGo 快捷上传` 快捷键来实现快速上传并得到图片指定格式链接。

- 在 PicGo 菜单栏中选择 `PicGo 设置`
- 点击修改快捷键，设置 `快捷上传` 快捷键
- 使用截图工具截图并复制截图到剪贴板
- 按下快捷上传快捷键（自动上传并复制指定格式的图片链接）
- 在所需位置直接粘贴即可

# 五、结束语

## 5.1 关于网站图床的其他选择

PicGo & Gitee 图床搭配只适用于图片较少且单张图片较小的小型网站，主要特点在于免费快速。

对于大型网站和有大量图片需求的网站而言配置专业的服务器是必须的。你可以购买 `本地服务器` 并自行配置，不过更建议购买 `云服务器` 使用，这样可以有效控制网站初期运营成本，并且也更加方便、快速、稳定和安全。

## 5.2 帮助文档

PicGo 提供了全面的 [PicGo 使用文档](https://picgo.github.io/PicGo-Doc/zh/guide/) 及 [PicGo 插件库](https://github.com/PicGo/Awesome-PicGo)，使用过程中遇到问题建议以官方文档为基准。
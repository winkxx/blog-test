---
title: Blog：GDshare
date: 2021-05-02
published: true
slug: blog
tags: ['blog', 'Tech']
canonical_url: false
description: "GDshare"

---
# 项目地址
~
[iwestlin/gdshare (github.com)](https://github.com/iwestlin/gdshare)



## 介绍

这是一款受goindex启发而产生的项目，适合部署于cloudflare worker，相比原版有以下特性：

- 全盘搜索（包括个人盘和所有有权限的团队盘，可点击搜索结果中的链接跳转到对应的google drive官方网址）
- 分页浏览（可自定义每页文件数，每页可根据文件名和大小排序）
- 更美观的UI（致谢 ant design）
- 防爬虫，对于所有目录和文件，只有管理员才有读取和下载的权限（原版goindex可以通过在目录下防止 .password 来给目录设置读取密码，但无法限制单个文件的下载）
- 可以生成下载直链，方便第三方下载工具下载，对于流媒体文件，可以用potplayer等播放器直接打开进行播放（可以自定义有效期）
- 可以生成带有提取码的分享链接，方便分享给他人浏览和下载（同样支持自定义有效期）

## 搭建方法

1. 有个cloudflare的号，创建一个worker
2. 打开template.js，根据提示修改变量：
3. 变量设置完成后，将文件整体复制到 cloudflare worker 中
4. 保存部署，体验！

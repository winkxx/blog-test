---
title: proxypool
date: 2021-05-02
published: true
slug: blog
tags: ['blog', 'Tech']
canonical_url: false
description: "proxypool"
---
# 搭建proxypool节点池子

---

## 正文

操作环境:vps(Centos7)宝塔
步骤:

1. 域名解析(没有虽然也可以，但可能不安全)
2. 建立网站，自己找个目录(记住)远程下载程序
   - https://github.com/xiaofei-ya/proxypool/releases/download/v0.5.3/proxypool-linux-amd64-v0.5.3.gz
   - 同时下载两个配置文件
   - https://raw.githubusercontent.com/xiaofei-ya/proxypool/master/config/config.yaml
   - https://raw.githubusercontent.com/xiaofei-ya/proxypool/master/config/source.yaml
3. 修改配置文件
   - 双击打开配置文件 config
   - domain 就是你解析的域名，source-files 这里把前面的文件夹去掉，留下./source.yaml 即可
   - cral-interval 是爬虫爬取间隔，speedtest可以打开或者关闭速度测试
4. 给权限运行程序，过后记得给守护过程(宝塔下载一般是够权限的，所以省了)

> + 做法1
>
> > 1. SSH命令`nohup ./proxypool -c config.yaml 1>>run.log 2>>run.log &`
> > 2. 停止运行则需要`cd /123 # cd后面是你自己设置的根目录`  `ps -ef`
> > 3. 找到 ./proxypool -c config.yaml的PID然后`kill -s 9 PID#自己找到的PID`
>
> + 做法2
>
> > 1. 宝塔下载supervisor管理器
> > 2. 添加守护进程，名字自己取，运行目录为你程序所在目录
> > 3. 运行命令则为 程序所在目录+./proxypool,调整优先级为10差不多了

5. 网站设置反代，名字随意，Url为127.0.0.1:12580(也可为VPS的IP:12580)

---

参考网站:https://ednovas.ml/2021/01/27/proxypool/
github源码fork版:https://github.com/xiaofei-ya/proxypool/
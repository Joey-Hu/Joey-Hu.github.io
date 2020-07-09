---
title: PostgreSQL安装
date: 2020-07-05 21:44:45
categories:
 - webGIS
tags: postGIS
---

## PostgreSQL安装

### 一、 下载安装

postgreSQL下载地址： https://www.enterprisedb.com/downloads/postgres-postgresql-downloads 

本文以 9.6.18 windows 64位版本为例

postgreSQL安装步骤可以设置一路默认，设置好管理员密码，端口，安装地址和安装内容，区域（Locale）选择默认即可。

![password.png](https://raw.githubusercontent.com/Joey-Hu/images/master/password.png)

![locale.png](https://raw.githubusercontent.com/Joey-Hu/images/master/locale.png)



### 二、 安装stack builder

PostgreSQL安装完成后，出现以下界面，勾选选择安装stack builder(或者在postgreSQL目录打开)

![setup.png](https://raw.githubusercontent.com/Joey-Hu/images/master/setup.png)

![setup2.png](https://raw.githubusercontent.com/Joey-Hu/images/master/setup2.png)

![stackbuilder1.png](https://raw.githubusercontent.com/Joey-Hu/images/master/stackbuilder1.png)



**出现问题：不能连接上applications-v2.xml**

![stackbuilderError.png](https://raw.githubusercontent.com/Joey-Hu/images/master/stackbuilderError.png)

解决办法：

1. 尝试[该方法]( https://serverfault.com/questions/555125/postgresql-stack-builder-installation-proxy-setting-on-windows )(未使用过)

2. 关闭安全中心的实时保护（经测试有效）

选择安装postGIS插件版本，安装地址要**和postgresql的安装路径一致**，接下来，一路默认安装即可。

空间扩展

![spatialExtension.png](https://raw.githubusercontent.com/Joey-Hu/images/master/spatialExtension.png)

安装完成！

![done.png](https://raw.githubusercontent.com/Joey-Hu/images/master/done.png)

## 参考：

[postgresql+postgis安装、postgresql汉化]( https://blog.csdn.net/rrrrroy_Ha/article/details/90751760 )
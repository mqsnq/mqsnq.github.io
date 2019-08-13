---
layout: post
title: AndroidStudio在gradle设置代理
categories: Android
description: AndroidStudio在gradle设置代理
keywords: AndroidStudio, 代理
---

### 设置全局代理

在`.gradle`目录中创建`gradle.properties`文件，`.gradle` 目录默认在用户目录下(区别window/linux)； 
 因为我设置了环境变量`GRADLE_USER_HOME=/data/.gradle` 所以我的在`/data` 下；

在gradle.properties加入如下内容： 

**配置HTTP代理**

```
systemProp.http.proxyHost=www.somehost.org

systemProp.http.proxyPort=8080

systemProp.http.proxyUser=userid

systemProp.http.proxyPassword=password

systemProp.http.nonProxyHosts=*.nonproxyrepos.com|localhost
```

**配置HTTPS代理**

```
systemProp.https.proxyHost=www.somehost.org

systemProp.https.proxyPort=8080

systemProp.https.proxyUser=userid

systemProp.https.proxyPassword=password

systemProp.https.nonProxyHosts=*.nonproxyrepos.com|localhost

 
```

**下面是我的实例文件：**

```
[root@localhost .gradle]# cat gradle.properties 

systemProp.http.proxyHost=192.168.6.136

systemProp.http.proxyPort=808

systemProp.https.proxyHost=192.168.6.136

systemProp.https.proxyPort=808
```

\# 需要验证时

```
systemProp.https.proxyUser=userid

systemProp.https.proxyPassword=password
```

 

\# 直接连接而不走代理设置

```
systemProp.https.nonProxyHosts=localhost
```

### 对单个项目设置代理

在项目根目录下gradle.properties 文件中，添加以上内容即可。

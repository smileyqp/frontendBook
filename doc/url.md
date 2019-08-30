# 从 URL 输入到页面展现背后发生的事

##### 基本概念
 - URL（Uniform Resource Locator 统一资源定位符
 - 常见的协议有：http（最常见的网络传输协议）、https（进行加密的网络传输协议）、file（本地文件夹协议）、ftp、telnet 
 -  DNS（Domain Name System 域名系统）——用来记录域名和 IP 地址相互映射的信息。

##### 基本流程概述
  - 输入URL
  - 浏览器查找域名对应的 IP 地址
    - 查找浏览器缓存
    - 查找系统缓存
    - 查找路由器缓存
    - 查找 ISP DNS 缓存
 
 - 浏览器根据 IP 地址与服务器建立联系;web server处理请求
 - 浏览器与服务器通信
    - 服务器返回了 html 字符串给浏览器，此时，浏览器将会对其进行解析、渲染并最终绘制网页
    - 加载（自上而下对html 页面加载；同时进行解析、渲染处理；遇到 link 标签、image 标签、script 标签时，再次请求获取资源）
    - 解析、渲染(生成 dom 树;并且将dom树可视化处理)
    - 绘制网页

##### 简而言之：
 - 输入网址回车
 - 域名解析到对应IP
 - 服务器webserver处理请求
 - 返回html字符串
 - 浏览器解析渲染
 - 遇到link、image、script等继续请求返回

> 博客地址：[smileyqp's Blog](https://blog.csdn.net/qq_34273059)
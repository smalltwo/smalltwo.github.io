---
title: interview
date: 2020-08-17 09:23:46
---

## 面试题汇总

### 能不能说一说XSS攻击？

#### xss介绍
XSS是跨站脚本攻击(Cross Site Scripting)。恶意攻击者往Web页面里插入恶意Script代码，当用户浏览该页之时，嵌入其中Web里面的Script代码会被执行，从而达到恶意攻击用户的目的。

#### xss 危害

1.窃取网页浏览中的cookie值(http-only保证cookie不能被滥用)
2.劫持流量实现恶意跳转
3.配合csrf攻击完成恶意请求

#### 分类
1. 反射型xss, 非持久型 服务端拼接
2. 存储型xss, 持久型
3. dom型 非持久型 客户端拼接

##### 反射型
通过url的方式传递给了服务器，而服务器则只是不加处理的把脚本“反射”回访问者的浏览器而使访问者的浏览器执行相应的脚本。
##### 储存型
服务器再接收到我们的恶意脚本时会将其做一些处理

#### 防范
1. 过滤
2. 编码
3. 限制

#### 其他防范措施
1. csp
2. 输入内容长度控制
3. http only 验证码

##### 个人观点
4. 通常情况下react 不会出现这种问题，因为react 不会用innerhtml插入文本
5. dangerouslySetInnerHTML 会有这种问题 所以需要进行转义一下
   
> 参考[!https://tech.meituan.com/2018/09/27/fe-security.html]
   
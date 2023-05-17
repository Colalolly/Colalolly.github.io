---
layout: post
title: 微博自动签到脚本
category: Proj

---

经常忘记超话签到,三四年虽然签了Todo天，但是相比之下每天上线点点有点烦了，所以突发奇想写个脚本。正在学Java，就使用Java编写吧。  
<!--excerpt-->
签到实际上是一个向服务器提交参数的过程，所以使用get方法就能够完成。

签到操作完成的前提是

1.    用户已经登录
2.    能够确定要签到的超话
3.    得到get方法需要的URL和其他参数
4.    进行签到时要携带用户账号信息  

根据以上的条件，可以确定需要采集的数据和进行的操作。  

用户登录需要**认证**，需要提供的数据包括Account和Pasword  

确定需要签到的超话，由于这里只有一个超话需要签到，直接通过超话页面获取参数。  

微博超话页面的URL"weibo/p/xxxx"中的xxxx即是超话id  

签到动作对应的URL可以通过在浏览器控制台查看，超话的API是http://i.huati.weibo.com/aj/super/checkin，  

用户信息的携带通过get方法参数设置  

代码已经发布到：

---

To be continued

---



参考  
[misc/weibo-chaohua-signin.js at master · kaleofeng/misc (github.com)](https://github.com/kaleofeng/misc/blob/master/soulsign/weibo/weibo-chaohua-signin.js)


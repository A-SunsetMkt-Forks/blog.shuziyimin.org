# 48 Cloudflare Email Routing 服务如何配置

Clouflare 是世界用户量最大的 CDN 服务商，截止 2022 年 1 月，有 4 百万用户，7.6 万网站使用 Cloudflare 的服务。Cloudflare 主要提供 DNS 解析、网络安全 DDOS 防护、CDN 等网络相关的服务，因为基础套餐均免费，所以用户众多。

除了 DDOS 防护和 CDN，Cloudflare 近年新业务扩展迅速，如 Cloudflare Registrar 域名购买服务，Cloudflare R2 对象存储服务等。本文主要介绍 Cloudflare Email Routing 即邮箱转发服务，对于有个人域名的来说，可以用企业邮箱服务或者[邮箱转发服务](https://shuziyimin.org/tools.html#privacy-mail-forwarder-8-1)来创建自定义域名邮箱。既然 DNS 解析服务商直接提供了免费且配置简单的服务，干嘛不去试下呢？

# 1. 使用 Cloudflare 作为默认的 NS 服务商
如果你的网站已使用 Cloudflare 作为域名解析服务商，请直接看第二步。
如果使用域名购买服务自己的 DNS 解析，或者使用其他的服务商，请自行斟酌是否要将 DNS 服务商换为 Cloudflare，官网提供了相关教程。
[https://support.cloudflare.com/hc/en-us/articles/205195708-Changing-your-domain-nameservers-to-Cloudflare]()

#  2. 添加 Cloudflare 的 MX 记录
Cloudflare Email Routing 目前仍处于公测状态，点击申请公测 “Request Access” 一般会在3天左右收到邀请公测的邮件。

DNS 解析记录如果之前有 MX 记录，需要先删除，然后点击一键导入 Cloudflare 自家的 MX 服务器信息。

# 3. 配置 Cloudflare Email Routing

3.1 Custom addresses 自定义邮箱地址
直接填写自定义的前缀，以及转发邮箱地址即可。需转发邮件地址会收到一封验证邮件。

3.2 Catch-all address 所有地址
配置这个后，所有
比较在乎隐私保护的朋友可以勾选这个，比如在注册各种网站服务时使用对应名字的邮箱。使用 craft，那就用 craft@shuziyimin.org; 注册 disney+ 就是用 disney@shuziyimin.org。 

3.3 Destination addresses 配置
Destination addresses / 转发地址 是同一个 Cloudflare 账户共享的。同一个 Cloudflare 账户下，如果你在配置域名 A 邮件转发的时候验证了 邮件地址 test@shuziyimin.org ，那配置域名 B 邮件转发时可以直接 test@shuziyimin.org，无需再次验证。

# 4. 使用自定义域名发邮件
自定义域名除了用来收邮件，一样可以用于发邮件。 
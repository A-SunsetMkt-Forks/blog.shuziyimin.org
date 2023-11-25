# 48 如何使用 Cloudflare 配置域名邮箱收发邮件

Clouflare 是世界上用户量最大的 CDN 服务商，截至 2022 年 1 月，已有 4 百万用户。Cloudflare 主要提供 DNS 解析、网络安全 DDOS 防护、CDN 等网络相关的服务，因为基础服务免费，所以用户众多。除了 DDOS 防护和 CDN，Cloudflare 近年新业务扩展迅速，如 Cloudflare Registrar 域名购买服务，Cloudflare R2 对象存储服务等。
本文主要介绍 Cloudflare Email Routing 邮箱转发服务的使用，有个人域名的朋友，可以用企业邮箱服务或者[邮箱转发服务](https://shuziyimin.org/tools.html#privacy-mail-forwarder-8-1)来创建自定义域名邮箱。既然 DNS 解析服务商直接提供了免费且配置简单的服务，干嘛不去试下呢？

# 1. 使用 Cloudflare 域名解析服务
如果你的域名已使用 Cloudflare 作为域名解析服务商，请直接看第二步。
如果仍在使用域名注册商自带的 DNS 解析，或使用其他服务商，请自行斟酌是否要将 DNS 服务商换为 Cloudflare，切换后可能会导致国内访问较慢，不支持同时使用多个域名服务商等。如果确定要切换，可以查看 Cloudflare 官网[教程](https://developers.cloudflare.com/dns/zone-setups/full-setup/setup)进行操作。


# 2. 添加 Cloudflare 的 MX 记录
在 Cloudflare 后台点击 Email 即可开始配置（新版本菜单栏在左侧，与下文的图稍有区别）。点击添加记录即可一键导入 Cloudflare 自家的 MX 服务器记录信息。
DNS 解析记录中如果添加过其他邮箱服务商的 MX 记录，**需要先删除原有 MX 记录**。
![](https://static.shuziyimin.org/48-03.png)

 
# 3. 配置 Cloudflare Email Routing

**3.1 Destination addresses （目标地址）配置**
这里我们首先配置目标邮箱地址。填入目标邮箱地址后，目标邮箱会收到来自 Cloudflare 的验证邮件，点击邮件的链接，即可验证成功。 

Destination addresses 目标地址是同一 Cloudflare 账户下所有域名共享的。同一个 Cloudflare 账户下，如果你在配置域名 A 邮件转发的时候验证了邮件地址 test@shuziyimin.org ，那配置域名 B 邮件转发时可以直接填入 test@shuziyimin.org，无需再次验证。

![](https://static.shuziyimin.org/48-04.png)

**3.2 Custom addresses 自定义地址**
添加且验证目标邮箱后，在配置这里时，填入自己想使用的域名前缀，指向目标邮箱即可。

**3.3 Catch-all address 所有邮箱地址**
配置 Catch-all 后，无论邮箱前缀是什么，所有发给该域名的邮件都会转发到指定目标邮箱。
比较在乎隐私保护的朋友可以使用这个服务，比如在注册各种网站服务时用服务名称临时编个前缀，注册 craft 时就用 craft@shuziyimin.org；注册 disney+ 时就用 disney@shuziyimin.org。 这样收到垃圾邮件时，可以知道是哪家服务商把你的信息泄露了，也可以根据收件人来拒收邮件。 

# 4. 使用自定义域名发邮件
对于大部分用户来说，完成上述步骤使用自定义域名进行收件即可。如果有使用自定义域名发邮件的需求，请查看下面教程，这里以 Gmail 为例。 

备注：此方法仅适合个人偶尔使用，不适合商业或者大范围使用。使用 Gmail 等个人邮箱替代域名邮箱来发，会被很多收件箱识别为垃圾或者钓鱼邮件。**如果有商用需求，请选择大型邮件服务商，商用发件服务已在事实上被大机构垄断。**

**4.1 获取谷歌账户专属应用密码**
在浏览器新窗口打开下方链接，登录谷歌账户后，即可在谷歌应用密码配置页面获取一个新的专属应用密码。“设备” 可以选择其他，然后自己填入自定义信息方便记忆，如下图，我写入了 “SZYM-test”来给这个新应用密码备注。获取密码后记得先保存。
[https://myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords)


![](https://static.shuziyimin.org/48-11.png)


**4.2 配置 Gmail **
在  Gmail 设置 - Accounts and Import 中，找到发送邮件的位置，点击“添加新邮箱地址”，如下图所示。
![](https://static.shuziyimin.org/48-05.png)
点击添加新邮箱地址，会出现下图弹窗。
- 邮箱名字会用于之后发邮件的默认名，会对外展示，请慎重填写。
- 域名邮箱地址，请事先在 Cloudflare 中配置此前缀域名邮箱，确认可以接收邮件

![](https://static.shuziyimin.org/48-06.png)
进入下一步，
- SMTP 需要填写 smtp.gmail.com
- port 端口保持默认即可，如果需要变更协议，端口需要做相应变更
- username 填写原本 Gmail 的用户名，即邮箱地址中除去 @gmail.com 之外的信息
- password 需要使用在步骤 4.1 中获取的专属应用密码 

![](https://static.shuziyimin.org/48-07.png)

如果上述信息填写成功，即可进入下一页面，Gmail 会收到一封邮件，填入对应的验证码即可。
![](https://static.shuziyimin.org/48-08.png)

配置完成后，发送邮件时就可以选择自定义邮箱了。也可以在 Gmail 设置中将此邮箱地址作为默认发件地址。
![](https://static.shuziyimin.org/48-09.png)


# 16 Youtube 后台播放，还有这些免费的办法可以一试

后台播放大概是很多 YouTube 用户或多或少需要使用的功能了。

<!-- more -->

# 首先，[Youtube Premium](https://www.youtube.com/premium)  了解一下？

[Youtube Premium](https://www.youtube.com/premium) 是YouTube 会员服务。有去广告，视频下载，后台播放，YouTube音乐会员，独家剧作五大权益，11.99 美元一个月。如果只是偶尔使用后台播放，这个价格还是比较贵的。同时，YouTube Premium 家庭共享是 [Google 家庭共享](https://families.google.com/families)的一部分，不建议和非家人好友共用家庭套餐。

下面进入正题，介绍 Android 和 iOS 平台可以免费后台播放 YouTube 的方法。
Android 平台可以使用浏览器获取桌面版网站。也可以用一些开源第三方客户端。
iOS 平台只能通过 Shorcuts/「捷径」 的办法跳转播放器实现。

# 1.  Android

## 1.1 Chrome/ Firefox 浏览器
![01](https://cdn.shuziyimin.org/blog-16-01-1564982155.png)

Android 平台上，使用 Chrome/ Firefox 浏览 YouTube 时，选择获取桌面版网站，即可通过上拉通知栏进行后台播放。


## 1.2 Youtube 第三方客户端 [NewPipe](https://f-droid.org/en/packages/org.schabi.newpipe/)
 
 ![02](https://cdn.shuziyimin.org/blog-16-02-1564982158.png)
 
 虽然 Google 收紧了政策，Google Play 上已经没法找到好用的 YouTube 客户端了，但仍有开源软件一直更新。 [NewPipe](https://f-droid.org/en/packages/org.schabi.newpipe/) 是一款开源免费的 YouTube 客户端，主打后台播放和浮窗播放功能，可以长按视频的缩略图，将视频加入后台播放列表。APP 下载地址是 F-droid.org ，最新更新时间是2018年10月。
 
优点：有选择清晰度、浮窗播放、后台播放等功能。
缺点：无法登陆YouTube，需要手动导出订阅频道等数据，再导入至 NewPipe

## 1.3 Youtube Music 第三方客户端 [Ymusic](https://labs.xda-developers.com/store/app/com.kapp.youtube.final)

![03](https://cdn.shuziyimin.org/blog-16-03-1564982159.png)


Ymusic 主打听音乐，功能十分强大。可以通过登陆 Google 账户来授权获取已赞视频、保存的视频列表等。界面截图如上。下载地址来自 XDA Labs，是 XDA 为保护开发者而提供的应用商店，避免 APP 被审核/下架。APP 最新更新时间为2018年12月。

优点：可能是安卓平台上最好的免费 YouTube音乐播放器。
缺点：因为是主打音乐播放，所有视频资源都会以音频形式播放，。


# 2. iOS 用户

在 iOS 12上， Safari，Chrome，Opera，海豚浏览器 等各类浏览器都无法通过使用访问桌面版 YouTube 来后台播放。Firefox 测试成功过，但功能不稳定，暂停后无法通过调用系统播放器再次开始。

## 2.1 [nPlayer 播放器](https://itunes.apple.com/us/app/nplayer-lite/id1078835991?mt=8)

nPlayer 作为 iOS 上的老牌播放器，可以直接播放链接。所以这里的思路是，复制 YouTube 链接，把链接转换为nplayer scheme url，打开自动跳转 nPlayer 播放，nPlayer 可以后台播放视频。

Workflow 下载请点[此处](https://workflow.is/workflows/71f824d0e5a64a069bd0abf554a85abb)。实测 [nPlayer](https://itunes.apple.com/us/app/nplayer-plus/id539397400?mt=8) 和 免费的 [nPlayer lite](https://itunes.apple.com/us/app/nplayer-lite/id1078835991?mt=8) 均可使用。

![04](https://cdn.shuziyimin.org/blog-16-04-1564982160.png)

使用流程如下
1. 复制 YouTube 链接
2. 点击 Workflow 
3. 播放
4. 锁屏后可以直接控制播放

nPlayer 通过URL Scheme 的方式只能播放单个视频，无法播放表单和直播。如有其他播放需要，也可以在 nPlayer 内置浏览器打开视频。

如您有其他好用的方法，欢迎在评论区讨论。



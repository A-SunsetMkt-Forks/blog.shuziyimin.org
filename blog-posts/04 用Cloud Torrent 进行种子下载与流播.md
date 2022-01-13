# 04 用Cloud Torrent 进行种子下载与流播

虽然 Netflix 和 国内视频网站的普及带来了很多资源，但是总有各种影视资源需要下载，除了美剧电影当然还有各种小黄片。迅雷也是不争气，到处都是违规资源，加之会员离线下载次数在最新版上被限制到了60次。所以如果有个搭梯子的 VPS，利用闲置资源闲置下载种子就很方便了。

# Cloud Torrent  简介

cloud torrent 是一个go 语言写的离线下载客户端，安装在 VPS 上，可以通过网页方便的进行任务管理和下载。离线下载完成的资源可以通过 HTTP 下载到本地。github 地址在[此](https://github.com/jpillora/cloud-torrent)。 

<!-- more -->

# Cloud Torrent 安装
很多教程都有一键安装版本，也有 docker 版本十分方便。我偷懒，用的是 hyperapp，一款 管理 VPS 的iOS客户端，可以一键通过docker 安装脚本。当然如果有自己的域名，也可以绑定域名。更具体的教程可以参见 Hyperapp 的[官方文档](https://www.hyperapp.fun/zh/Bt.html)。
![](https://cdn.shuziyimin.org/blog-04-01-1564981238.jpg)


在浏览器中输入 VPS地址：端口即可打开，例如 192.168.1.1:666
界面十分简洁，右上角三个按钮代表 **配置**，**下载** 和 **文件管理**。

# Cloud Torrent  配置

![digital\_immigrant\_04\_clooud\_torrent\_02](https://cdn.shuziyimin.org/blog-04-01-1564981238.jpg)


图中的允许做种功能，需要关闭。不然 VPS 流量会被跑完的 不要问我怎么知道的 🙈

# Cloud Torrent 下载 和 文件管理

最上面输入框输入链接下载；

cloud torrent 支持磁力链接。虽然不支持电驴，但是输入ed2k 链接，依旧会在已有资源中搜索对应文件。使用了几次搜索结果不理想，如果需要大规模加速下载电驴链接的话（对，我是说看小黄片），只能使用 115网盘了。

中间是任务状态，国外的种子速度十分快，经常在 10M/s；
 
下面是文件状态，点击文件名称前 **文件夹那个小图标**，可以查看下载后的内容。可以点击视频文件直接下载，也可以复制链接在其他下载工具里下载。最棒的是可以直接把视频链接复制到其他播放器进行流播哦。
![](https://cdn.shuziyimin.org/blog-04-03-1564981278.jpg)


# 直接播放视频

 很多视频播放器都支持输入链接直接播放，并且支持导入外挂字幕。

MacOS 上的 [IINA播放器](https://lhc70000.github.io/iina/)， Windows 上的 [Pot player ](https://potplayer.daum.net/) ， iOS 上 [Nplayer lite](https://itunes.apple.com/cn/app/nplayer-lite/id1078835991?mt=8) 都是不错的选择。这三个播放器都试用了，没有问题，倒是 Windows 上的 QQ影音 出现无法播放的情况。

![](https://cdn.shuziyimin.org/blog-04-04-1564981295.jpg)




# 29 如何绕过英文媒体付费墙 含NYT WSJ Economist

国外的多数专业媒体都需要付费订阅。当然多数也都提供一些免费阅读的额度。此篇文章介绍一些 “绕过” 付费墙的办法。适合专业媒体的非重度用户使用。

## 1. 付费墙的类型
付费墙/收费墙 (Paywall) 是个形象的比喻，是指内容发布者把内容放在墙的后面，需要付费才能获取。实际操作中，为了兼顾流量和营收，内容发布者的绝大部分的文章都可以有条件的免费访问。这里先简单介绍英文主流媒体常用的付费墙形式。

![](https://cdn.shuziyimin.org/blog-42-01-1565882332.png)

**Hard Paywall**
几乎所有内容都需要登录账号且订阅后才能阅读，仅有部分对自己内容十分有信息的内容服务商才采取这样的做法。
- 典型代表：The Wall Street Journal (WSJ)， Financial Times (FT)
- 绕过办法：基本无法绕过。可关注这些媒体的社交网络账号，阅读部分免费分享的文章。

**Metered Paywall**
付费文章限额阅读；阅读时常有弹窗或者横幅提示本月只能阅读5篇等文字。多数内容发布者使用这种做法，兼顾流量与营收。
NewYork
- 典型代表：The New York Times (NYT)
- 绕过办法：使用插件/打开隐私窗口等，下文有详细介绍

**The hybrid model**
也有媒体将上面两种方式结合在一起：部分内容免费；部分内容付费，未付费用户有额度限制；还有一部分付费内容必须登录账号订阅后才能阅读。这种方式要求较强的内容运营能力。


## 2. Windows Mac 等桌面端绕过付费墙
**2.1 安装浏览器插件 Bypass Paywalls**
[Firefox 版本](https://github.com/iamadamdev/bypass-paywalls-firefox) | [Chrome 版本](https://github.com/iamadamdev/bypass-paywalls-chrome)

此插件原理是及时清除主流新闻网站的 COOKIE，并把流量来源改为 Google，一般新闻网站就会将你当作新用户，这样就可以**合理多次使用**每月几篇文章的限额。因为此插件不符合 Chrome Web Store 的相关规则，无法上架。

下面简述安装过程：
- 在 GitHub 项目的 [Readme 页面](https://github.com/iamadamdev/bypass-paywalls-firefox/blob/master/README.md)点击 **download and install the latest version** 下载插件
- 在 Chrome 中打开地址 `chrome://extensions/` ，点击页面右侧，启用开发者模式
- 解压下载的安装包，将解压后的文件拖入 Chrome 扩展页面，即可安装

[](https://cdn.shuziyimin.org/blog-42-02-1565882332.png)

- 若在各个新闻网站没有账号登录，建议全选所有网站；若已付费订阅部分媒体，请在列表中取消勾选已订阅的媒体。
- 此插件开发者建议配合安装另一款 [uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm) 去广告插件，配合使用效果更佳。

![](https://cdn.shuziyimin.org/blog-42-03-1565882333.png)



**2.2 使用隐私模式打开**
在隐私窗口打开也是一个很方便的选择。因为操作步骤极为方便，包括 NYT 在内的部分新闻网站已经禁止用户使用隐私窗口。这些网站通过名为`filesystem` 的 API 接口检测用户是否开启了隐私窗口，在 2019年6月新发布的 Chrome76 最新版中，用户可以自定义此 API 的设置，网站就无法检测此 API 检测到用户是否打开了隐私窗口。教程如下：
- 升级 Chrome 到最新版 （76及更高版本）
- 复制右侧网址到 Chrome 中 `chrome://flags`
- 搜索关键字 filesystem
- 将 `Filesystem API in Incognito` 的选项 由 `Default` 改为 `Enable` 
- 重启浏览器后即会生效
- 你可以在隐身模式下访问 [此网站](https://jsfiddle.net/w49x9f1a/)来验证是否生效。

![](https://cdn.shuziyimin.org/blog-42-04-1565882334.png)

媒体因为自身利益，会通过各种技术手段检测访客是否开启了隐私窗口绕过免费额度限制。使用 filesystem 检测只是其中一种办法，其他[方法](https://mishravikas.com/articles/2019-07/bypassing-anti-incognito-detection-google-chrome.html)一样可以检测。长久来看，这应该是技术上猫鼠游戏了。


**2.3  [Outline.com](https://outline.com/)**

Outline.com 是一项免费的阅读服务，将需要阅读的网址填入后，Outline 会自动过滤各种广告与插件，仅展示内容。类似在 Pocket 等稍后读软件中阅读文章的样子，区别在于，使用 Pocket 绝大部分时候无法绕开新闻网站的限制。下图是本站的文章在 Outline 的展示情况，所有广告与多余的插件都被清除了。

![](https://cdn.shuziyimin.org/blog-42-05-1565882334.png)

以上三个简单的方法就能够帮助你绕过绝大部分主流媒体的付费墙了。进阶版会涉及修改 Javascript 等，不在本文讨论范围内。

## 3. Android iOS 等移动端绕过付费墙

FT， Bloomberg， Economist 等优质内容在移动端都是需要付费才能使用 App 的，基本不提供免费内容。对于重度用户，只能为专业内容付费了。对于轻度用户，关注 Facebook / Twitter 账号是个不错的方法。Twitter 用户还可以把同类型的专业媒体加入同一个 list，当作固定的信息来源。

**3.1 隐私窗口 与 搜索标题**
根据个人使用经验，iOS 使用 Safari 的阅读模式，与隐私窗口就可以阅读绝大部分的付费内容。
复制标题，在 Google 中搜索打开，同样能解决一部分的情况。

个人常通过 Twitter Feed 阅读各类付费媒体，以下是个人经验。
-  [Bloomberg](https://www.bloomberg.com/) 付费文章限额用完后，复制链接在隐私窗口打开即可绕过。
-  [FT](https://www.ft.com/) 隐私窗口常无效，使用下文中介绍的 shortcuts 可绕过。
-  [WSJ](https://www.wsj.com/) 隐私窗口常无效，使用下文中介绍的 shortcuts 可绕过。
-  [Economist](https://www.economist.com/) 隐私窗口常无效，最有效的办法是：隐私窗口 - 在搜索引擎中搜索文章标题，打开页面。
-  写这一段时候好心酸，没钱的人只能用时间来换钱。😭

**2.3  [Outline.com](https://outline.com/)**
同上，不赘述。

因为在移动端复制的链接常含有各种参数，也有可能是 AMP链接，所以 outline 有时候无法识别。没有在桌面端使用方便。


**3.3 iOS 设备 |  [Bypass Paywall](https://www.icloud.com/shortcuts/e0f1b6e1b3094293ab59bb2b63c1694b) Shortcuts 捷径**

iOS 设备也可以通过捷径绕过付费墙。新闻媒体常对来自 Facebook/ Twitter 等来源的用户提供免费阅读，而此 shortcuts 的原理也是将链接模拟成从 Facebook 访问。iOS 13 中，Shortcuts 在 Safari 分享菜单中的权重提高很多，此方法可以一试。（备注：iOS13 在 Safari 中使用此 shortcuts 可能会闪退，直接打开 shortcuts app，复制文章链接后打开浏览器正常。）

以下是使用教程
- 从 App Store 安装 shortcuts/ 捷径
- 点击右侧链接导入 shortcuts | [链接](https://www.icloud.com/shortcuts/e0f1b6e1b3094293ab59bb2b63c1694b) 
- 安装完成后，复制网址，点击 shortcuts 即可。



参考链接：
- [How to shift towards a paywall: a detailed guide](https://contentinsights.com/how-to-shift-towards-a-paywall-a-detailed-guide/)
- [How to Get Around Newspaper Paywalls in 2019 (UPDATED 5/2)](https://medium.com/black-edge-consulting/how-to-bypass-virtually-every-news-paywall-705602c4c2ce)
- [How to Get Past Paywalls in Chrome's Incognito Mode](https://lifehacker.com/how-to-get-past-paywalls-in-chromes-incognito-mode-1835513589)
- [Shortcuts Focus: how to work around publication paywalls to read articles for free](https://www.idownloadblog.com/2019/01/09/bypass-article-paywalls-apple-shortcuts-howto/)


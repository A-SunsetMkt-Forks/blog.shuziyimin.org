# 23  如何批量下载 Tumblr 博客内容/点赞内容

Tumblr 突然宣布[不再允许](https://tumblr.zendesk.com/hc/en-us/articles/231885248-Sensitive-content)用户发布任何裸露身体/色情内容。很多人可能需要备份自己在 Tumblr 上的内容了。

<!-- more -->

## 1. Windows 客户端： [TumblThree](https://github.com/johanneszab/TumblThree)

TumblThree 是 Windows 上一款开源软件，支持下载各种类型的 Tumblr 内容，十分全能，且官方[中文文档](https://github.com/Emphasia/TumblThree-zh)十分清晰。

**下载安装**
- [Github 下载地址](https://github.com/johanneszab/TumblThree/releases)
- 下载后解压，双击 exe 文件即可使用。

![25-1-tumblrthree-1](https://cdn.shuziyimin.org/blog-25-3-1565522920.png)

上图是使用界面，所有的操作按钮都在最下方一排。

**添加任务**
左侧输入Tumblr 地址即可添加入下载列表。
- 若需要下载某个博客的所有内容，输入地址即可， 如 `http://applemusic.tumblr.com/`
- 若需要下载某个用户的所有点赞内容，输入如下地址即可， 如 `https://www.tumblr.com/liked/by/username` 把其中的 username 替换为对应的用户名即可。若下载自己点赞的所有内容，请保证自己的已赞内容是公开可见的，可在此页面设置： `https://www.tumblr.com/settings/blog/username` (需将username 替换为自己的用户名)。
- 其他类型内容请参考[官方文档](https://github.com/Emphasia/TumblThree-zh)

**开始任务**
选中任务，点击 Crawl 即可进行爬数据并自动开始下载。
添加任务成功后，即可进行操作。选中此任务，最下方按钮若为深色，则可以进行该操作。

**其他设置**
默认下载地址在此程序文件夹中，可以右键任务列表查看所在文件夹。

**配置代理**
Tumblr 在中国无法直接访问。若是 Windows 10 系统，可在开启 shadowsocks 后更改系统代理设置。如下图，注意不同代理软件有所差异，端口可能不是1080。

![25-2-windows-proxy](https://cdn.shuziyimin.org/blog-25-2-1565522915.png)


## 2. Mac 平台的 [tumblr-lks-downldr-cli](https://github.com/andrscrrn/tumblr-lks-downldr-cli)

Mac 平台没有全功能的 Tumblr 下载工具，较好用的是 tumblr-lks-downldr-cli 。从名字就可以看出，这是一个下载 Tumblr 点赞内容的命令行工具。虽然很多[工具](https://github.com/neuro-sys/tumblr-likes-downloader)通过用户申请开发者API，就可以帮助用户下载已点赞内容，个人未试用成功，所以推荐这个命令行工具。注意，此命令行工具只能用于下载 已点赞内容中的图片，无法下载视频。

**安装**
安装[node.js](https://nodejs.org/en/) 过程省略。

终端/Terminal 中输入
`npm install -g tumblr-lks-downldr-cli`

**输入命令即可下载**
`tumblr-lks-downldr-cli -u 'andrscrrn.tumblr.com' -l 1000 -p  /Users/bates/Desktop` 

andrscrrn.tumblr.com  应替换为自己的 Tumblr 地址
- 数字 1000 代表点赞的 Post 数量，如需下载全部，输入一个比点赞Post 数量更大的数字 即可。
- 默认所有图片就被下载到 /Users/username (每个人名称不一样)，`-p  /Users/bates/Desktop` 这个参数可以用来自定义下载路径。
![](https://cdn.shuziyimin.org/blog-25-3-1565522920.png)


**为终端（Terminal）配置代理**
同样，考虑国内网络问题，需要为终端配置代理才能下载。

- 方案一：使用 VPN，不是 socks 类代理软件。

- 方案一：使用 [Surge](https://nssurge.com/) ：开启增强模式 ，选择全局代理模式，即可为终端进行代理，甚至无需针对进程添加代理规则，十分方便。Surge Mac 版本是付费软件，可试用 30天。

- 方案二：安装第三方库来为node 进行代理。npm 虽然可以配置代理，但是node 本身并没有网络代理相关的设置。tumblr-lks-downldr-cli 作为一个基于 Node.js 的第三方工具，本身也不提供代理。解决办法只能是 改代码 或者 安装第三方库，可以尝试 安装[global-tunnel-ng](https://www.npmjs.com/package/global-tunnel-ng) ，未使用。过程太艰难了，我不是一个程序员好不好 🤦‍♂️

## 3. Mac 平台的[ Tumblr like exporter](https://github.com/easychen/tumblr-like-exporter)

**使用**
此工具可下载点赞的图片及视频。
[中文说明](https://github.com/easychen/tumblr-like-exporter/blob/master/README_CN.MD)十分详细，不赘述。

**为终端（Terminal）配置代理**
- 方案一：使用 VPN，不是 socks 类代理软件。

-  若使用socks 类代理软件，可在终端中输入以下命令
`export all_proxy=socks5://127.0.0.1:1086`
仅对当前终端有效；同时需要注意不同代理软件端口不一样。

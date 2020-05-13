# DoChat /dɑɑ?t??t/ 盒装微信

[![Docker](https://github.com/huan/docker-wechat/workflows/Docker/badge.svg)](https://github.com/huan/docker-wechat/actions?query=workflow%3ADocker)
[![Powered By Wine](https://img.shields.io/badge/Powered%20By-Wine-red)](https://www.winehq.org/)

[![dockeri.co](https://dockeri.co/image/zixia/wechat)](https://hub.docker.com/r/zixia/wechat/tags)

DoChat（盒装微信）是一款用于Linux的微信PC Windows客户端。

![DoChat](https://huan.github.io/docker-wechat/images/dochat.png)

> 图片来源: [Docker 101](https://www.docker.com/blog/docker-101-introduction-docker-webinar-recap/) + [Icon Finder](https://www.iconfinder.com/icons/4539886/application_chat_communication_wechat_wechat_logo_icon), Ps-ed by Ruoxin Song

## 荣誉

- [推文](https://twitter.com/newsycombinator/status/1231489594765594625) by Y Combinator [Hacker News](https://news.ycombinator.com/item?id=22395507)
- [标题](https://huan.github.io/docker-wechat/images/oschina-feb-25-2020.png) by [OS China](https://www.oschina.net/)

## 免责声明

我们已经收到用户报告，他们的微信账号在使用本项目后已被禁用，因此请自行承担使用风险：

1. [昨天用了一下最新版的docker镜像立马微信就被封了 #55](https://github.com/huan/docker-wechat/issues/55)

## 用法 ![Powered Linux](https://img.shields.io/badge/WeChat-Linux-brightgreen)

微信PC将通过运行以下命令在Linux桌面上启动

```sh
curl -sL https://raw.githubusercontent.com/huan/docker-wechat/master/dochat.sh | bash
```

只需将上面的一行命令复制/粘贴到终端，然后按回车键。那么微信PC很快就会出现在你的XWindows桌面上。

![DoChat 终端命令](https://huan.github.io/docker-wechat/images/term-dochat.png)

## 特点

它只需要一行shell命令就可以开箱即用！

1. 完美地输入/显示汉字。
1. 使用“Ctrl+V”将复制的图像粘贴到微信`

![DoChat 截图](https://huan.github.io/docker-wechat/images/screenshot-dochat.png)

## 要求

1. 建议使用Linux Ubuntu发行版（DoChat是用UbuntuDesktop19.10开发的）
    1. Debian支持确认 ([#9](https://github.com/huan/docker-wechat/issues/9))
    1. OpenSUSE支持确认 ([#16](https://github.com/huan/docker-wechat/issues/16))
    1. 已确认架构支持 ([#26](https://github.com/huan/docker-wechat/issues/26))
    1. Ubuntu(19.04/18.10/18.04) 应该能够支持
    1. 其他Linux发行版：可能支持
1. Docker (运行 `sudo apt update && apt install docker.io` 为Ubuntu用户安装Docker)

## 环境变量

### `DOCHAT_DPI`

图形屏幕分辨率的DPI比例。

| DPI  | 比例 |
| ---: | :---: |
|  96 | 100% |
| 120 | 125% |
| 144 | 150% |
| 192 | 200% |

默认值: `120`

要放大窗口字体大小，请执行以下操作:

```sh
curl -sL https://raw.githubusercontent.com/huan/docker-wechat/master/dochat.sh \
  | DOCHAT_DPI=192 bash
```

### `DOCHAT_SKIP_PULL`

如果每次启动时都不想为最新版本提取docker图像，可以设置 `DOCHAT_SKIP_PULL` 环境变量.

```sh
curl -sL https://raw.githubusercontent.com/huan/docker-wechat/master/dochat.sh \
  | DOCHAT_SKIP_PULL=true bash
```

如果你下载了 `dochat.sh`:

```sh
DOCHAT_SKIP_PULL=true ./dochat.sh
```

### `DOCHAT_调试`

显示更多调试日志消息.

```sh
curl -sL https://raw.githubusercontent.com/huan/docker-wechat/master/dochat.sh \
  | DOCHAT_DEBUG=true bash
```

### `DOCHAT_微信版本`

使用微信的特定版本.

您可以在 <https://hub.docker.com/r/zixia/wechat/tags>

例如:

```sh
curl -sL https://raw.githubusercontent.com/huan/docker-wechat/master/dochat.sh \
  | DOCHAT_WECHAT_VERSION=2.7.1.85 bash
```

## 对于程序员来说

如果你想自己控制一切，比如在桌面上打开多个微信PC客户端；那么，你可能想查看我们存储库中的 [dochat.sh](https://github.com/huan/docker-wechat/blob/master/dochat.sh) 并尝试以下docker命令:

```sh
docker run \
  --name DoChat \
  --rm \
  -i \
  \
  -v "$HOME/DoChat/WeChat Files/":'/home/user/WeChat Files/' \
  -v "$HOME/DoChat/Applcation Data":'/home/user/.wine/drive_c/users/user/Application Data/' \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  \
  -e DISPLAY \
  \
  -e XMODIFIERS=@im=fcitx \
  -e GTK_IM_MODULE=fcitx \
  -e QT_IM_MODULE=fcitx \
  -e GID="$(id -g)" \
  -e UID="$(id -u)" \
  \
  --ipc=host \
  --privileged \
  \
  zixia/wechat
```

根据你的需要修改它.

## 版本控制

docker映像有两个版本控制模式:

1. `X.Y.Z.a`: This is for the WeChat PC Windows Client version
    1. `zixia/wechat:2.7.1.85`: WeChat 2.7.1.85
    1. `zixia/wechat:2.8.0.112`: WeChat 2.8.0.112
1. `x.y`: 这是docker镜像版本的。.
    1. `zixia/wechat:0.2`: docker-wechat version 0.2

两个版本的模式可能相互重叠

例如: the `zixia/wechat:0.2` 可能与 `zixia/wechat:2.8.0.112` 的图像相同.

## 已知问题

- [ ] 微信2.8.0.x不能发送大图片/文件 ([#341](https://github.com/huan/docker-wechat/issues/31))
  - 解决方法: 改用 [2.7.1.85](https://hub.docker.com/layers/zixia/wechat/2.7.1.85/images/sha256-e6e9d21c7cd1dfae0484e697f12f5f3c401de2f02e771d061868740e0d26549d) instead. (`DOCHAT_WECHAT_VERSION=2.7.1.85`)
- [ ] 在微信浏览器中不起作用 ([#2](https://github.com/huan/docker-wechat/issues/2))

## 待办事项列表

- [x] 微信PC登录数据信息永久存储 ([#3](https://github.com/huan/docker-wechat/issues/3))
- [ ] 生成Dockerfile时，自动从.exe安装程序安装微信PC (可能需要测试自动化工具)
- [ ] 监控微信PC版出版物，以便我们可以发布与docker图像相同的版本号.

## FAQ

### 带有Gnome桌面的系统托盘图标

安装 Gnome 扩展: [Top Icons Plus Git](https://extensions.gnome.org/extension/2311/topicons-plus/) by bijignome

> Note 1: 几乎有六个“TopIcons”扩展名非常相似：TopIcons、TopIcons Redux、TopIcons Plus、**TopIcons Plus Git**、TopIconsFix。使用**TopIcons Plus Git**，它是正确的。  
>
> Note 2: “TopIcons Plus”有一个bug，导致“wine”本身在桌面上显示一个窗口。 ([#19](https://github.com/huan/docker-wechat/issues/19))

### 在openSUSE Leap上使用代码5退出

当您在openSUSE Leap上遇到代码为5的应用程序退出的问题时，您需要禁用X服务器访问控制以允许任何用户在启动应用程序之前连接到X服务器。使用以下命令将其禁用:  

`$ xhost +`

### 启动2个或更多监视器设置后没有主窗口

这可能是由于' wine '中有一个旧的缺陷和多个监视器设置造成的。解决方法是使用单个监视器启动它，然后切换到多个监视器

此行为可能会导致在使用连接显示模式时视图消失，因此需要在应用程序启动时将模式更改为镜像，此脚本可能有帮助:

```Bash
#bin/bash
xrandr --output HDMI-1-2 --same-as eDP-1-1

curl -sL https://raw.githubusercontent.com/huan/docker-wechat/master/dochat.sh \
  | DOCHAT_SKIP_PULL=true bash &

sleep 5
xrandr --output HDMI-1-2 --right-of eDP-1-1
```

将HDMI-1-2更改为外部显示名称，将eDP-1-1更改为内置显示名称。显示两个以上，链接在 [这里](http://www.mikewootc.com/wiki/linux/usage/set_x_reso.html).<br/>***Notice***: 进程休眠5时，必须将登录对话框拖到内置显示端，否则视图可能卡在外部显示中. 

## 链接

- [使用X11Forward时输入法不起作用](https://ubuntuforums.org/showthread.php?t=913752)
- [与输入方法相关的环境变量](https://fcitx-im.org/wiki/Input_method_related_environment_variables)
- [Docker GUI最佳实践](https://github.com/zjZSTU/Containerization-Automation/blob/982d54458b05ef75fe6436f4ea72bbb66c4cb931/docs/docker/gui/%5BDocker%5DGUI最佳实践.md)
- [Linux 下 完美运行 wechat 微信](https://www.kpromise.top/run-wechat-in-linux/)
- [WeChat Linux桌面版](https://ferrolho.github.io/blog/2018-12-22/wechat-desktop-on-linux)

## 历史

### 版本

### v0.10 (2020年3月12日)

1. 将wine从v4.0升级到v5.0
1. 通过带有自动微信版本号的GitHub操作部署到Docker Hub.

### v0.8 (2020年3月3日)

1. 添加新的配置环境变量“DOCHAT_WECHAT_VERSION”以选择微信版本。
1. 添加 微信 v2.8.0.112
    1. 新增订阅号浏览
    1. 新增IPv6网络支持
    1. 新增看一看精选内容
    1. 新增打开聊天中小程序消息
    1. 新增在小程序中使用微信支付
    1. 新增聊天文件面板，可查看和管理所有聊天文件

```sh
curl -sL https://raw.githubusercontent.com/huan/docker-wechat/master/dochat.sh \
  | DOCHAT_WECHAT_VERSION=2.8.0.112 bash
```

### v0.5 (2020年2月24日)

1. 添加环境变量“DOCHAT_DPI”以设置图形屏幕分辨率的DPI比例。
1. 禁用自动更新.

### v0.4 (2020年2月21日)

从我的艺术朋友宋若欣那里得到了一个很棒的标志。.

1. 修复声音 ([#1](https://github.com/huan/docker-wechat/issues/1))
1. 修复升级过程中不退出的问题.

### v0.2 (2020年2月18日)

第一个工作版本，干杯！

### v0.1 (2020年2月17日)

项目创建。

## 感谢

1. [微信Linux桌面版](https://ferrolho.github.io/blog/2018-12-22/wechat-desktop-on-linux) - by [@ferrolho](https://github.com/ferrolho)
1. [Wine HQ 应用数据库-微信](https://appdb.winehq.org/objectManager.php?sClass=application&iId=16931)
1. [基于深度操作系统的微信 docker 镜像](https://github.com/bestwu/docker-wechat) by [@bestwu](https://github.com/bestwu)
1. 由我的朋友宋若馨设计的DoChat标志。

## 相关项目

1. [DoWork /dɑɑ?w??k/ 盒装企业微信](https://github.com/huan/docker-wxwork): Dockerized WeChat Work (企业微信) PC Windows Client for Linux

## 作者

[Huan LI](https://github.com/huan) ([李卓桓](http://linkedin.com/in/zixia)) Tencent TVP of Chatbot zixia@zixia.net

[![Profile of Huan LI (李卓桓) on StackOverflow](https://stackexchange.com/users/flair/265499.png)](https://stackexchange.com/users/265499)

## 版权 & 许可证

- Code & Docs © 2020-now Huan LI \<zixia@zixia.net\>
- Code released under the Apache-2.0 License
- Docs released under Creative Commons

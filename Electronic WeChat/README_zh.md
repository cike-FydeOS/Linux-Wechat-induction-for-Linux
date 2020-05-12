# Electronic WeChat
**注：**以下内容均来自原网站https://github.com/geeeeeeeeek/electronic-wechat


> **⚠️⚠️ NO LONGER IN ACTIVE DEVELOPMENT | 项目不再维护 ⚠️⚠️**
>
> Thanks for supporting this project for **1000** days since Feb 16, 2016.
>
> It started with the idea to make WeChat better on MacOS when the official support was abscent. It was de facto dead when Tencent rolled out a new WeChat and started to block other third-party clients. For me, it's no longer worthwhile to hack a lot to accomplish little. Hope this project had been helpful to you in any way. You're welcome to **fork** or **make copies with a reference.** HAPPY HACKING.
>
> 感谢历史上的用户和贡献者，你们已经陪伴这个项目走过了 **1000** 个日子。我曾经想要打造一个更好的 Mac 微信客户端，因为官方版本几年没有更新、bug 层出。而在腾讯自己开始了定期更新并限制第三方客户端时，这个项目实际已经没有什么意义。这个项目目前作为一个存档供大家学习。希望它曾经对你有所帮助，你也可以 **fork** 或者 **转载（标注来源）** 来进行修改。祝你玩得愉快。
>
> **SPECIAL THANKS TO | 特别感谢**
>
> [Kulbear](https://github.com/Kulbear),
> [arrowrowe](https://github.com/arrowrowe),
> [Rocka](https://github.com/rocka),
> [CC](https://github.com/iamcc),
> [xgdgsc](https://github.com/xgdgsc),
> [死水微澜](https://github.com/ripples-alive),
> [Jason](https://github.com/gzzhanghao),
> [Ce Gao](https://github.com/gaocegege),
> [viko16](https://github.com/viko16),
> [卡晨](https://github.com/awmleer),
> [Ray](https://github.com/ray26),
> [尹良灿](https://github.com/wenLiangcan),
> [gehuangyi20](https://github.com/gehuangyi20),
> [Kevin Tan](https://github.com/stkevintan),
> [Jiaye Wu](https://github.com/wujysh),
> [loufq](https://github.com/loufq),
> [Miaow](https://github.com/miaowing),
> [Chuan Ji](https://github.com/jichu4n),
> [Oaker](https://github.com/cyio),
> [Fengshuang Li](https://github.com/lfs1102),
> [Song Li](https://github.com/boltomli),
> [afon](https://github.com/samurai00),
> [lional wang](https://github.com/3dseals),
> [Haochen Tong](https://github.com/hexchain),
> [Zhuoyun Wei](https://github.com/wzyboy),
> [rivershang](https://github.com/rivershang),
> [Ivan Jiang](https://github.com/iplus26),
> [oBlank](https://github.com/oblank),
> [Cheng Gu](https://github.com/gucheen),
> [NullMDR](https://github.com/NullMDR),
> [ReadmeCritic](https://github.com/ReadmeCritic).
---



[![Gitter](https://badges.gitter.im/geeeeeeeeek/electronic-wechat.svg)](https://gitter.im/geeeeeeeeek/electronic-wechat?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=body_badge)  [![Build Status](https://travis-ci.org/geeeeeeeeek/electronic-wechat.svg?branch=master)](https://travis-ci.org/geeeeeeeeek/electronic-wechat)  [English](README.md)

**Mac OS X 和 Linux 下更好用的微信客户端. 更多功能, 更少bug. 使用[Electron](https://github.com/atom/electron)构建.**

**Important:** 如果你希望在自己的电脑上构建 Electronic WeChat，请使用 [production branch](https://github.com/geeeeeeeeek/electronic-wechat/tree/production)，master branch 包含正在开发的部分，并且不能保证是稳定的版本——尽管 production 版本也有bug ：D

![qq20160428-0 2x](https://cloud.githubusercontent.com/assets/7262715/14876747/ff691ade-0d49-11e6-8435-cb1fac91b3c2.png)

## 应用特性 ([更新日志](CHANGELOG.md))

-  **来自网页版微信的更现代的界面和更丰富的功能**
-  **阻止消息撤回**
-  **显示表情贴纸** [[?]](https://github.com/geeeeeeeeek/electronic-wechat/issues/2)
-  公众号文章支持一键分享到微博、QQ 空间、Facebook、Twitter、Evernote 和邮件
-  拖入图片、文件即可发送
-  群聊 @ 提及成员
-  原生应用体验，未读消息小红点、消息通知等数十项优化
-  去除外链重定向，直接打开淘宝等网站
-  没有原生客户端万年不修复的bug

## 如何使用

在下载和运行这个项目之前，你需要在电脑上安装 [Git](https://git-scm.com) 和 [Node.js](https://nodejs.org/en/download/) (来自 [npm](https://www.npmjs.com/))。在命令行中输入:

``` bash
# 下载仓库
git clone https://github.com/geeeeeeeeek/electronic-wechat.git
# 进入仓库
cd electronic-wechat
# 安装依赖, 运行应用
npm install && npm start
```

根据你的平台打包应用:

``` shell
npm run build:osx
npm run build:linux
npm run build:win
```

**提示:** 如果 `npm install` 下载缓慢，你可以使用 [淘宝镜像(cnpm)](http://npm.taobao.org/) 替代 npm 。

**新渠道:** 使用你熟悉的包管理工具安装。请查看 [社区贡献的镜像](https://github.com/geeeeeeeeek/electronic-wechat/wiki/System-Support-Matrix#%E7%A4%BE%E5%8C%BA%E8%B4%A1%E7%8C%AE%E7%9A%84%E5%AE%89%E8%A3%85%E5%8C%85) 。

**新渠道:** homebrew 安装也已支持 (更新至 electronic-wechat v1.2.0)！

```bash
brew cask install electronic-wechat
```

#### [下载开箱即用的稳定版应用](https://github.com/geeeeeeeeek/electronic-wechat/releases)

#### 项目使用 [MIT](LICENSE.md) 许可

*Electronic WeChat* 是这个开源项目发布的产品。网页版微信是其中重要的一部分，但请注意这是一个社区发布的产品，而 *不是* 官方微信团队发布的产品。

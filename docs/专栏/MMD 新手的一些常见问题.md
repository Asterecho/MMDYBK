> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv1947897?from=search&spm_id_from=333.337.0.0)

> 作者：[白毛鼹鼠](https://space.bilibili.com/12604289)

 新手会遇到的一些基本问题主要是我遇到的问题啦，摸索了几天终于找到了解决办法了，以下是按照我碰到的问题来解释的（个人看 av18499776 学习的啦，就是有些意料之外的问题）1. 导入 ray 渲后闪退. 可能是 m......

**新手会遇到的一些基本问题**

主要是我遇到的问题啦，摸索了几天终于找到了解决办法了，以下是按照我碰到的问题来解释的（个人看 [AV18499776](https://www.bilibili.com/video/av18499776) 学习的啦，就是有些意料之外的问题）

**1. 导入 ray 渲后闪退.**

可能是 mmd 本身的问题，换源下载以下应该就解决了

**2. mme 无法导入或者导入出错.**

路径（和文件名字）不可以有除英文外的字符，否则无法导入，改一下文件夹名字就好了

**3.ray 渲导入后提示‘已阻止应用程序访问图形硬件’**

电脑防火墙设置的问题，Windos Defender——防火墙和安全保护——允许应用通过防火墙——选择 mmd 的路径，就可以啦.

**4. 导入 ray 渲且为模型加载 main.fx 后模型变黑（全黑或者看不见那种，而且 mme 里模型名字是空白）.**

模型的路径（文件夹）不要有日语吧，反正中文我试了没事，英文应该也没事，和文件名称基本没关系.

**5.Skybox（天空盒）加载 lighting 后全屏幕变绿.**

lighting.fx 需要在 EnvLightMap 分栏中载入，而不是 main 分栏.

我遇到的暂且也就这几个问题，主要是我再百度等网站上搜索基本没有得到解决方案，所以希望能帮助到各位吧：）

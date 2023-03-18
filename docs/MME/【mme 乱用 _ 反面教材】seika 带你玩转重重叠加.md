> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv3165343?from=search&spm_id_from=333.337.0.0)

> 标题致敬了 old tomato（？Attention：本文有【大量沙雕的 mme 反面教材操作】出现请在确认自己足够勇敢且敢于面对鬼畜画面的情况下【慎重】阅读此文感谢！请在有成年的 mikumikudance 及 pmdeditor 的监护陪同下观看此文头图借物请见视频的简介：av60826636 好了直接进入正题。

标题致敬了 old tomato（？

**Attention：**

**本文有【**大量沙雕的 mme 反面教材操作**】出现  
**

**请在确认自己足够勇敢且敢于面对鬼畜画面的情况下**

**【**慎重**】阅读此文  
**

**感谢！**

![](http://i0.hdslb.com/bfs/article/8de1e44373f0026762224f3a0c834402f9ba2123.jpg@105w_113h_progressive.webp)请在有成年的 mikumikudance 及 pmdeditor 的监护陪同下观看此文

头图借物请见视频的简介：[AV60826636](https://www.bilibili.com/video/av60826636)

![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)

好了直接进入正题。

昨日我在机缘巧合之下触发了这个 bug，导致了这种奇妙的视觉效果的出现。

![](http://i0.hdslb.com/bfs/article/1073f0de82857282eb687170d70f07d39365b112.png@942w_452h_progressive.webp)重重叠加叠加叠加叠加加加加—— ![](http://i0.hdslb.com/bfs/article/d3210607ac8dcb38d93469054633004f855ee0e9.png@942w_447h_progressive.webp)鬼畜素材（？）

今天我替换了使用的多种 mme，最后找到了这个 bug 的触发途径和解决方法。

**只是个人 memo，并不是教程，慎重模仿！**

**只是个人 memo，并不是教程，慎重模仿！**

**只是个人 memo，并不是教程，慎重模仿！**

首先我搞明白了这个问题的来源，**是ビームマン P 的 post movie（本文使用的是 v10）和そぼろ的 AutoLuminous（本文使用的是 Ver.4.2 的 AutoLuminous.x，注意不是 basic 的那个！！）**神秘化学反应冲突所致。  

这里借用化身バレッタ的空中に漂う埃エフェクト的运动来演示 bug 的发生（？）

首先载入 postmovie（这里使用的是青系），然后载入空中に漂う埃エフェクト，为了方便观看，后者的 si 值我调整到了 3，postmovie 则不作调整，也不载入 controller.pmx 进行控制。

![](http://i0.hdslb.com/bfs/article/3ed3a0cc298655cbc64cd8ce01d2d0bf02ff0359.png@306w_243h_progressive.webp)

现在的效果非常正常【除了载入 mme 并且调整了空中粒子的 si 值没有任何别的操作】。

![](http://i0.hdslb.com/bfs/article/1a72f435af66242c980d4cddc49cb55643f703e0.png@942w_462h_progressive.webp)

现在载入 AutoLuminous.x，依然不作任何调整【其实对参数随便进行调整也完全 ok，这里我懒 x】。拖入之后会稍微卡一小下，然后可以看到直到目前，效果依然很正常对不对？

![](http://i0.hdslb.com/bfs/article/8cceb710db1e1b2ac90c49ec116fd7231e52ab24.png@942w_471h_progressive.webp)

然后魔法来了！

你只需要把 postmovie 的顺序，调整到 AL 之下！！！（不会调 mme 的小朋友上下顺序的请自己搜索 mmd 基础教程 x）  

![](http://i0.hdslb.com/bfs/article/990c7513137afec61bb7c61250c8730cd5399bda.png@468w_371h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/1ca9b17f9716fa94b3de6a0f751a370b0c8b9bbb.png@468w_371h_progressive.webp)

看！！是不是就立刻出来效果了！（以及载入的时候直接先载入 AutoLuminous 然后再载入 postmovie 也是 ok 的~）

![](http://i0.hdslb.com/bfs/article/51a69e88cc20663822f5375e80a0085459cd50ce.png@942w_452h_progressive.webp)

去掉空中粒子的亚子。

![](http://i0.hdslb.com/bfs/article/7c5714556ebc1728647e30976f45256258b8e732.png@942w_447h_progressive.webp)

这个时候，你只要把 AutoLuminous 的显示关掉，你就会发现一切又回归原状惹~

![](http://i0.hdslb.com/bfs/article/37598cd3322d8773f12d42553d41d040ac074a17.png@369w_627h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/6e998e1be669ec7819b0c60d125153a69fa26fb1.png@381w_714h_progressive.webp)

但是如果想同时保持发光 mme 的效果以及 postmovie 的效果，你就需要下面的解决方法：  

加入背景图片文件 / 天空球（.x 和. pmd、.pmx 都无所谓）/ 封闭房间的场景文件（或者开放空间的场景搭配天空球 or 背景图片文件），三种方法都可以~

![](http://i0.hdslb.com/bfs/article/87356191c400292f52ffe0029a343117bb6aec72.png@917w_714h_progressive.webp)图上的效果是我加了纯黑色的背景 png 图片

不过，其实最快的方法就是把 AL 调回到 postmovie 之下 x

![](http://i0.hdslb.com/bfs/article/990c7513137afec61bb7c61250c8730cd5399bda.png@468w_371h_progressive.webp)再发一遍正确效果，以免大家记错了 x

对于这个 bug，有一点就是，残影的浓淡效果是不太好自控的。可以调整 postmovie 的 si 值稍微改变残影的透明度，但是效果一般……？

![](http://i0.hdslb.com/bfs/article/e67671ac0205b46a116c996f92d2d6b782b8d146.png@942w_632h_progressive.webp)

不能更改 ti 值哦，更改 ti 值就会变成这个鬼样 x

![](http://i0.hdslb.com/bfs/article/ebd84e3089a90b4a13159888e26948c4d6d91e97.png@942w_641h_progressive.webp)

以及，如果你想试着使用常见的发光 mme 参数影响残影（如修改 x、Ry 的值，所谓的小清新唯美流渲染常用的发光范围拉长效果），也只能做到如下的效果：

![](http://i0.hdslb.com/bfs/article/dcb4583a85a43b00f58be20e456843fc7c3159e0.png@942w_629h_progressive.webp)残影并不能被 AL 的效果拉长，不过好歹拉长效果并没有消失

嘛，反正这只是个反面教材，大家谨慎看待。也可以自己玩玩看，有了新发现欢迎评论告诉我~

![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)

总之，写这个专栏是想教育大家：

1，mme 的顺序也是很重要的，有的 mme 必须放在最下面，有的则最好放在最上面。有些 mme 的上下组合效果是不一样的（比如大家常用的各种滤镜、还有彩铅效果 mme-PostHatchingShader_v011 和轮廓线 mme-Croquis_v012【这两个都是 Elle / データ P 的】）。

2，不是所有 bug 都是坏的，有时候可以稍加利用。

3，发现 bug 不仅要解决 bug，最好还能思考一下它从何而来，不仅能更好的解决它，说不定还能打开新世界的大门。

4，本文不一定正确，也不能保证这种效果是唯一的。仅做抛砖引玉，以及我并不太推荐大家都跟我一样乱玩 mme（x）

5，强迫症凑整。

感谢大家的观看。

OVER

seika 于 2019.07.26
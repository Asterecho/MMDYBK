> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv1284145?from=search&spm_id_from=333.337.0.0)

> 作者：[夏尔-妮尔娜](https://space.bilibili.com/32262020)

 SeriousShaer，想必大多数人都不认识有这么个渲染先讲一下这个渲染，它配布非常早，2011.01.22 v0.1 公開作者叫做：データ P 关于这个渲染没有太多的特殊介绍，毕竟是好多年前的老产品

**SeriousShaer，想必大多数人都不认识有这么个渲染**

2011.01.22 v0.1  公開

作者叫做：データ P

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

**我们下载到渲染包以后，打开里面有两个 fx 文件，一个是初始预设，一个是有改动的。**

![](http://i0.hdslb.com/bfs/article/201e343fd183a8ce26e01640478e425b44c280bd.png@942w_230h_progressive.webp)**按**  

注：渲染包到 b 碗 / vpvp 下载

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

1. 首先，打开 MMD，载入自己需要的场景和模型，之后到 MME 栏的 Main 板块，找到自己的模型 / 场景，给予挂载 SeriousShader.fx 或 SeriousShaderM.fx，如图

![](http://i0.hdslb.com/bfs/article/ac1a8231303c9af865ef88647161da83e459bcf1.png@942w_387h_progressive.webp)

这样就完成了基本的步奏了，然后再根据自己的喜好添加各类 MME 调节效果就完成了，怎么样，学会没？是不是很简单？

**简单你就输了！！！**

2. 关于 SeriousShader 的 fx 参数讲解【注：**重点**】

这一块知识属渲染中的重点，要求萌新尽量学会。

下面开始讲解 fx 内部参数效果调节，请准备以下软件

![](http://i0.hdslb.com/bfs/article/3b29b6f66bd6d49e65ecd6b5306b4ba15d082861.png@191w_33h_progressive.webp)

Notepad++，可以编辑文本及代码的软件。

下面我们使用 Notepad++，把 fx 打开，如图

![](http://i0.hdslb.com/bfs/article/d04b2c537328a20bda5b69111d518353840ef4ae.png@942w_755h_progressive.webp)

是不是开始头疼了？这些是什么？代码？？叫我写代码？？

没错，这些确实是代码，不过今天不是来教你写代码的【我不会】

我们要学的是去修改，修改什么？很简单，1234567890 会打吧，会那就可以。

我们的目的，是要学会怎么修改 fx 参数的数值大小，打个比方【define   xxxxxxxxxxx   1.0】

看到那个数字了吗？对照我们打开的 fx，我们修的就是那个数字

其实，这些一串串代码的通道，就是控制着 fx 在 MMD 中渲染的效果，而这些数字的值也就决定着效果大小 / 模式 / 开关等。

但是我们要修改，当然要知道，哪一栏代表着什么效果，所以这个不用你们头疼，夏尔已经把 fx 的可修改参数全部列了出来并且说明。

![](http://i0.hdslb.com/bfs/article/a993707c83f708cef6e17516296e7b041e38d103.png@942w_755h_progressive.webp)

框内都是可调节参数，下面夏尔把这些参数的详细信息带翻译列出来

基本参数 -

**#define ShadowDarkness   - 全局明暗度**

**#define UnderSkinDiffuse    - 皮下散乱**

**#define ToonPower   - 阴影的明暗度**

**#define OverBright   - 材质的亮度调节**

**影子校正 -**

**#define SOFTSHADOW_DISTANCE   - 窗口距离，字面意思说越小越远（不见得...）**

**#define SOFTSHADOW_THRESHOLD   - 阴影修真系数，值越大越小（有那么一丁点效果可以看到）**

**阴影贴图的计算大小（越大精度越高，不过看不出来）**

**#define SHADOWMAP_WIDTH 2048**

**#define SHADOWMAP_HEIGHT 2048      （2048 是贴图分辨率）**

由于修改中一部分参数的效果变化很细微以至于截图看不出，这里夏尔放两张例图

![](http://i0.hdslb.com/bfs/article/aae3c2240106885039807d3f08ad60ca953f5244.png@942w_428h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/493afb429e42c9d55d68fe303e9cae91865f41ae.png@942w_420h_progressive.webp)

**会改了吗？其实很简单罢了只是看着头疼，不过还有一点要注意，在修改数值过程中不要乱动那些代码，如果多个字母少个字母或者少个等号少个单词都有可能导致 fx 报废。**

**注意：修改参数以后要点保存才会读取效果！**

**以上是第一个 fx，SeriousShader.fx 的参数讲解  
**

![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)

下面我们来讲解 **SeriousShaderM.fx**  

**为什么要分开讲解呢，明明都是相同预设。**

**SeriousShaderM.fx** **和 **SeriousShader.fx 有些不同，他的 fx 参数多增了一个栏，名叫材质纹理调节，这个栏可以控制 fx 显现的纹理效果。如图****

![](http://i0.hdslb.com/bfs/article/e707391cdbb989b82e9243d5b449663dd36a862d.png@942w_755h_progressive.webp)

那要怎么调节呢？看到这个了吗？这个是材质纹理贴图的分辨率大小，分辨率大家都知道吧，越大越清晰，但是越占内存。

![](http://i0.hdslb.com/bfs/article/f11976c54238c17487e0e4892575028576fb598f.png@803w_138h_progressive.webp)

我们要修改的就是这个分辨率数字，一般数值是这样，256，512,1024,2048,4096,8192

下面给大家参考下修改的例图

![](http://i0.hdslb.com/bfs/article/34edd0517033ce2acd6248a62093040ee4760c86.png@942w_449h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/40e482fdfc9580e44138d3284c6468ad4818f713.png@942w_470h_progressive.webp)

可见，分辨率越大，材质越清晰，但是别忘了我说的，越大越占内存，也就是说...............

电脑不好不要作死。

![](http://i0.hdslb.com/bfs/article/a10fbeda661f51e573ddeb10632ff018af3171e8.png@942w_528h_progressive.webp)

看到这个 fps 你们懂我的意思了吧，电脑显存如果不够高只建议修改到 2048 即可以防卡死，

那关于 SeriousShader 的渲染教程就到这里，下面放几张效果图

![](http://i0.hdslb.com/bfs/article/1eabb5c3d6114134bbbf52a594cfeac2567ade45.png@942w_533h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/d9f42bae0ae4bbb0988207023dc6f9b6445ae425.png@942w_534h_progressive.webp)

封面也算一张

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

**SeriousShader 本属于非常单调的渲染，需要搭配不同的 MME 调节才能有最佳效果，夏尔列出几个**

**HgSAO**

**ExcellentShadow2**

**SvSSAO**

**Lightbloom**

**o_SurplusFilter_v0_3**

**ColorFilterSet_v001**

**Diffusion7**

**搭配以上 MME 使用且灵活调节参数可达绝佳效果**

**以及！！！！！！**

**个人建议将 MMD 中的 RGB 三色都降到 90-105 这个范围**

**虽然 fx 中可以调节光照但低于或高于原数值会很违和，所以直接调节 MMD 的光会好一些**

**当然也可以有自己的方法，不能死板什么都跟着来，万一我掉茅坑呢**

**好了，个人的建议也不多，就这些.**

那关于本期渲染教程就结束了，后续夏尔会抽空写和录更多教程，求关注~

如果对本次教程有什么不解可以私信夏尔

如果发现本期教程有出错的地方，请第一时间提醒夏尔，夏尔会感激到死的！QWQ

下期再见

2018/10/6

![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)

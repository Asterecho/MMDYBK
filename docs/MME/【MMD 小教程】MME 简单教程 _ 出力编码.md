> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv15673576?from=search&spm_id_from=333.337.0.0)

> 作者：[千野](https://space.bilibili.com/27521)

 点击进入查看全文 & gt;

从零开始的伊文 MMDER 调教 第二篇

借物表：

MODEL：吽 - ほのぼ悠琴がけと Pocky - kaz paperguitar.com

STAGE：怪獣対若大将 P  K10

MME：そぼろ 針金 P

**【MME 用法简介】**

MME 基本就 2 种使用方法

环境类的比如 ExcellentShadow（高质量阴影）WorkingFloorAL（地面镜面反射）

把对应的 X 模型拖进 MMD 里就会生效（如果没反应查看右上角的 MMEffect 菜单，将使用特效打勾）

![](http://i0.hdslb.com/bfs/article/19e94e7b6bbcc815c9ebecb7b62c3a9870d10629.jpg@242w_231h_progressive.webp)

在相机帧那里就会出现对应的 MME

![](http://i0.hdslb.com/bfs/article/d07242e6f9694eca58da319c6d809b2e150b060a.jpg@363w_296h_progressive.webp)

一般修改 Si 和 Tr 值就够了，Si 是大小，比如 WorkingFloorAL 就会将反射面扩大

Tr 是透明度，0 时相当于没有效果

渲染类的是第 2 种用法，即给模型套 fx 材质

点击 MMEffect 菜单，点击分配特效，选中模型，右键，就能给模型套渲染材质

![](http://i0.hdslb.com/bfs/article/189be6c5500a8ecded3073570ea904fe4d89ced7.jpg@737w_609h_progressive.webp)

也可以展开子项，给模型的各个部分单独设置材质

比如眼睛用发光材质，头发用毛发材质等

萌新自己琢磨可能蛮难的，推荐看看大佬们的配方或教程

↓我自己的 PS 渲配方

![](http://i0.hdslb.com/bfs/article/card/9516ae32c4bdea4dcbfdc742af103dda39f0ccbf.png)

↓RC 大佬的 RAY 渲教程

![](http://i0.hdslb.com/bfs/article/card/56907393862c53b4f096e191b76065c45c806994.png)

在第一种用法的基础上，有些 MME 自带控制器

比如 ikBokeh（景深）

需要拖入 ikBokeh.x 后，再拖入 ikBokehController.pmx

操控控制器的表情栏来调节景深的数值

↓写的很详细，推荐看看

文章加载失败

一些特殊的 MME 用法都会写在 readme 里，好好看看再摸索一下应该就会用了

实在不懂也可以搜 B 站视频或专栏，大佬们写了好多教程

**【MME 描绘顺序调整】**

点菜单的背景 - 附件编辑

![](http://i0.hdslb.com/bfs/article/9b1949288d85d64eb7e4cc0501d531398d373d03.jpg@575w_462h_progressive.webp)

选中要更改位置的 MME，点旁边的上或下调整

MME 的描绘顺序影响很大，排在下面的 MME 会影响到上面所有的 MME

参考配方时要注意顺序

○数字更后面的附件在模型描绘后

MME 通常在模型后描绘，如果加了天空球或道具的 X 模型（需要在模型前描绘）

那么这些 X 模型必须移到 MME 上面

比如这样

![](http://i0.hdslb.com/bfs/article/9c968b8687ad330e322bcc7fdf83ec90592f4d1c.jpg@579w_468h_progressive.webp)

X 模型的道具可以很方便绑定在角色的手部，也能轻松改变大小

![](http://i0.hdslb.com/bfs/article/4ca250b7fe608b525b568cd1cf1d0b805b46f780.jpg@942w_965h_progressive.webp)吽宝：pocky 啊……（意味深长）

不过现在因为有了外亲功能，所以 PMX 道具也越来越多了

但是需要注意：如果 X 模型含半透明材质，那就必须在模型后面描绘了，不然半透明部分不会正确显示

不要的 MME 或 X 模型可以在附件操作里删除

![](http://i0.hdslb.com/bfs/article/9eb27eb6d9d209e5af0574313c12b0ed1bc36583.jpg@375w_290h_progressive.webp)

■伊文的灵魂提问：附件操作的取消表示和分配特效框里的取消打勾有什么区别？

![](http://i0.hdslb.com/bfs/article/bf6e298665b2f1f3c209e81ab966d4384ed6829c.jpg@942w_420h_progressive.webp)

附件操作里取消表示

就相当于删除了这个 MME，不会在任何地方发生效果了

框里的取消打勾

这个 MME 只在这个框里无效，其他框内依然生效

通常用于解决粒子特效和其他 MME 的描绘冲突

需要注意的是 MME 设置后都是用帧的形式存在

![](http://i0.hdslb.com/bfs/article/39f16c071284a1e17f6ce1abb4cd34a0056d1513.jpg@291w_279h_progressive.webp)

像这样红点表示该 MME 的设定帧被选中了

如果此时又选中了镜头并删除，会连带 MME 的设置一起被删除，即变回了默认设置

正确做法：在帧的空白处随便点一下，取消红点后再删除镜头

![](http://i0.hdslb.com/bfs/article/53c25a4e54b58d613959d09eb2689c83a7cd5b39.jpg@521w_321h_progressive.webp)

伊文：我删镜头的时候好像把什么东西删掉了

过了一会儿

伊文：MME 设置一半变成默认了……

伊文大失败说

**【全选动作】**

菜单的编辑 - 选择所有姿势帧 / 选择所有表情帧 / 选择所有显示 IK 外亲帧

可以全选动作

然后点下方的删除可以快速删掉动作

关于 K 帧

这个真的只能自己多摸索

也可以看看大佬们的 K 帧教程

每个模型其实都有自己的关节旋转风格，只有多摸才能理解

顺便吽模原版有手腕捩的 bug，所以自 K 帧不推荐碰腕捩

同时他的关节权重刷得非常好，基本怎么转都不会破绽

一般是先确定下半身的动作，然后上半身，最后是头部和手臂

K 不了动作，自己摆摆 POSE 玩也很有趣的

顺便姿势文件.vpd 的那种，跟 vmd 不同，套入后需要按骨骼操作的注册才会被固定

**【无损压缩型 AVI 编码】**

Ut Video Codec Suite

http://umezawa.dyndns.info/wordpress/?p=7846

![](http://i0.hdslb.com/bfs/article/0e540aa6488b9469a79461ac11a054d53db60e48.jpg@329w_51h_progressive.webp)下载点这里

出力用，是无损的，保证没有画质丢失

我一般用这个编码

![](http://i0.hdslb.com/bfs/article/50cd5c487345625945bbf8a0786ff9def8926f32.jpg@563w_137h_progressive.webp)

压制用的小丸工具箱

小丸太久没更新居然被垃圾软件盗用了名字

伊文：啊我被装上了垃圾软件！！

我：…………

这波确实是我的锅（x

我好不容易搜到正确版本

https://pan.baidu.com/s/1jxOusaX9K8Sdh7yLU-eZcQ 提取码：xhkt

因为 B 站现在支持 2 万码率以内

所以我视频压制是用 19000

![](http://i0.hdslb.com/bfs/article/1ab037fa6b545fb701058080c399750fdc45ba98.jpg@572w_263h_progressive.webp)

防二压已经不存在了，现在是个视频都会被二压，那还不如自己压制码率高一点

暂时这么多了，后续更新看伊文发展状况

**【其他教程】**

![](http://i0.hdslb.com/bfs/article/card/e307a50794c3cb64703921357514e09fc5f99f18.png)![](http://i0.hdslb.com/bfs/article/card/57e88220f25f1fa8c930f5ad5e04f2537c6c4b48.png)![](http://i0.hdslb.com/bfs/article/card/068a6b949d9b415f6837b93e04edcf8cc8f61287.png)

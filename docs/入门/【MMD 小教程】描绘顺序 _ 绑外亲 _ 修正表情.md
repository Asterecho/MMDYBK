> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv15704704?from=search&spm_id_from=333.337.0.0)

> 点击进入查看全文 & gt;

从零开始的伊文 MMDER 调教 第三篇

揠苗助长的填鸭式教学大失败_(:з」∠)_

感觉自己没有当老师的才能，但是能怎么办呢？只能把教程写得再详细一点了

借物表：

MODEL：吽 - ほのぼ悠琴がけと  博士 - クロノ & 明日游轮

　　　　  道具 - キャベツ鉢 はますぎ

STAGE：怪獣対若大将 P  ゆづき  mogtan

MME：そぼろ 針金 P おたもん おこめ

■非常重要！

菜单的**背景 - 附件编辑 / 模型描绘顺序 / 模型计算顺序**

![](http://i0.hdslb.com/bfs/article/c875fd08bdc408a9daf5585f7b408378a36f880e.jpg@434w_618h_progressive.webp)

新人很容易忽略且不太理解的地方，今天来详细讲解一下

感觉伊文完全没有理解什么是「描绘顺序」

那我就好好再说明一下

如果有学过 PS，对图层有概念的话，就很好理解了

附件编辑只包含 X 模型，天空球和 MME 都是 X 模型，所以都在这里

![](http://i0.hdslb.com/bfs/article/82f61a058cae599854e8b81e51fea9f21363655b.jpg@942w_662h_progressive.webp)

通过调整上或下，我们可以给 X 模型排序

比如打乱一下顺序

![](http://i0.hdslb.com/bfs/article/0b3177a2e7d7b72fb9a11a2a100efc3bb9163886.jpg@942w_614h_progressive.webp)

通常排序是背景在上面，MME 在下面

而角色模型是 PMX 模型，不在附件列表里

排序是通过菜单的背景 - 模型描绘顺序进行的

![](http://i0.hdslb.com/bfs/article/64ee4930e5c6cdc6fcffda26adb566711d01159e.jpg@554w_515h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/96f0db7c10c21d6e6ff97534c3f3c0ebd1df46f4.jpg@554w_515h_progressive.webp)

那么如何决定 X 模型和 PMX 模型之间的顺序？

就是通过附件编辑的数字了

如果是 0，那么所有的 X 模型都排在 PMX 模型之后

![](http://i0.hdslb.com/bfs/article/cfbb7769965932f8149d7d9f325ecc5d1bb5eb45.jpg@942w_617h_progressive.webp)

如果是 1，那么最上面的 1 个 X 模型排在 PMX 模型之前，其他 X 模型排在 PMX 模型之后

![](http://i0.hdslb.com/bfs/article/0c7bd625e526667673996b3cb27b26ce44af4e2e.jpg@942w_606h_progressive.webp)

如果是 2，那么最上面的 2 个 X 模型排在 PMX 模型之前，其他 X 模型排在 PMX 模型之后

![](http://i0.hdslb.com/bfs/article/be76f1a42f53a985cbb03b354d7aaf302031db97.jpg@942w_606h_progressive.webp)

依次类推，就可以把天空场景等 x 模型排在角色模型前，mme 排在模型后

就像画画一样，先画个背景（天空和场景），再画个角色（pmx 模型），最后加点滤镜（mme）

![](http://i0.hdslb.com/bfs/article/d84180eba9bc58c73f0b7c404230c8d9cfea2eca.jpg@750w_1382h_progressive.webp)

描绘顺序就是这样决定各个模型被画出来的顺序

看到这里还是不理解的话，那就摆烂了！

数字直接填 0！一般不会出事

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

有半透明材质的模型，描绘顺序必须在模型列表的最后！

比如窗户玻璃

正确的顺序

![](http://i0.hdslb.com/bfs/article/b0f851a5ec7168daf316ee6cbf72a81ffb5ee620.jpg@750w_867h_progressive.webp)

错误的顺序

![](http://i0.hdslb.com/bfs/article/01819927c413f8d1deab7c4da26a15f77e35873c.jpg@750w_867h_progressive.webp)你看好端端一个狗子不见了

把道具绑到角色的头上或手上，这样转头抬手时会跟着一起动

**■X 模型的道具**

比如让吽宝拿一块饼干

我们先摆出吽宝的姿势

![](http://i0.hdslb.com/bfs/article/2674a25487ed04dadf750465c35810d31a58c08c.jpg@942w_783h_progressive.webp)

把饼干的 X 模型拖入 MMD

此时，饼干处于坐标 0 点位置

![](http://i0.hdslb.com/bfs/article/4049bc1e77abeb50c021ac7dc16cf25b3ad29859.jpg@381w_272h_progressive.webp)

在附件操作里选择饼干模型

地面下拉框里选中要绑的模型，右边的下拉框里选要绑定的骨骼（比如右手首，右ダミー等），再点注册

于是瞬间 X 模型就吸附在那个骨骼上了

推荐用右ダミー，这是专门用于绑道具的骨骼

![](http://i0.hdslb.com/bfs/article/7498a1d5640d0a558b11da78d52bd3f5d6fb3030.jpg@377w_600h_progressive.webp)

现在可以直接操控这个骨骼来调整道具的位置

![](http://i0.hdslb.com/bfs/article/47ce80f22d56e7e4089cd58e178e2a4143450ece.jpg@750w_666h_progressive.webp)

改变大小就是修改 Si，Tr 能改变透明度（跟 MME 一致）

![](http://i0.hdslb.com/bfs/article/c0a399dcb76417085fa6c6522b01f06172f39a65.jpg@750w_1098h_progressive.webp)

**■PMX 模型的道具**

如果没有放大缩小的表情，那就无法调整大小，必须通过 PE 改模

![](http://i0.hdslb.com/bfs/article/7b9e68430b800bdbb8bf5857ea8ff48a10880ebb.jpg@942w_525h_progressive.webp)

数字就是变大倍率，1.0 时不变，1 以上变大，1 以下变小

但表情丰富的 PMX 道具是远超 X 模型的

比如让吽宝端盘菜

首先把吽宝摆出一个端菜的姿势

![](http://i0.hdslb.com/bfs/article/5b67d9da4cccfe16c67331f50dd54b01021ad84e.jpg@942w_758h_progressive.webp)吽宝：我累了……

拖入菜的模型，点面板上的外

![](http://i0.hdslb.com/bfs/article/09aa71dfba6264266e10d15a719567fd7e4f4ea3.jpg@278w_314h_progressive.webp)

对象骨骼：选该模型的全ての親或センター或任意可以移动该模型的骨骼

在外部亲模型选要绑定的模型，外部亲骨骼选要绑定的骨骼（比如右ダミー）

点注册外亲和注册关键帧（2 个注册都要点）

![](http://i0.hdslb.com/bfs/article/f1e13fc37dcc97a42191c748812a011a9b1dd90e.jpg@693w_545h_progressive.webp)

跟 X 模型不同的是，绑定后的 PMX 模型并不会自动移动至绑定位置

![](http://i0.hdslb.com/bfs/article/733723f490145071331516e46ae62d14091fd0f3.jpg@323w_216h_progressive.webp)

所以在道具的骨骼帧那里选中全ての親或センター，在骨骼位置的框里将 XYZ 的数值都手动改为 0，然后按骨骼操作的注册

![](http://i0.hdslb.com/bfs/article/cdc351871f4ab2a56ba5f2778608082dd4530b79.jpg@689w_600h_progressive.webp)

此时就跟 X 模型的状态一致了

可以移动绑定的骨骼（比如右ダミー）来调整

![](http://i0.hdslb.com/bfs/article/260501c34fca9bbc8d4e05dd23c5ed1c6c02a89b.jpg@942w_812h_progressive.webp)

这盘菜有很多表情，除了放大缩小，还能减少一部分食物，这种花里胡哨的功能就是 X 模型做不到的

比如让所有的豆腐消失

![](http://i0.hdslb.com/bfs/article/9413392c58e66cfc175976ed35662da5e877714a.jpg@740w_710h_progressive.webp)

**■非常重要的一点！**

道具的计算顺序必须在角色下面，即让 MMD 先计算模型的动作，再计算道具的所处位置，如果反过来的话，第一帧的道具会脱节

![](http://i0.hdslb.com/bfs/article/watermark/b756c533cbc1f3e379ceec41f12c1291809482ea.jpg@326w_146h_progressive.webp)

一定要养成绑定完以后，检查菜单的背景 - 模型计算顺序的好习惯！

给头部绑定配件也是一样的道理

外部亲骨骼选头

因为头不能随便移动，所以调节配件本身的全ての親或センター到合适位置

然后让我们逆转思维，除了把道具绑在角色上，我们还能把角色绑在道具上

比如用 PE 插件加了手 IK 后

先摆个举重姿势

再把杠铃移到合适位置

![](http://i0.hdslb.com/bfs/article/b6d538e64a70efab7cbf84eb5a8d802a21476353.jpg@900w_482h_progressive.webp)

点吽模的外，对象骨骼选左右手 IK

![](http://i0.hdslb.com/bfs/article/e631b498793907f184d379290fb0fe6081fb24c3.jpg@251w_288h_progressive.webp)

外部亲模型选杠铃，外部亲骨骼选センター

![](http://i0.hdslb.com/bfs/article/4315f766b1942d676cb0ad826639e2138dd5baaa.jpg@692w_542h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/b3ae2ee96da7d37fb49257fbbbd81bfa929af92d.jpg@690w_545h_progressive.webp)

把左右手 IK 绑在杠铃的亲骨上

这样我们移动杠铃时，角色手会跟着移动

比调整手臂动作要轻松很多

![](http://i0.hdslb.com/bfs/article/ea983fd34003cc720ece7dc5b526cabaa8985442.jpg@942w_351h_progressive.webp)

甚至角色自己的骨骼也能绑在自己别的骨骼上

我让吽掏武器就是把武器骨骼绑在手上的

**非常重要**：如何正确载入包含外亲的动作

必须先绑定外亲，再载入动作，直接套动作只会错位

比如像扇子舞里扇子的 vmd

第一次载入后百分百错位，因为所有的外亲部分其实都是空的

需要根据作者的说明，在每个有外亲的帧处重新绑定，比如第一帧绑右手，第 200 帧绑左手，等等

全部正确绑定后，再把扇子的 vmd 载入一次，这次就位置对了

你们知道吽宝的表情有多么脆弱吗！

眼睛（两目）骨骼稍微多转一点就要穿模！

嘴巴（口型）表情稍微多叠加一点就要穿模！

可能这就是福瑞的宿命（指嘴巴建模太复杂了没法叠加

**■简易修正方法**

全选两目的骨骼帧

选择骨骼下拉框选两目

输入帧数范围后按选择范围，就全选了

![](http://i0.hdslb.com/bfs/article/2fbcc34153f3f5785e6086e0f49b13d579dd6f65.jpg@488w_290h_progressive.webp)

菜单的编辑 - 骨骼帧位置角度补正

把角度都改小，比如 0.5

就能让双眼的转动变小

![](http://i0.hdslb.com/bfs/article/15cd6b848d8e431abea88661bfc2ff6124b11abf.jpg@395w_479h_progressive.webp)

伊文试过一次结果更歪了，我觉得肯定是哪里操作错了（x

全选口型也一样

选择骨骼那里选あ、い、う、え、お

![](http://i0.hdslb.com/bfs/article/a81cda6092617efe73ac2ff54a3daa2062bf9579.jpg@707w_632h_progressive.webp)

等口型帧全变红以后

菜单的编辑 - 表情大小补正

同样改成 0.5 或更小，就能解决口型穿模了

![](http://i0.hdslb.com/bfs/article/ceb309467caf483273dad397d83ded876a44f1d2.jpg@398w_177h_progressive.webp)![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

看不懂没有关系，MMD 本来就不是光看教程就能懂的

自己多上手摸索多玩玩，自然而然就会懂了

我们当年哪有中文教程…… 都是野蛮生长自行发育过来的（x
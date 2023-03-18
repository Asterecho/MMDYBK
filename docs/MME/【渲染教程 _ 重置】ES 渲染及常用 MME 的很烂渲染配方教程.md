> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv91707?from=search&spm_id_from=333.337.0.0)

> 前言：对 MMD 基础相关的疑问，建议点开：http://bakakin.lofter.com/post/400994_16e51be 废话：大家好，这里是风瑾。之前的 es 教程是我一时兴起凭着感觉乱做出来

前言：对 MMD 基础相关的疑问，建议点开：http://bakakin.lofter.com/post/400994_16e51be 

废话：大家好，这里是风瑾。

之前的 es 教程是我一时兴起凭着感觉乱做出来的，所以也并没有认真的在意一些小 bug XD

希望我这次重置的非常不负责任的 es 教程能够帮助到您 www

【可能因为今天的状态并不是很好，头稍微有点晕 xxx 教程十分的枯燥无味，还请见谅 qwq(可能就是无尽的偷懒中 XD

之前的 es 教程：[https://www.bilibili.com/read/cv41121](https://www.bilibili.com/read/cv41121)

First. 给没有 spa 的模型贴 spa★

Q：spa 从哪儿获取？

A：链接：https://pan.baidu.com/s/1miFv09M 密码：lhap （自己整理的一些 spa）

![](http://i0.hdslb.com/bfs/article/c8f1ab11ed580027700f261042f024a1000eb556.png@942w_569h_progressive.webp)添加 spa 过程 ![](http://i0.hdslb.com/bfs/article/fe3e9301539a586d0a6d128bc15fc3e4054b8094.png@942w_519h_progressive.webp)对比

Second. 添加【LightBloom.x】附件★ 

LightBloom 加入后，如果看到什么变化都没有，这个是很正常的。这个附件可以确保之后的渲染画面都是白色的

![](http://i0.hdslb.com/bfs/article/985149fcc3263b216cae46871b012adb09c29b99.png@942w_519h_progressive.webp)效果展示 ![](http://i0.hdslb.com/bfs/article/6163dc42839f6ee07aa81c4672888678ef2e5e09.png@314w_236h_progressive.webp)放大

调节这个附件的 X 值，可以让周围变亮的。

建议 X 值参数调 2~10,，数值越大越亮。

Third. 添加【ExcellentShadow2】中的【full_ES.fx】，并载入【ExcellentShadow2.x】★ 

![](http://i0.hdslb.com/bfs/article/b480335c7e8c618bab41c4c0bbdcd86db18a3c22.png@942w_432h_progressive.webp)效果展示 ![](http://i0.hdslb.com/bfs/article/2d0ffef18e8ff627b08bb774777f10cefc9aca5f.png@300w_234h_progressive.webp)参数放大

调小 Tr 值，可以使模型的阴影变重。调的越小，阴影越重。建议参数 TR：0.00~0.20

调节 Rx 值，模型的阴影会变得柔和一些。建议数值：Rx：100~120

补充：ExcellentShadow2 文件中 ExShadowSSAO.x 的文件并不建议使用，后期输出视频时才发现加了这个后，人物的周边有黑色的微弱的残影 emmmm.....

Q：眼睛太暗？

![](http://i0.hdslb.com/bfs/article/ae0fc14d30e77429e842f419a3bcf281c6ccd95a.jpg@942w_198h_progressive.webp)眼睛暗

A：可以在 mme 里，对模型展开子集，找到眼睛和高光的两列，把它本身加上的 fx 文件去掉。添加【AdultShader_v014】中的【AdultShader.fx】。嫌太亮的可以添加【T_ToonShader Ver1.22_1.32】中的【T_ToonShader_S1_EyeOn.fx】  (悄咪咪的，用 T 渲里的这个 fx，眼睛里会有小圈圈的 qwq)。

![](http://i0.hdslb.com/bfs/article/292a7d44f1c128dfe94a7288ef03981c3ab6e78d.jpg@942w_194h_progressive.webp)T_ToonShader_S1_EyeOn.fx 的效果 ![](http://i0.hdslb.com/bfs/article/fc7191ed32da2abce1fdfa85c521b2d493cfb231.png@942w_171h_progressive.webp)AdultShader.fx 的效果

（偷懒 ing....ww）

Fourth. 载入【Diffusion7】中的【Diffusion.x】  

![](http://i0.hdslb.com/bfs/article/c2b265f1103fb5aae17138636f418357e20ca38a.png@942w_519h_progressive.webp)效果展示 ![](http://i0.hdslb.com/bfs/article/f74bc79c32f12512511fae4c5bda3704f0a64ea7.png@306w_246h_progressive.webp)放大

 Diffusion7 本身不调参数就是柔化作用。

调大 Si 值，会有画面发散的效果，建议参数 4~8.

调节 X 值，可以使画面一定程度的变红。相对的 Y 和 Z 是变成青黄色和紫色。一定程度上可以当做调色来用

Fifth. 载入【ikDiffusion  Diffusion1】中【ikDiffusion1.x】

![](http://i0.hdslb.com/bfs/article/4e2b0b59cec3777c77d75d09c3f8d86e1c9b7df8.png@942w_519h_progressive.webp)效果展示 ![](http://i0.hdslb.com/bfs/article/d8ec19a732350722c8f92f18bae5023c1c94fff4.png@302w_234h_progressive.webp)放大

这个 MME 的主要效果应该是周边泛光（？）

Si 的数值在（0,1】之间依次升序就是发光强度慢慢提升，在（1，+∞）之间发光的程度都是一样的。

建议 Si 数值为 1

Sixth. 载入【針金 P】的【HgSAO_v002】中的【HgSAO.x】

![](http://i0.hdslb.com/bfs/article/127b968d5a1c2af0378884a64221e04f8ab5d821.png@942w_519h_progressive.webp)效果展示 ![](http://i0.hdslb.com/bfs/article/c1f206ba83631b1daf49cb3a63a145820ff9a907.png@302w_240h_progressive.webp)放大

HgSAO 是有加深阴影的作用，可以按照实际需要叠 2 个（这儿偏向叠一个 xd）

Y 建议参数 - 2

Seventh. 载入【likelooks】中的【likelooks.x】

![](http://i0.hdslb.com/bfs/article/b7d7a133ca554cb908f260360bf9e9a604322490.png@942w_519h_progressive.webp)效果展示 ![](http://i0.hdslb.com/bfs/article/c1b1d8aeb698a494f036e51397a834e9291bbd7e.png@294w_248h_progressive.webp)放大

likelooks 是滤镜，大概偶尔颜色单调是添加润色的 www

Tr 值越小，效果越不明显 xxxx 这儿基本是不调参数的

Eighth. 载入【SelfBlend_v011】中的【SoftLightSB.x】

![](http://i0.hdslb.com/bfs/article/1d53bf46bdedb13f0e29c3e6efbe89b07129f26b.png@942w_519h_progressive.webp)效果展示 ![](http://i0.hdslb.com/bfs/article/63ddb97e85166ab2c5921a3a3a76c5607d885109.png@309w_242h_progressive.webp)放大

SoftLightSB 大概是会使 likelooks 效果稍微削弱（？）

Ninth. 建议使用【dGreenerShader】中的【dGreenerShader_TOON2.fx】

![](http://i0.hdslb.com/bfs/article/f10095d23288abe4e2443b426171cd54b41ff0b0.png@942w_374h_progressive.webp)效果展示

就是比较喜欢 dG 渲染场景的感觉吧 www

【具体原因请翻阅上一次的 es 教程后半部分 qwq

最后

Last. 按照自己的喜好打光

![](http://i0.hdslb.com/bfs/article/dc993a705b7dab4b4446f11c3061a96684a99eff.png@942w_519h_progressive.webp)效果展示（突然换模型 ww ![](http://i0.hdslb.com/bfs/article/22fe0462e7f343ed22cd22c8c2f857fb4b3e5fc9.png@279w_243h_progressive.webp)仅供参考

Other.

first. 【ikOverray_v003】

![](http://i0.hdslb.com/bfs/article/40183924466c52b1701b660b7c2bf7bda466ad92.png@942w_519h_progressive.webp)未修改任何数值 ![](http://i0.hdslb.com/bfs/article/5852d27aefe5ac1ec33ce7e73825f3d3f5b4b4b0.png@942w_519h_progressive.webp)未修改任何数值

ikOverray_v003 大概类似一个光源（并不是很能描述 XD），这个会随着打的光而转换位置，背光更能凸显这个作用。

![](http://i0.hdslb.com/bfs/article/738d54657f9ea9817f74d135e2fa4535bdf03017.png@285w_104h_progressive.webp)也可以修改这里参数，来改变光的颜色 ![](http://i0.hdslb.com/bfs/article/51f3d2d203d56207c64e88025471ca3ab3b967dd.png@942w_519h_progressive.webp)效果展示

可以根据自己的需要来控制色调

![](http://i0.hdslb.com/bfs/article/d03539e2fe91adb4d6f36c42b43bea7aa63a2f10.png@942w_519h_progressive.webp)改 Tr 值得效果展示 ![](http://i0.hdslb.com/bfs/article/3a654c663a1318859ee7d14d0d2fb06c842de402.png@305w_234h_progressive.webp)放大

Tr 值参数调的越小，效果也随之减小。

为了保证不使画面过亮，或者不使人物的脸变得突兀的白。 Tr 值建议在 0.2~0.4

second.【ikGodray_v002】

![](http://i0.hdslb.com/bfs/article/19540b1400ab45c0df81722f8043a277a06cfca7.png@300w_237h_progressive.webp)第一步

这儿用的是 [RedialC](https://www.bilibili.com/video/av15006288/) 配布的经过修改的 ikGodray（就在背景配布的文件夹中 XD）

![](http://i0.hdslb.com/bfs/article/dbbf5ddc031c5c9926039c2d9bdb69e2af04ae02.png@942w_393h_progressive.webp)第二步 ![](http://i0.hdslb.com/bfs/article/b93461e41d5e52d45d95fa9854bc9a7c61cb2613.png@942w_519h_progressive.webp)第三步

ikGodray 也会随着打的光而转换位置，具体用法和 ikOverray 差不多 xx

Si 参数建议 0 （具体原因可以尝试啦 xxx 毕竟我真的不会描绘嘛 www）

Tr 数值越小，光线效果也越弱

third.【AutoLuminous4（发光）】+【ikBokeh_v018b（景深）】

![](http://i0.hdslb.com/bfs/article/996af105a1a32feae55ee47b19dee9a502843bfd.png@942w_519h_progressive.webp)效果展示 ![](http://i0.hdslb.com/bfs/article/1817f12feee9bb938dd782f29f8f8ba87615db66.png@300w_237h_progressive.webp)放大

AutoLuminous4 有发光的效果，为了保护眼睛，Si 参数建议 0.3~0.4

![](http://i0.hdslb.com/bfs/article/a76b0c5adfe536df0d07dabb3da01fe724ca7544.png@299w_248h_progressive.webp)把 x 文件拖进来就好 ![](http://i0.hdslb.com/bfs/article/0ddc491abcc6bb3b8034b95a68e2ea03ee028191.jpg@942w_939h_progressive.webp)再载入其控制器 ![](http://i0.hdslb.com/bfs/article/78577c037a3f2681be06708424811c81dfe21c3b.jpg@942w_923h_progressive.webp)选择表情的第三栏中的第三个选项 ![](http://i0.hdslb.com/bfs/article/5484b8e590f7999c15f39d47db1332f0270d71b3.png@407w_243h_progressive.webp)参数图片

具体这样的做法原因请参照 [RedialC](https://www.bilibili.com/video/av11652436/) 的具体教程

![](http://i0.hdslb.com/bfs/article/c1ba460b759f2c264fefdeaf50922408713b7833.jpg@942w_1110h_progressive.webp)选择表情的第三栏中的最后一个选项 ![](http://i0.hdslb.com/bfs/article/2840399643fad213fc60846932c7338906d61056.png@404w_252h_progressive.webp)参数 ![](http://i0.hdslb.com/bfs/article/cc171239980d0cfef6bd7b55cab747344e8f6c10.png@942w_368h_progressive.webp)效果展示

以上的操作的效果就是周围粒子变成了虚化的一点一点，个人挺喜欢这种感觉的 XD

fourth.【空気遠近エフェクト】

![](http://i0.hdslb.com/bfs/article/e0868ef96cdbd41cd72c14ea03280ff8e09492e1.png@942w_519h_progressive.webp)before ![](http://i0.hdslb.com/bfs/article/327b1f45606a145268b1ad34804703cb40501fac.png@942w_519h_progressive.webp)after

空气远近就是镜头拉远后，背景的雾气就会白起来，可以充当雾霾（bushi）

总之很有现实感（？）

（假的）成果展示：

![](http://i0.hdslb.com/bfs/article/fba7d4007283eb76a5240f4368a45f7a030d6e7a.jpg@942w_354h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/f022a5a3a714c26bf4b803dda107731cf4d088c4.jpg@942w_354h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/c155d36c46b97819aab38d9e4095dd3a5dee506e.jpg@942w_354h_progressive.webp)

没啦

借物：

Model: Tda/Owth/PrincessOfLight22/Shioku/Evastar11/agahat

/Jin/HarukaSakurai/Likeabaka/miky-rei/crumelody/louuuuuuu / 风瑾（TDA Lazy Rin）

Tda/Harukasakurai/WKPY/RageXYZ / いつものほん / Nashie-C/MMDMMiki(Kagamine Kiiro-Rin)

Mme: そぼろ / ikeno / 針金 P/OH YEAH / 化身バレッタ / RedialC

/Elle / 下っ腹 P / めめ

Motion:ureshiiiiii

Stage: ゆづき（万年寝不足 - 別館)

Tool:MikuMikuDance/MMEffect/pmxeditor

【敬称略】

说好很认真的重置，结果还是浑水摸鱼的随意的就做了_(:з」∠)_

感谢观看教程，希望能给您带来一些帮助。

最后讲一个笑话：全屏玩 MMD？对我来说是不存在的: )

![](http://i0.hdslb.com/bfs/article/99aeaec59a6421b709370ec665993f820db10505.png@942w_531h_progressive.webp)桌面截图
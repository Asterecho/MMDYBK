> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv17708731?from=search&spm_id_from=333.337.0.0)

> 作者：[唐子七](https://space.bilibili.com/2268736)

 如题，是一个啊不对四个渲染配方的配布。

如题，是一个啊不对四个渲染配方的配布。渲染过程实在忘记录了，见谅。  

主要使用的是 **Ray-Toon**，使用的天空盒全部是 **Sky Hemisphere**，考虑到眼睛部分使用了**発光コンタクト（by 966）**所以全部采用了逆光，以及参考时请酌情关闭 ray 自带的轮廓线或者降低我下文提到的轮廓线 MME 的数值，我会尽量以清楚的方式记录配方。

详细借物表见→[BV1gg411Z7Vk](https://www.bilibili.com/video/BV1gg411Z7Vk?from=articleDetail)

人菜全靠 ikclut 撑起画面，比起渲染配方更像调色配方。

warning：大部分是以文字而非图像的形式表现数值，阅览起来十分枯燥无味。

那么，以上都没问题的话——

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

首先是视频第一段的配方。

![](http://i0.hdslb.com/bfs/article/f885e860d6237550ecfaa7a7dc95a8461cde3bb8.png@942w_531h_progressive.webp)神明

由于这个场景我使用了怪獣対若大将 P 的薄い夕焼け TP103，所以天空盒数值如下：

相机界面：赤 205，绿 154，蓝 103，X+0.3，Y-0.4，Z-0.6

SKYBOX：TopV+0.15，MediumV-0.3，BottomV-0.2，EnvDiff+0.05，EnvSpe-0.15， EnvSSS+0.2，EnvX+0.15，EnvZ+0.2

Controller：sunlight+0.05，sunshadowR+0.1  G+0.15   B+0.2  V-0.35，Multi-0.2，SSA0+0.15  -0.6，SSDO+1

BloomTd+0.55，BloomColorH+0.1  S+1  V+0.5 V-0.35，Exp-0.15，Dispersion+0.1

Contrast+0.2  -0.25，Saturation+0.05，Gamma-0.1，Tem-0.15，BalanceR+0.2  G+0.15  B+0.1  

然后接下来就是简单易懂的打光了：

载入 DirectionalLight，在 light 栏改成最长的那个。光源方向 Y-0.45，R/G/B+1，Range/Hard+1，In-0.75。注意，这是正面打光，请勿与以下两个侧面光混淆。

再载入两个 DirectionalLight，不要动 light 栏，光源方向 X±14，Y14，Z-77，R+0.45，G+15，Range+1，In+0.05

接着就是胡乱载入 MME 的时间了ᕕ(ᐛ)ᕗ 

SDFA：X 7.0，Si 0.7，Tr 0.7

Croquis：X/Y/Z 0.15，Si 0.55，Tr 0.55

PostDropHair：X 0.14，Y 0.07，Rx/y/z -350，Tr 0.35（不懂怎么用这个 MME 的请看 [CV17518919](https://www.bilibili.com/read/cv17518919?from=articleDetail) 的最后一个分类）

SvSSAO：Si 0.7

PostRimLighting：Si 0.7，Tr 0.7

这里载入了 ray 自带的 lightbloom，我用的是 LightBloom with DirtMap，控制器数值如下：BT 0.3，BR+0.35，BloomColor4S+1

再从 **ikOverray 改変_color（by うみ）**中载入 20 鼠. x 来加光，Tr 0.05。从 **ScreenTex 改変_動く入射光（by のりしお）中**载入 Cr_入射光 1.x 形成彩虹色光晕，Tr 0.25。

接下来就是神奇的叠滤镜调色时间 (ゝ∀･)

A lifetime love：Tr 0.15

7：Tr 0.35  

思い出のレモンスカッシュ - 2：Tr 0.55

スイートピー：Tr 0.7

Cyberpunk：Tr 0.35

D：Tr 0.7

以上分别出自 ikclut_Carnival of doomsday、ikClut_xx01、ikClut 改変 秘密の森、ikClut 改変 Flower、ikClut 改变 CP。

不要忘记 **Croquis 改変_フレア（by ひいらぎ）**也是有滤镜效果的哦，再加一个シナモン：Tr 0.25 就调色结束了。

最后我们来对一下顺序。虽然顺序的变换也能叠出不同的颜色来，但有些 MME 的顺序排列还是很关键的。

![](http://i0.hdslb.com/bfs/article/c0fd2da42ad591920742ffbdc2b6a88cab1d95e2.png@273w_486h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/1534fdc36df0634a238561d7cd1911ec27ee7f04.png@234w_296h_progressive.webp)

ikGouache：Tr 0.15

第一个渲染配方如上。

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

第二段大致如此：

![](http://i0.hdslb.com/bfs/article/b084fece3101fae7fb79839cecf1f0e4d271c3ec.png@942w_531h_progressive.webp)圣女

这段是在沙漠环境中，虽然感觉乍一看好像和第一段色调差不多，总体偏暖，不过还是要暗一些的。

相机界面：赤绿蓝不动，X+0.0，Y-0.6，Z-0.4

SKYBOX：TopV+0.1，MediumV-0.1，BottomV-0.2，EnvDiff+0.15，EnvSpe+0.05， EnvSSS+0.2，EnvX+0.15

Controller：sunlight+0.1  -0.55，sunshadowR+0.2  G+0.15   B+0.1  V-0.25，Multi-0.2，SSA0+0.15  -0.6，SSDO+1

BloomTd+0.6，BloomRadius-0.25，BloomColorS+1  V+0.35，Exp-0.25，Dispersion+0.1

Contrast+0.25，Saturation-0.1，Gamma-0.15，Tem+0.15，BalanceG+0.1  B+0.2

打光方法同上一个，但数值有更改。正面光光源方向 Y-0.7，In-0.75，其他不变。

侧面光的 R/G/B 改成 0.4，In-0.7

载入的其他 MME 同配方一的数值不变，除了 Croquis，Si/Tr 改成 0.75

到了 lightbloom 这一步，控制器数值如下：BT 0.45，BR-0.35，BloomColor1H+0.05  S+1，3S+1

载入 **ikOverray** 18 杏. x，Tr 0.15。载入 Cr_入射光 2.x，Tr 0.35。

然后又是叠滤镜时间——

黎明：Tr 0.15

01_トロピカル：Tr 0.35

夕暮れの憂鬱 - 2：Tr 0.35

film03：Tr 0.25

03_青い朝：Tr 0.25

Sharp：Tr 0.7

以上分别出自 ikClut 改变_Simon、ikCult 改変_shfilter、ikClut 改変 秘密の森、ikClut 改変 film、ikClut 改変 OldLens。

最后加入 **Croquis 改変_フレア**的ヴァレンシアオレンジ，Tr 0.25

这个场景里也加入了万年寝不足的金箔パーティクル和ビームマンＰ的 SoftSmoke 来营造氛围，所以也提供一下这两个控制器的数值。

首先是万年寝不足的：速度 0.75，范围 X/Z 0.35  

由于ビームマンＰ的文件夹里自带预设数据，所以我只是在预设上改动了下：范围 X/Z 0.3，透明度 0.75，明度 0.35，个数 0.75，速度 0.91，点减 0.98，Si 0.12，ゆらぎ 0.15

MME 的顺序排列如下：

![](http://i0.hdslb.com/bfs/article/d1229b90dd929b478ab18aee41a364ede5172404.png@222w_486h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/06da0cf1c53eca22f3dc448749be6dd7b7202117.png@198w_342h_progressive.webp)

ikGouache：Tr 0.15

第二个渲染配方如上。

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

第三段的画面示例：

![](http://i0.hdslb.com/bfs/article/f6083e9eba934878785e1f8f3172311563bb8615.png@942w_531h_progressive.webp)犹大

相机界面：赤 103，绿 103，蓝 122，X+0.0，Y-0.8，Z-0.6

SKYBOX：TopV+0.15，MediumV-0.15，BottomV-0.2，EnvDiff+0.1，EnvSpe-0.15， EnvX/Z +0.15

Controller：sunlight+0.15，sunshadowR+0.1  G+0.2   B+0.15  V-0.25，Multi-0.2，SSA0+0.15  -0.6，SSDO+1

BloomTd+0.55，BloomRadius+0.35，BloomColorH+0.65  S+1  V+0.05，Exp-0.1，Dispersion+0.1

Contrast+0.35，Saturation-0.1，Gamma+0.15  -0.05，Tem+0.2

没有正面光，考虑到枢机卿这个角色本身就已经很苍白了，再打正面光会显得整个画面太刺眼。侧面光的光源位置不变，X 为﹢14 的 R+0.05，G+0.4，B+0.3，In-0.5；为 - 14 的 R+0.05，G+0.25，B+0.5，In-0.5

这边数值和一差别有点大，所以重新写一遍：

SDFA：X 7.0，Si 0.7，Tr 0.7

Croquis：X/Y/Z 0.15，Si 0.75，Tr 0.75

PostDropHair：X 0.14，Y 0.07，Rx/y/z -350，Tr 0.35（不懂怎么用这个 MME 的请看 [CV17518919](https://www.bilibili.com/read/cv17518919?from=articleDetail) 的最后一个分类）

SvSSAO：Si 0.7

AutoLuminous：X 1.0

PostRimLighting：Si 0.75，Tr 0.75

接着是 lightbloom 的控制器数值：BT 0.35，BR-0.15，AllV+0.05，BloomColor1H+0.55  S+1，3H+0.65  S+1

载入 **ikOverray** 20 鼠. x，Tr 0.15。载入 Cr_入射光 1.x，Tr 0.25。

这里的 workingfloor 的 Tr 值是 0.15。

OK 又可以到重点的叠滤镜了√

紫 - 青 3：Tr 0.05

チョコレートコスモス：Tr 0.35

3. キャンディ：Tr 0.35

山頂のプラネタリウム - 2：Tr 0.15

ikClut_red004：Tr 0.25

Memories：Tr 0.25

01_トロピカル：Tr 0.15

以上分别出自 ikClut 改変まとめ、ikClut 改変 Flower、ikClut 改変_yummy、ikClut 改変 秘密の森、ikClut 改变_red_2、ikClut 改变 - R、ikCult 改変_shfilter。

本次的 MME 顺序如下：

![](http://i0.hdslb.com/bfs/article/1d06a755d43e98fc14da9f4d379590ce1b3e5d59.png@210w_488h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/1a6dfcdec14d29ea890a1bfc5a4e2ce9263be153.png@206w_327h_progressive.webp)

ikGouache：Tr 0.15

第三个渲染配方如上。

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

最后一段的画面大致如图：

![](http://i0.hdslb.com/bfs/article/daf2d592445f590b4d3b3bbcf9c2bdd5970353c0.png@942w_531h_progressive.webp)记忆

这段没有场景，基本上是围绕怪獣対若大将 P 的暗く光る空 ZZ7 这个天空盒来进行渲染的，所以专属性有些强。

相机界面：赤绿蓝不动，X+0.5，Y-0.7，Z-0.8

SKYBOX：TopV+0.1，MediumV-0.25，BottomV-0.2，EnvDiff+0.05，EnvSpe-0.05，EnvX+0.55  Z+0.1

Controller：sunlight+0.15，sunshadowR+0.1  B+0.05  V-0.25，Multi-0.2，SSA0+0.15  -0.6，SSDO+1

BloomTd+0.7，BloomRadius-0.15，AllV-0.25，BloomColorH+0.65  S+1  V+0.05，Exp-0.1

Contrast+0.25，Saturation+0.05，Gamma-0.25  -0.05，Tem+0.05，BalanceR+0.2  G+0.15  B+0.1

正面光的打法同上，在 light 栏改成最长的那个。光源方向 Y-0.55，R/G/B+1，Range/Hard+1，In-0.35。

两个侧面光的光源方向为 X±14，Y14，Z-77，R/G/B+1，Range+1，In-0.25

SDFA：X 7.0，Si 0.7，Tr 0.7

Croquis：X/Y/Z 0.15，Si 0.55，Tr 0.55

PostDropHair：X 0.14，Y 0.07，Rx/y/z -350，Tr 0.35（不懂怎么用这个 MME 的请看 [CV17518919](https://www.bilibili.com/read/cv17518919?from=articleDetail) 的最后一个分类）

SvSSAO：Si 0.7

AutoLuminous：X 6.0，Rz 1.4，Si 0.55

PostRimLighting：Si 0.7，Tr 0.7

lightbloom 的控制器数值：BT 0.28，BR-0.25，AllV-0.35，BloomColor3H+0.1  S+1

载入 Cr_入射光 4.x，Tr 0.25。

WorkingFloorAL：Y -0.01，Si 100，Tr 0.8

然后是滤镜 timeﾟ∀ﾟ)σ 

1. シェイク：Tr 0.15

8：Tr 0.35

salute：Tr 0.05

06_不夜城：Tr 0.25

2：Tr 0.35

7. ポップコーン：Tr 0.15

以上分别出自 ikClut 改変_yummy、ikClut_改变_Wuu、ikclut_Carnival of doomsday、ikCult 改変_shfilter。

再确认一下顺序就行啦： 

![](http://i0.hdslb.com/bfs/article/5597606a85cb0d93028dc58e4331abdb9afc61fb.png@240w_492h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/4836047f06e882a2d926d539d5109c9e08094514.png@228w_290h_progressive.webp)

ikGouache：Tr 0.15

第四个渲染配方如上。

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

最后整理一下我用到的滤镜包：  

ikClut 改変_yummy  by うみ

ikClut_改变_Wuu  by G_Wuuuuu

ikclut_Carnival of doomsday  by Wind.

ikCult 改変_shfilter  by サクライ

ikClut 改変まとめ  by ジノク

kClut 改変 Flower、ikClut 改変 film  by ハル

ikClut 改変 秘密の森  by 八実零々

ikClut 改变_red_2  by 鶴千暁

ikClut 改变 - R  by 盐渍甜樱酱

ikClut 改变_Simon  by 某璃的云鹤

ikClut 改変 OldLens  by 午前３時のおやつ

ikClut_xx01  by 响弦

ikClut 改变 CP  by 知了蝉

对所有配布者表示感谢。也感谢您的阅览。

> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv17518919?from=search&spm_id_from=333.337.0.0)

> 前言：本人水平很菜，只会 ray 渲且正如标题所言用于自存，不过某些小技巧是所有渲染通用的。

**前言**：本人水平很菜，只会 ray 渲且正如标题所言用于自存，不过某些小技巧是所有渲染通用的。想到哪写哪，大部分是自己摸索，可能对读者（您）而言非常基础，所以如有错漏之处恳请指出。  

斗胆抛砖引玉，见笑。

不适合完全没有基础的人看，如果您连基本的导入都不清楚该怎么做的话，还是建议先看其他人的教程。本文中提到的所有数值都并非固定的，仅用于参考。本文中提到的 MME 如果我记得可以提供原作者的配布页面，我不记得就麻烦您自行搜索了，基本上都是公配 or 公配过的。

能接受的话再请往下看吧σ`∀´) 

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

◇关于 ray 渲中开启轮廓线之后会出现黑色块状物的情况

其实 ray 渲的轮廓线并不是很好用，它会把一些隐藏的材质也一起加上黑线，导致观感上有些欠缺。因为这种情况出现的概率比较玄学，所以对于我这种手残且懒的人来说直接关闭比较容易。在 outline 栏把打钩的地方取消就行。

☆如果不知道怎么打开 ray 渲的轮廓线，可以在 ray.conf 中修改，将 OUTLINE_QUALITY 后面的数字从 0 改成 1/2/3，0 是默认关闭，1 是开启，2 和 3 是在 1 的基础上有抗锯齿，一般 **2** 就够了。

假使考虑到画面还是需要轮廓线，建议直接载入轮廓线专用的 MME。推荐 SDFA_v1.21（by 鍵束）或者 Croquis 改_v2（by Elle / データ P），但是在 ray 渲中前者的效果并没有后者那么直观，我个人还是更倾向于使用后者。

我平常使用的数值为：**X/Y/Z 0.15** → **Si 0.35-0.55** → **Tr 0.55-0.7**

说到 Croquis 改_v2，它还有很多改变 MME，推荐大家都尝试一下，比如 **Croquis 改変_フレア（by ひいらぎ）**就是各种改色后的轮廓线（貌似还有点滤镜效果）。

◇个人打光惯用选择：Directionallight

我的习惯是天空盒使用逆光，再用 DL 打正面光和侧面光，因为这个光它打得范围大，还方便调整。

↑通过这个已经可以知道本人确实菜且懒了 (;´ ヮ `)7 

正面光我会在 light 那栏把它的默认 fx 换成最长的那个，ambient_with_shadow，光源位置如果有地板就 - 1.8 没有就保持不动，到时候在 MME 栏一起取消，光源方向 **-0.35**，R/G/B **拉满**，Hardness **拉满**，**Intensity-  0.45-0.65**。这样可以给面部、头发留下阴影。

不过实际上我一般只给脸打，头发我用的是别的 MME，会在最后的 PSSM 栏取消头发的钩（不取消也没问题，但是看着会有些别扭），这个后面再讲。

侧面光的控制器数值是随环境变换的，这里不固定。我可以说下个人习惯的光源方向的数值是 **X±14,Y14，Z-77**，有两个从后方打过来的侧面光，一边一个。

当然还有一些点光源之类的，这个我就按个人习惯哪里太暗放哪里，毕竟 SpotLight 确实很好用。

☆**PostSpotLightDark v2.3c（by 角砂糖）**是可以和 ray 渲同时使用的。

◇材质出现白边的情况

如果关闭异性过滤还不能解决的话，可以参考：

有两种是 ray 渲专用的材质，**RayMMD Cutout Material（by StarNoodle495）**，以及 **ray-mmd_AlphaPatch（by less）**，记得在 main 栏和 material 栏分别载入材质包中专用的 main 和 material 文件，两者都需要这么做。还有一种是在 main 栏载入可以兼容所有渲染的 **o_full-AlphaTest（by おたもん）**。

◇眼睛部分太黑的处理方法

眼白部分比较简单的处理方法就是在 SSAOmap 栏里直接将眼白部分的阴影换成 0，但还是有可能变得很黑，那么我们可以使用 **ray-mmd Ver1.5.2 用 初心者マテリアルキット（by 更科）**中的 material_eye_white。顺便，这位作者的其他材质也很好用，如有兴趣可以自行尝试。

眼睛部分可能大多数人比较喜欢 AL 那种，我比较喜欢**発光コンタクト（by 966）**这种更自然一点的，当然这个只适合天空盒的参数处于逆光状态中，正面光的话会非常非常亮，无论用哪个都看不出本来的颜色，但是用 ray 的各种 light 打正面光是没问题的。

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

◇ikBokeh 的数值

我个人是习惯设置好一个值直接备用，镜头拉远 / 近后模糊的地方，再在那段镜头中间修改控制器中的数值。所以这里记录下平常习惯使用的数值供大家参考（没写的都是 0）：

**ピント距離 +    0.15**

**ボク +    0.28**

**前ボク -    1.0**

**Co      0.05** 

**玉ボク强调    0.3**

◇ikGouache 真的很好用

载入之后是犹如油画一般的效果，可以用于处理和人物风格不搭的场景，包括人物模型本身。

如果人物本身足够 2D 化了可以在 MME 的 DetailMap 栏选中角色后将默认的 fx 换成有 cancel 后缀的，Tr 的推荐数值为 0.15-0.3，太低了和没加载差不多，太高了的话远看很糊，容易把细节吃掉。

其实 ikDryBrush 也能做到，类似于铅笔画的感觉，但会不断抖动，对我来说很难调，所以我就不提供数值参考了（。）

◇Rhinestone - blingbling 会闪光的特效

这个感觉很多人知道，但考虑到知道却不会用的情况还是说一下好了。

没有 al 前缀的可以直接在 main 栏载入，有 al 的载入后在 AL 光的对应栏还要载入一遍才能有【明显】效果。个人平常喜欢放的位置：头发、领带 / 蝴蝶结、裙摆、鞋跟。具体情况具体分析。

同时推荐一个很好玩但我没怎么用过的改变后 MME：Galaxy Shader for Ikeno s Rhinestone（by MMD-Kyu），依然会闪光但整体会变黑，大概是这个效果：

![](http://i0.hdslb.com/bfs/article/ae7764393e5ebc9167106bbbf76f5e261414df44.png@942w_531h_progressive.webp)Model by DesmondChan

这个实在是不太好描述，我就直接上图了。  

◇ikGodray - 使用时记得取消天空盒 / 场景的勾选

如果不勾选的话会被遮蔽，ikGodray 这个偏白，ikGodraySun 这个偏金。

个人数值：**Si  0.35-0.55** → **Tr 0.55-0.7**

◇ikLensGhost - 光晕效果

因为我个人更习惯使用纯白天空盒（Sky Hemisphere），所以 ray 渲的镜头光晕我基本没用过……

这里也是直接提供数值参考：**X/70   Y/70   Z/35   Si/0.7   Tr/0.35**

根据场景的亮度不同，这些都可以更改。

如果嫌数值太多太麻烦，**ScreenTex 改変_動く入射光（by のりしお）**也是个不错的 MME，可以直接表现出合适的效果，仅需要调低 Tr 值即可。

◇ikClut - 我渲染画面全靠它了

简单粗暴一点，这个就是滤镜。看过我 MMD 的应该都知道我画面效果全靠叠滤镜，自己调色能力实在不行。

所以这里列举一下我常用的滤镜包 (ゝ∀･) 

我入坑晚，以下基本上都是正在公配中的，限时的应该没有。

**ikClut 改変まとめ by ジノク**

**ikclut_Carnival of doomsday / ikClut 改变_If / ikClut 改变_Love by Wind.**

**ikClut_xx01 by 响弦**

**ikClut_改变_Wu / ikClut_改变_Wuu by G_Wuuuuu**

**ikClut 改変 film / ikClut 改変 Flower by ハル**

**ikClut 改変 秘密の森 by 八実零々**

**ikClut 改変 白昼夢 by Ｍ・ト路ッソ**

**ikCult 改変_shfilter by サクライ**

**ikClut 改変_dystopia by 佐里井**

当然不止以上（我下载的至少几十个），总之还是推荐大家多去 B 碗上下载和尝试。

◇ikOverray - 默认跟随 MMD 内光照设定改变方向

这个在逆光中比较好使， 我一般使用的是 **ikOverray 改変_color（by うみ）**，有不同颜色的光可以选择，不怕麻烦或者觉得可选颜色数量太少的还是直接用原版好一点。我在使用时会把 Tr 值尽量调低，大概在 **0.15-0.25** 中间。

☆ik 渲有很多是可以和 ray 兼容的，还有很多有趣的 MME，请大家下载后自行尝试吧ᕕ(ᐛ)ᕗ 

以及，虽然 SvSSAO 与 ray 兼容，但 ExcellentShadow 不兼容。Ex 是根据 MMD 本身的光影来进行调节，而 ray 在载入之后会将其全部覆盖，故而 Ex 无法起作用。

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

其实到这里也没什么好讲的了…… 只能推荐点增加画面观赏度的 MME，毕竟我水平就这样。

◇天空盒

**Color_Dome_mo by mo** ：纯色

**s_skydome_data by さらは** ：比较梦幻，以蓝色粉色金色为主要色调。

**和風スカイドーム by シトロン（枸櫞）**

**怪獣対若大将 P** 和 **額田倫太郎** 都是比较写实的风格，鉴于这两位配布的实在太多了，我就不一列举了，直接搜 ID 更直观。

◇地面类

**966_DigitalRipple by 966** ：踩在地面上有波纹效果，RM 里有写推荐数值。

**SnowPlane_v0_3 by ビームマン P** ：雪地效果，如果人物动了会留下痕迹。

**砂浜 by ame2** ：是上面的改变版，从雪地变成了沙地。

**WorkingFloorAL 改変_割れハート by 桜和** ：在 workingfloor 的基础上，人物脚下会有裂开的爱心，行动了的话爱心也会跟着动。

**WorkingFloorX_v005 改_桜型 13 色 by ゆえ** ：同上，不过形状是樱花。

**WorkingFloorX_v006 - 改 by びすこってぃ** ：同上，可选形状更多，有五个。

**粒子床パーツ by ゆづき / 万年寝不足** ：这个我看有人问过，其实是包含在惑星ステージ里的，下载到这个场景就能找到了。万年寝不足的很多场景都附带有 MME 可以独立使用，建议多多下载。

◇粒子类

**小花パーティクル / 落葉パーティクル / 金箔パーティクル by ゆづき / 万年寝不足**

**藤の花パーティクルセット / 火の粉と焼けた紙エフェクト / 椿パーティクル by 一護牛乳**

**降雪 by 蒼すずめ**

**KiraKira_Z_LE_sakura 配布用 / KiraKira_Z_LE_キラキラ星配布用 / KiraKira_Z_LE_ハートセット改配布用 / KiraKira_Z_LE_竹の葉っぽい配布用 / キラキラエフェクト Z 改変星セット（配布用） /  蛍っぽいエフェクト Ver.1.0 by さくや**

**KiraKira_Z_LE_改変_2434 パーティクル by 心温**

**Puzzle_Particle / Rose_petals / Shatter Set / Bubble_ParticleV2 by winglayer**

**Sakura_v2_(Change1.1) by 溯北 P** 

**Sakura_v2 改変_紙吹雪 by ノン**

**キラキラエフェクト改変_フラワー＆スノー / キラキラエフェクト改変_フラワー＆リーフシャワー by ひいらぎ**

**butterfly_with_controller by VaDiM & Sh5**

◇屏幕类？

**evantine's screentex pack by 針金 P** ：各种边框

**ScreenTex_AS01 by 重言阿司**：同上

**ScreenTex_v004 の改変_額縁 / ScreenTex_v004 改変_2017.3.3** by 山田淀子 ：同上

**ScreenTex 改変_LBP by のりしお** ：同上

**ScreenTex 幅目安レターボックス by 潮** ：就是宽度不同的黑边啦，我个人很喜欢用。

**ScreenTex 改変 血糊 by M ・ト路ッソ**

**ScreenTex 改変_飛沫 by ヨーグルト姉**

**改変エフェクト３種 by のりしお**

**LiteDOF v3 by akeru ：前置模糊？**

**動く水面 - 改変 ScreenTex_v004 by 桜井 (kotami cafe)**

其实还有很多，只要搜 ikClut 或者 ScreenTex 能找到很多啦，我就不一一列举了。

◇不好形容的

**漫画風シェーダーエフェクト by ロットん** ：质感还不错的漫画风 MME，需要在 main 栏载入。

**PostDropHair_v0.4 by P.I.P** ：在前面提到过的给头发上阴影的 MME。载入 PostDropHair.x 后，在 MME 栏的 DropHairRT 选中头发换成前髪影，在 DropHairMaskRT 选中头发再换成影マスク。个人使用数值：**X/0.14  Y/0.07  RX/-350  RY/-350  RZ/-350  Tr/0.35。**

**PostRimLighting by ミーフォ茜** ：给边缘加光，在不需要的部位可以换成 PRL_InvisibleMask。

**切り絵トゥーン by 966** ：使模型黑白化，和発光コンタクト一起使用有特效。

**動く目隠し線 by のりしお** ：YOASOBI 様の楽曲「夜に駆ける」の MV に出てくる動く目隠し線っぽい物です。←RM 里的原话，MV 里眼睛那部分啥样用了它之后就可以啥样，使用时记得绑定到人物模型的 “頭” 骨。

**測定グリッド**  **作者不明** ： 字面意思，可以测算模型的身高，适配什么样的镜头。

**マンガっぽい吐息 by マルヒマ** ： 可以模仿呼出来的气，同样需要绑定人物模型。

**煙草用エフェクト by 塩イタチ** ： 字面意思，可以模仿烟点燃的效果。

**DropShadow_monochrome by chestnutscoop** ：黑白灰三种颜色的十个剪影。

**DropShadow_pastel / DropShadow_solid by chestnutscoop** ：赤橙黄绿青蓝紫七种颜色的剪影。

**Breath_v1_1 by ビームマン P** ：模仿呼出来的白气，RM 里有推荐数值参考。

**MeraFireParticle_v002 by 針金 P / MeraFireParticle 改変 7 色 by ame2** ：类似点燃的火，同时伴随有烟。

**CheapLens by そぼろ / CheapLens 改変_濃いめレンズ by ひの** ：边缘色移。改变版是换了不同颜色的。

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

暂时就到这里，感谢您的观看。

如果能对您起到一点帮助，不胜荣幸。

![](http://i0.hdslb.com/bfs/article/bb0392989191b21047a64c7f4da0d0dbf7d7275c.png@942w_531h_progressive.webp)借物表见 [BV1QU4y1m78s](https://www.bilibili.com/video/BV1QU4y1m78s?from=articleDetail)

2022.07.11 唐子七

2022.07.12 修改了部分错误数值、病字病句。增加了部分 MME 推荐。
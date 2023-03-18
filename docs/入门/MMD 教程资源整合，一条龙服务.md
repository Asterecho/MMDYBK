> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv15202676?from=search&spm_id_from=333.337.0.0)

> 开头作者的一些废话 3 年前已经写过了一篇关于 MMD 的教程资源整合专栏，但是随着时间的推移，其中部分链接已经失效，且内容亦需要补充完善，弃了好久的坑今天终于把它填上了。

开头作者的一些废话

       3 年前已经写过了一篇关于 MMD 的教程资源整合专栏，但是随着时间的推移，其中部分链接已经失效，且内容亦需要补充完善，弃了好久的坑今天终于把它填上了。

给萌新的话

       MMD 是一个门槛低上限高的一款三维动画软件，通过自己的学习钻研，定会开启不一样的新天地。

**前言**

 在 MMD 中，最为 MMDer 津津乐道的便是渲染，相信很多开始入坑的 MMDer 也会极力追求渲染的学习，我建议在去正式打开 MMD 研究渲染之前，先去看看优秀的 MMD 作品，或者优美的插画图片（se 图），只有在自己的审美得到提高后，才能知道自己想做出什么样的效果，从而在画面中表现出来。此外，追求更高原创性的 MMDer 肯定不会止步于渲染，MMD 的创作形式除了渲染，还有 K 帧，后期，模型等。当你渲染技术到了一定的高度后，不妨再去走走其他的道路吧。本专栏只提供教程，不负责教程中所需资源的指引如模型、软件等。

**准备工具以及工具介绍**  

**必要工具**

 MMD，全称 MikuMikuDance：是制作 MMD 视频的主要软件，目前更新到了 931 版本，国内能找到汉化版，需要 MME 插件才能进行各类 MME 的使用（即特效渲染），联动专业渲染器导出 abc 格式则需要桥版本。

**推荐工具**

      格式工厂：用于各种文件的格式转换

      Bandzip：解压用，可切换语言模式，防止乱码

      Notepad++：用于打开乱码的日文 Readme，或者更改 MME 中的代码参数。

      Photoshop：图片的处理

      Premiere/Aviutl：视频剪辑

      AfterEffect：视频后期处理

      PixPlant：材质纹理制作（对于 PBR 渲染需要用到）

      PmxEditor：MMD 模型编辑

      Metaseq/C4D：建模

      Blender：建模 / 剪辑 / 渲染（呀屎啦 老子全能做）

      小丸：视频压缩工具（主要用于防止 B 站 2 压）

      注：蓝色为第一推荐

**1.MMD 零基础教程（从****熟悉****软件开始）**

链接：[https://www.bilibili.com/video/av16525939](https://www.bilibili.com/video/av16525939)

这个视频也是 Up 自己入门看的第一个教程视频，大哥讲的很好理解，可帮助萌新快速入门。

使用别的太太配布的资源的时候，记得看 Readme，借物表要全！！

**2.MMD 零基础渲染教程**

MMD 的渲染依靠的是 MME，MME 大体分为主渲和特效，主渲主要用于为模型场景进行渲染处理，特效例如烟雾，粒子，主要用于给画面点缀，此外还有其他类型的 MME，如景深、滤镜等。

MMD 的主渲有很多种类，目前就 Up 自己用过的就包括 Ray、GenshinShader、PowerShader、A-Toon、PAToon 等，我不可能一一列举他们的使用方法，这里我将几个主流的渲染附上教程链接：

![][img-0]

Ray：

[https://www.bilibili.com/video/av18499776](https://www.bilibili.com/video/av18499776)

作者：RedailC

非常适合新接触 ray 的萌新达到快速入门的目的

Ray 进阶：

https://www.aplaybox.com/article/details/584129632

作者：Biscuit-773

具体到 Ray 的各项参数，虽有很少部分的内容需要完善，但是基本讲的很仔细，极力推荐  

[https://www.bilibili.com/video/BV1ZF411v7Py](https://www.bilibili.com/video/BV1ZF411v7Py)

作者：三金络合物

在 ray 中使用了等高线贴图以达到仿原神渲染的目的

其他 Ray 的补充：

[https://www.bilibili.com/read/cv14396290](https://www.bilibili.com/read/cv14396290)

作者：AR

修正了法线贴图在 MMD 中的使用

![][img-1]

msToon：

[https://www.bilibili.com/read/cv11034495](https://www.bilibili.com/read/cv11034495)

教程翻译作者：文音 - あやね -

效果瞩目的 2D 渲染

![][img-2]

合成类渲染：

[https://www.bilibili.com/read/cv6913121](https://www.bilibili.com/read/cv6913121)

作者：Taitohimea

作者在文章中提到了 M4Layer，这个 MME 也是合成流中的一种，T 姐在上面的文章中主要讲的是将遮罩用于后期软件进行合成渲染，M4Layer 则是直接在 MMD 中新开了一个 main 栏，并在该栏中进行合成渲染，M4Layer 与后期软件一样可以改变其影响下的模型与其他物体的叠加方式，本文仅仅是教程资源的整合专栏，这里不作过多赘述。最后推荐两款 MMD 配合 AE 的工具（合成流适用），MMD2AE：适用于将 MMD 的镜头数据导入到 AE 中进行后期合成；vmd Exporter 140：适用于将 AE 的镜头数据导入到 MMD 中进行使用。

![][img-3]

补充：

MMD 中一些常见 / 不常见问题的解决方案：

https://www.aplaybox.com/article/details/168657218

作者：枣

主要讲了渲染上可能会出现的问题以及关于视频导出的参数设定相关。

![][img-4]

这里我不推荐新人去看渲染配方类的教程，因为人家的配方不一定就适合你，你也不一定能照抄的一模一样。拿 ray 举例，对于人物身上的颜色，除了受 ray 的控制器、ray 的天空球环境光、ray 的灯光影响外，还和 ray 配置文件中设定的参数、人物材质参数以及日光颜色有关。

**3.MMD 零基础后期教程**

PR：

[https://www.bilibili.com/video/av27150046](https://www.bilibili.com/video/av27150046)

作者：我是于千

PR 是一款大众化的剪辑软件，学习来很容易，制作字幕、拼接片段、视频调色等方面十分友好。

![][img-5]

AE：

[https://www.bilibili.com/video/BV1Na4y1x7H5](https://www.bilibili.com/video/BV1Na4y1x7H5)

作者：影视后期日暮 Ailsa

小姐姐声音很好听，讲解很到位，这也是 Up 自己入门 AE 的教程之一

![][img-6]

Media Encoder：

[https://www.bilibili.com/video/BV1ep4y1p7F1](https://www.bilibili.com/video/BV1ep4y1p7F1)

作者：瓜皮油皮主

![][img-7]

这款软件可以批量导出视频，相对于 AE 直接导出而言，占用的内存会稍微小一点。但是安装这个软件的时候请注意，你所安装的 Media Encoder 的版本必须与 AE 和 PR 一致，AE 和 PR 的联动也需要保证其版本一致，所以这里 Up 建议在安装上述三款软件的时候直接使用同一个版本，这样能为以后各个软件之间的联动提前做好准备，避免不必要的麻烦。

**3.MMD 零基础 K 帧教程**

动作：

[https://space.bilibili.com/18316420/channel/seriesdetail?sid=1275925](https://space.bilibili.com/18316420/channel/seriesdetail?sid=1275925)

作者：MAC 创作学园

[https://www.bilibili.com/video/BV1Es411S7rs](https://www.bilibili.com/video/BV1Es411S7rs)

作者：CY

![][img-8]

镜头：

[https://www.bilibili.com/video/BV1Ns411f7j6](https://www.bilibili.com/video/BV1Ns411f7j6)

原地址：[](https://www.bilibili.com/video/av570037/?spm_id_from=333.788.video.desc.click)[sm16276623](https://acg.tv/sm16276623)

主要将讲关于 MMD 中补间曲线的知识

[https://www.bilibili.com/read/cv5127468](https://www.bilibili.com/read/cv5127468)

作者：Sano_

使用插件让 MMD 的镜头具有手持微微晃动的效果。

其实 B 站并没有关于 MMD 镜头的教程，更多的分镜、切镜技巧还得自己多加练习。

**4.MMD 零基础改模教程**

[https://www.bilibili.com/video/BV1Px411M7tM](https://www.bilibili.com/video/BV1Px411M7tM)

作者：oeasy

MMD 的改模主要使用的工具是 PmxEditor，可以通过该工具对 MMD 模型进行纹理的修改、表情、骨骼的制作等一切关于 MMD 模型的编辑操作。

**5.MMD 零基础 MME 编写教程**

[https://space.bilibili.com/27611393/channel/seriesdetail?sid=1246046](https://space.bilibili.com/27611393/channel/seriesdetail?sid=1246046)

作者：KarlvonDonitz

K 佬很强，是第一个我入坑 MMD 以来认识到的手码 MME 的男人，他本人也配布了许多实用的 MME，例如伪 3D、选择材质保留颜色（其余黑白处理）等

**6.MMD 技能树点歪教程**

**（1）布料解算**

[https://www.bilibili.com/video/av29732454](https://www.bilibili.com/video/av29732454)

作者：不想起床的懒虫熏染

**（2）Blender**

[https://www.bilibili.com/video/BV1Zi4y1b7vv](https://www.bilibili.com/video/BV1Zi4y1b7vv)

作者：RedailC

**（3）C4D**

[https://www.bilibili.com/video/BV1Qx411U7hs](https://www.bilibili.com/video/BV1Qx411U7hs)

作者：_碧空残云_

关于专业渲染器的教程实在是太多了，这里只是选了几个能很快出成果的教程。

**6. 其他补充**

关于 MMD 的相关发展历程以及现状：

https://www.aplaybox.com/article/details/155373353

作者：EX 涼芯

新人适当了解，避免越线

![][img-9]

新人向 MMD 资源较详细全面索引：

https://www.aplaybox.com/article/details/695739136

作者：H2Cu 阿相

![][img-10]

再也不用担心模型压缩包乱码啦！免费压缩软件 Bandizip 介绍：

https://www.aplaybox.com/article/details/389430561

作者：模之屋实习小编

**结语**

    MMD 的创作是自我审美的体现，希望更多的 MMDer 并不是单纯的套套乐，而是真正做出自己心中所想、怀中所爱。

Up 个人收藏的优秀 MMD 作品：

[https://www.bilibili.com/video/BV1as411G7Q3](https://www.bilibili.com/video/BV1as411G7Q3)

[https://www.bilibili.com/video/BV18C4y1p7qD](https://www.bilibili.com/video/BV18C4y1p7qD)

[https://www.bilibili.com/video/BV1v64y1x727](https://www.bilibili.com/video/BV1v64y1x727)

[https://www.bilibili.com/video/BV153411v7LR](https://www.bilibili.com/video/BV153411v7LR)

[https://www.bilibili.com/video/BV14L41157vU](https://www.bilibili.com/video/BV14L41157vU)

[https://www.bilibili.com/video/BV1nR4y1j7yW](https://www.bilibili.com/video/BV1nR4y1j7yW)

Up 个人部分 MMD 静画：

![][img-11] ![][img-12] ![][img-13]

借物见图片下方 Bv 号中

附：小居所技术交流群：787522419

**感谢你的观看**

[img-0]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-1]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-2]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-3]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-4]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-5]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-6]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-7]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-8]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-9]:http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png

[img-10]:data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABSQAAAAEAQMAAACtNaOvAAAABlBMVEUAAADAwMBkVjpxAAAAAXRSTlMAQObYZgAAACdJREFUKM9jGBrg////DPb//x/g////A/P//38GpcBgcAMRrhwSAABR2ukX7NiksgAAAABJRU5ErkJggg==

[img-11]:data:text/plain;base64,dW5rbm93biBwYXJhbXM6IHByb2dyZXNzaXZlLndlYnBidjFjNDR5MWE3a2JodHRwczovd3d3LmJpbGliaWxp

[img-12]:data:text/plain;base64,dW5rbm93biBwYXJhbXM6IHByb2dyZXNzaXZlLndlYnBidjFyeDR5MTU3cGdodHRwczovd3d3LmJpbGliaWxp

[img-13]:data:text/plain;base64,dW5rbm93biBwYXJhbXM6IHByb2dyZXNzaXZlLndlYnBidjEyczR5MXg3c3JodHRwczovd3d3LmJpbGliaWxp
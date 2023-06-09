> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv41130?from=search&spm_id_from=333.337.0.0)

> 作者：[TerayTech](https://space.bilibili.com/24434095)

 前言： (｡･∀･)ﾉﾞ嗨大家好，我是 TT。本文的内容基本在我的教程中都出现过，只是写给那些比较无聊的人看一看，总结一下我们走过的路。全程无图，没有耐心可以不用看的。如果有内容不准确，欢迎私信我反馈，

>  (｡･∀･)ﾉﾞ嗨大家好，我是 TT。本文的内容基本在我的教程中都出现过，只是写给那些比较无聊的人看一看，总结一下我们走过的路。全程无图，没有耐心可以不用看的。如果有内容不准确，欢迎私信我反馈，感激不尽！

那时大概是 2015 年的夏天，我刚入坑 MMD 的时候。我受一家漫展主办方的拜托，为漫展制作一段 MMD 动画。那个时候我对于 CG 方面还没有一丁点了解。

在网上寻找了各种各样的资料之后，我第一个打开的软件就是 Cinema4D。现在基本上所有玩过 MMD 的同学都应该对这个软件有所了解吧，可能大部分人都能看到 C4D 渲染出来的一些动画的画面非常漂亮。但他们可能不知道的是，这种渲染的效率很低。如果你拿一些热门的 GPU 渲染器，比如 blender 的 Cycle、Octane、Redshift 进行比较，你很轻松就能体会到效率上的差距了。

我当时刚刚入坑 CG，从来没有接触过任何一台相对来时能算得上是 “高性能” 的计算机。第一次安装 C4D 是在一个联想的笔记本上，这台笔记本还是学校在 2012 年发给教职工使用的办公笔记本。CPU 是 i3-380M，2C4T，主频为 2.53GHz。带有 GeForce 310M 独立显卡，显存 512MB。就是在这样的一个条件下，我开始了对 MMD 的研究。现在想想果然还是当时太年轻了呵呵。

动手 ******D 项目，参照 zzb311 的教程，很快就能做出来了，渲染第一张差不多花了十几分钟吧，当时 zzb 使用的也是像我这样的笔记本，CPU 系列也是 i5，具体是哪个型号记不太清了，但是也是第一代处理器。所以我们的用时基本上都差不多。的确，那个时候看着橘黄色的小框框一个一个的把图片渲染出来，是一件很神奇的事情。那个时候我才刚刚高一。

到了差不多八月，看了极客湾做的节目，推荐和很多百元神 U。于是攒了一些零花钱，购进了一片 AMD X4 955 处理器，接口为 AM3+。之后买了一张 ASUS M5A78L-LE 的主板。买了一块 NVIDIA Quadro FX3800 的专业图形卡。当时也是属于太无知了，不知道游戏引擎可能使用游戏显卡会更好一些，才买了这张专业显卡。再加上两根 AMD 专用内存，继续学习各种东西。当时的 CPU 已经是 4C4T 了，主频高达 3.2GHz。有时候渲染喜欢超频到 3.8 甚至 4.0GHz（当然现在的我肯定会认为超频渲染是一种十分愚蠢的行为）。这一次的升级，对我的 CG 学习效率有了很大的提升。当然 C4D 的渲染速度也就快了许多。但是很快的，他的渲染能力不再能满足我的需求了。

一种能代替 C4D 原生渲染器的更高效的渲染器成为了当时我寻找的目标。

也可能是比较巧吧。七月底的时候，在 MMD 百度贴吧出现了一个新的帖子。帖子的内容，正是 MMD 与虚幻 4 联动教程。教程的作者是 bahadaXXZM（现名 Arno_）吧哈达是我的好朋友，比我大了两岁，正在大学就读。就是他考完高考的那年暑假，他和一名台湾人霓虹猫（NeonCat）共同编写了这篇教程。而这，便是国内 UE4 联动解决方案发展的开始。

从 MMD 到游戏引擎，需要解决的最大问题就是模型问题。（其实模型动作表情摄像机都有问题.. 没一个是正常的。）下面我就来分析一下，从 MMD 模型到虚幻 4 的几种不同的方法。

首先就是最原始的 Pmx2FBX 导入法。PMX2FBX 最初起源于 Unity 的 MMD 插件——MMDMecamine。可以简单的认为，PMX2FBX 的程序就是从该插件中提取而来的。Github 上可以下载到这个程序。后来由吧哈达编写了一个批处理文件，使其更加方便的执行。你只需要在批处理文件中输入你想要转换的模型名称以及你想写入模型文件的动作数据名称，就可以一键转换为可以导入并且带有动画的模型文件了。但是这个插件有一个很大的缺陷。那就是完全无法使用表情。虽然这个插件导出的模型的确带有顶点变形目标（morph targets），但是导入之后其顶点变形目标没有任何关键帧。如果你懂一些虚幻开发有关的知识与开发能力，并且不需要表情关键帧或者是你有其他的硬件或是软件可以用于驱动表情关键帧，那么你完全可以使用这种转换方式，简单高效又便捷。

IM4U 导入法。IM4U 是 Github 上的一位开发者。从大约 UE4.3 的版本开始，他就已经开始开发 IM4U 系列的导入插件。IM4U 也是全球最先开始使用虚幻渲染动画的插件之一。通过一系列修复手段，例如单独导出表情动画关键帧、对模型表情部分进行修改、使用虚幻的动画蓝图等功能，的确是可以成功的修复使模型带有表情动作。但是我并不提倡大家这么做。有几个原因，第一，整个过程极为复杂，步骤繁多，很容易出错。我第一次操作的时候，重新制作了四五次，反反复复的询问吧哈达一些出现的问题，才最终成功制作出一个项目。当时也是觉得这种方法难度极大，光靠文字教程不一定能让大多数人看得懂，于是我便提出了制作视频教程的想法。然而制作视频的过程中还是出了许多次问题，最终一一解决，才做出了完整的一套教程，如需参考，可以简单的看下联动教程的第一集到第四集。

Blender 导入法。Blender 是一款小巧开源而又功能强大的 3D 工具。在 blender 中，有一个非常优秀的插件名为 MMD-Tools，在 git 上可以很轻松的找到。MMDtools 不仅可以正常的导入普通的 MMD 模型，而且还可以帮助所有动画关键帧烘焙物理效果，是目前所有专业 3D 软件中，出现 bug 最少的工具了。而且 blender 的 2D 渲染能力也是很棒的，有兴趣的同学可以尝试一下 blender，极力推荐。虽然 blender 在 MMD 模型导入方面看似已经比较完美了，但是它在导出方面仍然有一定的瑕疵。MMD 模型在导入过程中，会出现骨骼重名的现象。这个现象在 blender 输出 fbx 文件时成为了一个很棘手的问题。UE4 的模型定义方式不允许模型出现重名的骨骼，如果有重名便会报错，导致整个模型导入 UE4 失败。于是 git 上就在 MMDTOOLS 的下方，出现了一个 python 脚本，正是用于导出 UE4 时解决骨骼重名问题的脚本。这个脚本的工作原理很简单。就是把平时很容易出现重名问题的一部分骨骼重命名，通过这种方法来解决报错的问题。但是即便你正确的运行了这个脚本，完成了重命名，也仍然不一定能够成功的导入 UE4，这边是许多同学反映的问题，即便运行了脚本，尝试了多个模型，也只有少数模型可以使用。（我尝试了几个 icemega 的模型，都是可以的）还有一种解决方案，就是在运行脚本的基础之下，手动寻找并修改重名的骨骼，也是有一定几率可以成功的，祝君好运。

MMDBridge 全帧烘焙法。这个方法主要是日本地区的朋友们在使用。我也不是很清楚为什么我们的电脑无法烘焙。MMDbridge 想必使用过 C4D 的朋友们都不会陌生吧。Bridge 有好几种工作方式，可以输出不同类型的文件，主要是两种类型，一种是 alembic 几何体缓存文件（abc）一种便是 VMD 文件。他输出的 VMD 文件不同于普通 vmd 文件，bridge 在输出文件时，会按照所有的关键帧，搭配补间动画，烘焙出每一帧每一个受控物体的位置。这种方法也被用于解算物理。据我猜测，可能是因为日本地区和我们使用的文字编码不同，从而导致了在写入 vmd 文件时出现的错误，最终得到的 vmd 文件中什么数据都没有。如果你可以成功的烘焙所有的关键帧，此时使用 IM4U 导入这个模型以及动作，就可以达到你想要的结果了——带有表情动画的 MMD 模型。

 **（未完待续）**

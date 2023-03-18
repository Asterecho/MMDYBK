> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv14783392?from=search&spm_id_from=333.337.0.0)

> 动作提取，校对时轴，格式转换，骨骼映射，模型套用——总结下去年折磨自己的最大课题：导出游戏动作，也就是所谓的 Motion Rip。

动作提取，校对时轴，格式转换，骨骼映射，模型套用——

总结下去年折磨自己的最大课题：导出游戏动作，也就是所谓的 Motion Rip。

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

**前言**

**- 本专栏随时可能会因为众所周知的理由而消失。**

- 是 “思路” 而非“教学”，因此写的相对比较简明扼要。但如果看懂的话，可以让具有一定改模基础的人也能试着从游戏里拆动作玩。

- 整个提取流程依然有大量遗留问题以及需要改善的地方，并且实践过程会相当痛苦。

**- **不管什么游戏，提取 = 非正规途径，**无论最终进的是 MMD、CM3D、**恋活还是其他游戏的 workshop，本质还是版权物。**轻则被夹被封号，重则吃 DMCA，**如有意外，后果自负**。**

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

**鸣谢**  

**@LC_ilmlp：**一起高强度摸索开荒的**重炮**同担。除了提取动作以外，之前视频里的表情 / 口型时间轴解析也是通过他写的脚本才得以实现。

另外推荐各位去看看他的整活视频：

![](http://i0.hdslb.com/bfs/article/card/ed11ed28b81646c990318f5fc301eb7a99ef215c.png)

以及其对应教程，里面提到了一些关于 unity 资源分析 & 修改的技巧：

![](http://i0.hdslb.com/bfs/article/card/ebfe3b0d40b4e1092d5048eea02264174d7768f8.png)

**@Crabbed（**Hozuki**）：**最先进行 MLTD 动作提取的，在视频里多次致谢过的**星月佬**，在他的启发以及 github 上的 militore 工具页面的参考下，自己也摸出了 CY 两个游戏的提取流程。

  **@红白 de 黑白：**很早就进行过各类手游动作的提取，并提供了最初 fbx→bvh 的思路指导，为后续的研究找到了突破口。

以及，在屑站 / QQ/discord/deviantArt 上交流过经验的其他研究 Unity 的大佬们。﻿  

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

在阅读之前，请先确保自己对以下内容有一定了解：  

- 会解包，清楚 Unity 游戏的 Animator&AnimationClip 存储方式

- 会通过 AssetStudio 导出带动画的 fbx

- 改过游戏模型，熟悉 MMD 标准骨骼的基本结构 & 命名法  

- 能在 Blender 中进行骨骼动画的预览与导出，并且装好了 mmd_tools 插件**（重要！）**

- 会用 Blender 或其他工具对动作涉及到的 Armature 骨骼进行批量重命名**（非常重要！）**

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

****源文件的**准备**  

首先，准备好通过 AssetStudio 的 “Animator+Selected Animation Clips” 按钮导出的**带骨骼动画的模型 fbx 文件**。

![](http://i0.hdslb.com/bfs/article/12ff678ff9cc6816e418f5eabcb6e3930ade6dc0.png@942w_69h_progressive.webp)

**原则上适用于大部分 unity 游戏，**不知道怎么导出的话请回去重新研究解包。

本次的范例是耳熟能详的，**DD 头子的胜利动作**。

**也姑且算是纪念吧，毕竟，已经过去一个月了。**

![](http://i0.hdslb.com/bfs/article/88f684396a7a2f3ac59cbd16dd5f26a8a76d8b24.png@942w_56h_progressive.webp)

pfb_bdy1019_91（Animator）+ anm_res_chr1019_001（AnimationClip）

上面那个带动画，下面那个不带动画，有做过马娘改模的应该明白是什么意思。

有了源文件就可以开始了。整个流程其实很简单：

带动画的 fbx 文件→记录动作的 bvh 文件→骨骼映射改名→导出 vmd（或是其他软件的格式）

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

**第一步：fbx→bvh**  

左上角 - 文件 - 导入 - fbx，并确保能在 blender 里正常预览动画：

![](http://i0.hdslb.com/bfs/article/b98b646dd61633d2717536b3799f009070c47325.png@942w_567h_progressive.webp)

然后点开右下角①处的 “规格尺寸” 栏，注意到②处默认帧率是 25fps（这点每个游戏不一样，比如 MLTD 就是 60fps 的动作）

![](http://i0.hdslb.com/bfs/article/87f509e551014338a50ac00637b225dd0da5f066.png@677w_1508h_progressive.webp)

众所周知，MMD 的编辑帧率是 30fps，计算得 30/25=1.2，帧率和时间轴均放慢为 1.2 倍，因此在③处的 “时间重映射” 栏里应填上 “新建 / 原始” 为 1:1.2 的平方，也就是 1:1.44 的数值（比如 100:144），也可以自行调节比例以改变速度。

改完之后，拖动关键帧栏会看到映射后的时间轴效果：

![](http://i0.hdslb.com/bfs/article/1cb69da909ff33553829805083e0a507c0f60104.png@942w_72h_progressive.webp)映射前 ![](http://i0.hdslb.com/bfs/article/5e1dabef76bc42065108b185c42659fa0a7d7d9d.png@942w_77h_progressive.webp)映射后

时间重映射完毕后，左上角 - 文件 - 导出 - Motion Capture(bvh)，**不建议在此时****直接通过 mmd_tools 导出 vmd 文件**。

动画的起始帧和结束点按照**时间重映射后**的帧数来定，保险起见可以稍微多一点。本来动作大概是 127 帧，127*1.44=182.88，那就填 190 帧。这个数值并不会影响最后导出的 vmd 的总帧数，原先映射好的动画有多少帧最后导出来的就会是多少帧。

![](http://i0.hdslb.com/bfs/article/3b72c27be551a005e7bfff66ed87ba1fb7f01495.png@560w_410h_progressive.webp)![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

**第二步：bvh→vmd 测试**

新开一个 blender 窗口，导入刚才的 bvh 文件并确认能对动作正常进行预览：

![](http://i0.hdslb.com/bfs/article/0ba974cf394f9fa542d57c5f9decd29dc04913c4.png@942w_567h_progressive.webp)

接下来，在开始骨骼重命名前，最好先把模型和动作在 mmd 里测试下能不能套的上。

先导出 bvh：左上角 - 文件 - 导出 - vmd

同样，将不含动作的 fbx 模型导出成 pmx，然后在 mmd 里载入模型套上动作：

![](http://i0.hdslb.com/bfs/article/218252373e5d41c799be3a6de1670a7116d9a7e5.png@942w_569h_progressive.webp)

（当然，会改模的就可以把动作套到改过的同游戏的模型上进行测试）

确认没问题就可以回 blender 给动作的骨骼批量重命名了。

如果发现 mmd 里没有位移或者位移幅度不对，就需要在 blender 里调节导出时的倍率：

![](http://i0.hdslb.com/bfs/article/d6e618eace432af0965f5933e92d7bcccaadb872.png@482w_254h_progressive.webp)

调节到动作在 mmd 里适配模型为止，由于 3D 软件之间的坐标轴差异，缩放倍率一般在 10 的指数倍左右浮动（x1，x10，x100，x1000 等），请自行进行测试 & 调节。

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

**第三步：骨骼重映射**

关于 “如何批量重命名” 这一点，每个拆动作的人应该都会有自己最顺手的方法。

至少我不相信有人会闲着没事一个个对着 blender 里的骨骼手动改名。

具体怎么做就不详述了，每个人的习惯都不一样。

自己用的插件是有字典式改名功能的的 “mmd_tools_helper”，相当适合用于不同游戏模型 / 动作的批量骨骼改名：

https://github.com/Hogarth-MMD/mmd_tools_helper

（安装后如果无法在 blender 插件界面显示的话，请确认插件 & blender 版本是否正确）

熟悉一遍 github 上的 tutorial，然后对插件文件夹里的默认字典（bones_dictionary.csv 和 bones_fingers_dictionary.csv）进行修改以适配目标模型的改名。

建议在写字典之前，先对同游戏进行改模以熟悉该游戏各骨骼的对应位置关系，毕竟针对某个游戏写完一次之后，接下来就能一直用下去了。

以下内容为自己使用过程中的范例，仅供参考：

![](http://i0.hdslb.com/bfs/article/3488f3f038a84d7d09337d2b3d41638c5da3e9c0.png@942w_315h_progressive.webp)bones_dictionary.csv 的内容，被修改过以适配马娘模型的骨骼结构

写完字典后，在 blender 里只要点一下即可：  

![](http://i0.hdslb.com/bfs/article/e0bb0c7f391b649850a1cac68f24f348fa653356.png@942w_1389h_progressive.webp)

另外，这个插件很贴心的提供了 “在重命名完后显示骨骼名称” 的功能：  

![](http://i0.hdslb.com/bfs/article/da61149f82c8bd7a1a77bed387d0dba7e22422d3.png@942w_567h_progressive.webp)

确认骨骼改名无误，准备导出。

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

**第四步：导出 vmd 与校正**

和第二步一样，直接左上角导出 vmd 然后塞进 mmd。

如果发现位移不对，就回 blender 修改导出倍率。  

最后，拿去年为了修马娘和草菇动作改的重宝做下测试：

![](http://i0.hdslb.com/bfs/article/15c885a31afe75eefd2740bfe605322ec29ae745.png@942w_569h_progressive.webp)

**“ごちそうさまでした！！！”**

**——by** **爱丽数码****摩耶重炮**

![](http://i0.hdslb.com/bfs/article/card/e87de49c3b1e9895dee9ed739d03e2747ae56ce9.png)

以上。

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

**本期专栏头图：**

【超特急！フルカラー特殊 PP】爱丽数码 &

【すくらんぶる☆ゾーン】摩耶重炮

背景 - 特雷森学园 rip by **@欧阳慕オフィシャル**  

使用素材版权：

ウマ娘プリティーダービー  

Copyright©Cygames

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

本专栏里涉及到的 fbx、bvh，以及导出的 vmd 文件：  

**s/1Gxbvkbzz5ijfrntvMvZw0w** 

提取码：**maya**

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)

**最后**

从改模到提动作，需要的东西到此基本写完了，想做类似尝试的也许能以这几篇专栏作为参考，自己动手，丰衣足食。

不过拜此所赐，去年研究时整了些有意思的活，也认识了不少同好。

还好自己没推什么奇怪的东西，不然重炮就会被拉去跳 OTAHEN 而不是 Orange Sapphire 了。

虽然不知道未来会有什么新的想法，也不知道是否能将其实现。

但是，多做点研究总没错。

**...and in that light, I find deliverance.**
> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv15190494?from=search&spm_id_from=333.337.0.0)

> 作者：[NaCl_OGE咸橘](https://space.bilibili.com/34705293)

 序言如果你想要制作一个 BlenderMMD，那么第一件事肯定就是要把 MMD 模型导入进去了，要导入 MMD 模型，我们需要一个 Blender 插件：mmd-tools。

> **序言**

如果你想要制作一个 BlenderMMD，那么第一件事肯定就是要把 MMD 模型导入进去了，要导入 MMD 模型，我们需要一个 Blender 插件：**mmd-tools**。

**mmd-tools** 是一个用来导入 / 导出 MMD 模型的插件，另外它可以像 MMD 软件一样，导入 MMD 模型的姿势和动作。

要下载 mmd-tools 的话，请在 **https://github.com/absolute-quantum/cats-blender-plugin/releases** 这里下载一个叫做 **cats-blender-plugin** 的插件，这个插件自带 **mmd-tools**，同时可以用来导入 / 导出其他支持的模型，这里不做过多解释。

![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

打开网页之后（**有时候可能会打不开，请尝试刷新或者科学上网**），寻找合适的版本（**比如你的 Blender 是 2.93，那就下载 2.93 的版本，另外 3.00 和 3.01 版本可以使用 2.93 的版本哦**）下载即可，插件的文件格式通常为**.zip** 格式。

下载好插件之后，打开 Blender，打开**偏好设置**，在**插件**选项里点击安装，选中下载好的插件安装即可。

GIF

![](http://i0.hdslb.com/bfs/article/10dfe673cc30e17d8b6995681d63aa9c7e5e4bf2.gif)安装插件![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

安装好插件之后，请在 3D 视图内按 N 键弹出右侧菜单栏，点击 **CATS**。

![](http://i0.hdslb.com/bfs/article/c99017b432b54abb0bc0ea635794a2d4ae39086c.png@482w_830h_progressive.webp)

然后点击 Import Model 右边的三条线按钮，选择 MMD，即可导入 MMD 模型。

![](http://i0.hdslb.com/bfs/article/48a99dc43a0d52e0d31f0b0944cdaa2c80042ecd.png@806w_356h_progressive.webp)

或者，请在右侧菜单栏里点击 **MMD**。

然后点击 Model 下面的 Import，即可导入 MMD 模型。

![](http://i0.hdslb.com/bfs/article/00074b6868a06457fc198db6053e7b0c07b454b2.png@732w_776h_progressive.webp)![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

点击导入的时候，会看到这个界面：

![](http://i0.hdslb.com/bfs/article/532bd0524b7bc5e3e7abb5c733a1d615495673b2.png@663w_848h_progressive.webp)

我们只需要管 Types 和缩放就可以了。

Types 是指模型导入的元素，从左往右依次是网格、骨骼、物理、显示、Morphs（表情）。

我们只需要选择网格、骨骼、Morphs 即可（**如果需要在 Blender 烘焙物理的话，则需要选择物理，后面会讲这个**）

缩放是指模型导入的尺寸，笔者一般使用 **0.2** 倍导入。

![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

导入好模型之后，我们会看到：

![](http://i0.hdslb.com/bfs/article/3e1c154510fd3ac78789f2eda3e7d89712edb9bb.png@942w_927h_progressive.webp)Model by Kanata

首先是模型的本体，这个不需要讲，然后是模型身上一节一节的**锥体**，那个是模型的**骨骼**，最后是模型底下有一个**空轴**，那个是模型的**轴**，是用来绑定模型的骨骼的，可以对模型轴进行移动、缩放等操作。

我们先选择模型的骨骼，把显示方式改成：边界范围。这样有利于处理模型。

![](http://i0.hdslb.com/bfs/article/163d3b6347046a9a2278e56256ab7abf88e0b2df.png@827w_899h_progressive.webp)

这时候模型的骨骼就会变成一个大方形，不会遮挡模型了。

![](http://i0.hdslb.com/bfs/article/4c9f9fd88150d6f78e13ba13d992c85c1ed964d0.png@942w_881h_progressive.webp)

然后我们选择模型，打开右侧菜单栏的 MMD，点击 Convert Materials For Cycles，这会把渲染器变成 Cycles。

![](http://i0.hdslb.com/bfs/article/53da5b58a653a3f6d4e7c7e4914932f805c75831.png@942w_839h_progressive.webp)

然后点击左下角的菜单，勾选图中箭头所指的选项，这会把模型的所有材质转换为原理化 BSDF 节点。如果不想用 Cycles 渲染器就可以换回 Eevee 了。

![](http://i0.hdslb.com/bfs/article/3d9188dd4b65c711e96bfe8fecb2cb60cb963342.png@827w_303h_progressive.webp)

转换好材质之后，点击 Separate By Materials，这会把模型所有的材质分离成单独的模型（不会影响骨骼形变），有利于编辑材质。下面的 Join Meshes 会把模型所有的材质都合并到一块，就像刚导入一样。

![](http://i0.hdslb.com/bfs/article/c602cc312212980114a30548325c603b0b7e95e1.png@662w_950h_progressive.webp)![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

分离好材质之后，就可以对模型进行处理了，

比如：

1.  把三角面转换成四边面（**编辑模式全选模型，按 Alt+J**），清理重叠点（**编辑模式全选模型，按 M，选择按距离**）并对模型曲面细分（**物体模式 ctrl+1/2/3/4，或者直接添加曲面 / 表面细分修改器**）
    
2.  简单的布料解算（操作比较复杂，以后讲）
    
3.  ……
    

![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

终于处理好了模型，现在该让模型动起来了！！！

选择**模型轴**，在右侧菜单栏的 MMD 里，点击 Motion 下面的 Import，导入动作数据。

![](http://i0.hdslb.com/bfs/article/852e4c2ad0e98e42f234812d4f47f76587b6b145.png@656w_963h_progressive.webp)

把缩放改成导入模型时的大小，即可导入动作数据。

![](http://i0.hdslb.com/bfs/article/8e0a2a725cd84301195eed1df22d154bd4989958.png@452w_402h_progressive.webp)

导入好模型之后，点击播放，模型就自己动起来了。

但是！会发现模型没有物理效果，这是因为导入的动作只有身体骨骼的关键帧，没有物理骨骼的关键帧，这种问题有两个解决办法：

*   烘焙 Blender 的物理世界（需要导入模型时选择” **物理** “）
    
*   使用 MMM（**MikuMikuMoving**）烘焙物理骨骼，导出新的动作数据使用
    

第一种方法需要导入模型时选择” 物理 “才可以使用，点击 **Physics** 下面的 **Build**，启用模型的物理碰撞，启用后再播放动画就会发现有物理效果了。

![](http://i0.hdslb.com/bfs/article/78d41a2697f39d3e29ab09eba2114f8000c514f9.png@741w_930h_progressive.webp)

但是，播放起来非常卡顿，这是因为模型的物理是在播放动画时才会运算，我们需要先把物理运算好（烘焙），这样播放就不会卡顿了。

在场景设置里点击刚体世界环境的烘焙，来烘焙模型的物理效果，烘焙好之后保存工程文件就可以保留住这个物理烘焙了。

![](http://i0.hdslb.com/bfs/article/8f03b8f57356609f7ae018da07230e245f94d80e.png@509w_888h_progressive.webp)![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

第二种方法则需要 MMM 来烘焙物理，我们打开 MMM，导入模型之后点击 **Record**，即可烘焙物理骨骼。

![](http://i0.hdslb.com/bfs/article/8269868ae240acd5470b95623e2aa9fb2b049568.png@942w_146h_progressive.webp)

烘焙好之后就可以导出模型数据了，选择所有的骨骼和所有的关键帧，导出动作数据即可。

![](http://i0.hdslb.com/bfs/article/f33846aafd988fadfe3b6f705c7683caf06aab7c.png@792w_1040h_progressive.webp)![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

这两种方法各有各的利弊，请按需求使用。

*   第一种方法比较省事，不需要额外使用软件，但是点击 Build 很容易崩溃，烘焙物理的速度远慢于 MMM，烘焙时比较吃内存和 CPU。
    
*   第二种方法烘焙速度很快，而且 MMM 占用要比 Blender 小得多，但是保存的动作数据体积很大，动辄几十 MB，甚至几百 MB，导入这种动作数据会比较慢，而且占内存。
    

模型的处理已经完成，大家可以先做一个小动画试试看哦！

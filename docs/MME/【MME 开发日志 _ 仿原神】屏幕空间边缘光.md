> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv17709504?from=search&spm_id_from=333.337.0.0)

> 作者：[三金络合物](https://space.bilibili.com/1223127584)

 说明：开发日志仅简单讲解原理，大家想学怎么写 MME 的话可以找点别的教材或者等我哪天一时兴起做个写 MME 的教程（？首先我们看原神游戏内的边缘光效果原神游戏内的边缘光可能这样看不是很清楚，告诉大家一个小技巧在元素视野下，边缘光会变得非常清晰。

说明：开发日志仅简单讲解原理，大家想学怎么写 MME 的话可以找点别的教材或者等我哪天一时兴起做个写 MME 的教程（？

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

首先我们看原神游戏内的边缘光效果

![](http://i0.hdslb.com/bfs/article/19bd99667b8ffe44091321b514601ed25c86544b.png@942w_872h_progressive.webp)原神游戏内的边缘光

可能这样看不是很清楚，告诉大家一个小技巧

在元素视野下，边缘光会变得非常清晰。

![](http://i0.hdslb.com/bfs/article/5183ce0ee67575032db6071fcf541e9ca1db6bf2.png@942w_531h_progressive.webp)特别亮的地方就是了！

是基于屏幕空间的效果，需要 X 轴的视角法线，线性的空间深度还有投影。

- 为什么只需要 X 轴的视角法线？因为游戏内只对 X 方向做了偏移，这里以仿原神为目的。

![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

这里可以发现需要的信息刚好有三个，按理来说需要三张 map，不过节省资源的话可以把这些信息都整合到一张 map 中，分别使用 RGB 三个通道，省很多资源。

![](http://i0.hdslb.com/bfs/article/1ed615d8c05724282b6bc0ddaf9b9570d6585793.png@942w_512h_progressive.webp)三个信息整合在一张 map 中

然后要做偏移，这里说一下游戏里描边大小是不随模型远近变换的，但边缘光始终和模型保持等宽。

![](http://i0.hdslb.com/bfs/article/11e761e94504200018a86e661d153d09d6e63f43.jpg@942w_531h_progressive.webp)近 ![](http://i0.hdslb.com/bfs/article/969d5e988b100ef127c7bfd676a0062a16bca896.png@942w_531h_progressive.webp)远

可以看到边缘光粗细相对模型比例是一致的。

所以在对 map 偏移的时候要考虑到深度，校准深度值让偏移的比例是正确的，按视角法线方向来偏移。

```
coord.x = coord.x + scnmap.r * offsetThr / sqrt(scnmap.g) * (1 + SizeUp * 2.0f) * saturate(1 - SizeDown);
```

offsetThr 是偏移程度，SizeUp&Down 是控制器。

啊还有就是这个要在像素着色器做，我在顶点着色器里尝试是不太支持会报错。。

这串代码中的 scnmap.g 就是深度信息，因为我们之前把深度信息存在 g 通道里了。

scnmap.r 就是视角向量的 X 轴法线信息。

顺便说一下视角向量怎么获得，物体的世界法线和视角空间矩阵相乘就可以，

```
float3 normal = normalize( mul( Normal, (float3x3)WorldViewMatrix ) );
```

深度信息的话就是视角空间里的 w 轴。

然后偏移后的 map 和原来的 map 相减就行。

![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

这里注意一下这个边缘光有个特性是遮挡效果。

![](http://i0.hdslb.com/bfs/article/fa2b7a6c85c0c19fa5e555d1949f3a27571df6f8.png@942w_1148h_progressive.webp)游戏截图

就是视角边缘是正常亮度，但是如果被其他材质部分挡住了就会消失或者变暗。

看到有大佬是按照深度阈值的，但是 MMD 算出来的深度好像不太行。。所以用的剪影算视角边缘，法线算其他被遮挡的边缘。

啊还有视角法线要把 0.5 以下的映射到 0.5-1.0 之间的，方向问题。

```
if (Color.r < 0.5)
{
    // depmap.r = 0.5 - depmap.r;
    Color.r = 1 - Color.r;
}
if (depmap.r < 0.5)
{
    depmap.r = 1 - depmap.r;
    // Color.r =  1.5 - Color.r;
}
```

非常简单的判断映射！

![](http://i0.hdslb.com/bfs/article/3be300bf34f3ca9e00094c82bd7b64ebd64b7201.png@942w_512h_progressive.webp)还没按权重矫正之前

算出来是这样，然后不同通道需要按不同权重加在一起。

顺便说一下眼睛那些地方之类的可以加遮罩。

```
float inten = saturate(Color.r) + Color.g + saturate(Color.b * 1.0);
```

![](http://i0.hdslb.com/bfs/article/659278c74ef99d0522eb18369c60de2e1bc1c2f2.png@942w_512h_progressive.webp)按不同权重加在一起

最后加在按照需要的强度画在画面上就可以！

![](http://i0.hdslb.com/bfs/article/e9d39271af88079d8f5f69489ec0dc8a35e6c0e8.png@942w_512h_progressive.webp)Post 画上去

大概就是这些，之后就是调整颜色，强度，粗细之类的了，写个控制器全搞定！

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

五月份填的坑，是第一次从头写后处理 MME，从 AR 那里偷学来很多东西，收获很多！

有点类似描边的做法了，和传统 NdotV 形式然后取阈值相比的边缘光有好有坏吧。对卡渲硬面材质的效果很好。

兼容 ray 景深的话只需要多加一个附件去掉透明通道就可以放 ray 前面，不过只能加算。

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

相关参考资料：

《Unity URP Shader 与 HLSL 自学笔记六 等宽屏幕空间边缘光》 作者：Cutano

https://zhuanlan.zhihu.com/p/365339160

《屏幕空间等距边缘光》 作者：馬鹿家郎

[https://www.bilibili.com/read/cv11841147](https://www.bilibili.com/read/cv11841147)

MMD 借物：

模型：miHoYo / 观海

MME：Rui_cg / 三金络合物

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

配布暂时放我 MME 测试群里，以后可能会考虑公配。感谢测试群小伙伴帮我测试效果！

班尼冒险团三金分团：641580431

申请要求请看：

https://b23.tv/Y9lhwin

![](http://i0.hdslb.com/bfs/article/28c2242841df6cde785f669764b52e4386b9945e.png@942w_683h_progressive.webp)

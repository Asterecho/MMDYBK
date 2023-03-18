> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv18510252?from=search&spm_id_from=333.337.0.0)

> 哈喽，大家好啊！今天又来补充一下常见的问题很多的小伙伴们在使用 ray 渲染的钻研过程中会经常发现当一个 ray 环境下的材质贴图的 smoothness 过高、泛光过强、或者 emissive 强度过高时就会出现以下......

哈喽，大家好啊！

今天又来补充一下常见的问题

很多的小伙伴们在使用 ray 渲染的钻研过程中会经常发现当一个 ray 环境下的材质贴图的 smoothness 过高、泛光过强、或者 emissive 强度过高时就会出现以下这种情况

**当然，噪点在 3DCG 软件 blender/c4d/toolbag 中出现的频率也是比较常见的，但在 ray 渲染中出现的频率说高也不高**

![](http://i0.hdslb.com/bfs/article/039523302056236513e5fd68f9acf62477e3ff89.jpg@942w_531h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/360bf8230365a7c9d5f272adf80acf90ea712ab8.png@942w_707h_progressive.webp)

或者当我们使用 ray 渲染加载了其他的 MME，尤其是空中漂浮尘埃粒子类的 MME

![](http://i0.hdslb.com/bfs/article/5f9f73b255c94c8fd3eaf3c95eb8a637fea1ece4.png@942w_543h_progressive.webp)

以及泛光过多时，漂浮尘埃就会出现断断续续的噪点

![](http://i0.hdslb.com/bfs/article/405d5f586b4aeaeaa1e004260adbac20b9660890.jpg@942w_393h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/3fa3c24409964eee1869aac9c9ceb7b4051fb788.jpg@942w_393h_progressive.webp)

那我们又该怎么去解决这个问题呢？

**我们打开 ray 渲染文件，打开 ray 渲染里的 shader 文件**

![](http://i0.hdslb.com/bfs/article/cb151d12c9a6819fc4e21a4a7d26f9d7dc91d5e8.png@942w_639h_progressive.webp)

**找到 PostProcessBloom.fxsub 这个配置文件并打开它**

![](http://i0.hdslb.com/bfs/article/937adc58ce82cdfb9e84ccf9a68c758636aee634.png@942w_599h_progressive.webp)

**从配置文件中找到第 7 行的文件代码 static const float2 BloomScale，我们把 512 的强度改成 1024/2048/4072，越高越好！保存后关闭，这样你的 ray 渲染重新打开后就不会出现这样的问题了**

![](http://i0.hdslb.com/bfs/article/c7d7f670364f4f67b62245bb1b5d4d2381efa0e3.png@942w_416h_progressive.webp)

**重新打开 ray 渲染后的出图**

![](http://i0.hdslb.com/bfs/article/3b31f6a2e3bfb6533029823a28d65a7a0aac64d0.png@942w_531h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/c971aea6aa9bc2aa5e2854b891f0108e9b7ce682.png@942w_747h_progressive.webp)

众所周知，在所有的 CG 类型软件里当某项渲染参数或者材质 shader 采样过低时就会出现以下类似问题，ray 渲染会出现这种情况也是比较正常的  

![](http://i0.hdslb.com/bfs/article/8a143580f3d4cb3a0688845be2af0f505c9ed111.jpg@942w_393h_progressive.webp)

当然，如果你对 ray 渲染的 shader 有更多的见解的话也热烈欢迎跟我私聊讨论或者发布到专栏里面大家一起分享，一起进步！

这是交流群：979019435

欢迎加入！
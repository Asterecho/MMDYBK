> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv976510?from=search&spm_id_from=333.337.0.0)

> 这篇专栏是为了解决总会困扰 mmder 的透明通道问题。总会有人问开了全局渲染后，mmd 自带的透明通道消失了怎么办，导致还要后期抠图，有时候还抠不干净。这专栏就是给大家介绍一个 mme，自带能够遮罩住全局渲

这篇专栏是为了解决总会困扰 mmder 的透明通道问题。总会有人问开了全局渲染后，mmd 自带的透明通道消失了怎么办，导致还要后期抠图，有时候还抠不干净。这专栏就是给大家介绍一个 mme，自带能够遮罩住全局渲染的透明通道，操作也很简单，那就是  o_postKeying   ！

由于是作者个人主页配布，比较难搜到，这里就放个作者主页吧

（主页内有其他 o 系渲染，但相对比较普通，感兴趣可以自己试试）

https://okoneya.jp/mmd_files/

用法非常简单，只需要把会使透明通道消失的全局渲染放在 o_postkeying（之后简称 o_p）描绘顺序之上，就能出效果了。

![](http://i0.hdslb.com/bfs/article/506ad5c4f7443f57b8d3db7252160af37d1a337d.png@543w_459h_progressive.webp)把需要变成透明通道的 x 文件放在 o_postkeying 之上

下面给大家演示一下

![](http://i0.hdslb.com/bfs/article/caf9cd16f3963ec16766589cb70a89e1bec00bf6.png@942w_497h_progressive.webp)无全局渲染下的 ![](http://i0.hdslb.com/bfs/article/99a988a9b192f93cd06d66bf712eb24459a5a26f.png@942w_528h_progressive.webp)透明通道

可以看到 bmp 载入软件后是有透明通道的。

那么，载入几个常见的全局渲染和对比图

iklensghost

![](http://i0.hdslb.com/bfs/article/ca5667cde53e90ec6bab9882b925030333983879.png@942w_530h_progressive.webp)只载入 iklensghost 时并无透明通道出现 ![](http://i0.hdslb.com/bfs/article/ae1a35876d114c57e221cbe6ffe44226d2375f53.png@942w_554h_progressive.webp)在打上 o_p 后 ![](http://i0.hdslb.com/bfs/article/bb9a08f7dc257dd5157f611e8574699635c4c398.png@942w_522h_progressive.webp)softlightSB ![](http://i0.hdslb.com/bfs/article/6f876de21ba99a9efcb99aefc222610d1128e932.png@942w_524h_progressive.webp)打上 o_p 后 ![](http://i0.hdslb.com/bfs/article/b35e74920dbc165abb584cef5006f5485dde7b37.png@942w_525h_progressive.webp)滤镜 ![](http://i0.hdslb.com/bfs/article/31386b89aabae9a9f75408b9369bd6cae520c8b1.png@942w_521h_progressive.webp)打上 o_p 后 ![](http://i0.hdslb.com/bfs/article/fd6a2c2d5a426f6af544cb481d84e47fc1130f23.png@942w_501h_progressive.webp)同时来几个全局渲染也毫无问题

可以看出透明通道出现了，切出了模型，并且保留了全局渲染作用在模型上的效果。在场景和模型单独分离后，不容易产生人物和场景出现打光，渲染风格不一致的问题。

o_postkeying 内也自带有把 pmx 变成透明的 fx

![](http://i0.hdslb.com/bfs/article/8348238037638206e02fc643907e8b20965d7f79.png@942w_519h_progressive.webp)添加了自带的 nodraw.fx 后变成透明的床 ![](http://i0.hdslb.com/bfs/article/aecf1a049cb34d0e32fd535f41340878e2189bfd.png@942w_515h_progressive.webp)

nodraw 可以使物体被透过

同样也有可以让 pmx 变成纯白色, 纯黑色不可透过的物体的 fx，这里就不做介绍了，大家可以开脑洞试着玩玩。

![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)

但是，这个 o_postkeying 不能适用于 ray，ik 这种 pbr 渲染，我特意去试了。本身 ray 和 ik 需要用到天空球来渲染的，总不可能把天空球关了吧（

所以这部分是写给主要用 ray 又想抠图的 up 的

但正因为 ray 是基于天空球的渲染，它也只会作用于加载了特殊 fx 的 ray 配套天空球，所以其他普通天空球是不会起作用的（不懂这个原理的请再去复习一下 ray 的基础知识），那可以用'‘大球套小球的方式‘’来实现 ray 的抠图。在真正起作用的 ray 制天空球下面套一个小的纯色天空球，

外部的天空球控制渲染效果，内部的天空球控制可以看见的效果。

（以前都是用单一颜色抠图的，之前受到 富士山君 的提醒觉得三色抠图更干净效果更好就选用了红蓝绿三色抠图）

纯色天空球可以在 b 碗搜到的。实在不行可以 pe 自建一个球体改色然后开启双面描绘，导入后关掉 pssm 阴影就行了

![](http://i0.hdslb.com/bfs/article/fb8c257e25c9464a05d120a5d5b1e4f4f374e151.png@942w_512h_progressive.webp)这是已经做出大概效果的 ray 染 ![](http://i0.hdslb.com/bfs/article/51b3f9c5be9657c310192b721c39ddfae6cd96af.png@942w_528h_progressive.webp)近距离大概细节

看看载入三色纯色天空球之后的样子  

![](http://i0.hdslb.com/bfs/article/ba1cc39d6a2e5178d9ffc1b9b1a9b0018b4d38d1.png@942w_512h_progressive.webp)纯绿色天空球 ![](http://i0.hdslb.com/bfs/article/5419399cf47ce02e434cbbb73b50d72c2d1bd047.png@942w_510h_progressive.webp)纯蓝色天空球 ![](http://i0.hdslb.com/bfs/article/5104442039799528af6e73d1eb1d84030d6d8689.png@942w_507h_progressive.webp)纯红色天空球

对比可以看出来，“小球” 纯色天空球对模型阴影，光照，色调不会有任何影响，可以保证在模型做出效果后照样抠出来。（不过，耀光开太强的话，耀光部分还是有干涉的，有时候还是会被扣掉点的，所以才用三色来保证一下）  

至于为什么选用天空球而不是其他的，因为更容易全方位的抠图，不用为切换视角担心

![](http://i0.hdslb.com/bfs/article/31bf961a67fd1b7b9d0e7ad3149c9737b30f3e3c.jpg@942w_531h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/e56e71fe164ecdac7558448d5bb3b29c337ec3bf.jpg@942w_531h_progressive.webp)

(至于为啥没扣 ik 的，没试过，太难，不会，告辞（x，好吧，其实 ik 新版本根本不被看好了，所以现在根本没用过了，嗯。。。（

以上都是个人经验所谈，如果有更好的方法能指教的话，希望可以在评论区留言。
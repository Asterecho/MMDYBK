> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv6418622?from=search&spm_id_from=333.337.0.0)

> 所谓废物，就是我这种渲染无法入眼，却还要强行逞强的人啊大家好这里是秋岚因为实在是闲的无聊又不想填坑（什么），所以出一篇配方专栏（？？？）混个更（打死你了）。

> 所谓废物，就是我这种渲染无法入眼，却还要强行逞强的人  

啊大家好这里是秋岚因为实在是闲的无聊又不想填坑（什么），所以出一篇配方专栏（？？？）混个更（打死你了）。

这次我们要出的配方是从何而来？

视频

![](http://i0.hdslb.com/bfs/article/card/1-1card200907677_web.png)

来————  

然后大家可以看看封面

![](http://i0.hdslb.com/bfs/article/watermark/38355cc97a1b02254b321a0923e7bf0206cddd9b.png@942w_498h_progressive.webp)其实也算是最终效果图了

然后进入正题

首先是模型和场景的借物

model：PiettraMarinetta/SEGA

stage：万年寝不足 - 別館

然后让我们来看看渲染步骤

首先（咳咳——起个范儿）载入我们的主渲染——ray，带上天空球啊场景啊控制器啊光源啊之类的再调好参数，是这样的：

![](http://i0.hdslb.com/bfs/article/9b8348f6910a45d50a5276c6e750859ac2f3d6ec.png@942w_506h_progressive.webp)我把除了 ray 以外的 mme 都关掉了

让我们来，康—康——参———数——————吧！（什么神经病）

主光源的参数你们看见了，天空球我因为用的是 sky night 所以也没动，那么接下来可以看一下控制器的参数力~

![](http://i0.hdslb.com/bfs/article/558b076013dfc728f0ee864f6a462c98f994b1d9.png@254w_126h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/24e89d019a832c51ea69359df4e5354299821aab.png@263w_135h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/7bd82ad824bdb25e8a42609a69cd96c8347b69f2.png@266w_140h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/93a34fbcf0acabe6ef6adc4d765386c4a76b1e81.png@248w_128h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/ab032d2bb7bd515101da9107d5e3b02e636e5e0c.png@252w_132h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/39bbb52cc70f7dd76ea81d549ee1a06bc6a2f32e.png@258w_128h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/fb8a78c514da8009aabd45dfcf38de41e3248339.png@260w_140h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/e27c139bb4e0e74bbe22f60c766fc014c481d9db.png@254w_138h_progressive.webp)

具体的 RGB 参数根据你自己想要的风格和色调来，毕竟配方只是给个参考

接下来，看一下刚刚的那些 MME 的数值吧

P.S. 其实 FXAA 和 SMAA 用一个就够了带两个是我成习惯了，而且平常我使用 mme 绝大多数只会动它的 si 或者 tr

![](http://i0.hdslb.com/bfs/article/6538d96a420002f2b62a1736b769a4c33fdcc389.png@363w_299h_progressive.webp)そぼろ ![](http://i0.hdslb.com/bfs/article/8e2d564bf4a3b18a7f70096bae4f5704ca5e0125.png@374w_299h_progressive.webp)おたもん ![](http://i0.hdslb.com/bfs/article/9e18a43a9288364ae0ff5f7123e4683947d31798.png@371w_294h_progressive.webp)ハル ![](http://i0.hdslb.com/bfs/article/54c06c8b3e37f36b1147257dacc944daae992e44.png@372w_294h_progressive.webp)データ P ![](http://i0.hdslb.com/bfs/article/5a421dec028039941ef18b18ff8342157d277015.png@374w_302h_progressive.webp)ikeno / 黒 ![](http://i0.hdslb.com/bfs/article/0761bac2845d56b5a2bebb211a35b109d9ec8adf.png@369w_297h_progressive.webp)ikeno / 黒

RAY,FXAA,SMAA,IKBOKEH 都是默认**不要动它们**

然后是 ikbokeh 的控制器

![](http://i0.hdslb.com/bfs/article/eebf3e82cb31bf6b9ce902b0606dab7f1861fdc7.png@248w_144h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/34214b43a3e215cdcd846704cc4ce69809a12490.png@260w_152h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/3fc56c1b8b804da6eaee9ba73ffa1e3611e77738.png@257w_152h_progressive.webp)

差不多就是这样了

每个步骤的效果图我就不一一截图了（好麻烦啊），不过最后成品也就是你看的上面的封面了。  

好，那么就是这样

**我是无量塔秋岚，感谢您阅读这篇专栏。**  

![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)

所以完全不知道下期专栏和视频该出什么......
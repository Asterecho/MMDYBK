> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv1196885?from=search&spm_id_from=333.337.0.0)

> 作者：[-雾雾雾-](https://space.bilibili.com/40758890)

 大家好，我是小雾 (´ ・ω・)ﾉ今天给大家分享个人的 PowerShader 配方第一次写专栏，可能有些地方没说清楚，如果有疑问的话，可以在评论区留言。食用本配方前请注意【这不是教程，不会教你手把手做】【只

大家好，我是小雾 (´ ・ω・)ﾉ  

今天给大家分享个人的 PowerShader 配方

第一次写专栏，可能有些地方没说清楚，如果有疑问的话，可以在评论区留言。

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

食用本配方前请注意↓  

【这不是教程，不会教你手把手做】

【只放出 MME 名称和参数以及作者，请自行搜索下载，婉拒伸手党】

【请不要在评论区问智障问题，比如一些基础操作】

【本配方仅供参考，效果可能不一样】

【请勿转载到 bilibili 以外的网站】

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

先放渲染效果图

![](http://i0.hdslb.com/bfs/article/62fc8afe1d7d974db5951e3038bf905c25a6864d.png@942w_531h_progressive.webp)效果图如上![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

主渲是 **PowerShader v3**

**Shader(ExcellentShadow2 対応版)——Shader_Main.fx**

![](http://i0.hdslb.com/bfs/article/49025db3a19fe664c4f1a5d424a4b3c876b181c3.png@480w_450h_progressive.webp)使用到的 MME ![](http://i0.hdslb.com/bfs/article/16eca59388e080cac07a001a9b0381bf76be741b.png@455w_437h_progressive.webp)使用到的 MME

具体参数  

![](http://i0.hdslb.com/bfs/article/453a5b4b2bc2752670cea7aac82a597e3e427edc.png@296w_230h_progressive.webp)角砂糖 ![](http://i0.hdslb.com/bfs/article/4a9ed135f4b182287fa6eca6524ed03843091271.png@294w_230h_progressive.webp) 注：ikclut_ex_g    OH!YEAH!!!/ikeno ![](http://i0.hdslb.com/bfs/article/c06c21062c37276598b0890e01a6108584ecf6e8.png@291w_233h_progressive.webp)そぼろ ![](http://i0.hdslb.com/bfs/article/d4007f2184a9cfaca078e7adecaced561d98565b.png@290w_245h_progressive.webp)そぼろ ![](http://i0.hdslb.com/bfs/article/bc33488d5758793ff3c7a9b99532e958663d72a0.png@294w_234h_progressive.webp)針金 P ![](http://i0.hdslb.com/bfs/article/183d8b7e74fa74c4873637a80e0b442373aa7a38.png@293w_236h_progressive.webp)ikeno ![](http://i0.hdslb.com/bfs/article/b27f92434dd39cf60f8bdad900c30a928581890f.png@294w_236h_progressive.webp)注：ikclut_ex_g    OH!YEAH!!!/ikeno  
![](http://i0.hdslb.com/bfs/article/12043d6e13ba2d95a44d3a366e6dfe370213f083.png@296w_237h_progressive.webp)注：空中に漂う埃    化身バレッタ ![](http://i0.hdslb.com/bfs/article/63a6737065073c43c5c0aaf0b9f91bb7a933bc35.png@294w_237h_progressive.webp)注：Diffusion7     そぼろ ![](http://i0.hdslb.com/bfs/article/aedadf4b1af848a3207a6796bed5cfc18c640a30.png@291w_233h_progressive.webp)注：ikClut_改变_Wu      G_Wuuuuu/  ikeno ![](http://i0.hdslb.com/bfs/article/9c6e6bd9c1b235f61e1d8171afc961832e630652.png@288w_236h_progressive.webp)注：ikClut_改变_Wu      G_Wuuuuu/ ikeno  
![](http://i0.hdslb.com/bfs/article/e46ea733d8f9004dff45a1afa055f289abee2c68.png@293w_233h_progressive.webp)注: o_RayleighFilter_v0_1    おたもんおたもん ![](http://i0.hdslb.com/bfs/article/e9a6e49793a62dddfb8d4a34206581df6bb89c07.png@291w_233h_progressive.webp)おたもん ![](http://i0.hdslb.com/bfs/article/668817a2247f2b1744cfc37b89c2560d5112d1b2.png@294w_231h_progressive.webp)注：o_SurplusFilter_v0_1    おたもん ![](http://i0.hdslb.com/bfs/article/5f10fbdd31eec7c61f58703b8bcbda63bdd8ab09.png@288w_227h_progressive.webp)注：o_SurplusFilter_v0_1    おたもん ![](http://i0.hdslb.com/bfs/article/6f1b44af8559d06fe17dcbafadef59f8118c3183.png@293w_239h_progressive.webp)注：o_SelfOverlay_v0_6    おたもん ![](http://i0.hdslb.com/bfs/article/9a8dd72f96b379eabb75d3e2abe584116f7ae3ed.png@291w_227h_progressive.webp)注：ikDiffusion   ikeno  
![](http://i0.hdslb.com/bfs/article/ed0adf74a7f65e62e86d1a0f4ee491aeacca68f2.png@294w_231h_progressive.webp)ikeno ![](http://i0.hdslb.com/bfs/article/81a2abb7606572aa2f47471c0ccf274dcdb09b64.png@290w_222h_progressive.webp)ikeno ![](http://i0.hdslb.com/bfs/article/e58b3c0ffabf627424c9aa9ac751ce133009f6f3.png@285w_231h_progressive.webp)注：SelfBlend_v011   データ P ![](http://i0.hdslb.com/bfs/article/55a0becbcef4fb37c521bdda1375692771d0bb30.png@290w_230h_progressive.webp)注：ikclut_ex_g   OH!YEAH!!!/ikeno ![](http://i0.hdslb.com/bfs/article/5285f557e3ded258e7b75faa703b15c85243d829.png@282w_230h_progressive.webp)おたもん ![](http://i0.hdslb.com/bfs/article/fbc6024572288aeb4baa87e0675a897470cba0f9.png@297w_231h_progressive.webp)ikeno  
![](http://i0.hdslb.com/bfs/article/e96a5b035f7e7edae9a9a7c397665d86cab85197.png@291w_236h_progressive.webp)ikeno  
![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

PowerShader v3 的控制器

![](http://i0.hdslb.com/bfs/article/952fb6ba400e7a2d9b387da05e496eb84ada0878.png@402w_227h_progressive.webp)eyes 的第二栏

光源

![](http://i0.hdslb.com/bfs/article/e9af4823a0d1d9ab0e8759618b2b7aef925a1874.png@278w_237h_progressive.webp)调整光源位置调整光源位置![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

附：星尘的头发加上了 Rhinestone（作者：ikeno）

![](http://i0.hdslb.com/bfs/article/5aaa3fd6256472cd24994c48c1d56c9f5d97e476.png@644w_539h_progressive.webp)头发上闪闪的东西    

关于如何添加，请看 **RedialC 太太的教程**[](https://www.bilibili.com/html/help.html#k)

**[https://www.bilibili.com/video/av17522639](https://www.bilibili.com/video/av17522639)**（在 P2）

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

温馨提示：不要将 ikCinemorph 放到最后一位，可能会导致阴影过重

可以适当的调整 MME 顺序，也许会有更好的效果。

以上，完毕。

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

借物表↓

Model : 

建模：石英世界       绑骨 & 物理：大狗       贴图：石英       spa&toon: 石英

Stage : 石英世界 / ゆづき（万年寝不足 - 別館）/ 怪獣対若大将 P

Motion : moka

Camera : 劣质人  

Effect : 角砂糖 / OH!YEAH!!!/ikeno / そぼろ / 針金 P / 化身バレッタ / G_Wuuuuu / おたもん / データ P

Tool：MMEffect——舞力介入 P    MikuMikuDance——樋口优

（赞美借物表里面的太太！！）

**如果借物表有什么地方写错了或者漏了什么。请务必私信我，感谢！！！**

如果有错字的话请当做没看见，谢谢合作！

![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

                   感谢阅读到结尾，希望对大家有帮助！

                                 ｡:.ﾟヽ (｡◕‿◕｡)ﾉﾟ.:｡+ﾟ

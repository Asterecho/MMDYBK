> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv14063485?from=search&spm_id_from=333.337.0.0)

> 作者：[泽风大锅](https://space.bilibili.com/473203655)

 点击进入查看全文 & gt;

[专栏](https://www.bilibili.com/read/home?from=articleDetail) /

【MMD 教程】MMD 从入门到出师系列序言 MMD 超详细干货大教程！（联动持续更新

[

![][img-0]

](https://space.bilibili.com/473203655)

关注

![][img-1]

关注

第七课手把手大总结成品教学 P10 - 00:11

﻿

1. 显示——编辑模式时保持相机和光照

2. 抗锯齿和各项异性过渡关闭

3. 设定分辨率

4. 放入 ray.x 和 ray_controller

5. 放入 skybox

6. 背景——模型绘制顺序，天空盒放最上面，场景放在第二

7.MMEeffect ——main - 场景和人物都加上 main.fx

8.EnvlightMap-sky_with box 添加上相应的 light 后缀文件

9. 人物材质

MateriaMap 人物展开

面、肌肉 - skin-TAD

发 - hair_sss

目 - Materials-Emissive-Fixed Color Blink x1-material_albedo_x1

10. 插件 - AutoLuminous4-AutoLuminous.x

Diffusion7

OpticalFlares（太阳光）- 图层往上移

XDOF（景深）

11. 导出 - MJPEG

本文为我原创本文禁止转载或摘编

[img-0]:https://i2.hdslb.com/bfs/face/9989b176b7ac88457e056cb0a7800ea6bae33c40.jpg@96w_96h_1c_1s.webp

[img-1]:data:image/webp;base64,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

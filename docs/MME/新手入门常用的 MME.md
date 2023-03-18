> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv8885773?from=search&spm_id_from=333.337.0.0)

> 点击进入查看全文 & gt;

新手入门常用 MME

主渲染：ray-mmd-1.5.2 是 MMD 最牛逼的渲染器，也是 教程最多 比较推荐新手系统学习的渲染器

主渲染：PowerShader v3.2 和 Ray 一样是 MMD 主流的主渲染（和 Ray 不能通用），不过不是 Ray 那种物理渲染，PS 比较偏向卡通渲染

主渲染：ExcellentShadow2 算是最简单的一个主渲染了（和 Ray 不能通用），作用是增强阴影效果

辅助渲染：AutoLuminous4 自发光 如果想让某个部件发光需要用这个

辅助渲染：CheapLens 画面四角变暗 适用于酷炫 / 黑暗风格 的 MMD 视频

辅助渲染：Diffusion7 画面柔化 可以使画面更加柔和

辅助渲染：WorkingFloorAL 镜面地板，载入后 si 控制大小，tr 控制反射强度，一般推荐 0.2-0.4 强度

辅助渲染：HgDOF_v005 背景虚化 虚幻背景使人物更加突出（一般更推荐使用 ikBroken）

辅助渲染：HgSAO_v002 增加一种伪环境遮蔽 使人物 / 场景 阴影部分更有层次感

辅助渲染：ikBokeh_v018c 最专业的背景虚化 参数众多 更专业 一般想要背景虚化效果首推这个

辅助渲染：MotionBlur3L_v002 运动模糊 加上这个 人物快速运动时可以有残影 / 模糊的效果

辅助渲染：ikClut_RC 画面色彩纠正 您准备输出 MMD 视频前加上这个 可以纠正您视频中的错误色彩 让您视频更好看

辅助渲染：ikGodray_v002 太阳光丁达尔效应，需要将太阳光高度降低，且场景中存在遮挡体缝隙（例如窗户缝隙）时才能看出明显效果，Ray 自带丁达尔效果，在 Ray 的丁达尔效应不明显时，可以用 ikGodray 来辅助增强

辅助渲染：KiraKira_v2 漂浮粒子 ，有黑白两种颜色，载入 Controller_0 可以控制粒子速度 / 密度。与樱花飘落不能同时使用，有冲突

辅助渲染：Sakura_v2_(Change1.0) 樱花飘落，V2 版本除樱花外还增加了竹叶 / 银杏叶 / 枫叶飘落，载入 Controller_0 可以控制飘落速度 / 方向 / 密度。与漂浮粒子不能同时使用，有冲突

辅助渲染：MS-ScreenTex 仿摄像机拍摄画面，添加后会在 MMD 画面中添加仿摄像机画面，这个一般用的少，但是如果要用，注意附件顺序这个要放末尾，否则可能会被其他 MME 盖掉
> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv18563773?from=search&spm_id_from=333.337.0.0)

> 作者：[简单的の快乐](https://space.bilibili.com/33733417)

 需要用到的软件及插件：（末尾有下载链接 (•̀ω•́)） C4dr20 Maya UE5 MMD_Tool_For_C4D UnrealCameraGenerator_......

![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

需要用到的软件及插件：（末尾有下载链接 (•̀ω•́)✧）  

    C4dr20   

    Maya

    UE5

    MMD_Tool_For_C4D

    UnrealCameraGenerator_v1.0.py

![](http://i0.hdslb.com/bfs/article/card/ae29294258b75971f7a93e27c1a3bc5fc13ccf67.png)![](http://i0.hdslb.com/bfs/article/card/945f5eb0ba4c05caecb19d8907e981e80d41cc7c.png)

这里也有下载链接

![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)

 首先获取一个摄像机数据（模之屋下载的）

![](http://i0.hdslb.com/bfs/article/5bd9232038234df75838563e20fa4c60bc83a42c.png@905w_35h_progressive.webp).vmd 格式文件 ![](http://i0.hdslb.com/bfs/article/83e5e4ec55798f7d166d0b3ad560298369bca83f.png@942w_191h_progressive.webp)使用 mmdtool 导入 c4d 中，mmdtool 安装使用方法可以参考上面链接

导入 C4d 之后会获得两个摄像机数据

![](http://i0.hdslb.com/bfs/article/657caf4390c813b8ca054d28613bb044dfee6c04.png@942w_435h_progressive.webp)摄像机数据

摄像机文件导入 C4d 之后，选中两个文件导出为 fbx，再将 fbx 文件导入到 maya 中

![](http://i0.hdslb.com/bfs/article/a58902ed5988c2c108a676ed74a06842140ca1e1.png@711w_887h_progressive.webp)导出摄像机设置![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)

在 Maya 中导入后获得这两个文件  

![](http://i0.hdslb.com/bfs/article/a7ef53ba98288720022fafc8408df6a91dc2598b.png@942w_494h_progressive.webp)摄像机数据

使用 maya 摄像机导出插件，仅选中 Camera 进行转换

![](http://i0.hdslb.com/bfs/article/2a53373d2d3593f619dc4b959e0644f22d4f13f4.png@942w_650h_progressive.webp)导入插件并运行，插件使用方法也可以看上面链接 ![](http://i0.hdslb.com/bfs/article/ed2336f137f9f49fceefdf3565c4c874ee4280bc.png@537w_69h_progressive.webp)只选中 Camera ![](http://i0.hdslb.com/bfs/article/cf4517e9ffd419013b8b60aa51ae9cbf96cc4e14.png@704w_186h_progressive.webp)运行插件并选中 camera 后点击《《《，再点击 Create

转换后得到：

![](http://i0.hdslb.com/bfs/article/aecbd8bc0c9a98eccd7c711b9f221d5dcce034e4.png@942w_551h_progressive.webp)转换后的 ue 摄像机虽然有动画，但是没有关键帧

需要重新烘焙关键帧

![](http://i0.hdslb.com/bfs/article/da0f192a08fb9a7587e9b0b5bc96708fab02484e.png@942w_1224h_progressive.webp)烘焙

烘焙时根据摄像机动画时间范围进行烘焙，选中三个数据一起烘焙

![](http://i0.hdslb.com/bfs/article/ef44e7eb0b9b6d63e8204d1419203fb642f2c15e.png@455w_86h_progressive.webp) ![](http://i0.hdslb.com/bfs/article/1d7743eb752071423d1b61f97fdb5b2f141da3c9.png@942w_689h_progressive.webp)烘焙 ![](http://i0.hdslb.com/bfs/article/b8c9d7a80d8902308e6c4e1811b1088daa180533.png@942w_476h_progressive.webp)烘培完成

烘培完后运动的路径跟之前的摄像机不一致，直接导入 ue 即可，选中三个文件一起导出，朝上轴设置为 Z 轴

![](http://i0.hdslb.com/bfs/article/08e5be62aba1d9e34469732b4882241ec3cf1c4f.png@599w_1044h_progressive.webp)导出![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

进入 UE5  

![](http://i0.hdslb.com/bfs/article/dfa9cfeabf391929774ac59b79b57e6cc33cbc78.png@464w_926h_progressive.webp)小扳手导入

在 ue5 Sequencer 中点小扳手导入摄像机

![](http://i0.hdslb.com/bfs/article/01003305c0d8fdd111a2f9d24180107a890e8ab7.png@684w_510h_progressive.webp)导入设置

导入后会得到一个 camera 和一个 camera_to_export1 摄像机，camera_to_export1 就是转化后的摄像机，并且拥有完整的帧动画

![](http://i0.hdslb.com/bfs/article/0276bb8f9e5171d7d90876f4334b4dcc3418095c.png@942w_201h_progressive.webp)camera_to_export1

导入后需要将原有聚焦设置的 k 帧删除，手动将聚焦调整到正常数值

![](http://i0.hdslb.com/bfs/article/5f803358ed75dc0b275f8517f82878261db50500.png@942w_84h_progressive.webp)删除两个关键帧 ![](http://i0.hdslb.com/bfs/article/cd1dc2a3ccb5a767bfd3028be10a6c7ab5375ff9.png@740w_248h_progressive.webp)设置聚焦距离

导入完成

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)![](http://i0.hdslb.com/bfs/article/db75225feabec8d8b64ee7d3c7165cd639554cbc.png)![](http://i0.hdslb.com/bfs/article/71bf2cd56882a2e97f8b3477c9256f8b09f361d3.png)

Pmx 模型材质导入过程：模型直接通过 C4d 导入 UE，会有轴向出错的问题  

先看一下轴向：

       使用 mmdtool 将 pmx 格式的文件导入（模之屋下载的模型）。C4d 世界坐标轴为 Y 轴朝上，朝前为 Z-

![](http://i0.hdslb.com/bfs/article/351c766ab7b1400355b5f276a4201e888aa982f3.png@942w_743h_progressive.webp)C4d 轴向

在 ue 中世界坐标 Z 轴朝上，X 轴朝前

![](http://i0.hdslb.com/bfs/article/2b19817efc2dffe288457918129ee1d6f1cb5108.png@942w_587h_progressive.webp)ue 轴向

选中模型导出 fbx

![](http://i0.hdslb.com/bfs/article/a1bc74d24d12efc8009e37db1ffbe26c7d636794.png@711w_887h_progressive.webp)设置 Y 轴朝上匹配 ue 坐标 ![](http://i0.hdslb.com/bfs/article/2ef54dd8a1d93cc64d4ac919886b6c395cb12ecc.png@942w_606h_progressive.webp)如图将 c4d 坐标轴沿 x 轴旋转 - 90 度可得 ue 坐标，只需要将人物网格模型往反方向旋转 90 度即可得到在 ue 中头顶朝向 z 轴，面朝 y 轴的模型

ue 导入

![](http://i0.hdslb.com/bfs/article/a3fade2ffa3e3097f57be4a3fc493c1e11c0fda8.png@624w_1232h_progressive.webp)ue 导入时将 x 轴导入旋转设为 90，其他设置与 max 模型导入时一致 ![](http://i0.hdslb.com/bfs/article/975dd532b3d587b8e0bf27efdb187eb9a6b487c6.png@942w_374h_progressive.webp)导入后网格体状态 ![](http://i0.hdslb.com/bfs/article/16e4b67c5e597dc64888f0b34edee8ae55fd75a1.png@942w_317h_progressive.webp)导入后只有动画序列正常，骨骼模型和物理碰撞不对，将骨骼网格体 x 轴设置为 0 ![](http://i0.hdslb.com/bfs/article/e4ffdf3fcef3656d3fc3e1e040fe801f98189948.png@942w_618h_progressive.webp)将导入设置的 x 轴旋转设为 0，z 轴设为 - 90，点击重新导入 ![](http://i0.hdslb.com/bfs/article/c3703fd26a9995ecb12ee1b8ecbe16e0d1f6526d.png@942w_642h_progressive.webp)设置骨骼网格体后物理碰撞和骨架也会同步 ![](http://i0.hdslb.com/bfs/article/2a354e499b03310639a7204020d9d754d9be1137.png@942w_678h_progressive.webp)完美导入了骨骼动画和面部变形动画

导入完成。  

![](http://i0.hdslb.com/bfs/article/4aa545dccf7de8d4a93c2b2b8e3265ac0a26d216.png)![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)

两个插件的下载链接：  

链接：https://pan.baidu.com/s/12CgM9xv-7o5AstIK_-7TDg 

提取码：ivh3 

-- 来自百度网盘超级会员 V1 的分享

链接：https://pan.baidu.com/s/11DGrvpaw2mvca3ReCArxow 

提取码：dy2g 

-- 来自百度网盘超级会员 V1 的分享

原地址：

github 链接：https://github.com/AiMiDi/C4D_MMD_Tool 作者：艾米蒂 aimidi [https://www.bilibili.com/read/cv11499454?spm_id_from=333.999.0.0](https://www.bilibili.com/read/cv11499454?spm_id_from=333.999.0.0) 出处：bilibilidrive.google.co 防 m/file/d 吞 / 0BwtzZPUbG 补 NPJNVJYYzRKN0ZkRmc / 丁 view  
或 https://pan.baidu.com/s/1RCoiABYHcB_V5CJkqIxU2w  
提取码：kfu1

以上就是 Vmd 文件以及 Pmx 文件导入 ue 中的方法介绍，如果有朋友有更加方便快捷的方法也欢迎在下方留言

![](http://i0.hdslb.com/bfs/article/0117cbba35e51b0bce5f8c2f6a838e8a087e8ee7.png)![](http://i0.hdslb.com/bfs/article/4adb9255ada5b97061e610b682b8636764fe50ed.png)![](http://i0.hdslb.com/bfs/article/02db465212d3c374a43c60fa2625cc1caeaab796.png)

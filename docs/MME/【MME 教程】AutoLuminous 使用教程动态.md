> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/opus/758476299666718823?from=search&spm_id_from=..0.0)

> 红色为文件名

红色为文件名

绿色为操作选项

紫色为软件

Part1：基本参数及基本操作。

1. 载入 AutoLuminous.x。

2. 附件操作：

（1）X 控制光束数量。

（2）Y 控制全局反射强度。

（3）Z 和 Si 控制发光强度。

（4）Ry 控制光束长度。

（5）Rz 控制光闪烁的周期（单位为 s）。

（6）Rx 控制光束倾角。

（7）Tr 控制光的聚集程度。

Part2：强制发光与模型半透明。

1. 强制发光：

MME - 分配特效：AL_EmitterRT- 选择想要发光的部分 - 解除

2. 半透明：

MME - 分配特效：

AL_EmitterRT：选择想变半透明 - 解除。

Main：取消勾选想变半透明的部分。

Part3：选择发光及其他文件用法。

1. 选择发光（e.g：让本身都能发光的两个物体只有其中一个发光）：

MME- 分配特效：AL_EmitterRT- 选择想不发光的部分 - 双击：Options-AL_BlackMask.fxsub（注：有些的模型某些部分有高光贴图，需要用 PMDEditor 手动去除后此文件才有效。如果还是会发光，请载入 Options-LightSampling.x【背景 - 模型描绘顺序：AutoLuminous.x 必须在 LightSampling.x 上面。】）

2.AutoLuminousBasic.x：

发光较柔和，但附件操作中的 XYZ 参数不可以调。

强制发光只能发白光。

3.Options：

（1）AL_BlackMask.fxsub：上面有提到。

（2）AL_Test.x：可以看哪些地方在发光，哪些地方没有发光（有光的颜色）。

（3）ToneCurve.x：让模型变得更偏灰色。

（4）白背景. x& 黑背景. x：载入 AutoLuminous.x 后背景会变为黑色，如果想更改背景为白色请载入白背景. x。

4.Sample：一些发光的特效。

5.MME 发光特效载入后也可以从 AutoLuminous 的附件操作调各种参数。

6.MME 如果不能强制发光（按以上方法），请在 MME- 分配特效：AL_EmitterRT 选择此 MME 载入此 MME 自带的 fx 文件。

7.
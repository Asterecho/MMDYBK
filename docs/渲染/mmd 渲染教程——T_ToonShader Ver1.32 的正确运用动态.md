> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/opus/762011379873873958?from=search&spm_id_from=..0.0)

> 今天也是学习 mmd 的一天~（虽然下午返校...）

今天也是学习 mmd 的一天~（虽然下午返校...）

红色为文件名

蓝色为参数调节

1. 面部平面化（建议）

2. 导入模型并载入 T_ToonShader_S2.fx

3. 展开子项：

（1）面部和身体载入 T_ToonShader_S2_SkinOn.fx，也可以面部单独载入 T_ToonShader_S2_FaceOn.fx（谦亦老师建议前者）

4.MME（建议）：

（1）LightBloom：维持背景为白色，X：4.0。

（2）ExcellentShadow2：适当调节 Rx 参数，阴影会规整一些。

（3）t 渲自带的 Light_null.x：导入后模型会变白。

右下角调节角度的 “XYZ” 上方，英文单词点两下，变成 accessory。

右下角十字 Z 往后拉。

左下角十字 X 侧过来（应该是往左拉吧，自己调一调试试）。

附件操作 -Tr0.6。

5. 色彩修正：主要靠自己，谦亦老师的方法可以借鉴，不建议照搬。

（1）ColorFilterSet_v001-Brightness-ColorFilter_Brightness.x

（2）ColorFilterSet_v001-HSV-ColorFilter_HSV.x

（3）UnsharpMask-sdUnsharpMask.x（锐化，清晰度提升）。

（4）ikcult_ex_bg-forest（滤镜）

注：要有场景建议打关键帧，简单做个 PV 就不用改。
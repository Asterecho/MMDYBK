> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv14760659?from=search&spm_id_from=333.337.0.0)

> 常见的三个分别是 ThreeDPoseTracker、小 K 动捕和 OpenMMD。

常见的三个分别是 ThreeDPoseTracker、小 K 动捕和 OpenMMD。

**先说结论：**

上手难度：ThreeDPoseTracker < 小 K 动捕 < OpenMMD

硬件要求：ThreeDPoseTracker > OpenMMD > 小 K 动捕

更新频率：ThreeDPoseTracker / 小 K 动捕 > OpenMMD

**推荐：ThreeDPoseTracker > 小 K 动捕 > OpenMMD**

**详细比较：**

    ThreeDPoseTracker 的安装最为简单，几乎不需要任何配置，解压即用。使用时只需要选择好视频文件，点几个按钮就可以导出 vmd 动作文件，**操作非常方便**。

    ThreeDPoseTracker 的动作预测效果非常不错，经过 MotionSupporter 处理后只需要稍微修改一下，就可以得到接近真实的效果。

    ThreeDPoseTracker 也是现在市面上为数不多的可以用于直播的免费视频全身动捕软件。具体方法可以自行探索。  

    ThreeDPoseTracker 最大的缺点就是**有一定的硬件要求**，虽然作者说低一点的配置也没问题。但实际用起来就会发现，低于作者推荐配置情况下的延迟是非常大的（ThreeDPoseTracker 的动捕并不是一帧一帧的处理，会根据硬件情况进行跳帧，GTX 950 的跳帧高达 64 帧，也就是说角色两秒才会动一次）。ThreeDPoseTracker 也内置了一个低配置的训练模型，但那个同样几乎没有什么实用性价值。  

    小 K 动捕需要用户将待处理的视频上传到他们的网站上，小 K 的动捕是在线处理的，所以对用户来说，**没有硬件要求**。

    小 K 动捕的效果和 ThreeDPoseTracker 差不了太多。

    小 K 动捕最大的问题就是有 30 秒的时长限制，用起来非常不方便。

    总之对于配置较差的用户来说，小 K 动捕是非常好的选择。另外小 K 动捕和小 K 直播姬是一家的。小 K 直播姬的半身动捕可以说非常优秀，手指的匹配也非常精准。

    OpenMMD 其实只是一个把 OpenPose、3d-pose-baseline-vmd、FCRN-DepthPrediction-vmd、VMD-3d-pose-baseline-multi 整合起来的程序包。虽然最主要的 OpenPose 一直都在更新优化，但是作为中间环节的 3d-pose-baseline-vmd 早就停止了更新。

    使用新版 OpenPose（例如 1.5）导出的 Json 文件，与旧版的 3d-pose-baseline-vmd 不兼容。强行使用也会报 “IndexError: list index out of range” 错误。所以现在能用的只能是基于 OpenPose1.3 的 OpenMMD。

    与 ThreeDPoseTracker 和小 K 相比，OpenMMD 的配置明显要麻烦得多。与此同时，OpenMMD 生成的 VMD 效果与这两款程序相比，同样惨不忍睹。

   **所以对于纯粹的 MMD 小白，如果不想深入学习 OpenPose，只是想做做 MMD，推荐使用 ThreeDPoseTracker，而不是 OpenMMD。**

 [ThreeDPoseTracker 教程](https://www.bilibili.com/video/BV1FP4y1G7zJ)

ThreeDPoseTracker 下载地址：https://qiita.com/yukihiko_a/items/d5c9635e4f1d7f69451f

[小 K 动捕教程](https://www.bilibili.com/video/BV1hE411F7Es)

[更简单的 fbx 转 vmd 方法](https://www.bilibili.com/video/BV1iq4y1X7SP)

[OpenMMD 教程](https://www.bilibili.com/read/cv2835857)

[保姆级的 OpenMMD 教程](https://www.bilibili.com/video/BV1JQ4y127zx)

如有不足之处，欢迎指正。
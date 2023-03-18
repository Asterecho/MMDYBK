> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv164072?from=search&spm_id_from=333.337.0.0)

> 这套系统是给 K2 的，其实但是呢，偶然之间发现改下几个地方就可以给 ray 使用了呢么，对于看不懂英文的，或者懒人来说，这或许就是一个好机会吧！对了，经过测试，至少可以稳定在 ray1.3.1 上面运行，如果有

对了，使用的时候，标题可能是 karl2 配置中，请无视就好了，你就当是 ray 配置中...

@echo off

setlocal ENABLEDELAYEDEXPANSION

:begin

set Rank=0

set n=0

title Karl2 配置中...

echo 请选择配置方式：

echo 1. 选择默认配置   2. 输入配置，系统生成   3. 自定义

set /p c = 请输入数字：

if %c% equ 1 goto default

if %c% equ 2 goto automatic

if %c% equ 3 goto Manual

:default

title 默认配置选择中...

cls

echo 请选择配置：

echo 1. 最低   2. 低    3. 中等     4. 高     5. 最高

set /p c = 请输入数字：

if %c% equ 1 goto minimum

if %c% equ 2 goto low

if %c% equ 3 goto medium

if %c% equ 4 goto high

if %c% equ 5 goto highest

goto default

:automatic

cls

title 自检索配置中...

echo 请输入您的显卡厂商：

echo 1.NVIDIA 2.AMD 3.Inter 4. 其他

set /p c = 请输入数字：

if %c% equ 1 goto NVIDIA

if %c% equ 2 goto AMD

if %c% equ 3 goto redefault

if %c% equ 4 goto redefault

:redefault

cls

echo 很抱歉，该系统还没支持您所选择的显卡系列

echo 您可以选择使用默认配置或者自定义

goto begin

:NVIDIA

cls

echo 您显卡是什么级别的？

echo 1.GTX 2.GT 3.GTS

set /p l = 请输入数字:

if %l% equ 1 set /a Rank=Rank+1

if %l% equ 2 set /a Rank=Rank

if %l% equ 3 set /a Rank=Rank+1

cls

echo 您显卡是什么系列的？

echo 1. 10 系列  2. 9 系列   3. 8 系列    4. 7 系列     5.6 系列

set /p s = 请输入数字:

if %s% equ 1 set /a Rank=Rank+1

if %s% equ 2 set /a Rank=Rank+1

if %s% equ 3 set /a Rank=Rank+1

if %s% equ 4 set /a Rank=Rank

if %s% equ 5 set /a Rank=Rank

cls

echo 您显卡是什么系列等级的？

echo 1. 80(Ti)  2. 70   3. 60    4. 50(Ti)   5. 40   6. 30    7. 20     8. 10

set /p e = 请输入数字:

if %e% equ 1 set /a Rank=Rank+3

if %e% equ 2 set /a Rank=Rank+3

if %e% equ 3 set /a Rank=Rank+2

if %e% equ 4 set /a Rank=Rank+2

if %e% equ 5 set /a Rank=Rank+1

if %e% equ 6 set /a Rank=Rank+1

if %e% equ 7 set /a Rank=Rank+1

if %e% equ 8 set /a Rank=Rank

cls

if %l% equ 1 set l=GTX

if %l% equ 2 set l=GT

if %l% equ 3 set l=GTS

if %s% equ 1 set s=10

if %s% equ 2 set s=9

if %s% equ 3 set s=8

if %s% equ 4 set s=7

if %s% equ 5 set s=6

if %e% equ 1 set e=80(Ti)

if %e% equ 2 set e=70

if %e% equ 3 set e=60

if %e% equ 4 set e=50(Ti)

if %e% equ 5 set e=40

if %e% equ 6 set e=30

if %e% equ 7 set e=20

if %e% equ 8 set e=10

set n=1

echo 您的显卡是 %l%%s%%e% 么？

echo 1. 是的     2. 不是

set /p c = 请输入数字:

if %c% equ 2 goto automatic

if %c% equ 1 goto rank

goto NVIDIA

:AMD

cls

echo 您显卡属于哪个系列？

echo 1.Rx   2.R    3.HD

set /p l = 请输入数字:

if %l% equ 1 (

set /a rank=rank+1 

set l=Rx

goto AMDRx

)

if %l% equ 2 (

set /a rank=rank

set l=R

goto AMDR

)

if %l% equ 3 (

set /a rank=rank

set l=HD

goto AMDHD

)

:AMDRx

cls

echo 请输入您显卡的后缀数字

set /p num = 请输入数字（应在 3 位）:

set /a up=%num%/100

set /a down=%num% %% 100

if %up% equ 4 set /a rank=rank+1

if %up% equ 5 set /a rank=rank+2

if %down% equ 80 set /a rank=rank+2

if %down% equ 70 set /a rank=rank+1

if %down% equ 60 set /a rank=rank+1

cls

echo 您的显卡为 Rx %num% 么？

echo 1. 是  2. 不是

set /p c = 请输入数字:

if %c% equ 1 goto rank

if %c% equ 2 goto AMD

goto AMD

:AMDR

cls

echo 请输入您显卡的后缀数字

set /p num = 请输入数字（中间空格省略）:

set /a up=%num%/1000

set /a down=%num% %% 1000

if %up% equ 9 set /a rank=rank+3

if %up% equ 7 set /a rank=rank+2

if %up% equ 5 set /a rank=rank

if %down% gtr 299 set /a rank=rank+2

if %down% leq 299 set /a rank=rank+1

cls

echo 您的显卡为 R%up% %down% 么？

echo 1. 是  2. 不是

set /p c = 请输入数字:

if %c% equ 1 goto rank

if %c% equ 2 goto AMD

goto AMD

goto rank

:AMDHD

cls

echo 请输入您显卡的后缀数字

set /p num = 请输入数字（应在 4 位）:

set /a up=%num%/1000

set /a down=%num% %% 1000

if %up% equ 7 set /a rank=rank+3

if %up% equ 6 set /a rank=rank+2

if %up% equ 5 set /a rank=rank+1

if %up% equ 4 set /a rank=rank

if %down% gtr 499 set /a rank=rank+2

if %down% leq 499 set /a rank=rank+1

goto rank

:Manual

cls

title 自定义配置中...

echo 主光源是否启用？

choice /C YN /M "确认请按 Y，否请按 N"

if !ERRORLEVEL! equ 2 set MAIN_LIGHT_ENABLE=0

if !ERRORLEVEL! equ 1 set MAIN_LIGHT_ENABLE=1

cls

echo 阴影质量

echo 1. 最低    2. 低     3. 中等     4. 高      5. 最高

choice /C 12345 /M "请选择一位数字（1-5）"

if !ERRORLEVEL! equ 5 set SHADOW_QUALITY=5

if !ERRORLEVEL! equ 4 set SHADOW_QUALITY=4

if !ERRORLEVEL! equ 3 set SHADOW_QUALITY=3

if !ERRORLEVEL! equ 2 set SHADOW_QUALITY=2

if !ERRORLEVEL! equ 1 set SHADOW_QUALITY=1

cls

echo 基于图像照明

echo 1. 激活    2. 激活并且翻转纹理坐标

choice /C 12 /M "请选择一位数字（1-2）"

if !ERRORLEVEL! equ 2 set IBL_QUALITY=2

if !ERRORLEVEL! equ 1 set IBL_QUALITY=1

cls

echo 是否开启雾气

echo 1. 开启    2. 关闭

if !ERRORLEVEL! equ 2 set FOG_ENABLE=2

if !ERRORLEVEL! equ 1 set FOG_ENABLE=1

cls

echo 全屏定向遮闭

echo 1. 关闭   2. 32 采样     3.64 采样     4.128 采样

choice /C 1234 /M "请选择一位数字（1-4）"

if !ERRORLEVEL! equ 4 set SSDO_QUALITY=4

if !ERRORLEVEL! equ 3 set SSDO_QUALITY=3

if !ERRORLEVEL! equ 2 set SSDO_QUALITY=2

if !ERRORLEVEL! equ 1 set SSDO_QUALITY=1

cls

echo 是否启用高级屏幕空间反射？

choice /C YN /M "确认请按 Y，否请按 N"

if !ERRORLEVEL! equ 2 set SSR_QUALITY=0

if !ERRORLEVEL! equ 1 set SSR_QUALITY=1

cls

echo 是否启用屏幕空间次表面散射？

choice /C YN /M "确认请按 Y，否请按 N"

if !ERRORLEVEL! equ 2 set SSSS_QUALITY=0

if !ERRORLEVEL! equ 1 set SSSS_QUALITY=1

set HDR_ENABLE=1

cls

echo 人眼模拟

echo 1. 不启用    2. 12.7%% 中间灰度 100 光敏   3. 18%% 中间灰度 100 光敏

choice /C 123 /M "请选择一位数字（1-3）"

if !ERRORLEVEL! equ 3 set HDR_EYE_ADAPTATION=3

if !ERRORLEVEL! equ 2 set HDR_EYE_ADAPTATION=2

if !ERRORLEVEL! equ 1 set HDR_EYE_ADAPTATION=1

cls

echo 泛光模式

echo 1. 不启用    2. 影响     3. 饱和      4. 高亮曝光      5. 饱和曝光

choice /C 12345 /M "请选择一位数字（1-5）"

if !ERRORLEVEL! equ 5 set HDR_BLOOM_MODE=4

if !ERRORLEVEL! equ 4 set HDR_BLOOM_MODE=3

if !ERRORLEVEL! equ 3 set HDR_BLOOM_MODE=2

if !ERRORLEVEL! equ 2 set HDR_BLOOM_MODE=1

if !ERRORLEVEL! equ 1 set HDR_BLOOM_MODE=0

cls

echo 耀斑模式

echo 1. 不启用    2. 蓝色     3. 橘色    4. 自动

choice /C 1234 /M "请选择一位数字（1-4）"

if !ERRORLEVEL! equ 4 set HDR_FLARE_MODE=3

if !ERRORLEVEL! equ 3 set HDR_FLARE_MODE=2

if !ERRORLEVEL! equ 2 set HDR_FLARE_MODE=1

if !ERRORLEVEL! equ 1 set HDR_FLARE_MODE=0

cls

echo 耀斑星放射模式

echo 1. 不启用    2. 蓝色线式     3. 自动线式    4. 橘色耀斑    5. 自动耀斑

choice /C 12345 /M "请选择一位数字（1-5）"

if !ERRORLEVEL! equ 5 set HDR_STAR_MODE=4

if !ERRORLEVEL! equ 4 set HDR_STAR_MODE=3

if !ERRORLEVEL! equ 3 set HDR_STAR_MODE=2

if !ERRORLEVEL! equ 2 set HDR_STAR_MODE=1

if !ERRORLEVEL! equ 1 set HDR_STAR_MODE=0

cls

echo 色调映射

echo 1. 线性    2. 基于图像照明    3. 哈勃     4. 多亮点    5. 吉米 (2015)    6.ACES-sRGB        

choice /C 123456 /M "请选择一位数字（1-6）"

if !ERRORLEVEL! equ 6 set HDR_TONEMAP_OPERATOR=5

if !ERRORLEVEL! equ 5 set HDR_TONEMAP_OPERATOR=4

if !ERRORLEVEL! equ 4 set HDR_TONEMAP_OPERATOR=3

if !ERRORLEVEL! equ 3 set HDR_TONEMAP_OPERATOR=2

if !ERRORLEVEL! equ 2 set HDR_TONEMAP_OPERATOR=1

if !ERRORLEVEL! equ 1 set HDR_TONEMAP_OPERATOR=0

cls

echo 抗锯齿

echo 1. 不启用   2. 快速近似抗锯齿 (FXAA)  3. 增强型子像素形态学反锯齿 (SMAA)x1 中等      4. 增强型子像素形态学反锯齿 (SMAA)x1 高    5. 增强型子像素形态学反锯齿 (SMAA)x2 中等 6. 增强型子像素形态学反锯齿 (SMAA)x2 最高

choice /C 123456 /M "请选择一位数字（1-6）"

if !ERRORLEVEL! equ 6 set AA_QUALITY=5

if !ERRORLEVEL! equ 5 set AA_QUALITY=4

if !ERRORLEVEL! equ 4 set AA_QUALITY=3

if !ERRORLEVEL! equ 3 set AA_QUALITY=2

if !ERRORLEVEL! equ 2 set AA_QUALITY=1

if !ERRORLEVEL! equ 1 set AA_QUALITY=0

cls

echo 是否开启几何缓冲？

choice /C YN /M "确认请按 Y，否请按 N"

if !ERRORLEVEL! equ 2 set AA_GBUFFER_FILTER_QUALITY=0

if !ERRORLEVEL! equ 1 set AA_GBUFFER_FILTER_QUALITY=1

cls

echo 分散处理

echo 1. 不启用        2. 色移          3. 色差

choice /C 123 /M "请选择一位数字（1-3）"

if !ERRORLEVEL! equ 3 set POST_DISPERSION_MODE=2

if !ERRORLEVEL! equ 2 set POST_DISPERSION_MODE=1

if !ERRORLEVEL! equ 1 set POST_DISPERSION_MODE=0

goto out

:rank

cls

title 系统配置中，请稍后...

if %rank% gtr 5 set rank=5

if %rank% equ 1 goto minimum

if %rank% equ 2 goto low

if %rank% equ 3 goto medium

if %rank% equ 4 goto high

if %rank% equ 5 goto highest

echo 配置完成

pause

goto rank

:minimum

set SHADOW_QUALITY=1

set SSDO_QUALITY=1

set SSR_QUALITY=1

set SSSS_QUALITY=0

set HDR_BLOOM_MODE=0

set AA_QUALITY=1

goto output

:low

set SHADOW_QUALITY=2

set SSDO_QUALITY=2

set SSR_QUALITY=2

set SSSS_QUALITY=1

set HDR_BLOOM_MODE=1

set AA_QUALITY=1

goto output

:medium

set SHADOW_QUALITY=3

set SSDO_QUALITY=4

set SSR_QUALITY=2

set SSSS_QUALITY=1

set HDR_BLOOM_MODE=1

set AA_QUALITY=1

if %rank% equ 5 (if !n! equ 1 set AA_QUALITY=3)

goto output

:high

set SHADOW_QUALITY=4

set SSDO_QUALITY=5

set SSR_QUALITY=3

set SSSS_QUALITY=1

set HDR_BLOOM_MODE=1

set AA_QUALITY=1

if %rank% equ 5 (if !n! equ 1 set AA_QUALITY=4)

goto output

:highest

set SHADOW_QUALITY=5

set SSDO_QUALITY=6

set SSR_QUALITY=3

set SSSS_QUALITY=1

set HDR_BLOOM_MODE=4

set AA_QUALITY=1

if %rank% equ 5 (if !n! equ 1 set AA_QUALITY=5)

:output

set MAIN_LIGHT_ENABLE=1

set IBL_QUALITY=1

set FOG_ENABLE=1

set HDR_ENABLE=1

set HDR_EYE_ADAPTATION=0

set HDR_FLARE_MODE=0

set HDR_STAR_MODE=0

set HDR_TONEMAP_OPERATOR=4

set POST_DISPERSION_MODE=1

set AA_GBUFFER_FILTER_QUALITY=0

goto out

:out

cls

title 输出配置....

echo #define MAIN_LIGHT_ENABLE %MAIN_LIGHT_ENABLE% > ray.conf

echo #define SHADOW_QUALITY %SHADOW_QUALITY% >>ray.conf

echo #define IBL_QUALITY %IBL_QUALITY% >>ray.conf

echo #define FOG_ENABLE %FOG_ENABLE% >>ray.conf

echo #define SSDO_QUALITY %SSDO_QUALITY% >>ray.conf

echo #define SSR_QUALITY %SSR_QUALITY% >>ray.conf

echo #define SSSS_QUALITY %SSSS_QUALITY% >>ray.conf

echo #define HDR_ENABLE %HDR_ENABLE% >>ray.conf

echo #define HDR_EYE_ADAPTATION %HDR_EYE_ADAPTATION% >>ray.conf

echo #define HDR_BLOOM_MODE %HDR_BLOOM_MODE% >>ray.conf

echo #define HDR_FLARE_MODE %HDR_FLARE_MODE% >>ray.conf

echo #define HDR_STAR_MODE %HDR_STAR_MODE% >>ray.conf

echo #define HDR_TONEMAP_OPERATOR %HDR_TONEMAP_OPERATOR% >>ray.conf

echo #define AA_QUALITY %AA_QUALITY% >>ray.conf

echo #define AA_GBUFFER_FILTER_QUALITY %AA_GBUFFER_FILTER_QUALITY% >>ray.conf

echo #define POST_DISPERSION_MODE %POST_DISPERSION_MODE% >>ray.conf

echo 完成.

pause
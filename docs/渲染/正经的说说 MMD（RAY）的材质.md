> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.bilibili.com](https://www.bilibili.com/read/cv90182?from=search&spm_id_from=333.337.0.0)

> 本次对应渲染下载点：https://github.com/ray-cast/ray-mmd 首先我澄清下 不是因为懒得录视频教程我只是希望这样整理下 大家好记忆怎么使用材质贴图就是这样 不准反驳而且 很

#define USE_CUSTOM_MATERIAL 0

#define ALBEDO_MAP_ENABLE 1

#define ALBEDO_MAP_ANIMATION_ENABLE 0

#define ALBEDO_MAP_IN_TEXTURE 1

#define ALBEDO_MAP_IN_SCREEN_MAP 0

#define ALBEDO_MAP_UV_FLIP 0

#define ALBEDO_MAP_UV_REPETITION 0

#define ALBEDO_MAP_APPLY_COLOR 0

#define ALBEDO_MAP_APPLY_DIFFUSE 1

#define ALBEDO_APPLY_MORPH_COLOR 0

#define ALBEDO_MAP_FILE "albedo.png"

const float3 albedo = 1.0;

const float2 albedoMapLoopNum = 1.0;

#define ALPHA_MAP_ENABLE 1

#define ALPHA_MAP_ANIMATION_ENABLE 0

#define ALPHA_MAP_IN_TEXTURE 1

#define ALPHA_MAP_UV_FLIP 0

#define ALPHA_MAP_SWIZZLE 3

#define ALPHA_MAP_FILE "alpha.png"

const float alpha = 1.0;

const float alphaMapLoopNum = 1.0;

#define NORMAL_MAP_ENABLE 0

#define NORMAL_MAP_ANIMATION_ENABLE 0

#define NORMAL_MAP_IN_SPHEREMAP 0

#define NORMAL_MAP_IS_COMPRESSED 0

#define NORMAL_MAP_UV_FLIP 0

#define NORMAL_MAP_UV_REPETITION 0

#define NORMAL_MAP_FILE "normal.png"

const float normalMapScale = 1.0;

const float normalMapLoopNum = 1.0;

#define NORMAL_MAP_SUB_ENABLE 0

#define NORMAL_MAP_SUB_ANIMATION_ENABLE 0

#define NORMAL_MAP_SUB_IN_SPHEREMAP 0

#define NORMAL_MAP_SUB_IS_COMPRESSED 0

#define NORMAL_MAP_SUB_UV_FLIP 0

#define NORMAL_MAP_SUB_UV_REPETITION 0

#define NORMAL_MAP_SUB_FILE "normal.png"

const float normalMapSubScale = 1.0;

const float normalMapSubLoopNum = 1.0;

#define SMOOTHNESS_MAP_ENABLE 0

#define SMOOTHNESS_MAP_ANIMATION_ENABLE 0

#define SMOOTHNESS_MAP_IN_TOONMAP 0

#define SMOOTHNESS_MAP_IS_ROUGHNESS 0

#define SMOOTHNESS_MAP_UV_FLIP 0

#define SMOOTHNESS_MAP_SWIZZLE 0

#define SMOOTHNESS_MAP_APPLY_SCALE 0

#define SMOOTHNESS_MAP_FILE "smoothness.png"

const float smoothness = 0.0;

const float smoothnessMapLoopNum = 1.0;

#define METALNESS_MAP_ENABLE 0

#define METALNESS_MAP_ANIMATION_ENABLE 0

#define METALNESS_MAP_IN_TOONMAP 0

#define METALNESS_MAP_UV_FLIP 0

#define METALNESS_MAP_SWIZZLE 0

#define METALNESS_MAP_APPLY_SCALE 0

#define METALNESS_MAP_FILE "metalness.png"

const float metalness = 0.0;

const float metalnessMapLoopNum = 1.0;

const float metalnessBaseSpecular = 0.04; 

#define MELANIN_MAP_ENABLE 0

#define MELANIN_MAP_IN_TOONMAP 0

#define MELANIN_MAP_UV_FLIP 0

#define MELANIN_MAP_SWIZZLE 0

#define MELANIN_MAP_APPLY_SCALE 0

#define MELANIN_MAP_FILE "melanin.png"

const float melanin = 0.0;

const float melaninMapLoopNum = 1.0;

#define EMISSIVE_ENABLE 0

#define EMISSIVE_USE_ALBEDO 0

#define EMISSIVE_MAP_ENABLE 0

#define EMISSIVE_MAP_ANIMATION_ENABLE 0

#define EMISSIVE_MAP_IN_TEXTURE 0

#define EMISSIVE_MAP_IN_SCREEN_MAP 0

#define EMISSIVE_MAP_UV_FLIP 0

#define EMISSIVE_APPLY_COLOR 0

#define EMISSIVE_APPLY_MORPH_COLOR 0

#define EMISSIVE_APPLY_MORPH_INTENSITY 0

#define EMISSIVE_APPLY_BLINK 0

#define EMISSIVE_MAP_FILE "emissive.png"

const float3 emissive = 1.0;

const float3 emissiveBlink = 1.0;

const float  emissiveIntensity = 1.0;

const float2 emissiveMapLoopNum = 1.0;

#define OCCLUSION_MAP_ENABLE 0

#define OCCLUSION_MAP_IN_TOONMAP 0

#define OCCLUSION_MAP_UV_FLIP 0

#define OCCLUSION_MAP_SWIZZLE 0

#define OCCLUSION_MAP_APPLY_SCALE 0 

#define OCCLUSION_MAP_FILE "occlusion.png"

const float occlusionMapScale = 1.0;

const float occlusionMapLoopNum = 1.0;

#define PARALLAX_MAP_ENABLE 0

#define PARALLAX_MAP_UV_FLIP 0

#define PARALLAX_MAP_SUPPORT_ALPHA 0

#define PARALLAX_MAP_FILE "height.png"

const float parallaxMapScale = 1.0;

const float parallaxMapLoopNum = 1.0;

#define CUSTOM_ENABLE 0

#define CUSTOM_A_MAP_ENABLE 0

#define CUSTOM_A_MAP_IN_TOONMAP 0

#define CUSTOM_A_MAP_UV_FLIP 0

#define CUSTOM_A_MAP_COLOR_FLIP 0

#define CUSTOM_A_MAP_SWIZZLE 0

#define CUSTOM_A_MAP_APPLY_SCALE 0

#define CUSTOM_A_MAP_FILE "custom.png"

const float customA = 0.0;

const float customAMapLoopNum = 1.0;

#define CUSTOM_B_MAP_ENABLE 0

#define CUSTOM_B_MAP_UV_FLIP 0

#define CUSTOM_B_MAP_COLOR_FLIP 0

#define CUSTOM_B_MAP_APPLY_COLOR 0

#define CUSTOM_B_MAP_FILE "custom.png"

const float3 customB = 0.0;

const float2 customBMapLoopNum = 1.0;

这个.......

跳过.....
# Script Blueprint

## Project Overview

- **Project ID**: `2024-05-23_fallen_angel_rebirth_v01`
- **Source Style Pack**: `_stylepacks/seraphic_realism/look.yml` + `_stylepacks/seraphic_realism/lensset.yml` + `_stylepacks/seraphic_realism/safety.yml`
- **Core Prompt Blocks to Embed**: `_core/global_prompt.md` ｜ `_core/scene_block.md` ｜ `_core/audio_pack.md` ｜ `_core/qa_checklist.md`
- **Metadata File (optional)**: _n/a_

## One-Sentence Concept

在潮濕廢墟教堂中，曾墮落的戰士被光之羽翼包覆，從陰冷黑暗中蛻變為守護眾生的天使。

## Act & Beat Outline

### Act I – Setup
- **Beat**: 墮落者獨處於破碎聖壇
- **Visual Intent**: 24mm 緩推建立廢墟教堂結構，暗藍體積光穿過破窗，地面水漬映出殘破身影。
- **Audio Intent**: 低頻氛圍與遠處風聲，加入輕微滴水聲定位空間。

### Act II – Confrontation
- **Beat**: 內心呼喚與光之漩渦
- **Visual Intent**: 35mm 穩定手持追隨角色抬頭，塵埃懸浮，破碎石柱間形成圓環光暈。
- **Audio Intent**: 漸進弦樂墊底，加入反向吸氣特效引導光能聚集。

- **Beat**: 羽翼初生的痛楚
- **Visual Intent**: 35→65mm 拉焦至背部，陰影裂開，羽翼骨架透出藍白能量，背光勾勒輪廓。
- **Audio Intent**: 心跳加速與金屬碎裂聲，弦樂轉為高張力和弦。

### Act III – Resolution
- **Beat**: 光耀蛻變
- **Visual Intent**: 65mm 定格面部特寫，暖金光湧現，身後羽翼展開，整個空間被高對比暖光沖刷。
- **Audio Intent**: 合唱與鐘聲混合，高頻粒子音效形成尾韻。

- **Beat**: 帶光的天使前行
- **Visual Intent**: 無人機式繞拍退後，羽翼掃過水漬留下光軌，陰影被暖光驅散。
- **Audio Intent**: 音樂升華後斷奏，留柔和呼吸與風鈴聲結束。

## Character & Scene Roster

- **主角**：前墮落戰士（性別中性），鎧甲殘破、覆有煤灰與聖徽裂痕。
- **羽翼能量體**：由金色與白色粒子構成的羽翼與光暈。
- **場景**：廢墟教堂（破碎石柱、倒塌木椅、潮濕地面水漬）。
- **道具**：斷裂聖劍、散落羽毛、光之符印漂浮碎片。

## Visual Language & Style Notes

- 採用 `_stylepacks/seraphic_realism/look.yml` 的暗到暖色階切換，凸顯陰冷→溫暖的對比。
- 鏡頭按照 `_stylepacks/seraphic_realism/lensset.yml` 的焦段與運鏡配置，200° 快門保留粒子拖尾。
- 光線從高窗射入形成上冷下暖的分層，蛻變瞬間導入 Amber Volumetric 光暈。
- 細節維持 3A 遊戲 PBR 質感：濕潤石材、金屬刮痕、肌理與反射。

## Camera & Motion Plan

- 開場使用滑軌緩推（dolly slow_push）建立場景縱深。
- 中段手持穩定器 5% 抖動保持臨場感，輔以側向平移展示石柱間光影。
- 蛻變高潮以機械臂／jib 做 120° 繞拍，羽翼展開時加速出光軌。
- 結尾切換無人機式高位退離，展示教堂全貌與光芒蔓延。

## Audio & Voice Strategy

- 音樂：自低頻合成器轉入弦樂與合唱，最後加入鐘聲與風鈴，呼應 `_core/audio_pack.md` 的層次。
- SFX：水滴、石屑滑落、心跳、能量共鳴、羽毛震動。
- VO：無口語對白，以呼吸與嘆息聲帶出內心轉變。

## Pace & Timing Grid

- `00:00–00:03` 開場暗色全景，確立環境與角色孤獨。
- `00:03–00:06` 角色抬頭感受光的召喚，粒子開始旋轉。
- `00:06–00:10` 羽翼破殼、光能湧動，畫面快速切換中景與特寫。
- `00:10–00:15` 完整蛻變與前行，暖光掃過全景收束。

## Safety & Compliance Checklist

- 引用 `_stylepacks/seraphic_realism/safety.yml` 所列規範，避免具體宗教符號與閃光危害。
- 保持天使造型 T 級友善，無血腥與裸露細節。
- 所有臉部特寫需確保模型授權與種子記錄。

## Prompt Mapping Checklist

- [ ] `projects/2024-05-23_fallen_angel_rebirth_v01/prompt.md` header references this script.
- [ ] 嵌入 `_core` 全部指定段落。
- [ ] `_stylepacks/seraphic_realism` look/lens/safety 數據完整複製至 prompt。
- [ ] 場景節奏對應 15 秒節點並標示時間。
- [ ] 版本號保持 `v01` 一致。

## Revision Log

| Version | Date       | Notes |
| ------- | ---------- | ----- |
| v01     | 2024-05-23 | Initial draft for fallen angel rebirth concept. |

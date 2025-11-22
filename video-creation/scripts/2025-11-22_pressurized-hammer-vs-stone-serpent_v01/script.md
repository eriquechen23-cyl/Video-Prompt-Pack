# Script Blueprint — Pressurized Hammer vs Stone Serpent

## Project Overview

- **Project ID**: `2025-11-22_pressurized-hammer-vs-stone-serpent_v01`
- **Source Style Direction**: 2D 日系動漫風，黑＋黃主題色，正午白日環境。
- **Core Prompt Blocks to Embed**: `_core/global_prompt.md` ｜ `_core/scene_block.md` ｜ `_core/audio_pack.md` ｜ `_core/vfx_pack.md` ｜ `_core/qa_checklist.md`
- **Runtime Target**: 15 秒（12 幕 × 1.2s）
- **Deliverable Intent**: 展現「蓄壓重槌師・朝倉蓮」在廢棄神殿與石甲巨蛇對決，以蓄力節奏、黑黃衝擊波與漫畫格收尾的節奏感 BOSS PV。

## One-Sentence Concept

正午岩地的廢棄神殿前，蓄壓重槌師朝倉蓮以穩定步伐與黑黃蓄力紋點亮全身，在毒霧與烈日中用最後一槌漫畫格擊倒覆滿石甲的巨蛇。

## Continuity Layer Snapshot

- Axis & Camera Arc: 蓮固定在畫面右側、巨蛇偏左；鏡頭多站在蓮右後 120° 弧線移動，不跨軸。
- Lens Curve: Act I 24–35mm 建立環境；Act II 35–50mm 節奏中景；Act III 50–75mm 聚焦蓄力與漫畫格，避免 3 秒內跳焦。
- Light Lock: 正午太陽固定右上 45°，硬邊光；漫畫格時允許速度線黑白化，但收回同光位。
- Boss Stage Timeline: Stage 1（0–4s）石甲完整；Stage 2（4–8s）第一槌裂、第二槌大裂紋；Stage 3（8–15s）裂紋發光→擊殺崩碎。
- Ren State Timeline: 蓄壓條 0–4s 微光、4–8s 至 70% 並隨槌消耗、8–12s 滿格閃爍後清零；護膝 6–9s 警示一次、9–15s 收尾餘光。
- Hook Policy: Baseline 保持線性；Hook B 另寫 `hook_cut_prompt` 抽取 Beat 11 漫畫格 0.8s 再倒帶，不與 baseline 混寫。

## Act & Beat Outline

### Act I — 正午對峙（0.0–3.6s）
- **Beat 01｜白日神殿前的巨蛇**：中遠俯視廢棄神殿與盤踞的石甲巨蛇，熱浪扭曲空氣，蛇尾拍地出節奏起點。
- **Beat 02｜朝倉蓮登場**：低角度推近，蓮背對陽光踏下石階，黑黃戰槌扛肩，護膝反光像警示線。
- **Beat 03｜巨蛇先發制人**：蛇頭特寫，毒霧噴出，魚眼拉伸衝擊感，與第三下鼓點對齊。

### Act II — 蓄壓節奏（3.6–8.4s）
- **Beat 04｜穩步蓄壓起步**：側面追蹤蓮向前踏步，黑線浮現暗黃流光，步伐每下對應「ドン」。
- **Beat 05｜蓄壓槽點亮**：仰角特寫，戰槌拉肩，手臂線條被黃光逐格填滿，背景壓暗只剩邊光。
- **Beat 06｜第一組・穩定起槌**：斜 3/4 揮槌砸地，黑黃衝擊波震開巨蛇鱗片，碎石飛散。
- **Beat 07｜第二組・深度壓縮**：近景旋身再砸，護甲裂紋蔓延，兩連擊鼓點強化。

### Act III — 最終組（8.4–15.0s）
- **Beat 08｜舊傷警示**：近景護膝，警示紅黃光一閃，蓮調整站姿。
- **Beat 09｜最終組前的決心**：胸像近景，蓮露出「最後一組」微笑，全身戰紋滿格。
- **Beat 10｜慢動作蓄力・總結重擊起手**：慢動作廣角，巨蛇撲下，蓮旋身跨步，槌軌畫出黑黃光弧。
- **Beat 11｜漫畫格衝擊・擊殺瞬間**：畫面切成粗框漫畫格，槌頭與蛇頭交會，擬聲字「ドゴォン」炸白。
- **Beat 12｜塵埃落定・訓練結束**：拉遠巨蛇倒地，塵埃漂浮，蓮扶槌吐氣，黃光微閃收尾。

## Visual & Audio Anchors
- **Visual**：黑＋黃的戰紋與衝擊波、石甲質感與裂紋、正午刺眼的白金邊光、漫畫格粗線條與速度線。
- **Audio**：4/4 節奏重鼓「ドン」串起步伐與揮槌，毒霧尖嘯、石片崩裂低頻、最終擊的誇張衝擊與短暫耳鳴。


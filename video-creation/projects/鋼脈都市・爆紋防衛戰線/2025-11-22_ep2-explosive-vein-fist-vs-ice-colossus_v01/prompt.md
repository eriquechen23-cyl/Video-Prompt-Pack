
# 鋼脈都市・爆紋防衛戰線｜爆紋鬥拳・鋼川烈 vs 巨人冰石像 PV Prompt（15s｜2D 日系動漫＋漫畫終擊）

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
```
# Global Master Prompt Template

```
Master({時長}s｜{風格}｜{畫幅}｜{fps}｜{質感})
「{時間/地點}；{環境元素1/2/3}；{主體＆動作一句話}。
鏡頭：{滑軌/側向/繞拍/手持≤3%/穩定器}。
表演：{情緒/肢體/視線}。
臉型/髮型：{依上傳五官特徵}。
構圖：{三分線/中央/前中後/留白10–20%}；動態：{風/水/人群/道具}。
寫實細節：{服裝/材質/肌理/光影過門；PBR 粗糙度0.15–0.45/金屬度/法線或置換；微刮痕/汗液/指紋；重力/慣性/布料彈性/流體折射}。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35 空間｜50–75 親密｜100–135 壓縮；
光圈 {T2.0–T2.8/T4–T5.6}；快門角 {180°/144–172°/200–240°}；
對焦 {單點眼/呼吸拉焦/層次前→中→後}。
光影：{側逆/窗光/體積/霓虹混光}；色溫 {日5200–5600K｜黃昏4300–4800K｜夜3000–3800K}；
對比 {柔/高}；眼神光 {保留/可忽略}。
色調/LUT：{自然肌理/膚色優先/陰影微藍・高光暖/去飽和5–10%}。
聲音：環境/腳步/衣料/風/遠人聲（-6 dB 峰值）；音樂 {氛圍/絃樂/Lo-fi/節奏輕推}。
轉場：{直接切/光源匹配/鞭移/遮擋/羽化0.4–0.8s}。
安全：無品牌/無可讀文件/群眾臉不近特寫/連戲與時序一致。
```
```

### Scene Block Template（`_core/scene_block.md`）
```
# Scene Block Template

## Continuity Layer（連貫性強化規則｜撰寫於 Master 前）
- 先在 Master 前建立「Continuity Layer」，明示軸線、主光、鏡頭距離與角色狀態時間線，後續各 Beat 以「延續」語氣引用，避免鏡頭沙拉。
- 軸線鎖定：標註主角/BOSS 左右位置與鏡頭主要站位（例：「蓮右側，蛇左側，鏡頭多在蓮右後 120° 弧線」），禁止跨軸造成左右互換。
- 鏡頭距離曲線：15s 影片每 Act 僅用 1–2 個焦段族群（Act I 24–35mm｜Act II 35–50mm｜Act III 50–75mm）；三秒內避免廣角與長焦來回跳。
- 光源連貫：固定主光方向（例：太陽在右上 45°），保持陰影方向一致；僅在漫畫格或特效片段可暫時風格化，完成後回復原光位。
- 狀態時間線：BOSS 需列出每 4–5 秒的破壞 Stage（完整→裂紋→崩解）並在 Beat 內直接引用 Stage 名稱；主角則以蓄壓/傷勢/裝備亮度等分段標註當前階段（例：「蓄壓 70%、護膝警示一次」）。
- Hook 政策：Baseline Master Prompt 保持線性；如需 Hook 版（先擊殺再倒帶等），請獨立撰寫段落或檔案 `hook_cut_prompt`，不得混寫於 baseline 時間線。
- Beat 撰寫：每 Beat 開頭先重述與上一 Beat 的軸線/光位/距離/Stage 關係，再寫本幕唯一改動重點；仍須完整填 Camera、Lighting、Materials & Physics、Emotion & Performance、Audio & Transition，不得以「同前鏡」代稱。

```
Act {n}（{t0–t1}s）
意圖：{建立/敘事/情感/轉折/收束}
基調：{療癒/悸動/孤獨/決斷/緊張/盼望}
節奏域：{慢入0.8–1.5｜穩定1.5–2.4｜加速2.4–3.0}s
美術要點：{環境/道具/服裝/妝髮}

Beat {k}（{t0–t1}s）
重點：{情節/行為/情緒變化}
Blocking：{入畫/停位/互動/道具接觸}
Camera：
- 運鏡：{滑軌/側移/繞拍/手持≤3%/穩定器}
- 焦段/機位：{24–35/50–75/100–135mm｜眼高/胸高/膝高/俯拍}
- 對焦：{單點/呼吸拉焦/層次拉焦}
- 快門角：{180/144–172/200–240}；拍點：{關鍵動作/視線交換}
光影：{光型/色溫/對比/眼神光}
色調/LUT：{膚色優先/陰影微藍/高光暖/去飽和%}
聲音：旁錄 {環境/衣料/腳步/遠景人聲}；音樂 {BPM×運鏡速度0.8–1.2}
物理/質感：{重力/慣性/碰撞/布料彈性/流體黏度；PBR 粗糙度/金屬度/法線或置換；膚質分層/油光控制；景深/畸變/顆粒顆度}
轉場：{直接切/光源匹配/鞭移/遮擋/羽化} → 下一段

Angle {a}
構圖：{三分線/中央/前中後/留白}
內容：{特寫/中近景/過肩/道具近拍/環境建立/剪影/反射/倒影}
補充：{道具微動/風/水滴/人流/光影過門/粒子}
安全：{去Logo/去可讀字/成年註記}
```
```

### Audio Pack Template（`_core/audio_pack.md`）
```
# Audio Pack 指引

```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
人聲：避免加入一般人聲（對話、歌唱等），僅可使用詠唱或咒語式聲線作為氛圍點綴
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```
```

### Delivery Presets（`_core/delivery_presets.md`）
```
# 交付參數預設

```
畫幅：{16:9｜9:16｜1:1}
解析度：{1920×1080｜1080×1920｜2048×2048}
幀率：{24/30/48/60}（如需輕慢動：拍 48–60，輸出 24）
防抖：{開/關}；運動模糊：開；顆粒：微膠片
色彩：Rec.709（交付版）／LOG（調色版）
聲音：立體聲 48kHz；-14 LUFS（YouTube），-1 dBTP
種子：{固定/隨機（記錄）}；連戲：開；時序一致：開
```
```

### VFX Pack（`_core/vfx_pack.md`）
```
# VFX 通用 Pack

```
引擎：UE5 Niagara｜Unity VFX Graph
Shader：Fresnel 邊緣光｜Depth Fade｜SDF Dissolve｜Flowmap
模擬：Houdini Flipbook（破碎/煙/火/墨）→ Sprite Sheet（8×8/16×16 視素材）
音畫同步：音量/頻段 → 發射率/Bloom 強度（門檻-12 dB；攻擊20–40ms；釋放100–220ms）
手感鉤子：蓄力提示→觸發→回饋（聲/光/震）→冷卻可視化（顏色 or 粒子密度下降）

UE5 實作：Audio Synesthesia 或 Envelope Follower → Niagara User Params
Unity 實作：AudioSource.GetSpectrumData → VFX Graph Exposed Properties
Houdini 實作：RBD/Pyro → GameDev ROP；Alpha 外擴1px 防縫
```
```

## 引用 `_stylepacks` 原文
#### Style: Anime Fantasy Look（`_stylepacks/anime_fantasy/look.yml`）
```
name: Anime Fantasy Look
noise_reduction: clean_edges
saturation: vivid_controlled_skin
line_enhancement: strong_outline
color_palette:
  primaries: [pastel_magenta, teal, warm_gold]
  skin_tone: protected
motion_blur_shutter: 150
notes:
  - 邊緣俐落，維持動畫質感
  - 色彩飽和但控制膚色
  - 建議搭配 24–35mm 誇張空間感
```

#### Style: Sci-Fi Realism（`_stylepacks/sci_fi_realism/look.yml` + audio + vfx）
```
name: Sci-Fi Realism Look
lut: Neutral+BlueShadows
contrast: medium_high
highlight_control: neon_balance
reflection_priority: metal_glass
color_temperature_range: [3600, 4200]
bloom:
  base: 0.2
  peak: 0.6
notes:
  - 允許霓虹混光，保留暗部細節
  - 金屬與玻璃反射優先處理
  - 夜景需維持主體分離
```
```
name: Sci-Fi Realism Audio
bpm: 96
low_freq_pulse:
  range_hz: [40, 80]
  modulation: emission_rate
transient_layer:
  description: 金屬感瞬音對應能量釋放
  gain: -8
drone_bed:
  texture: synth_pad
  width: stereo_wide
mix_guidelines:
  lufs: -14
  true_peak: -1
  sidechain: vfx_trigger
notes:
  - 低頻脈衝驅動能量護盾亮度
  - 觸發瞬間添加 transient 以提升張力
```
```
name: Sci-Fi Realism VFX
niagara_presets:
  - 能量環
  - 粒子回彈
  - SDF 發光邊緣
unity_vfx_graph:
  - EnergyRing.vfx
  - ReboundParticles.vfx
  - SDFGlowEdge.vfx
houdini_flipbooks:
  - electric_arc
  - impact_smoke
bloom_control:
  idle: 0.2
  trigger_peak: 0.6
  cooldown: 0.3
audio_sync:
  low_freq_pulse: drives_emission_rate
  transient_hit: adds_burst
notes:
  - 將 Audio 閾值設在 -12 dB 觸發發射率上升
  - 冷卻階段以粒子密度逐步下降呈現
```

## Input & Project Config（必填欄位檢查）
- project_name：鋼脈都市・爆紋防衛戰線
- series_name/arc：鋼脈都市爆紋篇
- episode_index：2
- slug：explosive-vein-fist-vs-ice-colossus_v01
- target_platform：Short-form vertical video（Reels/TikTok/Shorts）
- duration_sec：15（12 幕 × 1.2s）
- style_primary：Anime Fantasy Look（ON）
- style_secondary：Sci-Fi Realism（Look+Audio+VFX ON）
- worldstate_ref：上一集殘留的高架裂痕與霓虹碎片；本集冰化廣場覆蓋
- goal：系統化「爆紋鬥拳」職業設定，呈現烈對巨人冰石像的終擊

## Technical Specs
- Aspect Ratio：9:16 直式；Resolution：1080×1920；FPS：24；Shutter：180°（漫畫格 200° 增拖影）。
- Lenses：24/35mm（Act I 建立冰封空間）、35/50mm（Act II 近身衝突）、50/75mm（Act III 終擊與漫畫分格）；景深淺至 T2.0–T2.8，漫畫格改平面化低景深感。
- Motion：穩定器滑軌為主，手持抖動 ≤3%；運動模糊開；顆粒微膠片 12% 強度，漫畫格顆粒降至 5%、線稿邊緣強化。
- Color Pipeline：log→filmic LUT→final contrast；陰影冷藍、高光紅橘；保留膚色 55–65 IRE；冰面高光 roll-off 控制防過曝。
- Compression Strategy：冰裂線條與爆紋邊線加強、局部銳化 0.2；體積霧對比提升 5%；漫畫格文字「ドガァァン!!」預留描邊避免壓縮糊掉。

## Brand Layer（系列設定與文案節奏）
- 角色共通：鋼川烈語氣克制、日語短句；口頭禪「拆開才算贏」。
- 色調：黑紅外套＋紅橘爆紋；背景冷藍冰霜，爆破時反射暖橙；字幕若後期添加使用白字 80% 透明。
- 文案語氣：中日雙語節奏，旁白低沈日語，鼓點對齊爆紋節奏。
- 爆紋鬥拳職業設定：手臂紅橘裂紋為可控爆能導管，平時黯紅，蓄壓時 emissive 8–14 nits，爆發時可形成微型衝擊波環（半徑 0.6–1.5m）。

## Negative Instructions
- 禁用真實商標、名人肖像、宗教或政治符號；避免可讀街牌文字。
- 禁止過曝、廉價濾鏡、魚眼畸變、過度晃動；血腥尺度維持 PG-13（碎冰/石可飛散）。
- 不出現無關路人臉部特寫；巨人破碎不露血肉，只呈冰與石。

## Continuity Layer（Act 前置連貫）
- 軸線：巨人冰石像居畫面右，鋼川烈在左側前景；鏡頭多在烈左後 110–140° 弧線，漫畫分格後回到同軸。
- 光位：主光冷月光左上 60°＋冰面反射；爆紋時疊加紅橘側光；漫畫格則以爆光為主光，背景黑白線稿保持高對比。
- 焦段曲線：Act I 用 24–35mm 建立空間；Act II 35–50mm 近身衝突與防禦；Act III 50–75mm 壓縮終擊＋漫畫平面化；三秒內避免焦段跳躍。
- 狀態時間線：
  - BOSS Stage：B0 完整冰甲→B1 膝裂→B2 腿部裂鏈→B3 胸口弱點開→B4 核心過載→B5 崩解漫畫爆。
  - 主角蓄壓：P0 爆紋暗紅→P1 預熱亮點→P2 連打串連→P3 防禦護盾→P4 蓄滿→P5 終擊爆穿。
- Hook 政策：本稿為 baseline 線性，不採倒敘；若需 Hook 版請另建檔。
- Camera Continuity：
  - 主鏡位偏烈左後 120°，高低角依 Act 調整，保持巨人右側方位一致。
  - 景深策略：Act I 前中後層景深分明；Act II 中淺景深鎖定烈與爆點；Act III 子彈時間保留淺景深，漫畫格平面化去景深。
  - 畸變控制：廣角段畸變≤2%，漫畫格使用直線化以配合線稿；鏡頭呼吸控制在 1–2% 範圍。

## Master Prompt（15s｜2D Anime + Sci-Fi Realism｜9:16｜24fps｜冰霜爆燃質感）
- 時間/地點：鋼脈都市邊緣，廢棄冷卻塔包圍的冰鎮廣場，夜間蒸汽與寒霧交織。
- 環境元素：冰封鋼梁、結霜地面、緩慢掉落的冰霜粒子，遠處霓虹反射在冰面上。
- 主體動作：巨人冰石像甦醒、鋼川烈啟動爆紋鬥拳，從膝關節破壞一路打穿胸口核心，最終以漫畫分格爆破收束。
- 物理/光學：重力 9.8 m/s²，碎冰彈道拋物；冰面摩擦係數 0.25，烈滑行留紅光殘跡；冰材粗糙度0.2金屬度0.05折射 1.31；石質粗糙度0.6金屬度0.1；烈皮膚粗糙度0.18、汗膜鏡面0.04、SSS 層 1mm；爆紋 emissive 8–14 nits，衝擊波折射空氣形成熱扭曲；漫畫格背景黑白線稿，深度簡化。
- Camera：滑軌/側向/繞拍，手持≤3%；對焦鎖烈或爆點；快門 180°，漫畫格 200°。
- Lighting：冷藍主光＋冰反射，紅橘爆光作反差；體積霧 0.35；漫畫格保留爆光彩色，背景改黑白線稿。
- Materials/PBR：冰甲粗糙度0.2/金屬度0.05/法線冰裂；石塊粗糙度0.6；鐵質冷卻塔粗糙度0.55金屬度0.7；爆紋 emissive；拳套粗糙度0.25金屬度0.6，指節磨損；地面霜層粗糙度0.35。
- Emotion & Performance：烈沉著、節奏感強；巨人由沉眠到暴走，光脈跳動加速。
- Audio：低頻心跳＋寒風呼嘯；爆擊瞬音帶冰裂高頻；漫畫格爆炸瞬間斷音後留殘響。
- Transition：直接切/光源匹配/鞭移；漫畫格以白光過曝轉入，再合併回全彩。

## Platform Layer
- Hook A（故事向 0–1s）：高空俯瞰冰鎮廣場，巨人甦醒裂紋亮起；字幕「冰封巨人醒了，誰敢先出拳？」。
- Hook B（衝擊向 0–1s）：第一拳膝爆紅橘衝擊環慢動；字幕「一拳=爆破，拆膝開始」。
- First-shot visual hook：霜面廣場＋巨人閃藍脈衝的壓迫遠景。
- Caption 建議：短版「爆紋鬥拳，冰塔拆解術」；長版「鋼川烈在冰封廣場對上巨人冰石像，以爆紋鬥拳節奏把核心打穿」。
- 縮圖：烈拳套紅光對準巨人胸口裂痕，背景冷藍霧，保留 20% 留白。 
- Hashtag：#爆紋鬥拳 #冰石巨人 #AnimeAction #爆破特效 #PV
- CTA：漫畫格爆炸後 0.2s 閃過「下一拳去哪裡？」白字（可後期）。

## Changelog vs Previous Episode
- 承接前一集的城市破壞軸線，轉場到冷卻塔廣場；新增冰封場景與巨人冰石像（全新 BOSS Stage B0–B5）；烈的爆紋從 P0 重新蓄壓。

## Next Episode / Spin-off Ideas
- 主線延伸 1：巨人核心碎片凝成藍白結晶，成為地下幫派爭奪目標。
- 主線延伸 2：烈的爆紋因過載留下冰燃傷痕，需要尋找冷卻手甲。
- 番外：短篇訓練錄，烈在冷卻塔內用微爆紋融冰雕刻。

## Persistent Elements & State Machine Snapshot
- Props：
  - 爆紋拳套（指節磨損、粗糙度0.25、金屬度0.6、內層防震軟墊粗糙度0.65）—狀態 P0–P5 亮度同步爆紋。
  - 冷卻塔鋼梁（粗糙度0.55、金屬度0.7、鏽蝕法線）—本集受爆震局部凹陷；下集需保留變形。
  - 冰霜地面（粗糙度0.2→0.4 隨爆擊提高）—留有烈滑行的紅光烙印；需延續至下一場景。
- UI/字幕：若後期添加字幕，保持白字 80% 透明、無描邊，位置偏下方 10%，與漫畫格不衝突。
- 音樂動機：96 BPM 鼓點對應爆紋節奏，子彈時間段降至 72 BPM 並加強低頻；下集可沿用此節奏動機。
- 狀態機：
  - Stage B0–B5 需在每 Beat 開頭註明當前節點；B5 之後殘骸狀態若進入下一集，須新增 B6「凍結碎片散佈」。
  - 蓄壓 P0–P5 於每個爆點標註能量百分比（本集 P5=100%）；若後續冷卻，新增 P6「冷卻煙霧」。
  - 軸線與光位沿用：巨人右、烈左；主光冷藍左上；若下集轉移場景，需在 Continuity Layer 明記新光源位置。
- 轉場與連戲：漫畫格後回到同軸與光位；碎冰與坑洞需在後續鏡頭保留；紅光烙印不要突然消失。
- 安全限制：保持 PG-13，無血肉、無尖刺穿刺畫面；擬聲字僅「ドガァァン!!」，避免使用現實品牌字型。

## Master → Act / Beat / Angle 分鏡（12 幕 × 1.2s）
Act I（0.0–4.8s）
意圖：建立冰鎮環境與雙方登場｜基調：寒冷壓迫→決斷｜節奏域：慢入1.2→穩定1.6｜美術：冰封鋼梁、淡藍光脈、烈黑紅外套與暗紅爆紋。

Beat 1（0.0–1.2s）｜軸線 B0/P0
- 重點：冰鎮廣場與巨人冰石像全景。
- Blocking：高空俯瞰推進，巨人立於中央，冷卻塔圍繞。
- Camera：24mm 鶴位緩推；穩定器滑軌；對焦層次前→中；快門180°。
- Lighting：冷月光主光 5200K 左上；遠處霓虹反射在冰面；體積霧 0.35。
- Materials & Physics：冰面粗糙度0.2 反射高光；鋼梁粗糙度0.55；冰霜粒子受重力緩落；折射 1.31 造成光斑。
- Emotion & Performance：巨人靜止但壓迫；無人群。
- Audio & Transition：寒風＋遠警報；光源匹配切 Beat2。

Angle：中央構圖，巨人佔中，冷卻塔成圓；前景冰霜粒子微動。

Beat 2（1.2–2.4s）｜軸線延續 B0→B0.5、P0
- 重點：巨人啟動，光脈亮起。
- Blocking：仰角特寫上半身，關節咯吱，眼窩藍白光點亮。
- Camera：30mm 仰拍微手震；對焦巨人眼窩；快門180°。
- Lighting：冰裂處自發藍白光；主光冷藍；副光霓虹反射。
- Materials & Physics：冰甲開裂飛出冰屑（粗糙度0.18）；石質法線粗糙；冰屑彈飛受慣性，撞擊地面碎裂；折射造成光暈。
- Emotion & Performance：巨人甦醒，動作沉重；烈未入鏡。
- Audio & Transition：冰裂高頻＋低頻隆隆；直接切 Beat3。

Angle：三分線上巨人頭部置右上，藍白光脈成節奏線；安全：無文字。

Beat 3（2.4–3.6s）｜軸線延續 B0.5、P0→P1
- 重點：鋼川烈登場，爆紋預熱。
- Blocking：低角度推近烈三分之二身，握拳亮紋。
- Camera：35mm 低角推軌；對焦腳→拳呼吸拉焦；快門180°。
- Lighting：主光冷藍勾邊；拳上爆紋暗紅自發光；冰面反射弱光。
- Materials & Physics：皮膚粗糙度0.18、汗珠折射；爆紋 emissive 8 nits；布料粗糙度0.55、有法線纖維；腳下冰霜裂痕遵循摩擦 0.25。
- Emotion & Performance：烈深吸氣、沉著；目光鎖定巨人膝。
- Audio & Transition：低頻心跳與細小爆火花；鞭移對準膝，切 Beat4。

Angle：烈居左下，巨人腳在右上模糊；前景冰霜裂線；安全：無可讀物。

Beat 4（3.6–4.8s）｜軸線 B0.5→B1、P1→P2
- 重點：第一拳擊中巨人膝關節。
- Blocking：烈貼地滑步繞過落下的掌擊，抬拳擊膝。
- Camera：35mm 側向跟拍後上仰；手持≤3%；對焦衝擊點；快門180°。
- Lighting：爆點紅橘光環瞬亮；主光冷藍保持；碎冰反射微光。
- Materials & Physics：衝擊形成紅橘衝擊環半徑0.9m，冰層內塌後爆開；冰屑彈射拋物線；地面冰霜破裂粗糙度提升到0.4；慣性使烈後滑。
- Emotion & Performance：烈眉緊鎖，拳勢決斷；巨人痛吼。
- Audio & Transition：瞬音帶冰碎聲；光源匹配切 Act II。

Angle：烈在左，拳頭撞上膝裂紋居右；邊緣魚眼式震動。

Act II（4.8–9.6s）
意圖：連打與反擊、防禦｜基調：決斷→緊張｜節奏域：穩定1.5→加速2.4｜美術：紅橘爆紋鏈、冰屑風暴、藍白脈衝。

Beat 5（4.8–6.0s）｜軸線 B1→B2、P2
- 重點：沿裂紋連續爆紋連打往上。
- Blocking：烈繞腿側面高速環繞連打，裂紋向上爬升。
- Camera：40mm 側後環繞 60°；對焦層次拳→裂紋；快門180°。
- Lighting：每拳局部紅橘爆光，藍光從裂縫透出；殘影略微拖尾。
- Materials & Physics：冰層向內塌陷再爆開；連打形成爆紋鏈；碎冰石塊朝一側噴飛；慣性使烈身後殘影；布料張力顯示肌肉拉伸。
- Emotion & Performance：烈節奏感強，「ドドド」連擊；巨人搖晃。
- Audio & Transition：鼓點連打疊加，冰裂聲連鎖；直接切 Beat6。

Angle：烈與巨人腿佔左右對角；背景殘影速度線；安全：無路人。

Beat 6（6.0–7.2s）｜軸線 B2→B2.5、P2
- 重點：巨人踏地反擊冰震波。
- Blocking：巨人抬腳重踏，冰震波擴散，烈被震退。
- Camera：45mm 中遠側視，全身入鏡；穩定器滑軌後退；快門180°。
- Lighting：踏地點藍白光柱；冰震波帶淡藍環光；主光冷藍。
- Materials & Physics：地面高柱冰刺拔起，冰震波沿地面波浪形推動；冰刺粗糙度0.25；烈滑行拖出冰屑軌跡；空氣中冰塵被震散。
- Emotion & Performance：巨人怒吼，烈咬牙穩身形。
- Audio & Transition：低頻衝擊＋碎冰爆破；鞭移至烈防禦姿勢，切 Beat7。

Angle：側視，震波環形成同心圓；烈向左後滑行。

Beat 7（7.2–8.4s）｜軸線 B2.5、P2→P3
- 重點：爆紋護拳抵消冰震波。
- Blocking：烈雙臂交叉胸前，爆紋全亮形成護盾。
- Camera：40mm 正面中近景；輕推；對焦烈；快門180°。
- Lighting：紅橘爆光與藍白震波互咬，形成雙色光暈；體積霧被撕裂。
- Materials & Physics：護拳周圍衝擊造成空氣扭曲；冰塵在波前被撕開；火花殘留跳動；布料震動遵循慣性。
- Emotion & Performance：烈屏息，眼神鎖定巨人；巨人光脈閃爍。
- Audio & Transition：雙色爆轟交疊，瞬間靜音 0.1s；光源匹配切 Beat8。

Angle：正面中央構圖，護拳光環成圓；安全：無文字。

Beat 8（8.4–9.6s）｜軸線 B2.5→B3、P3
- 重點：烈起跳打出胸口裂痕，露出弱點。
- Blocking：從背後跟拍烈踩冰柱跳起，一拳砸胸口。
- Camera：45mm 仰拍跟隨上升；對焦烈拳→裂痕；快門180°。
- Lighting：拳頭紅橘光照亮裂口，內部藍白核心亮起；外圈爆紋包圍。
- Materials & Physics：冰石碎片圓錐形炸開；裂痕邊緣粗糙度升至0.5；能量核心藍白光折射；重力使碎片落下拖尾。
- Emotion & Performance：烈怒吼，巨人胸口震顫；核心像炸彈嗡鳴。
- Audio & Transition：低頻隆隆＋尖銳能量聲；鞭移轉至落地蓄力 Beat9。

Angle：烈背影居下，拳頭與裂痕居中；能量核心特寫閃動。

Act III（9.6–15.0s）
意圖：蓄能、突進、漫畫終擊｜基調：決斷→爆發→收束｜節奏域：穩定1.6→加速2.6｜美術：紅光蓄能、螺旋尾跡、漫畫分格彩色主體＋黑白背景。

Beat 9（9.6–10.8s）｜軸線 B3、P3→P4
- 重點：落地滑行，吸回能量蓄勢。
- Blocking：烈落地向後滑一步，右腳穩住，雙拳收腰蓄力。
- Camera：50mm 斜俯視跟拍；對焦烈；快門180°。
- Lighting：滑行烙出紅光軌跡，周遭冰面反射紅光；主光冷藍。
- Materials & Physics：冰霜被烙出紅橘殘光後吸回拳頭；摩擦火花遵循拋物；布料因慣性抖動；熱浪造成空氣扭曲。
- Emotion & Performance：烈沉氣，呼吸與爆紋同步跳動。
- Audio & Transition：心跳與鼓點同步，紅光吸回時有「ギュウウ」壓縮聲；直接切 Beat10。

Angle：烈居左下，軌跡斜向右上；背景冷霧。

Beat 10（10.8–12.0s）｜軸線 B3→B4、P4
- 重點：爆紋蓄能特寫。
- Blocking：手臂與拳頭近特寫，爆紋一格格點亮。
- Camera：75mm 近景；背景虛化；對焦爆紋；快門180°。
- Lighting：爆紋逐段亮起紅橘，熱浪扭曲；冰屑環繞被光折射。
- Materials & Physics：爆紋 emissive 14 nits；微爆粒子向外飛散；空氣層折射模糊背景；拳套磨損可見法線；碎冰受低壓旋轉。
- Emotion & Performance：烈深呼吸，肌肉繃緊。
- Audio & Transition：低頻隆隆＋心跳；「ギュウウ」壓縮音；速度線 SFX 淡入；子彈時間切 Beat11。

Angle：中央拳頭填滿畫面，背景軌跡虛化；安全：無文字。

Beat 11（12.0–13.2s）｜軸線 B4、P4→P4.5
- 重點：子彈時間突進，螺旋尾跡。
- Blocking：烈爆發衝刺跳拳對準胸口核心，畫面放慢。
- Camera：60mm 側後方跟拍；子彈時間 0.6×；對焦烈；快門180°。
- Lighting：螺旋尾跡紅橘光帶；背景拉伸模糊；核心藍白光閃爍。
- Materials & Physics：螺旋爆紋尾焰像裂紋光帶；空氣受壓形成環形扭曲；冰粒子被尾焰捲起；重力仍作用但慢動顯示。
- Emotion & Performance：烈目光鎖核心，表情決絕；巨人胸口脈衝急促。
- Audio & Transition：音頻下沈、鼓點拉長；速度線音效；在即將命中時切 Beat12 漫畫格。

Angle：烈在左前，巨人胸口居右；速度線兩側拉伸。

Beat 12（13.2–15.0s）｜軸線 B4→B5、P4.5→P5（漫畫分格終擊）
- 重點：漫畫感爆破終擊，彩色主體＋部分黑白。
- Blocking：拳頭命中核心定格 0.1s → 畫面切成 3–4 格漫畫分鏡：中央大格彩色爆心，側格黑白線稿、底格落地收拳。
- Camera：起始 75mm 超近景定格；漫畫格平面化無景深；最後 50mm 慢推回全彩。
- Lighting：中央格紅橘爆光＋藍白核心；側格黑白高對比僅少量藍光；底格烈彩色背光冷藍；爆紋光環逐漸消退。
- Materials & Physics：爆炸向外膨脹鋸齒火花與冰粒子；冰石像從胸口炸開；漫畫格降低顆粒至5%、線稿黑白；恢復全彩時冰碎片落地受重力；拳頭煙霧黏度0.7。
- Emotion & Performance：烈保持出拳姿勢後落地半跪，指節微冒煙；巨人崩解無血肉。
- Audio & Transition：爆鳴「ドガァァン!!」立體字出現；短暫靜音後殘響；0.7s 後格子合併回全彩，留 0.2s 定格烈側臉收尾。

Angle：中央大格彩色爆心，側邊兩格黑白線稿描繪巨人分裂與碎冰雨，底部長條彩色烈背影半跪；安全：無可讀文字除擬聲字。

## Platform Delivery & Render
- Delivery Preset：9:16, 1080×1920, 24fps，運動模糊開，顆粒微膠片，Rec.709；漫畫格降低顆粒；種子固定；連戲開。
- Audio Pack：-14 LUFS，Limiter -1 dBTP；BPM 96 對齊拳擊；Transient 對應爆點；子彈時間段降速保持 tonal balance。
- VFX：使用 UE5 Niagara/Unity VFX Graph，Houdini flipbook 做冰屑與爆雲；音頻驅動 emission 閾值 -12 dB；漫畫格以 shader 平面化線稿。

## Assumptions
1. 巨人冰石像為原創設計，不涉及版權；若需特定 IP 需另行授權。
2. 廣場無路人與車輛，避免額外角色設計；若後續要加觀眾需更新安全範圍。
3. 字樣「ドガァァン!!」為漫畫擬聲字，可自製，不涉及商標；若需多語字幕需另開版本。
4. 霧氣與蒸汽均為可控體積效果，若硬體無法即時渲染，需於合成階段以多層霧片補足並保持光向一致。

## QA Checklist（提交前自評）
- [x] 結構完整：Master + Act/Beat/Angle + timecode + Continuity Layer。
- [x] 敘事一致：BOSS Stage B0→B5、主角蓄壓 P0→P5 依時間推進，軸線與光位在每 Beat 重述。
- [x] 視聽細節：攝影/光影/聲音/轉場皆具體可操作，漫畫格特別標註。
- [x] 風格準確：Anime Fantasy + Sci-Fi Realism + 漫畫終擊無衝突，開關明確。
- [x] 格式精準：段落命名、縮排、技術規格與平台層列出。
- [x] 物理質感到位：每幕寫明重力/慣性、PBR 材質、光學行為、體積霧/折射，漫畫格平面化說明完成。

## AGENT Self-Check
- 結構：含 Master、Act/Beat/Angle、時間碼、Continuity Layer、Platform 層、Changelog、Next Episode、Assumptions。
- Physics & PBR：每 Beat 填入重力/慣性、冰屑彈道、PBR 粗糙度/金屬度、折射、SSS、體積霧、熱扭曲；漫畫格標明顆粒與景深處理。
- Stylepacks 使用：Anime Fantasy Look（ON）、Sci-Fi Realism Look/Audio/VFX（ON）；漫畫終擊為自定風格處理，不與其他 Style 衝突。
- Continuity：軸線巨人右烈左，主光冷藍左上、爆光紅橘；焦段按 Act 分配；BOSS Stage、主角蓄壓按時間推進；漫畫格後回復原光位。
- 不足揭露：未指派配音員；若需品牌露出或字幕需另審；武器與服裝配件若要商品化需後續提供色碼表。

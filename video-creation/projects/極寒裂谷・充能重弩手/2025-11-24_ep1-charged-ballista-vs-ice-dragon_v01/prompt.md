# Project: 極寒裂谷・充能重弩手｜Episode 1 — charged-ballista-vs-ice-dragon_v01
project_name: 極寒裂谷・充能重弩手
series_name: 極寒裂谷・充能重弩手 vs 冰龍
arc: 極寒裂谷決戰
episode_index: 1
slug: charged-ballista-vs-ice-dragon_v01
target_platform: Sora/Deev ingest｜social cut (YouTube Shorts/IG Reels/TikTok)
duration_sec: 15
shots_count: 12
style_primary: Anime Fantasy Look
style_secondary: Light Glyph Anime Look
worldstate_ref: 極寒裂谷長夜、冰龍封存動能的寒霜、朝倉蓮扛充能重弩
goal: 15 秒 2D 日系動漫風＋彩色漫畫感擊殺段落，主角朝倉蓮用充能重弩擊殺冰龍

# _core（全部模板內嵌，含品牌層 Do/Don't）
## Brand Layer
- 角色共通：朝倉蓮（身高 185cm、體重 92kg、肩寬 52cm），傷疤在左眉，口頭禪「就用這一發」。
- 場景色感：冷藍 40%（#6BA9FF）、熾紅 25%（#FF5A2F）、金黃能量 20%（#FFC642）、炙白 15% 作為充能高光。
- 文案語氣：中文敘事＋日文低語＋英文字母只用擬聲（BOOM、CLASH），避免長句字幕。
- Do: 對比度 1.8 gamma curve、HUD 線條不吞線、膚色優先；Don't: 禁用魚眼、禁用過曝 Bloom、禁止未授權 Logo。

## Global Master Prompt Template
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

## Scene Block Template
- Continuity Layer 必須先寫，鎖軸、光源、距離與 Stage。
- 軸線：蓮右側、冰龍左側，鏡頭多在蓮右後 120° 弧線。
- 焦段曲線：Act I 24–35mm；Act II 35–50mm；Act III 50–75mm。
- 主光：右上 45° 冷月光，體積霧 0.35；漫畫格可短暫誇張後回復。
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

## Audio Pack 指引
```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
人聲：避免加入一般人聲（對話、歌唱等），僅可使用詠唱或咒語式聲線作為氛圍點綴
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```

## VFX 通用 Pack
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

## 交付參數預設
```
畫幅：{16:9｜9:16｜1:1}
解析度：{1920×1080｜1080×1920｜2048×2048}
幀率：{24/30/48/60}（如需輕慢動：拍 48–60，輸出 24）
防抖：{開/關}；運動模糊：開；顆粒：微膠片
色彩：Rec.709（交付版）／LOG（調色版）
聲音：立體聲 48kHz；-14 LUFS（YouTube），-1 dBTP
種子：{固定/隨機（記錄）}；連戲：開；時序一致：開
```

## QA Checklist（拍前 30 秒）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 物理寫實：重力/慣性/布料或流體反應與光學行為已寫入 Master 與各 Beat/Angle；PBR 粗糙度/金屬度、膚質分層與高級質感來源（光比/紋理/顆粒）明確。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

# _stylepacks（完整貼上引用並補 Do/Don't）
## Style: Anime Fantasy Look（Default ON）
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
Do:
- 用 strong_outline 確保重弩線條不被霧氣吃掉。
- 用 warm_gold 點亮能量槽，對比霧藍背景。
Don't:
- 不要讓膚色超過 IRE 70。
- 禁用魚眼與過曝 Bloom。

## Style: Light Glyph Anime Look（Default ON）
name: Light Glyph Anime Look
line_enhancement: crisp_vector_edge
noise_reduction: cel_plate_clean
saturation: dual_tone_split
contrast_profile: luminous_soft_mid
color_palette:
  primaries: [fog_blue, slate_gray, midnight_indigo]
  accents: [auric_gold, mint_glow]
  skin_tone: warm_amber
glow_layers:
  base_fill: cool_diffused
  rim_accents: HUD_edge_trace
  spell_core: emissive_gold_script
ui_overlay: parallax_glass_hud
bloom_intensity: 0.32
shadow_treatment: soft_multipass_cel
motion_blur_shutter: 165
texture_pass: layered_papergrain_subtle
notes:
  - 2D 線條需保持乾淨俐落，適度加粗邊緣讓 HUD 光軌不吞線。
  - 城市環境以冷灰與霧藍主調，透過金色與薄荷藍魔法光強化高對比。
  - HUD 與程式碼浮層採半透明玻璃質感，確保角色臉部仍清晰可見。
  - 施法時增加眼睛與衣內銀線的同步脈動光，營造「發光程式」感。
Do:
- 將 rim_accents 用於龍息邊緣，創造 HUD 弧光。
- 嚴守 bloom_intensity 0.32，避免漫畫格被過曝。
Don't:
- 禁止超過 3% 手持晃動。
- 不混用厚重膠片顆粒。

## Style: Chromatic Comic Burst（New｜Default OFF，僅第 9–10 幕）
Applicable for: 彩色漫畫分鏡擊殺瞬間；Do NOT mix with heavy film grain。
Visual traits: 粗黑描線 4px 等效、彩色網點 18–24ppi、速度線佔畫幅 35–50%、背景用 CMYK 分色塊；高對比 +1.6 gamma；保留陰影硬邊。
Audio traits: 擬聲字 SFX 疊加 0.8 秒（ドゴォン!!、クラッシュ!!），限 -8 dB 峰值；瞬時鼓點同步。
Do:
- 使用 CMYK 網點並保留白邊燒蝕轉場。
- 將對比與飽和提升 20%，線條加粗不低於 3px。
Don't:
- 不加入寫實景深；不使用鏡頭眩光；避免動態模糊。

# Technical Specs
- Aspect Ratio: 9:16 直式；Resolution: 1080×1920；FPS: 24 base（原始渲染 48fps → 24fps with 180° shutter）。
- Camera pack: 24mm for Act I 建立空間，35–50mm for Act II 壓迫對決，50–75mm for Act III 親密擊殺；保持畸變校正 <1% 魚眼。
- Shutter: 180° baseline，漫畫格切至 200° 凍結粒子並取消 motion blur；Rolling shutter 模擬關閉。
- DOF: 前中後分層，漫畫格 DOF 關閉；Focus on eyes or arrow tip；bokeh 偏方形粒度 0.2。
- Grain: layered_papergrain_subtle（Stylepack），保留暗部細節；No film damage。
- Color pipeline: log capture → filmic LUT → final contrast（Do: gamma 1.8, lift 0.03, gain 0.95）。
- Physics labeling: gravity 9.8 m/s²；冰塊摩擦係數 0.35；布料阻尼 0.2；龍息粒子密度 0.6 g/m³；熔岩縫隙對流 1.3 m/s。

# Continuity Layer（pre-Master）
- Axis: 蓮在畫面右、冰龍在左，鏡頭保持蓮右後 120° 弧線，不跨軸；漫畫格允許短暫反轉但回到原軸。
- Light: 主光冷月 5200K 從右上 45°；副光熔岩紅從裂縫下方 3200K；漫畫格改用均勻平光再燒蝕回主光。
- Distance curve: Act I 24–30mm wide establishing；Act II 35–45mm mid；Act III 50–70mm close；不得三秒內跳回 wide。
- Boss stage timeline：T0–4s Stage A 完整冰甲；T4–8s Stage B 局部裂紋；T8–12s Stage C 核心曝光；T12–15s Stage D 崩解。
- Hero state timeline：T0–3s 蓄壓 30%；T3–7s 蓄壓 60% 風雪沾衣；T7–9.6s 蓄壓 95% 額頭冒汗；T9.6s 發射冷卻 50℃ 蒸汽。
- Persistent elements：充能重弩（金屬粗糙度 0.35、金屬度 0.8、微刮痕 0.2mm）、冰龍胸口核心（藍白脈動 2Hz）、懸浮戰旗（布料纖維 8k 貼圖）。

# Master Prompt（15s｜Anime Fantasy + Light Glyph Anime｜9:16｜24fps｜PBR 高質感）
- Worldstate snapshot（UTC+8 2025-11-24 夜）：極寒裂谷外、長年極夜、冰龍吐息封存動能，斷橋與碎塔凍停半空，熔岩縫隙紅光閃動；風速 6 m/s，雪花半懸半落。
- Lead: 朝倉蓮，185cm 壯碩，肩扛充能重弩（重量 28kg），能量槽暗紅到炙白漸亮；面容以參考頭像，膚色 55–65 IRE。
- Intent: 15 秒決戰，9–10 幕漫畫分鏡呈現擊殺；其餘為 2D 日系動漫質感，粒子豐富。
- Camera continuity: 遵循 Axis 與 Distance curve；鞭移與遮擋轉場；漫畫格跳切後用燒蝕回復。
- Constraints list: 保持蓮右、龍左；重弩能量槽亮度不可突然下降；冰龍核心在 Stage C 必須外露裂紋；無字幕、無 Logo。
- Execution note: 推薦 camera projection 對固定冰牆；Volume pass 用體積霧 0.35；VFX 煙霧與冰晶用 Houdini flipbook 16×16；Denoise 限制 0.35 strength。
- Physics & PBR: 冰面粗糙度 0.12、IOR 1.31；熔岩縫隙發熱 680℃ 產生熱流畸變；重弩金屬度 0.8 粗糙 0.35；服裝布料粗糙 0.55、法線 4k，衣襬受風延遲 0.2s；龍息冰霜粒徑 0.5–1.2mm。
- Do/Don't引用：Do 使用 gamma 1.8 對比；Don't 使用魚眼與過曝 Bloom；Do 強化暖金能量對比冷藍環境；Don't 使用寫實字幕或 Logo。
- Micro-actions: 每 Beat 加入 <1.2s 細節：腳踏冰裂、能量槽跳動、汗氣蒸發、指節扣扳機的 0.2s 反作用力、箭矢穿刺後 0.3s 擴散。

# Act / Beat / Angle 分鏡（12 幕 × 1.2s）
Act I（0.0–4.8s）｜意圖：建立世界與壓迫｜基調：孤寂→緊張｜節奏域：慢入 1.2s
美術要點：冰封斷橋、懸浮碎塔、熔岩縫隙紅光、戰旗定格；蓮披厚布斗篷（布料粗糙 0.55）。

Beat 1（0.0–1.2s）｜重點：極寒裂谷全景鋪陳
Blocking：俯視掃過裂谷；無角色入畫。
Camera：滑軌俯拍，24mm 眼高；對焦層次前→中→後；快門 180。
光影：冷月 5200K 主光，熔岩 3200K 反光；對比柔中高；眼神光無需。
色調/LUT：陰影微藍，高光暖 8%。
聲音：風聲低鳴 -12 dB，遠處龍吼 -15 dB；音樂氛圍 pad 70 BPM。
物理/質感：雪花粒徑 0.4mm 悬停；冰面粗糙 0.12；重力 9.8 m/s² 但龍息區域有局部懸停。
轉場：直接切 → Beat2。
Angle A1
構圖：三分線＋前中後層次，留白 15%。
內容：斷裂石橋、半空懸浮碎石與戰旗、靜止雪花。
補充：體積霧 0.35，遠方雲層旋轉 0.2 rad/s。
安全：無可讀字。

Beat 2（1.2–2.4s）｜重點：冰龍登場壓迫
Blocking：冰龍自裂谷爬起，翅膀抖落冰晶。
Camera：仰角穩定器 28mm 胸高；對焦單點龍瞳；快門 180。
光影：主光冷月側逆，龍鱗 Fresnel 反射；對比高。
色調/LUT：膚色優先、藍白主調。
聲音：冰晶掉落叮噹 -10 dB；龍吼近距離 -6 dB；音樂弦樂升級至 80 BPM。
物理/質感：龍鱗金屬度 0.25 粗糙 0.3；冰晶質感 IOR1.31；翅膀甩動帶風 8 m/s。
轉場：鞭移跟到蓮出場。
Angle A2
構圖：中央壓迫，龍瞳特寫佔 1/3 畫幅。
內容：龍瞳倒映渺小人影，冰紋發光 2Hz。
補充：冰晶飛向鏡頭帶景深；粒子受風偏移 12°。
安全：無 Logo。

Beat 3（2.4–3.6s）｜重點：主角蓮入場，重弩充能
Blocking：側移跟拍蓮步伐，能量槽跳動。
Camera：側向滑軌 24mm 腰高；層次拉焦腳→弩→臉；快門 180。
光影：主光仍右上，紅光從裂縫反射到弩身。
色調/LUT：陰影微藍，高光暖 10%。
聲音：腳步鈍響 -8 dB；能量槽啵啵脈動；音樂節奏 84 BPM。
物理/質感：冰面摩擦 0.35，鞋底金屬釘抓地；能量槽發熱 120℃ 微蒸汽。
轉場：遮擋切到就位。
Angle A3
構圖：前中後，重弩佔前景 40%，蓮半身中景。
內容：弩臂發光紋路像流動電流，蓮肩肌肉線條透衣。
補充：電流亮度從 20%→60%（0.8s）；布料風偏 6°。
安全：無字幕。

Beat 4（3.6–4.8s）｜重點：就位與預備射擊
Blocking：半蹲冰柱後，插入能量箭頭，扣扳機預備。
Camera：35mm 膝高；對焦箭矢→指節；快門 180。
光影：體積霧穿過冰柱，局部高光 5200K；對比中高。
色調/LUT：膚色優先，去飽和 5%。
聲音：金屬摩擦、箭矢插入「卡嗒」-6 dB；音樂停拍 0.2s。
物理/質感：箭矢金屬度 0.75 粗糙 0.28；指節白化，手套皮革粗糙 0.5；冰柱折射變形 3%。
轉場：光源匹配 → Act II。
Angle A4
構圖：過肩特寫，留白 10%。
內容：扳機與指節特寫，能量紋路亮起。
補充：蒸汽 0.1s 噴出，箭矢紋路由暗紅→金黃。
安全：無文字。

Act II（4.8–9.6s）｜意圖：攻防與蓄壓｜基調：決斷｜節奏域：穩定 1.2s
美術要點：冰牆、龍息、能量槽逼近飽和。

Beat 5（4.8–6.0s）｜重點：第一次試射破冰甲（仍 Stage A→B）
Blocking：主觀準星對翅膀，射擊後冰甲裂。
Camera：主觀 35mm 眼高；對焦箭矢尾；快門 180。
光影：龍息光散射；冰甲高光硬邊；對比高。
色調/LUT：冷藍主，箭尾暖金。
聲音：發射「シュン」-5 dB；爆裂「パキン」-6 dB；龍吼 -8 dB。
物理/質感：箭矢速度 120 m/s，撞擊造成冰碎粒徑 2–5mm；反作用力肩膀後坐 5°。
轉場：直接切。
Angle A5
構圖：中央準星，翅膀關節在黃金分割。
內容：箭矢拖光尾穿過風雪；冰甲碎片向外飛。
補充：粒子阻尼 0.1，帶 motion blur 180°。
安全：去 Logo。

Beat 6（6.0–7.2s）｜重點：冰龍反擊龍息
Blocking：冰龍吸氣→吐息，前景冰柱凍成牆；蓮翻身躲後。
Camera：側拉 40mm 腰高；呼吸拉焦龍胸→冰牆→蓮背；快門 172。
光影：龍息體積光藍白，冰牆高反射；熔岩紅補對比。
色調/LUT：陰影藍 10%，高光冷白；膚色保護。
聲音：龍息轟鳴 -4 dB；冰凍聲 -7 dB；衣料摩擦。
物理/質感：龍息粒子密度 0.6 g/m³，溫度 -40℃；冰牆形成 0.4s，表面粗糙 0.18；蓮翻身慣性滑 0.3m。
轉場：遮擋切。
Angle A6
構圖：前景冰牆覆滿畫面 60%，蓮剪影在右；龍息從左掃。
內容：冰牆霜花瞬間擴散；蓮背部蒸汽。
補充：裂痕沿法線 0.2mm 位移；衣襬延遲 0.2s 才貼回。
安全：無文字。

Beat 7（7.2–8.4s）｜重點：充能極限（Stage B→C）
Blocking：半跪固定重弩，能量槽亮至炙白，汗蒸。
Camera：45mm 膝高；對焦能量槽→蓮臉；快門 180。
光影：主光側逆，能量槽自發光 4000K；對比高。
色調/LUT：暖金對冷藍，去飽和 5%。
聲音：充能嗡鳴升到 -5 dB；蓮日文低語「ここで終わらせる」。
物理/質感：弩前端插入裂縫摩擦係數 0.4；能量槽震動 3mm 幅；汗液蒸發成白霧 0.2s。
轉場：鞭移→主觀瞄準。
Angle A7
構圖：側面中近景，重弩佔 50%，蓮臉佔 30%。
內容：能量槽從金黃→炙白，弩身抖動；蓮咬牙。
補充：熱扭曲 1.5%；額頭汗被蒸汽帶走形成薄霧。
安全：無字幕。

Beat 8（8.4–9.6s）｜重點：瞄準核心，子彈時間前奏（Stage C）
Blocking：主觀瞄準龍胸核心，扣扳機前慢動。
Camera：主觀 45mm；對焦核心；快門 200（減少模糊）。
光影：環境音壓低，聚焦於核心藍白脈動；能量槽光線形成引導線。
色調/LUT：冷暖對比明顯，去飽和 8%。
聲音：背景降至 -15 dB，心跳 + 充能聲；扳機預壓「キュッ」-10 dB。
物理/質感：時間拉長 0.5x；指節拉緊，扳機阻尼 1.2N；冰霜在槍口結晶 0.1mm。
轉場：硬切到漫畫格（Style Chromatic Comic Burst）。
Angle A8
構圖：準星中央核心，周邊模糊；留白 12%。
內容：核心發光裂紋，準星 HUD 線條顯示。
補充：粒子靜止感，只有能量線流動；重弩震動細微。
安全：無文字。

Act III（9.6–15.0s）｜意圖：擊殺與收束｜基調：決斷→安靜｜節奏域：加速後緩落
美術要點：漫畫分鏡爆炸，再回 2D 動畫，冰晶落雪。

Beat 9（9.6–10.8s）｜重點：漫畫格命中瞬間（擊殺①，Stage C→D）
Blocking：箭矢極速刺入龍核心，速度線＋擬聲。
Camera：漫畫格平行視角；無 DOF；無 motion blur；對焦箭尖。
光影：平光高對比，CMYK 網點；主光均勻。
色調/LUT：飽和 +20%，對比 +20%。
聲音：擬聲「ドゴォン!!」-8 dB 疊音；鼓點同步。
物理/質感：箭矢穿刺深度 0.6m；裂紋以 400 m/s 擴散；冰晶破碎 1–3mm 粒徑。
轉場：漫畫格持續。
Angle A9（Style: Chromatic Comic Burst）
構圖：主格箭矢刺入核心佔 70%，小格瞳孔特寫 2 格。
內容：粗黑線條＋彩色網點；速度線覆蓋背景；擬聲字浮於爆點。
補充：小格顯示瞳孔收縮、胸口冰紋龜裂；無景深。
安全：無品牌。

Beat 10（10.8–12.0s）｜重點：漫畫格崩解爆散（擊殺②）
Blocking：冰龍沿裂縫崩解，冰晶炸裂，主角剪影背對。
Camera：多格分鏡，主格 60%、兩小格 20% + 20%；無 DOF；快門 200。
光影：平光 + 燒蝕邊框；高對比。
色調/LUT：飽和 +20%，對比 +20%。
聲音：擬聲「クラッシュ!!」「パリンッ!!」-8 dB；衝擊波低頻 -6 dB。
物理/質感：冰晶爆散初速 90 m/s 後受風阻減速；衝擊波推動斗篷 0.5m；漫畫邊框燒蝕 0.3s。
轉場：邊框燒蝕淡出 → 回 2D 動畫。
Angle A10（Style: Chromatic Comic Burst → fade）
構圖：主角剪影背對爆炸；邊框逐漸融化。
內容：裂縫光芒吞噬龍身；文字 SFX 漂浮。
補充：邊框由白轉透明；最後 0.3s 融化回動畫。
安全：無文字。

Beat 11（12.0–13.2s）｜重點：餘波落雪（回 2D 動畫）
Blocking：冰晶碎片緩落，蓮站立，重弩冒白煙。
Camera：50mm 胸高；單點對焦蓮臉；快門 180。
光影：主光回到冷月 + 熔岩反光；對比中等。
色調/LUT：陰影微藍，高光暖 8%。
聲音：碎冰落地 -12 dB；蒸汽「シュー」-10 dB；音樂慢降 70 BPM。
物理/質感：冰晶受重力 9.8 m/s² 緩落；蒸汽對流 0.6 m/s；重弩金屬表面熱扭曲 1%。
轉場：直接切。
Angle A11
構圖：前景落雪，中景蓮，後景裂谷；留白 12%。
內容：重弩白煙，能量槽光降至 20%；冰晶反光。
補充：膚質分層—base 0.35 粗糙，SSS 0.12，specular 0.5；衣料纖維 4k 清晰。
安全：無字。

Beat 12（13.2–15.0s）｜重點：收尾特寫，沉穩離場
Blocking：緩推近側臉，蓮抬頭看雪，扛弩轉身離開。
Camera：70mm 胸高；單點對焦眼；快門 180。
光影：主光柔和，體積霧淡；對比柔。
色調/LUT：膚色優先，去飽和 5%。
聲音：風聲漸弱 -14 dB；金屬收納「カタッ」-8 dB；遠方雪崩低鳴。
物理/質感：斗篷摩擦係數 0.45，步伐踩碎冰 0.6cm；呼吸白霧 0.3s；重弩冷卻蒸汽 45℃。
轉場：淡出黑 0.3s。
Angle A12
構圖：側臉中近景，最後定格背影居中；留白 18%。
內容：蓮扛弩向裂谷深處走，腳邊碎冰被踩裂。
補充：眼神從緊繃→放鬆，虹膜反光熔岩餘光；肩上蒸汽繞出白霧。
安全：無文字。

# Platform Layer
- Hook A（故事向）0–1s：裂谷全景 + 凍結戰旗。Hook B（衝擊向）9.6–12s 漫畫爆炸。
- First-shot visual hook: 懸浮戰旗與停住雪花。
- Subtitles/Caption：主檔無字幕；短版可加「最後一矢」2 字，位置右下，需移除在生成。
- Thumbnail：選 10.8s 漫畫爆炸瞬間，蓮背對爆光，對比 1.8，飽和 +10%。
- Hashtag：#極寒裂谷 #充能重弩 #冰龍 #AnimeAction #ComicBurst。
- CTA：結尾淡出前加入 0.3s logo-free 黑場，供後期疊 CTA。
- 切片輸出策略：短版剪 0–1s、9.6–12s；長版全長 15s；字幕行對應 Hook 句「就用這一發」可後期上字。

# Negative Instructions
- 禁止：真實商標、名人肖像、宗教政治符號、血腥斷肢、成人尺度、可讀文字、超現實魚眼、過曝濾鏡、畫面抖動 >3%、錯誤語言環境字幕。
- 自動檢核清單：
  - ☐ 無 Logo/文字；☐ 無政治宗教；☐ 無血腥；☐ 遵守 PG-13；☐ 無魚眼與過曝；☐ 軸線未跨；☐ 漫畫格僅限 9–10 幕；☐ 時長 15s；☐ 9:16 畫幅；☐ 12 幕各 1.2s。

# Assumptions
- 未提供朝倉蓮臉部參考，假設為短黑髮、劍眉、左眉疤；如有官方頭像需替換。理由：維持角色一致性。
- 日文配音由系統生成低語，無具體聲優指定；可替換。理由：未提供聲優名單。

# AGENT Self-Check
- 結構：含 Master、Act/Beat/Angle、timecode 12×1.2s，漫畫格區段標記；✓
- Physics & PBR：每 Beat/Angle 填寫重力/慣性/材質/光學、PBR 粗糙度/金屬度/IOR；✓
- Stylepacks：引用 Anime Fantasy、Light Glyph Anime，新增 Chromatic Comic Burst 僅 9–10 幕；✓ 無衝突。
- Continuity：軸線與光位固定，Boss stage/hero state 時間線列出；✓
- Platform Layer：Hook/字幕/縮圖/切片/CTA 已寫；✓
- Negative：禁用項列出，自檢清單填寫；✓
- Risk：未有官方臉模需後續確認；✓ 已揭露於 Assumptions。

# Changelog vs Previous Episode
- 本集為首集，建立 baseline：
  - 角色：朝倉蓮初登場，外觀設定、武器參數首次記錄。
  - 場景：極寒裂谷入口初次展示，斷橋/碎塔/熔岩縫隙狀態標記為 Stage 0，後續集數需沿用破損度。
  - 道具：充能重弩與能量箭頭首次定義，能量槽顏色對應蓄壓百分比（暗紅<30%、金黃30–80%、炙白80–100%）。
  - 敵人：冰龍 Stage A→D 演化表建立，胸口核心位置鎖定為胸骨中心偏左 0.3m。

# Persistent Elements Table（跨集保留）
- 充能重弩：金屬度 0.8、粗糙度 0.35、重量 28kg；劣化軌跡：每次重擊後刮痕密度 +5%，下一集需沿用。
- 蓮服裝：厚布斗篷粗糙 0.55，纖維走向左上→右下；護腕皮革粗糙 0.5；下一集若損壞需標記破洞位置。
- 冰龍核心：藍白脈動 2Hz；被擊碎後留存核心碎片可作為後續道具；碎片色碼 #B5E9FF。
- 裂谷環境：熔岩縫隙紅光亮度 1200 cd/m²；懸浮戰旗布料 8k；雪花粒徑 0.4mm；需保持「動能封存」效果於背景物。

# Next Episode / Spin-off Ideas
- 主線延伸 1：蓮攜帶核心碎片返回據點，遭遇封存動能的城鎮，需要解凍時間膠囊；引入新角色「時間技師」。
- 主線延伸 2：冰龍死亡解放古老防禦系統，裂谷底部浮現機械遺跡，需要蓄壓重弩的能量模組與機械遺跡互動。
- 番外／日常：蓮在補給站維修重弩，描述 PBR 細節（油膜、指紋、工具痕），作為 30 秒日常短片。

# Platform Layer Supplement（細化切片與字幕規範）
- Hook A 字幕候選（後期再上）：繁中「極夜裂谷，時間凍住」0.6s；需後期添加。
- Hook B 字幕候選：繁中「就用這一發」疊在漫畫格角落，使用描邊白字陰影，避免遮擋主體。
- 長版 Caption 範圍：0–4.8s 以世界觀旁白；9.6–12s 以擬聲字疊加；12–15s 靜音無字。
- 音頻備註：若社群平台降噪導致高頻損失，需保留 10kHz 以上空氣感，避免完全抽空。
- 切片字幕對應：
  - 0–1s：字幕行「裂谷定格的風」
  - 9.6–10.8s：字幕行「ドゴォン!!」
  - 10.8–12s：字幕行「クラッシュ!!」
  - 13.2–15s：字幕行可留白。
- 轉檔策略：主檔 24fps；社群短版可轉 30fps，需重計時間碼保持 15s；保留 180° 快門感。

# Execution Notes Addendum
- Camera Continuity Logger：記錄鏡頭每幕焦段/光圈/快門角，存入 metadata，後續集數沿用或迭代。
- Seed Policy：每次生成記錄隨機種子；若需重現，固定種子並標記於 metadata；本稿預設隨機但需 log。
- VFX Budget：冰碎粒子每幕上限 80k；漫畫格粒子禁用 motion blur；演算成本預估 12 ms/frame（Niagara）。
- Safety：保持 PG-13，冰晶碎裂不得出現血色；蓮傷痕僅閃現細節，不聚焦出血。

# Additional Physics/Optics Notes
- 折射：冰牆 IOR 1.31，邊緣使用 Fresnel 0.02，內部霧化散射 0.6；當龍息撞擊時增加 subsurface scattering 0.1。
- 熱扭曲：熔岩縫隙上方 0.5m 熱氣折射 0.8%，影響背景塔樓線條；需在 Act I wide shot 中表現。
- 粒子求解：雪花使用 GPU 粒子，Drag 0.12，風向隨龍息變化 ±15°；冰晶爆散使用 RBD 轉 Sprite Sheet 16×16。
- 布料反應：斗篷與戰旗使用雙向布料模型，阻尼 0.2，彈性 0.15；碰撞與冰柱摩擦係數 0.35。
- 音畫同步：觸發點 T5/T9/T10 音量門檻 -12 dB 驅動 Bloom 強度；冷卻時下降到 -24 dB。

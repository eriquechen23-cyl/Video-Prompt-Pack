# Project: 鋼脈都市 MUSCLE LINE｜Episode 2 — thunder-flash-aoe_v01
project_name: 鋼脈都市 MUSCLE LINE
series_name: 鋼脈都市 MUSCLE LINE｜雷閃天擊篇
arc: 霓虹鋼影之夜
episode_index: 2
slug: thunder-flash-aoe_v01
target_platform: Sora/Deev ingest｜social cut (YouTube Shorts/IG Reels/TikTok)
duration_sec: 15
shots_count: 12
style_primary: Anime Fantasy Look
style_secondary: Lightning Chain Look
worldstate_ref: 鋼鐵廢墟夜城、暗紫霓虹裂雲、小怪潮、朝倉蓮黑黃主題色、雷閃瞬移+天雷 AOE
goal: 15 秒 9:16 2D 日系動漫風＋漫畫格閃現，主角朝倉蓮「雷閃天擊」一拳清場，日文配音＋激烈電子搖滾 BGM

# _core（全部模板內嵌，含品牌層 Do/Don't）
## Brand Layer
- 角色共通：朝倉蓮（身高 185cm、體重 92kg、肩寬 52cm），主題色黑黃，左眉疤，口頭禪「就用這一發」。
- 場景色感：鋼鐵廢墟暗紫 40%（#3A2E4F）、霓虹洋紅 25%（#D45CFF）、電弧藍白 20%（#9BE0FF）、焦橙火星 15%（#FF8A3C）。
- 文案語氣：中文敘事＋日文低語（短句）＋英文字母只用擬聲（BOOM、CRACK），避免長句字幕。
- Do: 對比度 1.8 gamma curve、膚色 55–65 IRE、保留 HUD 線條與殘影；Don't: 禁用魚眼、禁用過曝 Bloom、禁止未授權 Logo 或可讀標語。

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

# QA Checklist（拍前 30 秒）
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
- 以 warm_gold 勾勒蓮手背雷紋，配合黑黃服裝形成品牌對比。
- 使用 strong_outline 確保廢墟鋼筋與殘影分層清晰。
Don't:
- 不要讓膚色超過 IRE 70。
- 禁用魚眼與過曝 Bloom。

## Style: Lightning Chain Look（Default ON）
name: Lightning Chain Look
lut: Ionized-Arc
saturation_adjust: 0.12
contrast: high
highlights: electric_blue
shadows: graphite_cool
texture: rain_slick_leather
chromatic_aberration: tangential_blue_shift
lens_distortion: controlled_pincushion
notes:
  - 強調藍白電弧的高亮輪廓，保留肌膚 52 IRE 微暖
  - 地面濕潤反光需加入局部高光刷動
  - 霧氣與電暈採用分層曝光避免過曝
Do:
- 用 electric_blue 高光跟隨雷鏈節點，讓瞬移殘影拖曳 3 frame。
- 增加雨_slick 質感在破裂街面水坑，反射紫霓虹。
Don't:
- 禁止將 bloom 推超過 0.82，避免吞沒漫畫格線條。
- 不使用高飽和紅光與藍光同時過曝。

## Style: Lightning Chain VFX（Default ON）
name: Lightning Chain VFX
niagara_presets:
  - 圓弧雷鏈生成
  - 電暈過曝脈衝
  - 地面枝狀放電
unity_vfx_graph:
  - ArcLoop.vfx
  - ChainLeap.vfx
  - OzoneBloom.vfx
houdini_flipbooks:
  - lightning_flash_cluster
  - ozone_mist_swirl
  - finger_arc_ignition
shader_settings:
  bolt_core_thickness: 0.45
  afterglow_decay: 0.65
  spark_density: 1.8
  refraction_ripple_intensity: 0.3
sdf_settings:
  stickiness: 0.25
  jump_arc_delay: 0.15
  impact_scorch_radius: 1.2
bloom_control:
  idle: 0.18
  trigger_peak: 0.82
  cooldown: 0.3
audio_sync:
  zap_triggers: align_arc_leaps
  bass_hit: accent_phase_interference
notes:
  - 雷鏈跨目標時需保留殘影拖曳 3 frame
  - 地面放電使用形狀配對剪與光閃過門銜接
  - HUD 元素需與鏈路節點一一對應，避免漂移
Do:
- 觸地雷紋擴散時 stickiness 0.25 保持附著在破裂鋼筋，並鎖定 impact_scorch_radius 1.2m。
- 以 jump_arc_delay 0.15s 排節奏，對齊電子搖滾 120 BPM 八分音符。
Don't:
- 不混用風暴霧氣厚度 >0.6，避免遮蓋雷紋。
- 禁止減少 afterglow_decay 至 <0.4，需保留尾焰。

## Style: Lightning Chain Audio（Default ON）
name: Lightning Chain Audio
core_layers:
  - ozone_drone_bed
  - crackle_triplets
  - sub_thump_sync
peak_events:
  - timestamp: ignition
    sfx: finger_arc_snap
    level_db: -6
    stereo_width: 100
  - timestamp: convergence
    sfx: thunder_iris
    level_db: -3
    stereo_width: 140
rhythmic_grid:
  bpm: 120
  subdivision: eighths
  swing: 0.04
sidechain:
  trigger_bus: impact_bus
  target: ozone_drone_bed
  reduction_db: 2
dynamics:
  crest_factor: 10
  transient_protection_db: -1
notes:
  - 120 BPM 節奏需呼應每 0.5s 電弧節點亮起
  - 扣指瞬間加上金屬尖銳高頻 6kHz
  - 殘光收束後留 1.5s 氣流與餘電尾音
Do:
- 在天雷落下瞬間觸發 thunder_iris SFX 並 sidechain 壓低 ozone_drone 2 dB。
- 配合日文低語，將 crackle_triplets 音量降至 -12 dB 以留出人聲空間。
Don't:
- 不要在 300Hz 以下堆疊過量低頻，避免與衝擊波低頻衝突。
- 禁止手持晃動聲或環境嘈雜聲蓋過雷鳴主事件。

## Style: Storm Boss Lock-On Look（Default OFF，僅作雨感參考）
name: Storm Boss Lock-On Look
lut: Tempest-Rain
saturation_adjust: -0.02
contrast: high_dynamic
highlights: electric_blue
shadows: deep_charcoal
texture: rain_slick_armor
chromatic_aberration: restrained_blue_fringe
lens_distortion: micro_barrel
notes:
  - 夜雨環境保留冷藍閃電反光，膚色維持 58 IRE
  - 地面水漬需加入鏡面高光與波紋疊層
  - HUD 螢光元素亮度限制在 120 nits，避免壓過雷弓電弧
Do:
- 僅在第 1–2 幕鋼鐵廢墟雨痕上使用 texture: rain_slick_armor。
- 保持對比高_dynamic 以凸顯霓虹裂縫。
Don't:
- 不混用於漫畫格（9–10 幕）。
- 不將 chromatic_aberration 提升超過預設，避免邊緣彩邊過厚。

## Style: Chromatic Comic Burst（New｜Default OFF，僅第 9–10 幕）
Applicable for: 彩色漫畫分鏡擊殺瞬間；Do NOT mix with heavy film grain。
Visual traits: 粗黑描線 4px 等效、彩色網點 18–24ppi、速度線佔畫幅 35–50%、背景用 CMYK 分色塊；高對比 +1.6 gamma；保留陰影硬邊。
Audio traits: 擬聲字 SFX 疊加 0.8 秒（ドゴォン!!、バキィ!!），限 -8 dB 峰值；瞬時鼓點同步。
Do:
- 使用 CMYK 網點並保留白邊燒蝕轉場回動畫。
- 對比與飽和提升 20%，線條加粗不低於 3px。
Don't:
- 不加入寫實景深；不使用鏡頭眩光；避免動態模糊。

# Technical Specs
- Aspect Ratio: 9:16 直式；Resolution: 1080×1920；FPS: 24 base（原始渲染 48fps → 24fps with 180° shutter）。
- Camera pack: 24mm for Act I 廢墟全景，35–45mm for Act II 閃現連招，50–70mm for Act III AOE 收束；畸變校正 <1%。
- Shutter: 180° baseline，漫畫格切至 200° 凍結粒子並取消 motion blur；Rolling shutter 模擬關閉。
- DOF: 前中後分層，漫畫格 DOF 關閉；Focus on eyes or雷紋；bokeh 偏六角粒度 0.2。
- Grain: 控制在 papergrain subtle，暗部保細節；No film damage。
- Color pipeline: log capture → filmic LUT → final contrast（Do: gamma 1.8, lift 0.03, gain 0.96）。
- Physics labeling: gravity 9.8 m/s²；雨膜摩擦係數 0.32；布料阻尼 0.22；電弧粒徑 0.2–0.5mm；雷擊氣化塵粒密度 0.4 g/m³。

# Continuity Layer（pre-Master）
- Axis: 蓮在畫面右，怪群從左後→前逼近；鏡頭保持蓮右後 100–120° 弧線，不跨軸；漫畫格可短暫反轉但回原軸。
- Light: 主光霓虹裂雲 3600K 自左上掃過；副光紫霧地燈 3200K；雷擊瞬間加白光 6500K 0.2s；漫畫格用平光後燒蝕回主光。
- Distance curve: Act I 24–28mm wide；Act II 32–45mm mid；Act III 50–70mm close；三秒內不跳回 wide。
- Enemy stage timeline：T0–4s 小怪 Stage A（完整潮）；T4–8s Stage B（被雷紋束縛，速度降 40%）；T8–12s Stage C（遭天雷擊碎，成黑剪影）；T12–15s Stage D（焦痕冒煙、地面坑洞）。
- Hero state timeline：T0–3s 蓄雷 30% 指節雷光；T3–7s 蓄雷 60% 前臂雷紋；T7–9.6s 蓄雷 95% 肩頸放電；T9.6s 天雷落下後冷卻 45℃ 蒸汽。
- Persistent elements：黑黃戰衣（布料粗糙 0.52、金屬護甲粗糙 0.28 金屬度 0.7）、雷紋手套（導電紋路粗糙 0.35）、街面金屬碎樑（金屬度 0.85 刮痕 0.2mm）。

# Master Prompt（15s｜Anime Fantasy + Lightning Chain｜9:16｜24fps｜PBR 高質感）
- Worldstate snapshot（UTC+8 2025-11-24 深夜）：鋼鐵廢墟街區，雲層被霓虹撕成暗紫裂縫，雨痕未乾的地面反射霓虹；風速 5 m/s，空氣含金屬粉塵 0.3 g/m³。
- Lead: 朝倉蓮，黑黃主題戰衣，身高 185cm，右拳雷紋沿指節→肩膀亮起；膚色 55–65 IRE，手套導電紋路發光。
- Intent: 15 秒雷閃瞬移 + 天雷 AOE，一拳貼地引雷清場；第 9–10 幕用彩色漫畫分鏡強調擊殺。
- Camera continuity: 遵循 Axis 與 Distance curve；鞭移與遮擋轉場；漫畫格燒蝕回復；手持晃動 ≤3%。
- Constraints list: 蓮站右側不可左右交換；雷光亮度不可突然下降；小怪不可消失不見需被雷光吞噬；無字幕、無 Logo、PG-13。
- Execution note: 破裂街面使用 camera projection 固定；Volume pass 紫霧 0.25；雷紋陣用 Houdini flipbook 16×16；Denoise 限制 0.32 strength。
- Physics & PBR: 地面濕潤粗糙度 0.18 IOR1.33；金屬梁粗糙 0.3 金屬度 0.85；雷光折射 1.0、餘暈 scattering 0.4；布料阻尼 0.22；拳擊反作用力肩部後坐 6°；殘影拖曳 3 frame。
- Do/Don't引用：Do 使用 gamma 1.8 高對比；Don't 使用魚眼與過曝 Bloom；Do 強化黑黃對比與電弧藍白；Don't 使用寫實字幕或可讀標示。
- Micro-actions: 每 Beat 加入 <1.2s 細節：指節緊握的 0.2s 雷光跳動、殘影閃移 0.3s 拖尾、雷紋沿地面擴散 0.4s、天雷擊中後 0.2s 煙塵回捲。

# Act / Beat / Angle 分鏡（12 幕 × 1.2s）
Act I（0.0–4.8s）｜意圖：建立廢墟與危機｜基調：緊張→決斷｜節奏域：慢入 1.2s
美術要點：鋼筋斷裂、霓虹裂雲、雨痕地面反射、黑黃戰衣陰影。

Beat 1（0.0–1.2s）｜重點：夜城全景，小怪潮逼近
Blocking：俯視掃過廢墟街道，影子小怪在裂縫間竄動。
Camera：滑軌俯拍 24mm 眼高；層次拉焦前→後；快門 180。
光影：霓虹裂雲 3600K 從左上掃，街燈紫霧補光；對比中高。
色調/LUT：陰影微藍，高光暖 6%。
聲音：遠處低鳴 -12 dB；腳步碎響 -10 dB；音樂電子搖滾前奏 120 BPM。
物理/質感：雨膜厚 0.8mm，反射霓虹；小怪影子速度 4 m/s；重力 9.8 m/s²；地面摩擦 0.32。
轉場：直接切 → Beat2。
Angle A1
構圖：三分線＋前中後層次，留白 15%。
內容：斷裂鋼筋與霓虹倒影，遠處小怪剪影。
補充：體積霧 0.25，遠方雲裂閃現電弧 0.1s。
安全：無可讀字。

Beat 2（1.2–2.4s）｜重點：主角走入畫面，雷光在指節竄動
Blocking：蓮從右側走向畫面中心，握拳雷光沿指節跳動。
Camera：側移 28mm 腰高；層次拉焦腳→拳→臉；快門 180。
光影：主光仍左上，雷光自發光 4800K；對比高。
色調/LUT：膚色優先，陰影藍 8%。
聲音：靴子踏水聲 -8 dB；雷光「パチ」-10 dB；低語「ここで止める」。
物理/質感：手套粗糙 0.35 金屬紋路導電；水花粒徑 1–2mm；雷光拖尾 3 frame。
轉場：遮擋切到前推。
Angle A2
構圖：前景斷鋼筋，蓮半身中景；留白 12%。
內容：拳頭雷紋亮度從 20%→40%，肩膀微抖。
補充：服裝布料風偏 5°，雨滴沿手背滑落。
安全：無 Logo。

Beat 3（2.4–3.6s）｜重點：蓮蓄力，雷紋爬上前臂
Blocking：停步蓄力，雷光沿前臂→肩膀像電路亮起。
Camera：穩定器 30mm 胸高；對焦雷紋→臉；快門 172。
光影：主光保持，雷紋自發光提升；對比高。
色調/LUT：黑黃服飾對比強，去飽和 5%。
聲音：雷紋嗡鳴 -6 dB；衣料摩擦；音樂進入主旋律 120 BPM。
物理/質感：電弧厚 0.5cm，亮度 120 nits；肌肉張力肩部隆起；汗霧 0.2s 蒸發。
轉場：鞭移 → Beat4。
Angle A3
構圖：中近景三分線，雷紋佔前景。
內容：前臂雷紋像電路圖，肩膀亮點成網絡。
補充：殘影 3 frame 疊加，背景霓虹拉成線。
安全：無文字。

Beat 4（3.6–4.8s）｜重點：瞬移啟動，殘影穿梭小怪
Blocking：蓮身影瞬移，留下多重殘影穿插小怪群。
Camera：側向平移 28mm 腰高；對焦殘影中點；快門 200（降低模糊）。
光影：霓虹混光 + 雷光閃爍；對比高。
色調/LUT：陰影微藍，高光暖 10%。
聲音：瞬移「シュン」-6 dB；小怪尖鳴 -9 dB；音樂鼓點加重。
物理/質感：殘影位移 3m/0.2s；地面水花被氣流帶起 0.3m；雷鏈拖尾 0.15s。
轉場：光源匹配切 Act II。
Angle A4
構圖：斜向過肩，殘影排成弧線。
內容：小怪被氣浪推開，雷光在地面留下細線。
補充：水滴被電弧汽化形成薄霧 0.1s。
安全：無可讀字。

Act II（4.8–9.6s）｜意圖：束縛與蓄力｜基調：決斷｜節奏域：穩定 1.2s
美術要點：雷紋陣圖、殘影繞場、霓虹光反射在金屬梁。

Beat 5（4.8–6.0s）｜重點：雷紋陣貼地展開（Stage A→B）
Blocking：蓮落地右拳貼地，雷光收束成刺眼亮點，陣紋蔓延鎖住怪群。
Camera：俯角 32mm 膝高；層次拉焦拳→陣中心；快門 180。
光影：主光左上，雷陣自發光 5200K；體積霧被雷光切開。
色調/LUT：冷暖對比強，去飽和 6%。
聲音：雷陣「バチバチ」-6 dB；地面裂紋「ゴゴ」-8 dB。
物理/質感：雷紋半徑 6m，擴散速度 12 m/s；地面粗糙 0.18；電弧附著 stickiness 0.25。
轉場：直接切。
Angle A5
構圖：俯視陣中心，雷紋放射佔畫幅 70%。
內容：小怪被鎖定，腳下雷鏈纏繞。
補充：電弧跳躍延遲 0.15s，尾焰 afterglow 0.65。
安全：無 Logo。

Beat 6（6.0–7.2s）｜重點：抬頭宣告，殘影仍繞圈
Blocking：蓮抬頭凝視雲層，殘影繞陣邊緣拖雷光圈。
Camera：繞拍 40mm 胸高；對焦眼→雲裂；快門 172。
光影：霓虹反光側逆，眼神光保留；對比中高。
色調/LUT：黑黃對比 + electric_blue 高光。
聲音：日文低語「ここで終わりだ」；雷光旋轉聲 -7 dB；音樂節奏推至 128 BPM。
物理/質感：殘影以 4 m/s 繞圈；雷鏈 bolt_core_thickness 0.45；衣襬延遲 0.2s 甩動。
轉場：遮擋切。
Angle A6
構圖：低角度中央構圖，雲裂占上半。
內容：眼中倒映電光，殘影形成環。
補充：Chromatic aberration 控制在 tangential_blue_shift 細微。
安全：去可讀字。

Beat 7（7.2–8.4s）｜重點：雷光凝聚肩膀，準備天雷
Blocking：雷光沿前臂爬上肩膀，形成亮點向天衝。
Camera：35mm 胸高；對焦肩膀亮點→雲；快門 180。
光影：肩膀亮點 6200K；周圍暗部加 rim 光；對比高。
色調/LUT：暖亮點 vs 暗紫背景，去飽和 5%。
聲音：能量聚集低頻 -6 dB；電弧刺耳高頻 6kHz 微升。
物理/質感：亮點能量 1.2kW 等效；肩部肌肉隆起，護甲金屬度 0.7 反射；汗霧 0.2s 蒸散。
轉場：鞭移 → Beat8。
Angle A7
構圖：側肩中近景，亮點居三分線。
內容：雷光化成細線往雲層射出。
補充：皮革護肩粗糙 0.28 反光；電弧擊穿空氣產生細微等離子閃。
安全：無文字。

Beat 8（8.4–9.6s）｜重點：拳向天揮出，引爆雲裂（進入漫畫格前奏）
Blocking：蓮拳向天揮出，雷紋直衝雲層撕裂暗紫雲。
Camera：仰角 45mm 胸高；對焦拳→雲裂；快門 200。
光影：雷柱照亮雲底，體積光向下；對比極高。
色調/LUT：冷紫雲層＋炙白雷柱；膚色保護。
聲音：雷柱轟鳴 -4 dB；音樂 drop 前預備，鼓點停 0.2s。
物理/質感：雷柱寬 0.6m，速度 300 m/s；雲裂張口 5m；氣流上升 2 m/s。
轉場：硬切至漫畫格（Style Chromatic Comic Burst）。
Angle A8
構圖：拳頭居中央，雲裂佔上半；留白 10%。
內容：雷柱射穿雲層，邊緣速度線。
補充：motion blur 降至 0；線條加粗 3px 提前適應漫畫格。
安全：無字幕。

Act III（9.6–15.0s）｜意圖：天雷落下清場｜基調：衝擊→收束｜節奏域：加速後緩
美術要點：漫畫格爆閃、黑色剪影飛散、焦痕坑洞。

Beat 9（9.6–10.8s）｜重點：漫畫格—天雷直擊陣心（擊殺① Stage C）
Blocking：天雷落下砸在陣中心，小怪化黑剪影。
Camera：漫畫格平行視角；無 DOF；快門 200；對焦雷擊核心。
光影：平光高對比，CMYK 網點；硬邊陰影。
色調/LUT：飽和 +20%，對比 +20%。
聲音：擬聲「ドゴォン!!」-8 dB 疊合；低頻衝擊 -5 dB。
物理/質感：雷擊直徑 1m，衝擊波推飛碎屑 20 m/s；剪影飛散角度 45°。
轉場：漫畫格維持。
Angle A9（Style: Chromatic Comic Burst）
構圖：主格雷擊佔 70%，兩小格展示小怪剪影飛散。
內容：速度線填滿背景；擬聲字漂浮。
補充：網點密度 20ppi；邊框燒蝕邊緣 0.2s。
安全：無品牌。

Beat 10（10.8–12.0s）｜重點：漫畫格—爆閃擴散，雷紋沿地面蔓延（擊殺② Stage C→D）
Blocking：雷紋沿地面奔跑，爆閃吞沒剩餘小怪，邊框燒蝕回動畫。
Camera：多格分鏡，主格 60% 地面雷紋，兩小格 20%+20% 怪被掃；無 DOF；快門 200。
光影：平光 + 燒蝕邊框；對比高。
色調/LUT：飽和 +20%，對比 +20%。
聲音：擬聲「バキィ!!」「ズガァン!!」-8 dB；電子鼓點同步。
物理/質感：雷紋速度 18 m/s；地面焦黑粗糙度提升到 0.5；碎屑粒徑 2–5mm。
轉場：邊框燒蝕淡出 → 回 2D 動畫。
Angle A10（Style: Chromatic Comic Burst → fade）
構圖：主格雷紋蛇形，邊框漸融；留白 8%。
內容：小怪剪影化成灰屑；雷光餘暈漂移。
補充：燒蝕 0.3s，回到原 LUT。
安全：無可讀字。

Beat 11（12.0–13.2s）｜重點：光芒散去，坑洞冒煙（Stage D）
Blocking：光散去，只剩裂地坑洞與冒煙焦痕，蓮站中央收拳。
Camera：50mm 胸高；單點對焦蓮臉；快門 180。
光影：主光回霓虹 3600K；焦痕餘光橙紅 3000K；對比中。
色調/LUT：陰影微藍，高光暖 8%。
聲音：餘電滋滋 -10 dB；蒸汽「シュー」-10 dB；音樂回落 110 BPM。
物理/質感：坑洞直徑 4m 深 0.6m；焦痕粗糙度 0.5；蒸汽對流 0.5 m/s；布料阻尼 0.22。
轉場：直接切。
Angle A11
構圖：前景裂縫，中景蓮，後景霓虹裂雲；留白 12%。
內容：蓮收拳站穩，雷紋逐漸熄滅。
補充：膚質分層—base 0.34 粗糙，SSS 0.12，specular 0.52；金屬護甲反光顆粒 0.2。
安全：無字。

Beat 12（13.2–15.0s）｜重點：手背雷紋熄滅，風帶走餘電（收束）
Blocking：近景手背雷紋漸暗，蓮轉身離開，夜風吹過帶走細微放電聲。
Camera：70mm 胸高；對焦手背→側臉→背影；快門 180。
光影：主光柔和，體積霧淡；對比柔。
色調/LUT：膚色優先，去飽和 5%。
聲音：放電尾音 -14 dB；腳步踩碎金屬片「カシャ」-8 dB；風聲低鳴。
物理/質感：雷紋亮度從 15%→0%，耗時 1s；布料摩擦係數 0.45；金屬碎片彈性係數 0.35 輕彈。
轉場：淡出黑 0.3s。
Angle A12
構圖：側臉中近景到背影，留白 18%。
內容：背影離開，腳下焦痕圓坑。
補充：殘影最後 2 frame 消散，風帶起塵粒 0.2mm 粒徑。
安全：無文字。

# Platform Layer
- Hook A（故事向）0–1s：廢墟全景＋小怪潮奔跑。Hook B（衝擊向）9.6–12s 漫畫爆閃與雷紋掃蕩。
- First-shot visual hook: 俯視霓虹裂雲映在雨面，怪影穿梭。
- Subtitles/Caption：主檔無字幕；短版可加「雷閃天擊」3 字右下角，生成時仍移除文字。
- Thumbnail：選 9.6s 天雷擊中漫畫格，蓮背對爆光，對比 1.8，飽和 +12%。
- Hashtag：#鋼脈都市 #朝倉蓮 #雷閃天擊 #AnimeAction #ComicBurst。
- CTA：結尾淡出前 0.3s 黑場供後期疊 CTA，原檔不含字幕。
- 切片輸出策略：短版剪 0–1s、9.6–12s；長版全長 15s；字幕行對應 Hook 句可後期上「ここで終わりだ」。

# Negative Instructions
- 禁止：真實商標、名人肖像、宗教政治符號、血腥斷肢、成人尺度、可讀文字、超現實魚眼、過曝濾鏡、畫面抖動 >3%、錯誤語言環境字幕。
- 自動檢核清單：
  - ☐ 無 Logo/文字；☐ 無政治宗教；☐ 無血腥；☐ 遵守 PG-13；☐ 無魚眼與過曝；☐ 軸線未跨；☐ 漫畫格僅限 9–10 幕；☐ 時長 15s；☐ 9:16 畫幅；☐ 12 幕各 1.2s。

# Assumptions
- 項目採用「鋼脈都市 MUSCLE LINE」既有世界觀，假設本集為雷閃篇 Episode 2，未提供前一集鏡頭延續，僅沿用品牌色與主角設定。理由：維持系列一致性。
- 未提供日文聲優，使用中性低語風格；如需指定聲優可替換。理由：未給出人選。
- 未提供城市地圖，假設廢墟為高樓倒塌街區，保留霓虹牌與鋼筋。理由：符合文案描述。

# AGENT Self-Check
- 結構：含 Master、Act/Beat/Angle、timecode 12×1.2s，漫畫格區段標記；✓
- Physics & PBR：各 Beat/Angle 填寫重力/慣性/材質/光學、PBR 粗糙度/金屬度/IOR；✓
- Stylepacks：引用 Anime Fantasy、Lightning Chain（Look/VFX/Audio）、Storm Boss Lock-On 參考、Chromatic Comic Burst 新增；✓ 無衝突。
- Continuity：軸線與光位固定，敵人/英雄狀態時間線列出；✓
- Platform Layer：Hook/字幕/縮圖/切片/CTA 已寫；✓
- Negative：禁用項列出，自檢清單填寫；✓
- Risk：未有官方地圖與聲優，已於 Assumptions 提出；✓

# Changelog vs Previous Episode
- 延續品牌：黑黃戰衣、雷紋手套、朝倉蓮口頭禪「就用這一發」。
- 新增內容：霓虹鋼鐵廢墟舞台、雷閃瞬移殘影機制、天雷 AOE 陣圖；漫畫格切換首次加入雷擊段落。
- 狀態更新：街區地面新增雷擊坑洞（直徑 4m 深 0.6m）需在後續集數保留；護甲表面新增燒蝕痕跡密度 +5%。

# Persistent Elements Table（跨集保留）
- 黑黃戰衣：布料粗糙 0.52、纖維走向右上→左下；護甲金屬度 0.7、粗糙 0.28；雷擊後燒蝕點需沿用。
- 雷紋手套：導電紋路粗糙 0.35、發光亮度 120 nits；拳擊反作用力 6° 肩後坐；下一集若破損需標註位置。
- 街區環境：霓虹裂雲暗紫、雨痕地面反射；新增焦痕坑洞、燒蝕鋼筋；塵粒密度 0.3 g/m³ 需持續。
- 雷陣圖：半徑 6m 放射紋刻入地面，焦黑粗糙度 0.5；後續場景需保留。

# Next Episode / Spin-off Ideas
- 主線延伸：雷擊後開啟地下變電站，蓮需下探修復核心，加入垂直空間鏡頭與磁場反作用力描述。
- Boss 進階：下一敵人具電磁護盾，需要調整 bolt_core_thickness 與 shield_crystalize_speed 參數，強調反射與折射。
- 日常短篇：蓮在臨時庇護所維修手套與護甲，拍攝 PBR 細節（油膜、刮痕、指紋），作 30 秒安靜段落。

# Platform Layer Supplement（細化切片與字幕規範）
- Hook A 字幕候選（後期再上）：繁中「霓虹下的雷光」0.6s；需後期添加。
- Hook B 字幕候選：繁中「天雷一拳」疊於漫畫格角落，白字黑描邊，避免遮擋主體。
- 長版 Caption 範圍：0–4.8s 世界觀旁白；9.6–12s 擬聲字疊加；12–15s 靜音無字。
- 音頻備註：社群降噪時保留 10kHz 以上空氣感，避免抽空；sidechain 保持 2 dB 壓降即可。
- 切片字幕對應：
  - 0–1s：字幕行「鋼鐵廢墟的夜」
  - 9.6–10.8s：字幕行「ドゴォン!!」
  - 10.8–12s：字幕行「バキィ!!」
  - 13.2–15s：字幕行可留白。
- 轉檔策略：主檔 24fps；社群短版可轉 30fps，需重計時間碼保持 15s；保留 180° 快門感。

# Execution Notes Addendum
- Camera Continuity Logger：記錄鏡頭焦段/光圈/快門角、雷紋亮度變化，存入 metadata 供後續延續。
- Seed Policy：每次生成記錄隨機種子；若需重現，固定種子並標記於 metadata；本稿預設隨機。
- VFX Budget：雷鏈與雷陣粒子每幕上限 90k；漫畫格禁用 motion blur；演算成本預估 13 ms/frame（Niagara）。
- Safety：保持 PG-13，小怪僅為影子與骨刺剪影，無血腥；雷擊焦痕不得出現組織碎片。

# Additional Physics/Optics Notes
- 折射：雨膜 IOR 1.33，地面水坑有鏡面高光；電弧折射 1.0，周圍體積霧散射 0.4；雷擊後熱扭曲 1.0% 影響背景霓虹線條。
- 粒子求解：雷鏈粒徑 0.2–0.5mm，Drag 0.08；煙霧使用 VDB 密度 0.35；塵粒受風偏移 10°。
- 布料反應：戰衣布料阻尼 0.22、彈性 0.16；碰撞與鋼筋摩擦係數 0.38；風吹 5 m/s 造成衣襬 0.2s 延遲。
- 音畫同步：觸發點 T5/T9/T10 音量門檻 -12 dB 驅動 Bloom；冷卻時下降到 -24 dB；sidechain 2 dB。
- 轉場物理：鞭移時保留運動模糊 180°；漫畫格關閉 motion blur 防止速度線重疊；燒蝕轉場耗時 0.3s。

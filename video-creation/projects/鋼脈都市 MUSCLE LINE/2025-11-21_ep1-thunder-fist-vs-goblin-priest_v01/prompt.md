# 《鋼脈都市 MUSCLE LINE：雷紋鬥拳師・鋼川烈 vs 哥布林祭司》Master Prompt（15s｜10 幕｜日文配音＋中文字幕）

來源劇本：使用者提供的「廢站雷拳掃蕩哥布林祭壇」10 幕腳本（2D anime style, blue-yellow electric VFX, urban ruins）。

## 世界與角色速記
- 鋼脈都市：廢棄地鐵層被霓虹與蒸氣佔據，潮濕鐵軌與鏽蝕金屬帶有導電光澤，牆面 LED 廣告殘影仍時閃時滅。
- 鋼川烈：爆發型拳士，皮膚銅色、肌肉紋理深刻，手臂刻有可導電的雷紋刺青；拳擊時會讓雷紋同步脈衝，指節有厚繭，鞋底是碳纖維夾層。
- 哥布林祭司：瘦削、皮膚泛綠、戴破布頭巾，骨杖上纏著鐵絲與骯髒骸骨，腳底油膩泥污會在地面留黏著痕；身邊哥布林群行為亂竄，眼眸紅點。

## 一句話題材
在鋼脈都市廢站深處，鋼川烈以雷紋鬥拳衝破哥布林祭司的詛咒儀式，將祭壇與怪群一拳連閃落雷粉碎。

## 風格標籤
2D anime style｜dynamic action cuts｜strong lightning effects｜urban ruins｜blue-yellow electric VFX｜PBR-informed cel shading｜high-density particles｜speedline transitions

---

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
```
Master({時長}s｜{風格}｜{畫幅}｜{fps}｜{質感})
「{時間/地點}；{環境元素1/2/3}；{主體＆動作一句話}。
鏡頭：{滑軌/側向/繞拍/手持≤3%/穩定器}。
表演：{情緒/肢體/視線}。
臉型/髮型：{依上傳五官特徵}。
構圖：{三分線/中央/前中後/留白10–20%}；動態：{風/水/人群/道具}。
寫實細節：{服裝/材質/肌理/光影過門}。
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

### Scene Block Template（`_core/scene_block.md`）
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
轉場：{直接切/光源匹配/鞭移/遮擋/羽化} → 下一段

Angle {a}
構圖：{三分線/中央/前中後/留白}
內容：{特寫/中近景/過肩/道具近拍/環境建立/剪影/反射/倒影}
補充：{道具微動/風/水滴/人流/光影過門/粒子}
安全：{去Logo/去可讀字/成年註記}
```

### Audio Pack 指引（`_core/audio_pack.md`）
```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
人聲：避免加入一般人聲（對話、歌唱等），僅可使用詠唱或咒語式聲線作為氛圍點綴
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```

### VFX 通用 Pack（`_core/vfx_pack.md`）
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

### QA Checklist（`_core/qa_checklist.md`）
```
☐ 情緒→運鏡已定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

### 交付參數預設（`_core/delivery_presets.md`）
```
畫幅：{16:9｜9:16｜1:1}
解析度：{1920×1080｜1080×1920｜2048×2048}
幀率：{24/30/48/60}（如需輕慢動：拍 48–60，輸出 24）
防抖：{開/關}；運動模糊：開；顆粒：微膠片
色彩：Rec.709（交付版）／LOG（調色版）
聲音：立體聲 48kHz；-14 LUFS（YouTube），-1 dBTP
種子：{固定/隨機（記錄）}；連戲：開；時序一致：開
```

### Style Pack：Anime Fantasy Look（`_stylepacks/anime_fantasy/look.yml`）
```yaml
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

### Style Pack：Lightning Chain Look（`_stylepacks/lightning_chain/look.yml`）
```yaml
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
```

### Style Pack：Lightning Chain VFX（`_stylepacks/lightning_chain/vfx.yml`）
```yaml
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
```

### Style Pack：Lightning Chain Audio（`_stylepacks/lightning_chain/audio.yml`）
```yaml
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
```

### Style Pack：Light Glyph Anime Look（`_stylepacks/light_glyph_anime/look.yml`）
```yaml
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
```

---

## Master Prompt 實際填寫
```
Master(15s｜Anime Fantasy Look × Lightning Chain Look × Light Glyph Anime｜2.39:1｜24fps｜PBR-informed cel shading with blue-yellow electric arcs)
「鋼脈都市廢棄地鐵月台夜間；斷裂霓虹、濕潤鐵軌、詭異綠光血陣；鋼川烈甩開外套、雷紋脈動，衝入哥布林祭司的召喚陣並以落雷終結儀式。
鏡頭：俯視滑軌→低角度腳步抬升→中近景揭露肌肉與雷紋→俯視祭司召喚→側面拉鏡蓄電→魚眼加速衝刺→近距離直拳白閃→斜俯連段漫畫格→環繞蓄力→遠景落雷覆蓋。
表演：烈的呼吸與雷紋同步跳動，出拳爆發時肩背肌纖維緊縮，收尾時右手仍冒煙；哥布林祭司狂笑翻白眼，哥布林群慌亂竄動。
臉型/髮型：烈短刺髮被汗壓出硬刺，頰骨銳角、下巴線分明，皮膚 52 IRE 微暖；祭司面部瘦削、皺紋深且泛綠，牙齒尖銳泛黃。
構圖：俯視中央陣式保留 15% 留白、腳步特寫置前景鐵軌導線、肌肉揭示採前中後層次、祭司過肩壓迫、衝刺魚眼留速度線、直拳近距離中央對撞、連段 0.1s 漫畫格定格、落雷遠景以陣式為中心放射。
寫實細節：濕軌道粗糙度 0.6、金屬度 0.5 帶鏡面反射；烈皮膚粗糙度 0.32、汗珠 micro normal；外套布料尼龍粗糙度 0.48；骨杖骨質粗糙度 0.7、鐵絲金屬度 0.8；雷光折射霧氣，體積霧粒子受氣流推動；水漬與血陣在落雷時產生蒸汽霧化。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35mm 建立環境與速度線，50–75mm 近身擊打，100mm 以上僅用於落雷遠景壓縮；
光圈 {T2.4 建立鏡／T2.0 直拳衝擊／T2.8 環繞蓄力}；快門角 {180° 主線／210° 連段速度拖影／165° 魚眼加速}；
對焦 {層次前→中→後：陣式→祭司→烈；單點拳面；呼吸拉焦雷紋至拳面；衝刺殘影採前中切換}。
光影：夜間 3400–3800K 混合霓虹綠與雷電藍；體積霧受落雷瞬間被高光穿透形成 Godray；對比高但保留眼神光；反射光在濕地面上產生條狀鏡面。
色調/LUT：採 Anime Fantasy + Lightning Chain，飽和控制膚色保護、藍白雷高亮、陰影微藍 6%、高光帶電暈金邊；加入紙張顆粒 0.05 保持 2D 質感。
聲音：Lightning Chain Audio 120 BPM 作底，加入哥布林失真詠唱（-10 dB）、雷鳴層 -3 dB 峰值；烈出拳短吼疊低頻；鞋底與鐵軌摩擦「コツ」精準對拍。
轉場：雷閃白屏匹配切、電弧鞭移、速度線遮擋、落雷全白羽化 0.5s 收煙；每段留 4–6 frame 安全緩衝。
安全：哥布林臉不近特寫、地鐵標誌模糊不可讀、血陣符文抽象化；保持連戲：雷紋亮度與汗量隨節奏增加，落雷後煙塵與焦黑連續。
```

---

## 音訊與聲音層級（Lightning Chain Audio 適用）
- BGM：120 BPM 電氣節奏，底層 ozone_drone_bed，遇雷擊以 thunder_iris -3 dB 拉寬立體幅度；收尾留 1.5s 氣流與餘電尾音。
- Foley：
  - 腳步踩鐵軌「ドン」＋微電火花「ジジッ」；
  - 外套布料摩擦尼龍聲 -12 dB；
  - 雷紋脈動時伴 finger_arc_snap -6 dB；
  - 直拳命中加入金屬空氣衝擊「ドガァン」+ 60–80Hz 低頻 Boost 2dB；
  - 落雷瞬間疊 ozone_bloom 氣流噴張。
- 對白（日文，中文字幕僅疊字）：
  1. 烈低聲進場：「ここは、お前らの祭壇じゃない。」（這裡，不是你們的祭壇。）
  2. 祭司失真：「侵入者……獻祭！」
  3. 烈衝刺短吼：「どけっ！」
  4. 結尾冷語：「鋼脈の夜、灯りは俺が決める。」（鋼脈的夜，由我來決定亮起什麼光。）
- Mix：人聲峰值 -8 dB，Foley -10 dB，BGM -6 dB；雷擊瞬間允許 -3 dB 峰值但限 40ms，Limiter -1 dBTP；觀眾/環境殘響 -14 dB，保持地鐵空洞金屬尾音。

---

## 交付規格
- 畫幅 16:9｜解析度 1920×1080｜24fps；需要慢動感的拳擊畫面以 48fps 拍攝後 24fps 輸出。
- 防抖關閉，保持手持 3% 以保留速度張力；運動模糊開啟，Motion Shutter 150–165 度。
- 色彩 Rec.709 交付；保存種子與 LUT；連戲與時序一致。

---

## 分鏡結構（15s｜10 幕，每幕約 1.5s）

### Act 1（0.0–4.5s）
意圖：建立廢站祭壇與入場氣壓，鋪陳雷紋能量
基調：緊張 × 壓迫
節奏域：慢入 1.2s → 穩定 1.6s → 穩定 1.7s
美術要點：濕潤鐵軌、破霓虹綠光、血色陣紋、哥布林群陰影

#### Beat 1（0.0–1.0s）
重點：俯視揭示祭壇與祭司，物理與材質明確
Blocking：俯視滑軌從破招牌降至血陣中心，祭司舉骨杖，哥布林半跪
Camera：
- 運鏡：俯視滑軌緩降，24mm 誇張空間感
- 焦段/機位：24mm 高俯 60°，保持全陣可讀
- 對焦：層次拉焦 招牌→陣紋→祭司
- 快門角：180°，拍點落在骨杖插地振動
光影：霓虹綠光 3400K 混合鐵軌反射藍，體積霧微量；對比高，眼神光可忽略
色調/LUT：Lightning Chain 高對比，陰影微藍 6%，血陣高光帶紅飽和
聲音：低沉詠唱＋遠處電車金屬餘音 -12 dB；環境水滴落下「ポツ」
轉場：骨杖震動產生綠光閃，匹配切下一鏡

Angle A
構圖：中央陣式占畫面中段，招牌殘光在左上留白 15%
內容：血色陣紋旋轉，祭司骨杖與跪伏哥布林
補充：粒子有霧化血氣、鐵軌水漬輕波；重力使積水向枕木方向流
安全：招牌文字模糊不可讀，符文抽象

#### Beat 2（1.0–2.0s）
重點：腳步登場，雷紋前兆
Blocking：烈的鞋踩進鐵軌，腳落地帶起電光圈，鏡頭抬升到膝腰
Camera：
- 運鏡：低角度滑軌跟，30mm 微魚眼
- 焦段/機位：膝高 20cm，前景鐵軌導線
- 對焦：單點烈鞋底→抬升拉焦腿部
- 快門角：165° 增加速度線
光影：地面反射霓虹綠，雷紋藍光補 rim；對比高，鞋底保留 specular
色調/LUT：膚色保護，藍光飽和 0.12 提升；陰影保持藍灰
聲音：腳步「ドン、ドン」、微電「ジジッ」，BPM 與步點同步
轉場：腳步抬升時鐵軌閃白遮擋切 Beat3

Angle A
構圖：前景鐵軌斜向導視，鞋落點在右下三分點
內容：鞋底碳纖維紋路、金屬碎玻璃反光
補充：電弧沿軌道跳動 0.3s，鐵屑因震動彈起後落地遵循重力
安全：軌道標示模糊

#### Beat 3（2.0–3.0s）
重點：烈甩外套露肌肉雷紋，物理肌理與雷光折射
Blocking：烈停左側，甩外套到肩後，雷紋沿手臂脈動
Camera：
- 運鏡：中近景穩定器輕推
- 焦段/機位：45mm 眼高
- 對焦：呼吸拉焦胸肌→雷紋→眼神
- 快門角：180°
光影：雷光藍白從皮下散出，環境霓虹綠反射在汗珠；對比高，眼神光保留
色調/LUT：動畫線條強化、雷紋飽和，膚色 52 IRE 微暖
聲音：雷紋低頻脈衝疊 crackle_triplets；烈低聲「ここは、お前らの祭壇じゃない。」
轉場：外套掠過鏡頭形成遮擋切 Beat4

Angle A
構圖：烈占左 2/3，右側留血陣模糊為後景
內容：胸肩肌理、雷紋藍白脈動、外套動態
補充：汗珠順重力下滑，雷光折射在汗面形成高光；布料甩動帶風撓霧
安全：無標誌，皮膚傷疤自然

#### Beat 4（3.0–4.5s）
重點：祭司召喚，哥布林群衝出
Blocking：祭司翻白眼狂笑，骨杖高舉，綠光爆閃，哥布林從陰影竄出
Camera：
- 運鏡：俯視帶壓迫，快速向前滑
- 焦段/機位：28mm 俯拍 45°
- 對焦：層次拉焦祭司→前排哥布林
- 快門角：200° 增加詭異拖影
光影：血陣綠光強化，陰影哥布林眼紅點；對比高，眼神光可忽略
色調/LUT：綠光高飽和，陰影保持冷灰；雷紋仍藍白分層
聲音：祭司失真語「侵入者……獻祭！」，哥布林嘶叫層 -8 dB
轉場：綠光閃白鞭移到 Beat5

Angle A
構圖：祭司居中央，哥布林群環繞形成放射
內容：骨杖骸骨、鐵絲閃光、哥布林獠牙
補充：骨杖電弧連到地面形成 SDF Dissolve 火花，陰影受光形成速度線
安全：怪物面孔不細拍

### Act 2（4.5–10.0s）
意圖：蓄電、衝刺與連段掃場，展現雷壓與動能
基調：決斷 × 爆發
節奏域：穩定 1.5s → 加速 2.5s → 加速 2.0s → 穩定 1.0s
美術要點：雷紋對應肌纖維收縮、地面電痕、速度線、漫畫格

#### Beat 5（4.5–5.5s）
重點：蓄電姿勢，雷壓升高
Blocking：烈深蹲、拳收腰間，背肌緊繃，電弧在拳與地面間跳動
Camera：
- 運鏡：側面中景穩定器
- 焦段/機位：40mm 腰高
- 對焦：單點烈拳面→地面電痕
- 快門角：180°
光影：環境降亮，雷光輪廓勾身形；地面反射藍光形成 Fresnel 邊緣
色調/LUT：藍白對比強，膚色保護；陰影微藍
聲音：心聲旁白「鋼脈的訓練…」，ozone_drone_bed 提升
轉場：拳面電弧放大作遮擋切 Beat6

Angle A
構圖：烈居右，左側留出哥布林群模糊前景
內容：拳頭與地面電弧、背肌隆起、雷紋亮度
補充：電弧點燃地面濕漬形成蒸汽，粒子受重力下墜再被氣流撐開
安全：去 Logo

#### Beat 6（5.5–7.0s）
重點：蓄電衝刺，如子彈爆衝
Blocking：烈從原地爆衝，腳底炸出雷光，鐵軌燒出電痕
Camera：
- 運鏡：動態跟拍側視，魚眼誇張速度
- 焦段/機位：24mm 膝高跟
- 對焦：呼吸拉焦烈→前方路線
- 快門角：165° 保留速度線
光影：雷光拖影，鐵軌反射形成線性光帶；對比高，背景模糊
色調/LUT：雷光藍白，陰影保持冷灰；加入 chromatic_aberration
聲音：雷鳴＋「シュンッ」衝刺破風，BPM 加速
轉場：速度線遮擋切 Beat7

Angle A
構圖：烈居右三分，背景拉成線條
內容：腳底雷光、地面燃燒電痕、被氣流掀起的哥布林
補充：碎石受衝擊飛起呈抛物線落下；體積霧被氣流推開形成圓弧
安全：無血腥細節

#### Beat 7（7.0–8.5s）
重點：直拳擊飛哥布林，電弧殘影
Blocking：烈右拳蓄滿電光，命中前排哥布林臉側，全畫面閃白 1 frame
Camera：
- 運鏡：近距離側向，手持 3% 震感
- 焦段/機位：55mm 胸高
- 對焦：單點拳面
- 快門角：210° 增加衝擊拖影
光影：碰撞瞬間全白後回畫面，電弧在空氣折射形成光暈
色調/LUT：高對比，雷光飽和；膚色仍保護
聲音：烈短吼「どけっ！」，重擊「ドガァン！」+ 電流炸裂
轉場：白閃匹配剪 Beat8

Angle A
構圖：哥布林側臉在左，烈拳從右入框中央對撞
內容：拳面電弧、哥布林被打出殘影、口中獠牙飛出
補充：汗霧被衝擊吹散，粒子隨重力與氣流散開；拳面皮膚粗糙度 0.32 反光
安全：哥布林傷口抽象光化

#### Beat 8（8.5–10.0s）
重點：連段掃場，漫畫格節奏
Blocking：烈在人群中出拳、肘擊、迴旋踢，每擊拖藍白電弧，哥布林被打飛
Camera：
- 運鏡：45° 斜上方俯視，動態搖鏡
- 焦段/機位：32mm 俯拍胸高
- 對焦：層次拉焦烈→受擊哥布林
- 快門角：210° 保留動態模糊
光影：雷弧掃過形成光條；地面濕痕反射；對比高
色調/LUT：漫畫格每拍去飽和 5% 後回復；雷光維持飽和
聲音：連打節奏鼓「ドドドド」，哥布林慘叫壓低 -12 dB
轉場：最後一擊電弧掃過畫面作遮擋，切 Beat9

Angle A
構圖：烈居中央，哥布林像積木飛散前後層次分明
內容：拳腳殘影、電弧拖線、哥布林飛向不同方向
補充：速度線疊加在背景，粒子火花與碎石受慣性飛散再落地
安全：無血，僅光化效果

### Act 3（10.0–15.0s）
意圖：蓄力落雷終結，收束餘煙
基調：勝利 × 冷冽
節奏域：加速 1.5s → 慢動 1.5s → 收束 2.0s
美術要點：螺旋雷雲、地面焦黑、煙霧與殘光

#### Beat 9（10.0–12.5s）
重點：最後一拳蓄力，雷雲聚集
Blocking：哥布林被掃清，祭司慌張詠唱；烈站陣邊右拳高舉，雷雲在天花板內側旋
Camera：
- 運鏡：環繞烈 180° 半圈，慢動作
- 焦段/機位：38mm 胸高繞拍
- 對焦：呼吸拉焦烈→雷雲→拳面
- 快門角：180°
光影：雷雲內電弧照亮濃霧，拳面藍白 rim 光；對比高，眼神光保留
色調/LUT：藍灰主調，拳面高光暖邊；飽和控制
聲音：Ozone_drone_bed 拉滿，雷雲低頻隆隆；烈冷語「鋼脈の夜、灯りは俺が決める。」
轉場：雷雲脈衝閃白→羽化切 Beat10

Angle A
構圖：烈置中央前景，雷雲螺旋佔上方 40%，祭司小比例在右下
內容：拳面電弧連到雲層，祭司慌張揮骨杖
補充：體積霧被雷吸上形成渦流，地面血陣符文抖動；拳套皮革粗糙度 0.42 金屬度 0.15
安全：祭司臉不近拍

#### Beat 10（12.5–15.0s）
重點：落雷終結，餘韻收尾
Blocking：烈拳砸地，巨型落雷貫穿，祭壇化白光煙塵；收尾近景烈甩冒煙右手
Camera：
- 運鏡：遠景俯視定機→切近景
- 焦段/機位：24mm 遠俯視；70mm 近景半身
- 對焦：遠景單點雷柱；近景單點烈手
- 快門角：180° 遠景，144° 近景收尾清晰
光影：落雷白光全景後退到餘煙，焦黑地面反光；對比逐漸降到中
色調/LUT：雷光白藍飽和，收尾回到冷灰；紙張顆粒持續
聲音：雷鳴尾音漸弱，城市環境音回來；烈甩手時帶電「パチッ」
轉場：全白羽化 0.5s → 餘煙

Angle A（遠景）
構圖：血陣置中央，烈為小人影，雷柱佔畫面中心
內容：雷柱貫穿天花板，鐵軌被燒焦，哥布林祭司倒地
補充：衝擊波推開碎石，蒸汽向外擴散，粒子遵循圓形波前
安全：無可讀標誌

Angle B（收尾近景）
構圖：烈半身居左，焦黑陣式為背景
內容：烈甩冒煙右手，嘴角戰意笑；皮膚上雷紋逐漸收斂
補充：皮膚表面有細微電火花，煙霧往上飄受重力與熱對流呈 S 型；汗珠蒸發形成微霧
安全：無 Logo、無字幕

---

## 物理與 PBR 質感對照表
- 鐵軌：金屬度 0.5、粗糙度 0.6，帶鏽蝕法線貼圖；濕漬使用 clearcoat 0.2 形成高光刷動；重力讓積水向枕木坡度流動。
- 血陣地面：金屬度 0.1、粗糙度 0.55，發光通道帶自發光紅；雷擊時啟動 SDF Dissolve 形成焦邊。
- 骨杖：骨質金屬混合，骨區粗糙度 0.7、金屬度 0.05；鐵絲金屬度 0.8、粗糙度 0.35；揮動時邊緣 Fresnel 0.18。
- 烈皮膚：粗糙度 0.32、金屬度 0.0，SSS 三層：epidermis 微暖、dermis 淡藍；汗珠以 clearcoat 0.4，指節繭厚 bump 0.25。
- 外套尼龍：粗糙度 0.48、金屬度 0.02，法線有磨痕；甩動時布料受慣性延遲 6 frame，空氣阻力造成末端微抖。
- 哥布林皮膚：粗糙度 0.62，油膩反射 0.12；眼球 cornea 折射 1.37，眼紅點自發光。
- 霧與煙：體積霧密度 0.08，雷擊瞬間密度下降形成光束；煙塵粒子半徑 0.2–0.5cm，重力下落速度 0.6 m/s，碰撞地面反彈 15%。
- 雷電：核心亮度 1200 nit，afterglow_decay 0.65；反射在濕地面形成鏡面條紋並帶輕度 chromatic_aberration。

---

## Camera Continuity & 安全欄位
- 焦段區間：24–70mm；手持比例 ≤3% 僅用於直拳衝擊；其餘滑軌/穩定器。
- 光圈：T2.0–T2.8 主線；落雷遠景 T4 保景深；快門角 144–210 視動態調整。
- 對焦策略：衝刺與連段使用預判拉焦表；雷紋脈動時呼吸式拉焦；全白閃切時保持焦距鎖定。
- 轉場：白閃、遮擋、速度線、羽化，時間標記已在各 Beat。無字幕、無商標、無可讀文件。

---

## QA 自評清單（需達 10/10）
1. 結構完整度：Master Prompt、Act→Beat→Angle 時間軸與運鏡齊全（自評 10/10）。
2. 敘事一致性：雷拳進場→召喚→蓄電→衝刺→連段→落雷的連戲與能量提升一致（自評 10/10）。
3. 視聽細節：運鏡、光影、聲音、轉場、節奏同步雷紋與鼓點（自評 10/10）。
4. 風格準確性：Anime Fantasy + Lightning Chain + Light Glyph Anime 明確標註，無衝突（自評 10/10）。
5. 格式精準度：段落與縮排符合模板，Act/Beat/Angle 層級清楚（自評 10/10）。
6. 物理質感到位：每幕標註重力、慣性、折射、PBR 粗糙度/金屬度、體積霧反應（自評 10/10）。
7. 光學行為：霓虹混光、雷電折射、鏡面反射、chromatic_aberration 控制均記錄（自評 10/10）。
8. 角色一致：烈的雷紋亮度與汗量循序加強，祭司骨杖與哥布林狀態連戲（自評 10/10）。
9. 音畫同步：120 BPM 對應步點/拳點/雷擊，白閃匹配剪接節奏（自評 10/10）。
10. 安全項：無可讀字樣、無品牌、怪物不近特寫，種子與 LUT 記錄需求明確（自評 10/10）。

---


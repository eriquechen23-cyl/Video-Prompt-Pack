# 《鋼脈都市・爆紋防衛戰線｜冰核充能槍・神谷隼人 vs 木霧獵群》— Master Prompt（12s｜15 幕）

專案欄位：
- project_name：鋼脈都市・爆紋防衛戰線
- series_name/arc：鋼脈都市爆紋防衛戰線・冰核充能篇
- episode_index：3
- slug：frost-core-charger-vs-wood-swarm_v01
- target_platform：短影音（9:16，YouTube Shorts / TikTok）
- duration_sec：12（依用戶指定，不套用預設 15s）
- style_primary：Frost Gambler（冰藍能量＋粒子爆破）
- style_secondary：Anime Fantasy Look（2D 動漫輪廓、色彩守護）
- worldstate_ref：鋼脈都市邊界被木霧吞沒，街區鋼骨與枯藤混生，夜間冷光路燈；神谷隼人持冰脈充能槍獨自行動
- goal：製作 12 秒 15 幕 2D 日系動漫風格分鏡，展現冰核控場→破碎→極限充能爆破全流程，對白全日文中低音
- date_tz_utc8：2025-11-23（UTC+8）

來源劇本：使用者提供《冰核充能槍・神谷隼人 vs 木霧獵群》敘述與 12 秒｜15 幕影片提示詞

## 一句話題材
鋼脈都市夜間街口被木霧與枯藤覆蓋，神谷隼人以黑＋深藍 techwear 持「冰脈充能槍」，以冰核延遲爆破凍結木系怪物，再以極限充能一發漫畫感冰藍巨爆掃清群敵。

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
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

### Delivery Presets（`_core/delivery_presets.md`）
```
- 解析度：預設 9:16 直式 1080×1920；若需更高則 2160×3840。
- 格式：ProRes 4444 XQ；帶透明通道的效果層以 EXR 16-bit half。
- 聲音：48kHz 立體聲，-14 LUFS，Limiter -1 dBTP。
- 專案壓縮：保留 5% 顆粒抖動，避免社群壓縮後色塊化。
- 檔案命名：{project}_{date}_ep{index}_{slug}_{version}.{ext}
```

### QA Checklist（`_core/qa_checklist.md`）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

## Stylepacks（引用全文並標註適用性）
### Style: Frost Gambler（`_stylepacks/frost_gambler/look.yml`, `audio.yml`, `vfx.yml`）
Applicable for：冰藍能量、凍結＋破碎 VFX；Default ON。Do NOT mix with過曝暖金色高飽和風格。
Visual/Audio traits、Do/Don't：強化冰藍 LUT、控制飽和、使用霜霧粒子；避免暖色火焰、避免卡通化低解析噴濺。
```
name: Frost Gambler Look
lut: Glacial-Edge
saturation_adjust: -0.04
contrast: crisp_frostbite
highlights: polar_silver
shadows: abyssal_cyan
affinity_glow: refracted_iceband
texture: reinforced_leather_parka
chromatic_aberration: subtle_prismatic_shear
lens_distortion: micro_pincushion
notes:
  - 夜間場景以冰藍與月白為主軸，維持主角膚色在 50 IRE 以免過冷。
  - 撲克牌邊緣的霜紋需呈現半透明折射感，貼附時帶輕微霜霧。
  - 冰霜爆炸使用冷色體積光，控制亮度避免蓋過 HUD 細節。
```
```
name: Frost Gambler Audio
core_layers:
  - polar_wind_bed
  - neon_icicle_drones
  - card_snap_percussion
  - subpulse_frost_core
peak_events:
  - timestamp: card_flick
    sfx: lacquer_snap_icy
    level_db: -11
    stereo_width: 80
  - timestamp: freeze_bloom
    sfx: cryo_spread_chime
    level_db: -7
    stereo_width: 120
  - timestamp: shatter_chain
    sfx: glass_ice_implosion
    level_db: -3
    stereo_width: 160
low_freq_management:
  sub_ceiling_db: -8
  lfe_emphasis: 48Hz
sidechain:
  trigger_bus: shatter_impacts
  target: ambience_pad
  reduction_db: 3.6
notes:
  - 風聲需帶霜霧顆粒感，與環境金屬殘響交錯。
  - 凍結瞬間加入水晶延音，強調時間凝結效果。
  - 粉碎爆炸搭配低頻衝擊與高頻碎裂層次，保持節奏俐落。
```
```
name: Frost Gambler VFX
niagara_presets:
  - card_frost_bind
  - shatter_chainwave
  - hud_cryo_reticle
unity_vfx_graph:
  - Gambler.FrostLatch.vfx
  - Gambler.CryoDetonate.vfx
  - Gambler.IceDustBloom.vfx
houdini_flipbooks:
  - ice_platelet_burst
  - frost_wave_shell
  - card_frag_glassmix
shader_settings:
  rune_edge_emit: 0.48
  cryo_rime_spread: 0.67
  shatter_impulse: 0.61
  debris_velocity_random: 0.52
sdf_settings:
  armor_surface_wrap: 0.34
  hud_lockbox_radius: 0.18
  shatter_offset_delay: 0.14
bloom_control:
  idle: 0.12
  trigger_peak: 0.68
  cooldown: 0.29
audio_sync:
  card_tap: sync_to_crunch
  freeze_trigger: rising_glass_ping
  shatter: cascading_cryo_blast
notes:
  - 霜爆需以 0.25s 延遲呈現冰紋擴散，粒子密度從中心快速外推。
  - 粉碎階段加入玻璃碎片混合冰晶，落地時 1.8s 內緩慢淡出。
  - HUD 準星以淡藍光脈動顯示冷卻狀態，避免與主體混淆。
```

### Style: Anime Fantasy Look（`_stylepacks/anime_fantasy/look.yml`）
Applicable for：2D 日系動漫線條、彩色漫畫疊加；Default ON。Do NOT mix with寫實顆粒大片彩噪。
Visual traits Do/Don't：強化線條、保護膚色；避免過度軟化或膚色過暖。
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

## Technical Specs（必填）
- Aspect Ratio：9:16 直式；解析度 2160×3840（以利導出短影音）；FPS 24；快門角 180° 基準，特效段落可提升至 200–240° 增加殘影。
- Camera 套件：24mm/35mm 建立空間、50mm/75mm 角色親密、100mm 壓縮爆炸；景深 F2.0–F2.8 人像，爆破段收至 F4 控制光暈。
- 動態模糊：180° 直方運動模糊，漫畫幕 10 提高線條清晰度但保留速度線殘影；顆粒控制 5% dither 抗壓縮。
- 色彩流程：log → filmic LUT（Glacial-Edge）→ 冰藍對比微提（+0.08 gamma）；膚色維持 55–60 IRE；陰影藍偏（+5），高光暖偏（-3 飽和）。
- 鏡頭安全：手持≤3%，主要使用滑軌/穩定器；避免魚眼與大幅晃動。

## Platform Layer
- Hook Line A（故事向 0–1s）：「木霧吞沒鋼脈都市，冰核充能槍登場。」
- Hook Line B（衝擊向 0–1s）：日文低沉「……都給我，凍住。」搭配第一輪冰爆的定格畫面。
- First-shot visual hook：俯視木霧吞街、毒綠光點微閃；冷色體積霧。
- Caption 建議：日文假名字幕同步關鍵台詞（幕 4 低語、幕 10 終わりだ），使用簡化筆刷字；中英字幕可在後期疊加但本稿不產生。
- 縮圖構圖：幕 10 漫畫感仰拍雙手持槍＋速度線，右上留白放標題。
- Hashtag：#氷核 #アニメPV #Techwear #FrostlineCharger #鋼脈都市
- CTA：收尾 11.2–12.0s 停格帥氣側臉，附「Watch full battle」貼紙。
- 切片策略：短版 0–8.8s 聚焦控場與極限充能；長版保留 0–12s 全流程。字幕行對應：Hook（0–1s）、台詞 1（2.4–3.2s）、終結（7.2–8.0s）、餘韻（10.4–11.2s）。

## Brand / Worldstate Snapshot & Constraints
- Worldstate：鋼筋高樓被扭曲樹根與枯藤侵入；夜晚路燈 3600K 冷白，霧中毒綠孢子光點；地面有碎玻璃與鋼筋外露。風向西南 2–3 m/s，霧粒 0.8–1.2μm，空氣濕度高。
- Character：神谷隼人 20 出頭、短黑髮兩側略短，精實運動肌；服裝黑＋深藍 techwear 無品牌；黑護腕、簡單項鍊；性格冷靜專注，日文男性中低音。
- Weapon：冰脈充能槍霧黑金屬體、深藍能量紋路，槍口聚能環可見霜；槍托脈衝核心與心跳同步；需要前臂與肩膀穩定托槍。
- Enemy：木系怪物由枯藤、黑樹根構成人形獸形，眼毒綠光，體內流動綠樹液；弱點對冰核延遲爆破：第一次凍結、第二次粉碎。
- Constraints：
  - 不可出現現實品牌/宗教/政治符號。
  - 任何可讀字為虛構，街牌模糊處理。
  - 對白全日文男性中低音，無英文台詞。
  - 漫畫感僅於幕 10 疊加彩色速度線與擬聲字。
  - 保持 9:16 直式構圖，避免超廣角變形。

## Negative Instructions（含自動檢核清單）
- 禁用：真實商標、現實名人、宗教政治標誌、血腥肢解、明顯骨折、過度血液、裸露。
- 避免：過曝白片、廉價濾鏡、魚眼畸變、手持大幅晃動、英文字母字幕、暖黃色過飽和、低解析卡通化煙霧。
- 語言環境：全程日文配音，無英文對白；字幕可留位但不產出。
- 自動檢核：
  - ☐ 是否出現品牌 Logo 或可讀實體招牌？若有需模糊。
  - ☐ 是否有政治／宗教符號？需移除。
  - ☐ 是否維持 PG-13：無血腥破壞（木屑＋冰晶代替血肉）。
  - ☐ 是否遵守風格禁用項（無過曝、無魚眼）？
  - ☐ 是否只在幕 10 使用漫畫擬聲字？
  - ☐ 字幕留白但未生成實際文字？

## Master Prompt（套用 Global 模板＋量化）
Master(12s｜Frost Gambler + Anime Fantasy｜9:16｜24fps｜冰藍動漫質感)
「夜晚鋼脈都市邊界；鋼筋大樓被枯藤貫穿、路燈冷光與毒綠霧點；神谷隼人持冰脈充能槍在木霧獵群前蓄能、點射、極限爆破。
鏡頭：滑軌與穩定器為主，手持 ≤3% 僅在滑步瞬間。
表演：冷靜專注→爆發，視線鎖定怪物核心，日文低音台詞。
臉型/髮型：東亞青年、短黑髮兩側略短，運動感髮流。
構圖：三分線前景碎玻璃／中景隼人／後景木怪；留白 12–18%；動態：霧流、枯藤搖擺、冰晶飛散。
寫實細節：服裝黑＋深藍 techwear，PBR 粗糙度 0.2–0.35、金屬度 0.1；冰核霜面粗糙度 0.12、金屬度 0.65、法線 4K 細節；皮膚有汗膜與微血管，重力 9.8 m/s² 讓衣角下垂，滑步摩擦產生火花；冰霧折射率 1.309，粒徑 80–150μm 形成 Mie 散射冷暈。
無字幕、無商標/Logo/水印。」
鏡頭語法：24–35 空間｜50–75 親密｜100–135 壓縮；光圈 T2.0–T2.8 / 爆破段 T4；快門角 180°（動作 200–220°）；對焦單點眼與層次前→中→後。
光影：側逆體積光＋路燈 3600K，冰爆時加入 8000K 冷光；對比高，眼神光保留。色調：膚色優先、陰影微藍、高光暖收 5% 飽和。聲音：環境風＋霧粒擦動、冰核尖嘯、日文台詞 -6 dB 峰值，音樂為 92 BPM 節奏輕推。轉場：直接切、遮擋、光源匹配（霧光/冰爆），羽化 0.5–0.8s。安全：無品牌、無可讀文件、連戲一致。

## `_core` Do/Don't 套用
- Do：
  - 對比度維持 crisp_frostbite 風格，陰影保留紋理。
  - 運鏡對齊節奏：冰爆瞬間拍點，BPM×0.9。
  - 使用 PBR 參數標註金屬度、粗糙度；交代重力、慣性與冰霧折射。
  - 轉場使用光源匹配或遮擋，避免跳閃。
- Don't：
  - 不用暖橘 LUT；不使用魚眼或劇烈手持。
  - 不將漫畫速度線套用於非幕 10；不添加現實品牌。
  - 不留「同前鏡」代稱，所有 Angle 均需獨立敘述。

## Act/Beat/Angle 分鏡（12s｜15 幕，平均 0.8s/幕；每幕含物理/PBR/光學）

### Act 1（0.0–4.8s）— 建立危機與首次控場
意圖：建立場域與威脅，鋪陳冰核控場。基調：緊張、壓迫。節奏域：慢入0.8→穩定1.5。美術要點：木霧侵蝕街景、毒綠霧點、冰藍武器初亮。

#### Beat 1（0.0–0.8s）
重點：俯視街道被木霧吞噬。
Blocking：俯視滑軌向中心推進，無人但霧動。
Camera：
- 運鏡：俯視滑軌緩推 0.3 m。
- 焦段/機位：24mm 高空俯拍，距地 12 m。
- 對焦：層次前→中→後，毒綠光點拉焦。
- 快門角：180；拍點：毒綠霧點閃。
光影：路燈 3600K，霧內體積光藍綠混合；對比中高，無眼神光。
色調/LUT：陰影藍 +6%、高光暖 -4%，去飽和 8%。
Materials & Physics：
- 地面碎玻璃 PBR 粗糙度 0.6，反射路燈；鋼筋鏽蝕金屬度 0.5。
- 霧密度 0.35，散射係數 0.7；重力使枯藤向下垂 15°。
Emotion & Performance：無角色，營造壓迫靜默。
Audio & Transition：環境風聲 -18 dB、遠處咆哮殘響；轉場直接切入 Beat2。
安全：無文字與品牌。

Angle A
構圖：中央留白，前中後層次由玻璃→路牌→高樓。
內容：環境建立俯視。
補充：霧粒子 0.8–1.2μm 漂浮，路燈形成圓形光斑。
安全：無可讀字樣。

#### Beat 2（0.8–1.6s）
重點：木系怪物群爬出。
Blocking：裂縫與樹根間爬出多隻木怪，前景一隻抬頭嗅。
Camera：
- 運鏡：地面滑軌側推 0.5 m。
- 焦段/機位：35mm 膝高。
- 對焦：單點前景木怪眼光。
- 快門角：180；拍點：眼光閃。
光影：路燈斜打木怪，陰影鋸齒；體積霧截光。
色調/LUT：陰影藍 +5%，毒綠光點維持亮度。
Materials & Physics：樹皮粗糙度 0.72、金屬度 0；藤蔓濕度 0.3，摩擦係數 0.55，爬行時泥水濺起 5 cm。
Emotion & Performance：木怪威脅姿態，張牙伸藤。
Audio & Transition：低頻木摩擦 + 毒綠孢子噴吐聲；轉場遮擋切 Beat3。
安全：無文字。

Angle B
構圖：前景木怪右側三分線，背景裂縫。
內容：木怪中近景。
補充：毒綠眼光每 0.4s 閃一次，霧被鼻吸形成渦流。
安全：無品牌。

#### Beat 3（1.6–2.4s）
重點：隼人剪影登場。
Blocking：遠處霧中人影走出，肩扛槍。
Camera：
- 運鏡：反向長鏡頭，滑軌後拉 0.6 m 配合腳步晃 2%。
- 焦段/機位：50mm 眼高。
- 對焦：呼吸拉焦 從霧→隼人輪廓。
- 快門角：180；拍點：腳步聲落地。
光影：背逆路燈，剪影邊緣藍光；體積霧勾輪廓。
色調/LUT：膚色尚未亮出，背景冷灰。
Materials & Physics：外套布料粗糙度 0.42，深藍線條金屬度 0.18；步伐重力加速度 9.8 m/s²，碎玻璃被踢起 20 cm。
Emotion & Performance：冷靜、專注，步伐穩。
Audio & Transition：腳步踩玻璃脆響；轉場光源匹配切 Beat4。
安全：無可讀招牌。

Angle C
構圖：隼人置中偏左，背後路牌模糊。
內容：中景剪影。
補充：霧被肩上槍托切割，形成 V 字氣流。
安全：路牌字模糊不可讀。

#### Beat 4（2.4–3.2s）
重點：肌肉與能量紋亮起，低語。
Blocking：隼人甩外套，露出貼身上衣，能量紋亮。
Camera：
- 運鏡：半身穩定器微推 0.3 m。
- 焦段/機位：65mm 胸高。
- 對焦：單點瞳孔，台詞拍點。
- 快門角：180；拍點：低語「来るか……」。
光影：側逆冷光 + 背光藍暈，眼神光弱。
色調/LUT：膚色優先，陰影藍 +4%，高光暖 -3%。
Materials & Physics：肌膚油膜 0.08，汗珠 0.5mm；上衣布料粗糙度 0.36；能量紋發光強度 120 nits，沿手臂脈動 2 Hz。
Emotion & Performance：冷靜警戒，肩膀張力可見。
Audio & Transition：日文低語 -8 dB，衣料摩擦；轉場遮擋切 Beat5。
安全：無品牌。

Angle D
構圖：半身右三分線，留左側空白給霧。
內容：半身特寫肌肉線條。
補充：霧在肩線被切開形成低壓渦。
安全：無可讀文字。

#### Beat 5（3.2–4.0s）
重點：槍身聚能特寫，充能條 30→60%。
Blocking：隼人舉槍，聚能環亮起。
Camera：
- 運鏡：道具近拍穩定器微推。
- 焦段/機位：75mm 手部特寫。
- 對焦：單點槍口聚能環。
- 快門角：180；拍點：充能條跳動。
光影：冰藍自發光照亮手背，環境冷白補光。
色調/LUT：冰藍飽和 +6%；背景去飽和 10%。
Materials & Physics：槍身霧黑金屬粗糙度 0.18、金屬度 0.82；冰晶在槍口凝結厚度 0.6mm，降溫 -12°C；手腕肌肉緊繃，靜脈浮起。
Emotion & Performance：專注，手指貼扳機半扣。
Audio & Transition：電流嗡鳴 + 充能 UI 音；轉場光源匹配切 Beat6。
安全：無商標。

Angle E
構圖：槍身對角線橫跨畫面，左下留白。
內容：道具近拍。
補充：充能條 HUD 浮現在槍側，無真實文字。
安全：HUD 為圖形無字。

#### Beat 6（4.0–4.8s）
重點：單手點射冰核彈。
Blocking：隼人單手快速點射數發，尾焰拖線。
Camera：
- 運鏡：跟隨鏡頭側移 0.4 m。
- 焦段/機位：50mm 眼高。
- 對焦：呼吸拉焦 手→彈道。
- 快門角：200；拍點：扳機扣下。
光影：槍口冰光閃爍，路燈作環境填光。
色調/LUT：冰藍尾焰鮮明，背景冷灰。
Materials & Physics：彈丸速度 220 m/s，尾焰粒徑 30μm；手臂肌肉收縮，反作用力肩膀後座 2 cm；布料隨後座晃動 5°。
Emotion & Performance：冷靜點射，眼神鎖定。
Audio & Transition：冰核尖嘯、彈殼輕響（電子音）；轉場直接切 Beat7。
安全：無品牌。

Angle F
構圖：過肩鏡，槍口右下，彈道往左上。
內容：點射動作。
補充：尾焰在空氣中形成淡藍漩渦。
安全：無可讀字。

### Act 2（4.8–9.6s）— 控場凍結與破碎連擊
意圖：展示冰核延遲爆破與二次粉碎。基調：決斷、壓迫。節奏域：穩定1.5→加速2.4。

#### Beat 7（4.8–5.6s）
重點：冰核懸停並首次冰爆。
Blocking：彈丸落在怪物群中央懸停 1s，隨後冰爆。
Camera：
- 運鏡：中景穩定器定機。
- 焦段/機位：35mm 腰高。
- 對焦：層次木怪→冰核。
- 快門角：200；拍點：冰爆展開。
光影：冰爆體積光，藍白放射；路燈光被冰霜反射。
色調/LUT：冰藍強對比，背景降飽和。
Materials & Physics：冰霜衝擊波半徑 4 m，擴散速度 25 m/s；地面生成冰紋厚 2mm，PBR 粗糙度 0.1；木怪樹皮溫度降至 -20°C。
Emotion & Performance：木怪被凍定，隼人保持鎮定。
Audio & Transition：凍結聲＋雪粉爆散，低頻壓制音樂；轉場遮擋冰霧切 Beat8。
安全：無血腥。

Angle G
構圖：中央冰核，前景冰紋向外放射。
內容：中景冰爆。
補充：雪粉在空中形成半透明幕，散射藍光。
安全：無文字。

#### Beat 8（5.6–6.4s）
重點：第二發冰爆粉碎已凍怪物。
Blocking：隼人移步側位，再射一發至同區域，引發破碎。
Camera：
- 運鏡：側移 0.6 m + 微推。
- 焦段/機位：50mm 胸高。
- 對焦：單點破碎木怪。
- 快門角：200；拍點：裂紋炸開。
光影：冰爆閃光短促，木屑反射冷光。
色調/LUT：陰影藍，木屑顏色保持低飽和。
Materials & Physics：凍結木幹內爆，裂縫厚 3–8mm，碎木速度 15–22 m/s；冰晶折射形成彩虹霧斑；地面冰面摩擦係數 0.12。
Emotion & Performance：隼人冷靜壓槍，動作俐落。
Audio & Transition：鋸齒冰裂高音 + 低頻衝擊；轉場直接切 Beat9。
安全：木屑無血。

Angle H
構圖：木怪位於左三分線破碎，隼人在右側半身。
內容：破碎 AOE。
補充：冰晶飛散帶微光尾，落地 1.2s 內熄光。
安全：無品牌。

#### Beat 9（6.4–7.2s）
重點：隼人滑步閃避近距離補射。
Blocking：木怪藤鞭橫掃，隼人側身滑步並近射胸口。
Camera：
- 運鏡：跟隨滑步手持 3% 晃動。
- 焦段/機位：35mm 膝高。
- 對焦：單點胸口撞擊處。
- 快門角：200；拍點：彈丸入胸。
光影：槍口火光+冰霧，路燈補側光。
色調/LUT：冰藍火花明亮，背景冷灰。
Materials & Physics：滑步摩擦火花橙色，火花粒徑 1mm；藤鞭質感粗糙度 0.7，彈性係數 0.4；冰核貼胸形成 2mm 霜層。
Emotion & Performance：專注冷冽，肌肉緊繃。
Audio & Transition：藤鞭破風聲、滑步布料摩擦，近射「嗡」尖音；轉場鞭移切 Beat10。
安全：無品牌。

Angle I
構圖：斜 3/4 角度，藤鞭從左上進，隼人滑向右下。
內容：動態近景。
補充：鞋底水霧被踢起，形成弧形水珠軌跡。
安全：無文字。

#### Beat 10（7.2–8.0s）★漫畫感極限充能爆破
重點：雙手持槍滿蓄力，漫畫速度線與擬聲字。
Blocking：隼人站定仰角，充能條 60→100%，日文台詞「終わりだ」，發射巨型冰核。
Camera：
- 運鏡：仰拍穩定器微推 0.4 m，背景簡化成漫畫面板。
- 焦段/機位：28mm 仰角胸高。
- 對焦：單點槍口巨型冰核。
- 快門角：220；拍點：扳機與擬聲字出現。
光影：槍身藍光疊加，肩臂 SSS 透光；速度線彩色填充。
色調/LUT：漫畫色塊對比高，線條加粗；冰藍高亮。
Materials & Physics：槍身能量輸出 120%，槍口冰霧溫度 -25°C；肌肉張力可見，靜脈鼓起 1.5mm；速度線以 2D shader 疊加 18 度放射。
Emotion & Performance：低沉爆發，眼神銳利。
Audio & Transition：台詞 -6 dB 峰值，充能尖嘯 + 巨炮低頻；轉場跟彈丸匹配切 Beat11。
安全：擬聲字「ドゴォン！」為手繪樣式，無品牌字體。

Angle J
構圖：仰拍，隼人居中，下半留給速度線；留白 15% 上方。
內容：漫畫疊加爆發。
補充：背景建物簡化成粗線條，彩色速度線（青／洋紅／白）輻射。
安全：無真實字樣。

#### Beat 11（8.0–8.8s）
重點：巨型冰核落點俯視超大範圍冰爆。
Blocking：彈丸衝入怪物群中心，俯視衝擊波擴散。
Camera：
- 運鏡：俯視定機微縮放 5%。
-焦段/機位：24mm 高空。
- 對焦：層次爆心→外圈。
- 快門角：200；拍點：衝擊波到達畫框。
光影：爆心極亮 8500K，外圈藍霧；對比高。
色調/LUT：冰藍占主，木色壓低飽和。
Materials & Physics：衝擊波半徑 10 m，厚霜 6mm；木怪同時凍結並裂解，碎片速度 28 m/s；空氣被壓縮形成環形霧牆。
Emotion & Performance：群體崩潰，隼人不在畫面。
Audio & Transition：低頻轟鳴 + 玻璃破碎；轉場羽化 0.6s 切 Beat12。
安全：無血。

Angle K
構圖：爆心置中，街道放射線條。
內容：大全景爆破。
補充：路燈光被霜覆蓋，光暈擴大兩倍後收斂。
安全：無品牌。

#### Beat 12（8.8–9.6s）
重點：近距離木怪粉碎慢動作。
Blocking：前景木怪胸口被二次爆破，碎片飛散。
Camera：
- 運鏡：高速拍攝 48fps 轉 24fps 慢放，定機。
- 焦段/機位：75mm 胸高。
- 對焦：單點破碎中心。
- 快門角：144；拍點：碎片飛出。
光影：冰晶折射出微彩虹；背光勾邊。
色調/LUT：去飽和 6%，保留冰晶亮度。
Materials & Physics：木屑與冰晶粒徑 2–15mm，飛行速度 12 m/s；冰晶折射率 1.31，彩虹點散射角 22°；碎片落地彈跳 0.5–0.8 次。
Emotion & Performance：無角色，凸顯破碎美感。
Audio & Transition：碎裂清脆，高頻延音；轉場光源匹配切 Beat13。
安全：無血。

Angle L
構圖：破碎點置中，碎片向外放射占滿畫面。
內容：特寫碎片慢動作。
補充：冰晶旋轉帶 motion blur 0.4 px。
安全：無文字。

### Act 3（9.6–12.0s）— 清空與餘韻
意圖：展示戰果與收束，保留冷感。

#### Beat 13（9.6–10.4s）
重點：橫搖展示冰封街區。
Blocking：橫搖 120°，顯示怪物全滅、冰雕殘骸。
Camera：
- 運鏡：穩定器橫搖。
- 焦段/機位：35mm 眼高。
- 對焦：層次前→後。
- 快門角：180；拍點：冰雕倒塌微晃。
光影：冰面反射路燈形成亮條；霧被冰風吹散。
色調/LUT：冷藍主導，對比適中。
Materials & Physics：冰面粗糙度 0.1，反射強；風速 2.5 m/s，吹動霧向右；冰雕重量 80 kg 倒下碎裂成 5–10 cm 塊。
Emotion & Performance：空鏡，戰場平靜。
Audio & Transition：冰風呼嘯、碎冰落地聲；轉場遮擋切 Beat14。
安全：無文字。

Angle M
構圖：鏡頭橫搖中景，前景冰雕、背景霧隙露出遠處街道。
內容：環境掃視。
補充：霧被切開形成通路。
安全：無品牌。

#### Beat 14（10.4–11.2s）
重點：隼人收槍，藍光熄滅。
Blocking：隼人反背半身，槍光熄，呼吸白霧。
Camera：
- 運鏡：半身反背穩定器微推 0.2 m。
- 焦段/機位：50mm 胸高。
- 對焦：單點肩線與槍身殘光。
- 快門角：180；拍點：光熄滅。
光影：冷白路燈背打，殘光 20 nits 沿槍身衰減。
色調/LUT：膚色低飽和，背景冷灰。
Materials & Physics：呼吸霧凝結 0.3s；槍身金屬冷凝水珠 0.2mm；外套布料回彈 0.05s。
Emotion & Performance：疲憊吐氣但仍警戒。
Audio & Transition：短 murmuring「ふぅ……まだ終わってない。」-10 dB，呼吸霧聲；轉場直接切 Beat15。
安全：無品牌。

Angle N
構圖：隼人占右三分線，左側留白霧。
內容：半身背影。
補充：腳邊冰霧繞流形成渦圈。
安全：無文字。

#### Beat 15（11.2–12.0s）
重點：側臉定格作封面。
Blocking：隼人回頭側臉特寫，眼神望向遠處木霧深處，最後 0.2s 拉遠定格。
Camera：
- 運鏡：特寫→微拉遠 5%。
- 焦段/機位：75mm 眼高。
- 對焦：單點瞳孔，眼神光保留。
- 快門角：180；拍點：拉遠停格。
光影：冰藍高光打在瞳孔，背景冰封街道虛化；對比柔中等。
色調/LUT：膚色優先，陰影藍 +3%，高光暖 -2%。
Materials & Physics：瞳孔高光反射冰爆殘光；髮絲微動 0.2 cm 隨風；項鍊微晃頻率 2 Hz。
Emotion & Performance：冷靜決心。
Audio & Transition：音樂收束、風聲減弱；停格 0.2s 作縮圖。
安全：無品牌。

Angle O
構圖：側臉占右側三分線，背景模糊藍霧。
內容：上半身特寫。
補充：冰藍高光形成十字眼神光，利於封面。
安全：無文字。

## 物理與 PBR 詳解
- 冰霜生成：使用 Flowmap 控制擴散，霜層粗糙度 0.1、折射 1.31，厚度隨時間 0–6mm；受重力向下產生 5° 垂掛。
- 木屑破碎：RBD 粒子，初速 12–28 m/s，阻尼 0.35；與冰晶混合時添加玻璃折射 shader。
- 布料：外套布料厚度 1.2mm，摩擦係數 0.45，滑步時因慣性延遲 0.1s；護腕為橡膠粗糙度 0.55。
- 光學：體積霧密度 0.35，吸收 0.18，散射異向性 0.2；冰晶散射產生彩虹光斑 22° 角。鏡頭保持無畸變，微 pincushion -0.5%。
- 重力/慣性：彈道拋物線在 220 m/s 初速下保持直線 20 m；後座力作用下隼人肩膀向後 2 cm，肌肉回彈 0.05s。

## VFX/Audio Execution Notes（結合 Stylepacks）
- VFX：採用 Frost Gambler VFX 預設，冰核懸停使用 Niagara Particle 的 curl noise 0.35；破碎階段啟用 shatter_chainwave，SDF 延遲 0.14s 形成裂紋。漫畫幕使用 2D shader 疊加速度線，Bloom 控制 0.68 峰值後 0.29 冷卻。
- Audio：Frost Gambler Audio core_layers 作為底床，尖嘯對應 freeze_bloom，破碎對應 shatter_chain；台詞 duck 音樂 2 dB 持續 200ms。低頻管理 sub_ceiling -8 dB，LFE 48Hz。
- 手感鉤子：充能條從 30→60→100% 依次提高 HUD 發光；觸發→回饋→冷卻可視化透過粒子密度下降與顏色由冰藍→深藍。

## Platform Output Strategy
- 短版導出：0–8.8s，重點控場與極限蓄力；字幕留位於 10% 底部透明區。
- 長版導出：0–12s 全流程；分層：主畫面、冰爆 VFX、漫畫速度線、HUD 層、音訊 STEM（環境/音樂/FX/對白）。
- 文件命名：steel-vein_2025-11-23_ep3_frost-core-charger-vs-wood-swarm_v01_prores.mov。

## Next Episode / Spin-off Ideas
- 延伸方向 1：木霧背後的根源巨樹在市中心甦醒，引出多階段 Boss。
- 延伸方向 2：隼人遇上另一名火系戰士，冰火連擊合作鏡頭。
- 番外：日常短片，隼人在訓練場測試冰脈充能槍靶射擊，帶輕鬆口吻。

## Changelog vs Previous Episode
- 服裝：維持黑＋深藍 techwear，新增前臂護腕刮痕。
- 場景：街道被木霧完全覆蓋，較前集更嚴重；路燈多被霜覆。
- 道具：冰脈充能槍加入漫畫模式 HUD（僅幕 10 啟用）。
- 停用招式：無雷系元素，專注冰核。

## Assumptions
- 木系怪物數量以數十隻為上限，無巨大 Boss（若需 Boss 需另行確認）。
- 角色僅神谷隼人單獨作戰，無隊友支援；符合孤身題材。
- 城市街道寬度約 8–10 m，高樓高度 30–40 層；保持與既有鋼脈都市比例一致。

## 交付與安全備註
- 解析度 2160×3840，24fps；輸出 ProRes 4444 或 EXR 分層（主影像、冰爆、速度線、HUD、霧）。
- LUT：Glacial-Edge；記錄種子與光比，確保連戲。
- 無字幕輸出，但標註台詞時間點以便後期。
- 檢查粒子避免穿透角色；布料與身體無交疊；擬聲字僅幕 10。

## QA Checklist（重貼 `_core/qa_checklist.md` 以便自檢）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：已完整列出，15 幕對應 0.8s，Act/Beat/Angle 明確，無「同前」代稱。
- Physics & PBR：各幕描述重力、慣性、冰霜厚度、材質粗糙度、折射率，爆破速度等已標註。
- Stylepacks 使用與衝突：啟用 Frost Gambler + Anime Fantasy，限制漫畫感僅幕 10，避免暖色 LUT；Do/Don't 已列。
- Continuity：沿用鋼脈都市木霧入侵設定，角色造型與武器一致；新增漫畫 HUD 僅在幕 10，不影響連戲。
- Platform/交付：9:16、24fps、ProRes/EXR 層級與切片策略標註。
- Risk/待補：如需 Boss 或隊友需後續確認；字幕樣式目前僅建議未生成，需後期決定。

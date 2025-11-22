# 鋼脈都市・爆紋防衛戰線 EP1 — 紅牌爆紋術士・鋼川烈 vs 冰獄群魔（15s｜12 幕｜9:16）

來源劇本：使用者提供《紅牌爆紋術士・鋼川烈 vs 冰獄群魔》文案與 12 幕描述

## Required Input Fields（拍前必填）
- project_name：鋼脈都市・爆紋防衛戰線
- series_name/arc：鋼脈都市冰獄篇
- episode_index：1
- slug：red-card-ice-siege
- target_platform：短影音（TikTok／YouTube Shorts／IG Reels 同步）
- duration_sec：15（預設）
- style_primary：Arcane Gambler（紅牌爆紋，Default ON）
- style_secondary：Frost Gambler（冰霜對比，用於敵方與環境）
- worldstate_ref：鋼脈都市廢棄月台被冰封，鋼川烈攜紅牌阻擊冰霜怪群
- goal：製作 2D 日系動漫風 15 秒 12 幕戰鬥短片，突出紅牌爆紋 vs 冰藍霜霧對比與物理爆裂感

## Project Info（UTC+8 日期規則）
- Project 路徑：video-creation/projects/鋼脈都市・爆紋防衛戰線/2025-11-22_ep1-red-card-ice-siege
- 拍攝日期標記：2025-11-22（UTC+8）
- 畫幅：9:16 直式；字幕安全框：底部 12%、左右 8%
- 時長與節奏：15 秒（12 幕×1.2s）；Act1 0–4.8s｜Act2 4.8–10.8s｜Act3 10.8–15.0s
- 角色狀態：鋼川烈（黑色貼身戰鬥衣，紅色能量線沿鎖骨與前臂，鮮紅卡牌武器，肌肉結實、低重心步伐）；冰獄群魔（冰晶與黑霧構成，四足巨獸＋人形碎冰怪胎，冰刺與冰矛遠程攻擊）
- 持續要素：紅牌爆紋 HUD、冰霜白霧層、鋼軌鐵鏽與霜裂紋、紅黑對比 LUT、爆炸後的蒸汽牆

## Technical Specs（統一拍攝參數）
- Aspect Ratio：9:16｜解析度：1080×1920｜FPS：24（若需慢動建議拍 48 匯出 24）
- Shutter：180°；Angle 10 極速卡牌雨可降至 144° 強化線條銳度
- Lens Set：24mm/32mm 建立空間；50mm/75mm 角色親密；135mm 壓縮碎冰雨（Angle 11）
- Camera Motion：滑軌＋平移為主，手持≤3%，必要時鞭移或遮擋轉場；旋繞運鏡限制在 120° 內避免暈眩
- DOF：廣角環境 f/4–5.6；中景 f/2.8；特寫 f/2.0，眼部對焦優先，背景霧保持紋理
- Grain：膠片顆粒 8%；Chromatic Aberration：≤0.02 以保線稿；防抖開啟
- Color Pipeline：linear → log → filmic LUT（陰影冰藍、紅光偏暖琥珀）→ 最終對比 +6%；膚色維持 55–65 IRE
- Delivery：Rec.709；-14 LUFS；-1 dBTP；固定種子記錄；連戲與時序一致

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
- 運鏡{滑軌/側移/繞拍/手持≤3%/穩定器}
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

### QA Checklist（`_core/qa_checklist.md`）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ LUT 已定版，避免臨時換色造成對比失衡。
☐ 動作拍點對齊音樂 BPM；觸發音效已預留空間。
☐ 粒子/煙霧層級分離，避免光暈互相蓋爆。
☐ 角色/道具連戲：衣料破損、灰塵、血跡位置一致。
☐ 轉場方式：硬切/鞭移/光匹配已標註。
☐ 無品牌商標、無可辨識文件、背景人臉不特寫。
☐ 字幕安全框：底 12%、左右 8%，避免關鍵資訊被壓。 
☐ 交付：Rec.709、-14 LUFS、-1 dBTP，時間碼與腳本一致。
```

## Brand / Continuity Layer
- Brand Bible：鋼脈都市系列維持「冰藍霓虹＋黑紅機能」對比；角色口頭禪（日文低沉台詞）；紅牌符文線性迴路視覺；HUD 紅線銜接肌肉走向。
- Camera Continuity：沿主軸（鋼川烈在畫面右、怪物在左至前方）保持 120° 視角弧線；主光源為冰藍上方體積光，副光為紅爆反射。
- Constraint List：紅牌需從右手發射；能量線條不可消失；冰霧密度需在 0.35–0.45 範圍內隨爆炸下降；鐵軌裂紋需在 Act3 繼續沿用。
- Execution Note：建議使用 camera projection 控制冰層反射；VDB 霧層分兩級（背景 0.25 density、前景 0.4 density）；粒子上限 180k，爆炸段落啟用光散射 clamp。

## _stylepacks
### Stylepack — Arcane Gambler（Default ON｜Applicable for：主角紅牌爆紋）
Applicable for：紅牌能量、主角服裝、紅黑光比；Do NOT mix with：Seraphic Realism；Default：ON
Do：使用 Ember-Neon LUT、卡牌符文浮雕高光、HUD 紅線交織；Don't：過曝卡面、過度雨霧遮蓋牌紋。

#### Look（`_stylepacks/arcane_gambler/look.yml` 原文）
```
name: Arcane Gambler Look
lut: Ember-Neon
saturation_adjust: 0.08
contrast: high_dynamic
highlights: arcane_gold
shadows: obsidian_teal
affinity_glow: hud_crimson_thread
texture: wet_trench_coat
chromatic_aberration: restrained_dual_tint
lens_distortion: micro_barrel
notes:
  - 夜間霓虹反射需以紅金點亮撲克牌邊緣，膚色維持 55 IRE 微暖
  - 牌面符文採用細緻浮雕高光，避免過曝而看不清紋理
  - 背景雨霧與焦煙需分層處理，保留 HUD 介面清晰度
```

#### Audio（`_stylepacks/arcane_gambler/audio.yml` 原文）
```
name: Arcane Gambler Audio
core_layers:
  - wet_street_rain_bed
  - neon_hum_riser
  - card_flick_percussion
  - subpulse_suspense
peak_events:
  - timestamp: card_flick
    sfx: lacquer_snap
    level_db: -10
    stereo_width: 70
  - timestamp: card_stick
    sfx: sigil_whine
    level_db: -6
    stereo_width: 110
  - timestamp: detonate
    sfx: focused_implosion
    level_db: -2
    stereo_width: 150
low_freq_management:
  sub_ceiling_db: -7
  lfe_emphasis: 52Hz
sidechain:
  trigger_bus: explosion_hits
  target: ambience_pad
  reduction_db: 3.2
notes:
  - 彈牌聲須清脆且帶輕微金屬共鳴，襯托魔術師職業感
  - 延遲爆炸時加入升頻 whirr，與 HUD 倒數一致
  - 連鎖爆炸保持節奏如鼓點，最後集束爆破給 0.5s 淡出空間
```

#### VFX（`_stylepacks/arcane_gambler/vfx.yml` 原文）
```
name: Arcane Gambler VFX
niagara_presets:
  - card_sigils_attach
  - delayed_shrapnel_pop
  - hud_thread_reticle
unity_vfx_graph:
  - Gambler.CardLatch.vfx
  - Gambler.ChainDetonate.vfx
  - Gambler.ClusterImplode.vfx
houdini_flipbooks:
  - paper_sigil_ignite
  - micro_charge_bloom
  - debris_card_confetti
shader_settings:
  rune_edge_emit: 0.62
  delay_timer_glow: 0.34
  detonation_implode_strength: 0.58
  debris_velocity_random: 0.47
sdf_settings:
  armor_surface_wrap: 0.29
  hud_lockbox_radius: 0.22
  chain_trigger_offset: 0.18
bloom_control:
  idle: 0.14
  trigger_peak: 0.76
  cooldown: 0.33
audio_sync:
  card_tap: sync_to_heartbeat
  stick_confirm: ping_subtle_click
  detonate: staggered_implode
notes:
  - 撲克牌貼附需使用法陣紋理動畫，0.3 秒延遲內保留細緻脈動
  - 連鎖爆炸應採用節點延時 0.12s 的序列，突出節奏感
  - 爆炸後殘留紙屑粒子 1.6s 內漸進淡出，避免畫面太亂
```

### Stylepack — Frost Gambler（Applicable for：冰霜怪物與環境；Do NOT mix with：Seraphic Realism；Default：ON for enemies）
Applicable for：冰封城市、冰霜咆哮、寒氣爆裂；Do：冷藍 LUT、霜紋折射、霧顆粒；Don't：過度霧化遮擋主角線條。

#### Look（`_stylepacks/frost_gambler/look.yml` 原文）
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
  - 夜間場景以冰藍與月白為主軸，維持主角膚色在 50 IRE 以免過冷
  - 撲克牌邊緣的霜紋需呈現半透明折射感，貼附時帶輕微霜霧
  - 冰霜爆炸使用冷色體積光，控制亮度避免蓋過 HUD 細節
```

#### Audio（`_stylepacks/frost_gambler/audio.yml` 原文）
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

#### VFX（`_stylepacks/frost_gambler/vfx.yml` 原文）
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

## Master Prompt（15s｜2D 日系動畫｜紅黑 vs 冰藍對比｜高物理質感）
- Worldstate Snapshot（T0=夜晚，冰封鋼脈都市廢棄月台；裂開的鐵軌、結霜看板、列車殘骸；冰霜粒子濃度 0.4、溫度 -18°C；鋼川烈在右後方入場，冰獄群魔在左前方蠕動）
- Constraint List：
  - 軸線：鋼川烈始終位於畫面右側或右後；怪物在左至前側；禁止跨軸。
  - 服裝與 PBR：戰鬥衣粗糙度 0.28、金屬度 0.52，手臂紅線發光強度 120 nits；冰層粗糙度 0.07、折射 1.31，霧散射 0.4。
  - 粒子：爆炸段最大 180k 粒子；冰碎最大 160k；蒸汽霧 alpha clamp 0.8；爆光不超過 95 IRE。
  - 情緒曲線：平穩冷靜 → 集中 → 決斷爆發；語氣低沉。
- Execution Notes：camera projection 控制冰層反射；VDB 雙層霧；Ice shader 使用 subsurface 0.18；紅牌爆紋採延遲爆炸 0.12s 序列；接觸面摩擦 0.45、彈性 0.12、阻尼 0.28。
- Camera Continuity：24–35mm 建立空間；旋繞不超 120°；Angle 10 使用 32mm 快速拉遠；Angle 12 50mm 半身背後。
- Stylepacks：主線啟用 Arcane Gambler；冰霜與環境疊加 Frost Gambler；Angle 4/9/10 強化紅牌符文；Angle 1/2/6/11 強化冰霜折射。
- Physics & PBR：重力 9.8 m/s²；卡牌質量 120g、初速 22–28 m/s；冰碎落地反彈係數 0.18；爆炸火焰溫度峰值 1800K，蒸汽霧溫差導致折射閃爍。
- Sound：日本男性聲優低沉；BPM 96，鼓點與卡牌爆炸對齊；風與霧聲 -16 dBFS 背景。
- Safety：無商標、無可讀字；血腥與肢解降至 PG-13（碎冰代替血）。

## Act / Beat / Angle
### Act 1（0.0–4.8s） — 建立冰封場景與主角入場｜基調：緊張冰冷、慢入節奏 0.9–1.5s
#### Beat 1（0.0–2.4s）
- 重點：環境建立與冰獄群魔威脅入畫；延續主光冰藍 + 霧。
- Blocking：俯視推進；怪物在遠處蠕動；無主角。
- Camera：滑軌俯拍推進 24mm；對焦從前景霜裂拉到遠處冰影；快門角 180°；拍點對齊遠處冰影抖動。
- 光影：主光冰藍 4300K 體積光從左上；對比 1:2；眼神光忽略。
- 色調/LUT：Glacial-Edge 冰冷；去飽和 8%。
- 聲音：環境冰風、金屬鳴響；音樂淡入 96 BPM 輕鼓。
- 物理/質感：冰層厚 6–10cm，粗糙度 0.07、折射 1.31；鐵鏽粗糙 0.55；霧粒子半徑 0.35mm；重力正常。
- 轉場：直接切入 Beat 2。

Angle 1（0.0–1.2s）
- Camera：高角度俯拍，24mm，慢速推進；景深 f/5.6；層次對焦前→中→後。
- Lighting：冰藍體積光 + 月白 rim；環境遮蔽 0.3；光霧散射描邊冰刺。
- Materials & Physics：冰面 PBR 0.07 粗糙度、法線霜裂；鋼鐵梁金屬度 0.72；雪塵顆粒 0.2mm 重力下 0.3 m/s 落下；折射微閃。
- Emotion & Performance：無角色；營造孤寂與寒冷。
- Audio & Transition：寒風 + 遠處低吼 -18 dB；切到 Angle2 硬切。

Angle 2（1.2–2.4s）
- Camera：低角 close-up 35mm，手持微晃 3%，對焦冰獸口部；快門 180°。
- Lighting：冰藍主光，怪物霜霧側逆光，對比 1:2.5。
- Materials & Physics：冰刺折射 1.31、SSS 0.12；黑霧密度 0.35；呼氣霧 0.4 density 向鏡頭推進；咆哮帶噴霧速度 4 m/s。
- Emotion & Performance：怪物怒吼張嘴；威脅感。
- Audio & Transition：低頻咆哮 -10 dB、霜霧噴射；鞭移遮擋轉至 Beat2。

#### Beat 2（2.4–4.8s）
- 重點：鋼川烈入場，紅線能量啟動；環境蒸汽因熱足跡產生。
- Blocking：鏡頭貼地平推跟腳步；主角從畫右入；卡牌浮現。
- Camera：滑軌貼地 28mm；對焦腳→小腿→腰；快門 180°。
- 光影：紅光沿腿部上升；冰面反射藍光；對比 1:1.8。
- 色調/LUT：混合 Ember-Neon + Glacial-Edge，保膚色 60 IRE。
- 聲音：鞋底摩擦冰聲 + 卡牌震鳴 -12 dB；配合 96 BPM。
- 物理/質感：鞋底橡膠粗糙 0.6 摩擦；冰面因熱蒸汽 0.2s 壓力煙；卡牌質量 120g 懸浮。
- 轉場：光匹配切 Act2。

Angle 3（2.4–3.6s）
- Camera：貼地 tracking，24mm；對焦鋼川烈鞋與腿；景深 f/4。
- Lighting：腳下反射冰藍，紅線光 120 nits 逐步上升；微弱背光輪廓。
- Materials & Physics：冰面薄霜蒸發形成 0.5mm 水膜，摩擦 0.4；紅能量線粗糙度 0.18，菲涅耳 0.9；蒸汽向上 0.8 m/s。
- Emotion & Performance：堅定步伐，重心低穩。
- Audio & Transition：足音 + 卡牌輕鳴；直接切 Angle4。

Angle 4（3.6–4.8s）
- Camera：中近景側面 50mm，繞肩 60°；對焦臉與卡牌；快門 180°。
- Lighting：紅 rim 光 + 冰藍 fill；對比 1:2；眼神光保留。
- Materials & Physics：戰鬥衣 PBR 粗糙 0.28，金屬度 0.52，布料皺摺延遲 0.1s；卡牌邊緣爆紋 emissive 0.62；空氣霧折射閃爍。
- Emotion & Performance：低聲台詞「氷なんかに、この街は渡さない。」；眼神冷靜。
- Audio & Transition：日文 VO -6 dB，背景風 -16 dB；硬切 Act2。

### Act 2（4.8–10.8s） — 交鋒與爆裂戰鬥｜基調：緊張加速 1.5–2.6s
#### Beat 3（4.8–7.2s）
- 重點：首次爆裂擊退；卡牌慢動作爆紋。
- Blocking：手部近拍彈牌→卡牌插地→爆炸震怪。
- Camera：極近手 75mm；切到低角 35mm；快門 180°。
- 光影：紅光爆紋；冰面反射紅光；對比 1:2.2。
- 色調/LUT：Ember-Neon 主導，陰影保冰藍。
- 聲音：彈牌「咔」-10 dB；爆炸 implosion -2 dB；鼓點加重。
- 物理/質感：卡牌初速 26 m/s；爆炸壓力波 0.6 atm；冰晶破片大小 2–12mm；重力正常。
- 轉場：爆光白閃遮擋。

Angle 5（4.8–6.0s）
- Camera：極近手特寫 75mm；子彈時間 0.6x；景深 f/2.0 聚焦指節。
- Lighting：紅卡邊緣高光 180 nits；手部皮膚 SSS 0.22；對比 1:2。
- Materials & Physics：手套皮革粗糙 0.38；指節摩擦彈牌施力 18N；卡牌表面浮雕法線 0.6；殘影 motion blur 144°。
- Emotion & Performance：彈指果決；肌肉緊繃。
- Audio & Transition：卡牌彈聲 + 短促吸氣；白閃切 Angle6。

Angle 6（6.0–7.2s）
- Camera：低側角 35mm；卡牌插地近距；爆圈向外。
- Lighting：紅爆光主，冰層反射藍次光；過曝 0.3s 控制；體積光推開霧。
- Materials & Physics：地面冰層破裂，裂縫深 3cm；碎冰彈速 12 m/s；怪物腳步後退 0.6m；爆炸火花粒徑 0.4mm。
- Emotion & Performance：怪物被震退；主角姿態穩。
- Audio & Transition：爆炸低頻 + 碎冰高頻；鞭移轉 Beat4。

#### Beat 4（7.2–10.8s）
- 重點：多怪衝擊，主角滑步連投；蒸汽牆對抗冰矛。
- Blocking：主角中心，怪物多方向衝；滑步旋轉丟牌；蒸汽牆擋光束。
- Camera：中距旋繞 32mm；側 tracking 28mm；快門 180°；拍點對齊每次爆炸。
- 光影：紅爆交錯冰藍光束；體積霧被蒸汽推開；對比 1:2.5。
- 色調/LUT：紅黑占主體，冰藍作補；去飽和 5%。
- 聲音：連續爆炸與冰矛破空交錯；音樂層次增加。
- 物理/質感：滑步摩擦 0.35；冰矛速度 30 m/s；蒸汽牆厚 0.6m、溫度 120°C；卡牌爆炸延遲 0.1s。
- 轉場：旋繞帶遮擋切入 Act3。

Angle 7（7.2–8.4s）
- Camera：中景 32mm 繞主角 90°；景深 f/3.2；對焦主角胸口。
- Lighting：紅爆光交錯冰藍 rim；對比 1:2.4；粒子反射。
- Materials & Physics：冰面滑度 0.38；布料皺摺因旋轉延遲 0.12s；卡牌爆紋弧光厚 1.5cm；碎冰飛行拖曳 0.02s。
- Emotion & Performance：動作流暢、目光鎖定不同怪物。
- Audio & Transition：連續爆炸節奏如鼓點；遮擋轉 Angle8。

Angle 8（8.4–9.6s）
- Camera：側 tracking 28mm；同平面跟隨；對焦卡牌與冰矛交會處。
- Lighting：冰矛藍光束 5000K；紅爆光 2200K；蒸汽白霧散射。
- Materials & Physics：冰矛由冰晶粒子 1–3mm 組成；紅卡爆炸產生蒸汽牆厚 0.6m；流體折射閃爍；滑步摩擦火星稀疏。
- Emotion & Performance：主角冷靜閃避，手腕甩牌俐落。
- Audio & Transition：冰矛破空 + 爆炸互壓；直接切 Angle9。

Angle 9（9.6–10.8s）
- Camera：中遠景 35mm 環繞 110°；紅牌環形陣式；慢速 0.8x。
- Lighting：紅能量線連接胸口與牌；周圍體積霧被紅光染色；對比 1:2。
- Materials & Physics：懸浮牌每張 120g，繞身半徑 1.4m；磁懸浮軌跡平滑；能量線粗糙 0.18；粒子微塵上升 0.4 m/s。
- Emotion & Performance：低語「――全部、まとめて終わらせる。」；肌肉繃緊。
- Audio & Transition：低語 -6 dB；紅能量嗡鳴；硬切 Act3。

### Act 3（10.8–15.0s） — 集束爆破與收束｜基調：決斷爆發 2.4–3.0s
#### Beat 5（10.8–13.2s）
- 重點：卡牌雨同時射出；多怪同步爆炸。
- Blocking：特寫眼→拉遠全景；卡牌雨貼怪弱點；連鎖爆炸。
- Camera：極近眼 85mm；snap zoom out 至 32mm；快門 144°；時間稍減速 0.85x。
- 光影：紅光強對比；冰層碎裂反光；對比 1:3。
- 色調/LUT：Ember-Neon 主導，冰反光保持冷。
- 聲音：集束射出「嗖」+ 多重爆炸；音樂高潮。
- 物理/質感：卡牌群初速 28 m/s；貼附後 0.12s 延遲爆；冰殼破片最大 18mm；火光溫度 1800K；衝擊波推動霧牆。
- 轉場：爆炸連接 Beat6。

Angle 10（10.8–12.0s）
- Camera：極近眼 85mm → snap zoom out 32mm；對焦眼後拉焦到卡牌軌跡；景深變化 f/2.0→f/4。
- Lighting：紅光反射在瞳孔；背景冰藍對比；對比 1:2.8。
- Materials & Physics：角膜高光、皮膚 SSS 0.22；卡牌軌跡殘影長 1.2m；空氣摩擦產生微紅火花；慣性推動衣料延遲 0.15s。
- Emotion & Performance：眼神決斷；下頜收緊。
- Audio & Transition：短促吸氣 + 卡牌雨；拉遠後直接切 Angle11。

Angle 11（12.0–13.2s）
- Camera：掃掠平移 35mm，左→右；對焦不同怪物爆點；景深 f/5.0。
- Lighting：同步爆炸紅光不同距離亮起；冰晶碎片反射；對比 1:3；少量速度線。
- Materials & Physics：冰殼破裂，碎片飛行 14–18 m/s；爆炸衝擊波推開霧粒；彈性 0.18；掉落時顆粒與地面摩擦 0.35。
- Emotion & Performance：怪物分段爆解；主角在遠處穩定站姿。
- Audio & Transition：多段爆炸「ドンッ」「バンッ」擬聲；掃掠切 Angle12。

#### Beat 6（13.2–15.0s）
- 重點：收束，主角背影＋最後紅牌成灰；環境回到寂靜。
- Blocking：背後半身；遠處冰霧飄落；最後一張牌燃燒成光灰。
- Camera：50mm 半身背後；慢推近側臉；快門 180°。
- 光影：紅爆光衰減；背景藍霧；對比 1:1.6；殘光勾勒輪廓。
- 色調/LUT：混合紅暖邊緣 + 冰藍背景；去飽和 3%。
- 聲音：沉重呼吸 + 風聲；音樂漸弱至 -18 dB；紅灰燃燒小噼啪。
- 物理/質感：紅牌灰燼粒徑 0.2mm 向上 0.3 m/s 飄；衣料因呼吸微起伏 5mm；冰霧 density 0.25 緩落。
- 轉場：影片結束；可留 0.3s 餘韻。

Angle 12（13.2–15.0s）
- Camera：背後半身 50mm；慢推近側臉；景深 f/2.8；對焦肩線→側臉。
- Lighting：背景紅光漸暗，冰藍霧填充；手臂紅紋微弱閃爍；rim 光描邊。
- Materials & Physics：戰鬥服紋理清晰；紅牌燃成光灰，粒子消散 1.2s；冰晶飄落 0.6 m/s；蒸汽淡出。
- Emotion & Performance：呼吸沉穩；保持警戒姿態。
- Audio & Transition：風聲 + 呼吸；結束停留 0.3s。

## Platform Layer
- Hook A（故事向 0–1s）：Angle1–2 冰封俯視＋怪物怒吼；字幕建議「冰獄封城，誰能阻止？」
- Hook B（衝擊向 10–11s）：Angle10 snap zoom + 卡牌雨；字幕「一口氣炸光！」
- First-shot visual hook：冰藍霓虹裂縫＋蠕動冰影；高對比立即吸睛。
- Captions：日文台詞旁白，中文字幕靠底 10%；字體避免遮擋卡牌軌跡。
- Thumbnail：主角背對、紅牌陣式＋冰怪剪影；文字「紅牌爆紋 vs 冰獄」置頂。
- Hashtag：#鋼川烈 #紅牌爆紋 #冰獄群魔 #2D動畫PV #爆炸卡牌
- CTA：末尾留 0.3s 餘韻可疊「追蹤解鎖下一戰」。
- 切片輸出策略：短版可截取 10.8–13.2s 爆破段；長版則全長 15s；字幕對齊時間碼。

## Negative Instructions
- 禁用：真實商標、名人肖像、宗教政治符號、寫實血腥/肢解（以碎冰替代）、過曝閃光>95 IRE、魚眼畸變、過度手持晃動>3%。
- 自動檢核清單：
  - 確認無商標/可讀文件/未成年人特寫。
  - 確認字幕區不遮擋關鍵 VFX 或眼神。
  - 確認 LUT 與風格包未混用 Seraphic Realism。
  - 確認冰霧密度控制在 0.25–0.45，避免霧牆遮擋。
  - 確認 VO 為日文男性低沉音色，峰值 -6 dB。

## Assumptions
- 假設本集為鋼脈都市・爆紋防衛戰線系列第 1 集，後續可延續同場景損毀狀態。
- 假設無外部腳本檔，直接以使用者文案為基礎；若有官方腳本需覆蓋對應台詞與鏡頭。
- 假設配音採日文男性熱血低沉音色；若需其他語言需另行標註。

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：已含 Master、3 Act、12 Angle、明確時間碼與節奏標註。
- Physics & PBR：各幕標註重力、摩擦、質量、溫度、粗糙度、折射；爆炸/霧/冰粒子參數齊備。
- Stylepacks 使用與衝突：主用 Arcane Gambler，敵用 Frost Gambler，明列 Do/Don't，未混用 Seraphic Realism。
- Continuity：軸線與光向固定；持續要素（紅線、冰霧、鐵軌裂紋）延續到 Act3；Camera Continuity 已寫。
- QA Checklist：已貼原文並適用；字幕安全框與交付規格確認。
- 風險揭露：未有官方腳本檔案；若實際配音或 LUT 有更動需重跑對齊；粒子上限需測 GPU。

# Guardian or Calamity: Noon Dragonfall — Master Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-20_guardian-calamity-dragonfall_v01/script.md

## 一句話題材
正午黑龍墜落、解構成披著龍鱗護甲的東亞肌肉青年，他在白日強光下盯向鏡頭，懸在「守門人或災禍」的抉擇瞬間。

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

### QA Checklist（`_core/qa_checklist.md`）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

### Style Pack：Zenith Noon Real Look（`_stylepacks/zenith_noon_realism/look.yml`）
```yaml
name: Zenith Noon Real Look
lut: Zenith-Overexpose-HDR
saturation_adjust: -0.03  # 去飽和 3%
contrast: high_linear
highlight_rolloff: hard_clip_with_bloom
shadow_floor: lifted_sand  # 影子被抹平
white_point: 1.05  # 刻意過曝
texture: tempered_glass_scale
specular_detail: molten_gold_edges
heat_warp_pass: micro_ripple_sheet
notes:
  - 強化正午過曝質感，暗部保留極少量沙紋，不產生藍色陰影。
  - 鱗片表面需呈現多層玻璃反射並含熾橙內發光。
  - 景深受熱浪影響需保持邊緣抖動，勿套柔焦濾鏡。
```

### Style Pack：Zenith Noon Real VFX（`_stylepacks/zenith_noon_realism/vfx.yml`）
```yaml
name: Zenith Noon Real VFX
heat_haze_layers:
  - id: zenith_ground_glimmer
    distortion: 0.42
    speed: 1.6
  - id: apex_sky_veil
    distortion: 0.28
    speed: 0.9
solar_column_profile:
  core_color: fff8cf
  rim_color: ffad45
  falloff: exponential_hard
  particles: silica_dust_updraft
wing_trail_shader:
  refractive_index: 1.23
  thickness_cm: 65
  ember_specks: 0.18
sundial_cage_geometry:
  slices: 24
  rotation_speed_rps: 0.85
  cut_beam_width_cm: 8
reflection_cache:
  afterglare_delay_s: 2.2
  intensity_scale: 1.35
notes:
  - 光柱與光籠採體積陰影貼圖而非 2D billboard，以利真實折射。
  - 翅膀熱浪需在遠景造成背景折射，並帶動砂塵短暫懸浮。
  - 尾巴日晷展開時，光條必須對應地面刻度動畫並可作為腳本判定區域。
```

### Style Pack：Real Cinema Lens Set（`_stylepacks/real_cinema/lensset.yml`）
```yaml
name: Real Cinema Lens Set
primary_focals: [35, 50, 75]
shutter_angle: 180
dolly:
  move: glide_in
  speed_ratio: 0.8
handheld_usage: 0.03
support: slider_or_stabilizer
usage_notes:
  - 室內情緒戲採滑軌緩推
  - 側向平移保持視線連續
  - 聚焦於自然膚質呈現
```

### Style Pack：Real Cinema Safety Checklist（`_stylepacks/real_cinema/safety.yml`）
```yaml
name: Real Cinema Safety Checklist
rules:
  - 避免可讀字與商標曝光
  - 群眾不近特寫，維持隱私
  - 保持自然膚質與光比
  - 記錄 LUT 與種子以利 QA
```

## Camera Continuity
- 上一鏡面結束狀態：黑龍吞光後輪廓裂解，塵霧尚未落定，鏡頭停在黑環中心 50mm 眼高；光比為側逆+頂光高對比，色溫 5600K，對焦點在龍眼。
- 本集延續：保持 50–75mm 親密視角接入 Beat05，滑軌緩推連續；對焦由龍眼平滑拉到中心人影，快門角保持 180°；熱浪折射與塵霧粒子延續 2.0s 後逐漸衰減。
- 轉換前置條件：自 Beat04 至 Beat05 以黑環邊緣光源匹配切；Beat08 收瞳後，Beat09 需維持眼線對中鏡頭的連戲，避免突然換側。

## Master Prompt
Master(15s｜Zenith Noon Real Look × Real Cinema Lens｜16:9｜24fps｜正午過曝寫實)
「正午荒原／城市邊緣；烈日、碎瓦、熱浪折射；黑龍墜落解構成東亞肌肉青年披鱗，抬眼判定守護或災禍。
鏡頭：滑軌＋環繞，手持≤3%；
表演：墜落驚怒→變身平靜警戒→結尾凝視帶懸念；
臉型/髮型：東亞男性、短黑髮、臥蠶清楚；
構圖：中央/三分線交錯，前中後景含塵霧、碎鱗、遠景城市；動態：熱浪、塵土、鱗片漂浮；
寫實細節：龍鱗玻璃質感、肌肉汗光、裂紋反光、無可讀字樣。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35 空間，50–75 親密；光圈 T4–T5.6；快門角 180°；對焦單點眼→層次拉焦。光影：側逆＋頂光體積塵霧；色溫 5600K；對比高；眼神光保留。色調：膚色優先、陰影微提、去飽和 3%。聲音：熱風、碎石、鱗片金屬音、遠景環境低鳴（-6 dB 峰值）；音樂氛圍弦樂混低鼓。轉場：直接切或光源匹配 0.5s。安全：無品牌、無可讀文件、群眾不近特寫、連戲一致。

## 分鏡（15s｜12 幕 × 約 1.25s｜白天寫實電影風）

### Act I（0–5s） — Dragonfall
意圖：建立災兆與衝擊。基調：緊張→悸動。節奏域：慢入1.25 → 穩定2.0。美術要點：正午烈日、冷白勾邊的黑鱗、塵霧。

- Beat 01（0.0–1.25s） 天空異常｜鏡頭：仰角滑軌微推；焦段 24mm 眼高→胸高；對焦單點龍影；快門角180。
  - Angle A1｜構圖：三分線，前景路牌被陰影覆蓋，中景藍白天空被巨大黑影撕裂，遠景雲層口。補充：熱浪閃動；安全：無可讀字。
  - 聲音：熱風底噪（baked_desert_wind）、遠處金屬嗡鳴（distant_metal_creak）。轉場：直接切。

- Beat 02（1.25–2.50s） 穿雲俯衝｜鏡頭：側向滑軌跟拍；焦段 35mm 胸高；層次拉焦由翼尖到頭；快門角180。
  - Angle A2｜構圖：前中後景帶動，黑龍側身俯衝，鱗片邊緣被日光勾出冷白線；翼拍炸出白霧衝擊。補充：wing_trail_shader 折射空氣。
  - 聲音：helio_dive 轟鳴＋thermal_wing_cut 斬風；轉場：光源匹配切。

- Beat 03（2.50–3.75s） 墜地衝擊｜鏡頭：膝高低角定機；焦段 35mm；單點對焦地平線；快門角200。
  - Angle A3｜構圖：中央地平線，黑龍撞地爆出土浪與碎瓦，塵霧衝向鏡頭前景；路牌、草木猛晃。補充：heat_haze_layers 造成背景折射。
  - 聲音：subsonic_column_crush 低頻衝擊；塵霧摩擦；轉場：遮擋切（塵霧）。

- Beat 04（3.75–5.00s） 吞光吐息｜鏡頭：半身近景穩定器；焦段 50mm 眼高；呼吸拉焦口鼻→黑環；快門角180。
  - Angle A4｜構圖：中央近景，龍頭抬起張口，吐出向外擴散的黑色光環，中央變暗、邊緣仍是耀眼白日。補充：solar_column_profile 光柱邊緣吞光。
  - 聲音：solar_pressure_drop 落差感＋glass_ring_sweep 環音；轉場：黑環邊緣光源匹配切。

### Act II（5–10s） — Unravel
意圖：解構與變身。基調：決斷。節奏域：穩定1.8。美術要點：漂浮鱗片、玻璃質感、汗光肌理。

- Beat 05（5.00–6.25s） 鱗碎崩解｜鏡頭：俯視滑軌緩推；焦段 35mm；層次拉焦碎鱗→中心人影；快門角172。
  - Angle A5｜構圖：中央旋渦，黑龍輪廓裂開如碎玻璃，鱗片漂浮繞圈；中心人影亮起。補充：reflection_cache 殘光拖影。
  - 聲音：鱗片碎裂叮噹＋heat_buzz_harmonics；轉場：直接切。

- Beat 06（6.25–7.50s） 人形著地｜鏡頭：膝高定機；焦段 50mm；單點對腳；快門角200。
  - Angle A6｜構圖：中央腳落地，碎石飛散，幾片鱗片滑落腳邊轉動；腿部線條帶汗光。補充：微塵逆光粒子。
  - 聲音：granular_sandfall＋footstep落地；轉場：遮擋切（塵霧）。

- Beat 07（7.50–8.75s） 鱗披成形｜鏡頭：背後中近景滑軌上升；焦段 50mm 胸高；層次拉焦背肌→鱗披；快門角180。
  - Angle A7｜構圖：背對鏡頭，短髮與寬厚肩背；脊椎兩側鱗片如液態金屬攀上肩背變披風護肩；陽光在邊緣反光。補充：heat_haze_layers 微抖。
  - 聲音：distant_metal_creak 拉升；鱗片摩擦金屬聲；轉場：直接切。

- Beat 08（8.75–10.00s） 側臉收瞳｜鏡頭：側臉近景穩定器；焦段 75mm 眼高；單點對眼；快門角144。
  - Angle A8｜構圖：胸口以上側臉，短黑髮、臥蠶清晰；瞳孔由縱向獸瞳收斂成正常眼，眉頭微皺。補充：呼吸拉焦眼→肩鱗；留白 10%。
  - 聲音：環境聲抽空只留 heat_buzz_harmonics 微鳴；轉場：直接切。

### Act III（10–15s） — Verdict
意圖：收束並留下懸念。基調：決斷→盼望/不安。節奏域：穩定2.0。

- Beat 09（10.00–11.25s） 守門符號｜鏡頭：正面中景滑軌微推；焦段 50mm 眼高；層次拉焦胸→地裂；快門角180。
  - Angle A9｜構圖：青年站在中央，身後地裂延伸出巨大圓形圖案，半邊耀眼白光、半邊黑色深淵，像門也像封印。留白 15%。
  - 聲音：低頻嗡鳴＋silica_dust_updraft 細沙；轉場：光源匹配切。

- Beat 10（11.25–12.50s） 鱗披展開｜鏡頭：微仰角中近景滑軌前移；焦段 50mm 胸高；單點對胸鱗；快門角180。
  - Angle A10｜構圖：青年踏步，龍鱗披風被風掀起，露出胸肌與鎖骨線條；鱗片排列成護胸護臂並微微震動。補充：specular_detail 熱光邊緣。
  - 聲音：衣料/鱗片振動＋風聲 sidechain 3 dB；轉場：鞭移至下個角度。

- Beat 11（12.50–13.75s） 抉擇能量｜鏡頭：側後繞拍 90°；焦段 50mm 眼高；呼吸拉焦掌心→遠景城市；快門角172。
  - Angle A11｜構圖：青年半側，前方遠景城市一側破敗、一側完好；抬手掌心亮起光芒，顏色介於救贖與毀滅。補充：afterglare_delay_s 2.2 的殘光。
  - 聲音：vacuum_slice_thump 切風＋光芒能量脈衝；轉場：直接切。

- Beat 12（13.75–15.00s） 終局凝視｜鏡頭：上半身正面特寫緩推；焦段 75mm 眼高；單點對眼；快門角144。
  - Angle A12｜構圖：胸口到頭頂，白日光線打在肌肉線條與龍鱗披風上，額頭汗珠；一眼反射藍天、一眼反射黑裂縫。胸腔隨呼吸緩起伏，嘴角模糊在微笑或冷笑間。0.5s 定格。
  - 聲音：音樂與環境漸收，只留心跳與微風；問句旁白 0.7s 中央定位："守門人，還是災禍？" 殘響 0.3s 後歸於靜音。轉場：停頓收束。

## 風格與技術補充
- 光影：採 Zenith Noon Real Look 過曝陽光與玻璃鱗片反射，陰影抬升保持肌理；鱗片 specular 需有熾橙內發光。
- 運鏡：依 Real Cinema Lens Set，以滑軌/穩定器為主，手持占比≤3%；焦段按 35/50/75mm 切換，保持眼線連續。
- VFX：使用 Zenith Noon Real VFX 的 heat_haze_layers、wing_trail_shader、solar_column_profile，衝擊與吐息對應音畫同步。
- 聲音：遵循 Audio Pack 指引，底噪維持 baked_desert_wind＋heat_buzz_harmonics，衝擊點對應 cue（helio_dive、subsonic_column_crush、glass_ring_sweep）。結尾旁白 band_limit_mid_high 處理。

## QA 自檢
- 結構完整度：Master/Act/Beat/Angle 時間軸與運鏡齊備。
- 敘事一致性：白天黑龍墜落→解構變身→守門/災禍懸念串聯。
- 視聽細節：焦段、運鏡、光影、VFX、音畫同步皆標註，轉場明確。
- 風格準確性：Zenith Noon Real + Real Cinema Lens 指定並內嵌全文，與正午寫實需求吻合。
- 格式精準度：遵循模板與時間標記；無可讀文字與商標；生成設定與交付規格一致。

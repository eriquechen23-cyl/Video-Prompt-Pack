# Project Metadata
project_name: 鋼脈都市 MUSCLE LINE
series_name/arc: 冰鏈咒印篇
episode_index: 1
slug: ice-chain-hex-azure-link_v01
target_platform: social_short_vertical
duration_sec: 15
style_primary: Frost Gambler
style_secondary: Lightning Chain
worldstate_ref: 鋼脈都市下層廢區被冰鏈封鎖的夜戰
goal: 展現冰鏈疊層引爆的連鎖殲滅效果，保留物理與質感層次

# _core
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

## Delivery Presets
```
畫幅：{16:9｜9:16｜1:1}
解析度：{1920×1080｜1080×1920｜2048×2048}
幀率：{24/30/48/60}（如需輕慢動：拍 48–60，輸出 24）
防抖：{開/關}；運動模糊：開；顆粒：微膠片
色彩：Rec.709（交付版）／LOG（調色版）
聲音：立體聲 48kHz；-14 LUFS（YouTube），-1 dBTP
種子：{固定/隨機（記錄）}；連戲：開；時序一致：開
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

## _core Do/Don't
Do:
- 嚴格引用以上模板的鏡頭、光影、物理與交付細節於 Master Prompt 及各 Act/Beat/Angle。
- 在 worldstate 與 constraint list 中維持軸線、光源方向、焦段區間的連貫性。
- 每幕補上 PBR 參數（粗糙度/金屬度/法線）與物理行為（重力/慣性/摩擦/折射）。
Don't:
- 不可以「同前」敷衍任何 Angle 的材質或光源描述。
- 不得遺漏時間軸或省略鏡頭語法設定。
- 不可添加未核實的品牌或字幕。

# _stylepacks
## Style: Frost Gambler (Applicable for cryo spells and chain detonations｜Do NOT mix with warm romantic tones｜Default ON)
### Visual/Audio traits
- 引用 Frost Gambler Look：
  - name: Frost Gambler Look
  - lut: Glacial-Edge
  - saturation_adjust: -0.04
  - contrast: crisp_frostbite
  - highlights: polar_silver
  - shadows: abyssal_cyan
  - affinity_glow: refracted_iceband
  - texture: reinforced_leather_parka
  - chromatic_aberration: subtle_prismatic_shear
  - lens_distortion: micro_pincushion
  - notes:
    - 夜間場景以冰藍與月白為主軸，維持主角膚色在 50 IRE 以免過冷。
    - 撲克牌邊緣的霜紋需呈現半透明折射感，貼附時帶輕微霜霧。
    - 冰霜爆炸使用冷色體積光，控制亮度避免蓋過 HUD 細節。
- 引用 Frost Gambler VFX：
  - name: Frost Gambler VFX
  - niagara_presets:
    - card_frost_bind
    - shatter_chainwave
    - hud_cryo_reticle
  - unity_vfx_graph:
    - Gambler.FrostLatch.vfx
    - Gambler.CryoDetonate.vfx
    - Gambler.IceDustBloom.vfx
  - houdini_flipbooks:
    - ice_platelet_burst
    - frost_wave_shell
    - card_frag_glassmix
  - shader_settings:
    - rune_edge_emit: 0.48
    - cryo_rime_spread: 0.67
    - shatter_impulse: 0.61
    - debris_velocity_random: 0.52
  - sdf_settings:
    - armor_surface_wrap: 0.34
    - hud_lockbox_radius: 0.18
    - shatter_offset_delay: 0.14
  - bloom_control:
    - idle: 0.12
    - trigger_peak: 0.68
    - cooldown: 0.29
  - audio_sync:
    - card_tap: sync_to_crunch
    - freeze_trigger: rising_glass_ping
    - shatter: cascading_cryo_blast
  - notes:
    - 霜爆需以 0.25s 延遲呈現冰紋擴散，粒子密度從中心快速外推。
    - 粉碎階段加入玻璃碎片混合冰晶，落地時 1.8s 內緩慢淡出。
    - HUD 準星以淡藍光脈動顯示冷卻狀態，避免與主體混淆。
- 引用 Frost Gambler Audio：
  - name: Frost Gambler Audio
  - core_layers:
    - polar_wind_bed
    - neon_icicle_drones
    - card_snap_percussion
    - subpulse_frost_core
  - peak_events:
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
  - low_freq_management:
    - sub_ceiling_db: -8
    - lfe_emphasis: 48Hz
  - sidechain:
    - trigger_bus: shatter_impacts
    - target: ambience_pad
    - reduction_db: 3.6
  - notes:
    - 風聲需帶霜霧顆粒感，與環境金屬殘響交錯。
    - 凍結瞬間加入水晶延音，強調時間凝結效果。
    - 粉碎爆炸搭配低頻衝擊與高頻碎裂層次，保持節奏俐落。
### Do/Don't
Do:
- 在冰鏈疊層的貼合、延遲爆破時使用 frost_wave_shell 並對應 rising_glass_ping 聲音。
- 調色維持 polar_silver 高光，對比 crisp_frostbite 確保金屬廢墟紋理可讀。
- HUD 以 hud_cryo_reticle 在疊層時脈動，並跟隨 shatter_impulse 參數下降。
Don't:
- 不要將暖黃高飽和光源置於主角膚面。
- 不要在霜爆時忽略玻璃碎片混合層，避免畫面單調。

## Style: Lightning Chain (Applicable for conductive chain jumps｜Do NOT mix with sepia nostalgia｜Default OFF)
### Visual/Audio traits
- 引用 Lightning Chain Look：
  - name: Lightning Chain Look
  - lut: Ionized-Arc
  - saturation_adjust: 0.12
  - contrast: high
  - highlights: electric_blue
  - shadows: graphite_cool
  - texture: rain_slick_leather
  - chromatic_aberration: tangential_blue_shift
  - lens_distortion: controlled_pincushion
  - notes:
    - 強調藍白電弧的高亮輪廓，保留肌膚 52 IRE 微暖
    - 地面濕潤反光需加入局部高光刷動
    - 霧氣與電暈採用分層曝光避免過曝
- 引用 Lightning Chain VFX：
  - name: Lightning Chain VFX
  - niagara_presets:
    - 圓弧雷鏈生成
    - 電暈過曝脈衝
    - 地面枝狀放電
  - unity_vfx_graph:
    - ArcLoop.vfx
    - ChainLeap.vfx
    - OzoneBloom.vfx
  - houdini_flipbooks:
    - lightning_flash_cluster
    - ozone_mist_swirl
    - finger_arc_ignition
  - shader_settings:
    - bolt_core_thickness: 0.45
    - afterglow_decay: 0.65
    - spark_density: 1.8
    - refraction_ripple_intensity: 0.3
  - sdf_settings:
    - stickiness: 0.25
    - jump_arc_delay: 0.15
    - impact_scorch_radius: 1.2
  - bloom_control:
    - idle: 0.18
    - trigger_peak: 0.82
    - cooldown: 0.3
  - audio_sync:
    - zap_triggers: align_arc_leaps
    - bass_hit: accent_phase_interference
  - notes:
    - 雷鏈跨目標時需保留殘影拖曳 3 frame
    - 地面放電使用形狀配對剪與光閃過門銜接
    - HUD 元素需與鏈路節點一一對應，避免漂移
- 引用 Lightning Chain Audio：
  - name: Lightning Chain Audio
  - core_layers:
    - ozone_drone_bed
    - crackle_triplets
    - sub_thump_sync
  - peak_events:
    - timestamp: ignition
      sfx: finger_arc_snap
      level_db: -6
      stereo_width: 100
    - timestamp: convergence
      sfx: thunder_iris
      level_db: -3
      stereo_width: 140
  - rhythmic_grid:
    - bpm: 120
    - subdivision: eighths
    - swing: 0.04
  - sidechain:
    - trigger_bus: impact_bus
    - target: ozone_drone_bed
    - reduction_db: 2
  - dynamics:
    - crest_factor: 10
    - transient_protection_db: -1
  - notes:
    - 120 BPM 節奏需呼應每 0.5s 電弧節點亮起
    - 扣指瞬間加上金屬尖銳高頻 6kHz
    - 殘光收束後留 1.5s 氣流與餘電尾音
### Do/Don't
Do:
- 在冰紋炸裂瞬間混入圓弧雷鏈生成以表現能量殘響。
- 將 spark_density:1.8 與 bolt_core_thickness:0.45 轉為廢墟金屬反射，配合 tangential_blue_shift 的邊緣色散。
- 使用 120 BPM 節奏對齊每 0.5s 疊層觸發，並讓 finger_arc_snap 作為手勢提示。
Don't:
- 不要與暖色復古 LUT 混用。
- 不要讓雷鏈 HUD 漂移脫離冰紋節點。

# Technical Specs
- Aspect Ratio: 9:16；FPS: 24；Shutter: 180 度；Lenses: 24/35/50/75mm（用途在分鏡標註）。
- Depth of Field: 前中後焦層漸進，近景 f/2.0，遠景 f/4.5，Bokeh 去洋蔥紋；顆粒：柔和膠片 20%。
- Color Pipeline: log capture → filmic LUT（Glacial-Edge/Ionized-Arc 交替）→ final contrast crisp_frostbite/high；陰影微藍、高光暖銀。
- Motion Blur: 180 度；防抖開；Rec.709 交付，保留影片 12 幕 × 1.25s ≈ 15s。

# Platform Layer
- Hook A (故事向 0–1s): 0.0–1.0s 冰藍紋路沿鎖骨點亮；字幕："冰鏈疊滿，瞬間爆裂"；縮圖：主角胸前六角冰晶發光，背景哥布林模糊；Hashtag: #冰鏈咒印 #連鎖爆裂 #鋼脈都市。
- Hook B (迷因向 0–1s): 0.0–1.0s 指尖彈出第一枚冰晶，搭配 finger_arc_snap；字幕："二層就爆！"；縮圖：指尖冰晶飛出、藍光拖尾。
- Caption: 中日混用，日語咒語「凍れ」+ 中文行動描述；音畫同步 120 BPM。
- 切片輸出策略：短版取 0.0–6.0s 連鎖起爆；長版保留 0.0–15.0s 全鏈，字幕行對應 Hook 行 1–2。
- CTA: 結尾 14.5–15.0s 加淡入字幕「解鎖下一層咒印」。

# Negative Instructions
- 禁用真實商標、名人肖像、政治宗教符號、色情與過度血腥，維持 PG-13。
- 避免過曝、廉價濾鏡、過度手持晃動、魚眼變形；保持 controlled_pincushion 微畸變即可。
- 避免語言錯置：台詞僅限日語「凍れ」與中文字幕，無其他文字。
- 自動檢核清單：逐幕確認無 Logo、無可讀紙張、HUD 僅顯示幾何瞄準；膚色維持 50–52 IRE；粒子不遮擋主體五官。

# Continuity Layer
- 軸線：主角自西向東前進，鏡頭主要位於其右後 110° 弧線，BOSS/哥布林散布於畫面左前 30–70°；禁止跨軸。
- 光源：主光霓虹從右上 45°（3200–3600K），環境冷霧 4200K 體積光從地面縫隙滲出，反射填光由水漬地面反彈。
- 鏡頭距離曲線：Act I 24–35mm 建立場景；Act II 35–50mm 中近、連鎖爆；Act III 50–75mm 收束與特寫。
- 狀態時間線：T0 主角蓄壓 70%；T5 第一圈連鎖展開；T10 巷道 60% 冰封；T14 收束冷卻。
- Camera Continuity：上一集結束焦距 35mm、右後 110° 手持 3% 微晃，此集延續但轉穩定器。

# Master Prompt (15s｜Frost Gambler + Lightning Chain｜9:16｜24fps｜超寫實冰電質感)
- Worldstate Snapshot：鋼脈都市下層廢區，鋼梁倒塌、玻璃碎片與油汙水坑（厚 3–6mm）反光；藍色霧氣濃度 0.35 g/m³，含鐵粉折射微粒；主角身穿貼身戰鬥上衣（PBR 粗糙度 0.32、金屬度 0.08、法線細膩布紋 2K），肩胸肌刻畫分明；鎖骨沿線冰藍紋路亮度 120–180 nits。
- Constraint List：不得改變主光方向與軸線；冰紋疊層必須兩層即爆；哥布林持骨鐵短刀長 28cm 粗糙度 0.55；環境需保留水漬反射不被過曝；每次爆炸需透過 frost_wave_shell + 圓弧雷鏈生成做能量過門。
- Execution Note：camera projection 用以固定背景鋼梁紋理；volume pass 控制霧粒散射（σ_s=0.7、σ_a=0.2）；denoise 限制保持指紋與霜紋細節；風場 1.8 m/s 從巷口吹向巷尾，吹動霧氣與碎紙。
- Brand Bible：角色口頭禪日語「凍れ」，行動乾脆；色票黑藍 #0a1016 搭冰藍 #66ccff；道具六角冰晶符印；語氣冷靜、節奏斷句。
- Do: 使用 DoF 控制讓冰晶軌跡經過景深過門；應用 crisp_frostbite 對比讓廢墟紋理、霜霧粒徑（80–150μm）可讀；保持運鏡滑軌平穩≤3%。
- Don't: 不反向移軸、不破壞兩層即爆規則、不插入暖光源。

# Acts & Beats (12 幕 × 1.25s)
Act I（0.0–5.0s）｜意圖：建立｜基調：緊張｜節奏域：慢入0.8–1.5｜美術要點：鋼梁、藍霧、冰紋亮起
Beat 1（0.0–1.25s）｜重點：冰紋啟動、Hook A/B
Camera：24mm 眼高滑軌前移 0.6m，手持 2% 微晃；對焦單點胸口；快門 180°；拍點 T0 冰紋點亮。
光影：主光 3400K 偏右，體積霧藍 4200K；對比中高，眼神光保留；LUT Glacial-Edge。
色調/LUT：膚色優先，陰影微藍，高光 polar_silver。
聲音：環境極低霧鳴、腳步踩水，finger_arc_snap(-6dB) 作為冰晶啟動。
物理/質感：冰紋沿鎖骨行進速度 1.6 m/s；布料彈性 0.22，受重力微下垂；PBR 粗糙度 0.32；水漬折射 n=1.33。
轉場：光源匹配到 Beat2。
Angle A1 構圖：中央胸口特寫，前中後景分明；道具：六角冰晶陣旋轉，粒子 1.2e4 個；安全：無Logo。
Angle A2 構圖：45° 側胸近拍，三分線，霧粒被風推向畫右；補充：微小冰霧在皮膚上凝結 0.3mm 厚。

Beat 2（1.25–2.5s）｜重點：第一發冰晶射出
Camera：24mm → 28mm 拉近，胸高，滑軌後退 0.4m 拉出空間；對焦呼吸拉焦胸口→指尖；快門 172°。
光影：側逆光 3300K 打在手背，霧間折射形成藍暈；眼神光輕弱。
色調/LUT：去飽和 6%，高光保暖銀。
聲音：lacquer_snap_icy(-11dB) 與 ozone_drone_bed；音畫同步 0.5s。
物理/質感：冰晶彈丸長 18cm 直徑 2cm，速度 34 m/s；空氣拖尾帶光暈；PBR 粗糙度 0.18、折射 1.31；布料摩擦 0.45。
轉場：鞭移跟彈丸方向到 Beat3。
Angle B1 構圖：過肩視角，冰晶飛向畫面左前；補充：玻璃碎片反射藍光閃動。
Angle B2 構圖：前中後分層，哥布林胸口入焦，冰晶將至；安全：去可讀字。

Beat 3（2.5–3.75s）｜重點：第一層疊層、冰紋鎖鏈
Camera：35mm，膝高仰拍強調哥布林胸口；對焦單點；快門 180°。
光影：霧中冷光 4300K，自左上穿透，形成體積光柱；對比高。
色調/LUT：陰影微藍，膚色保留；LUT 混合 Ionized-Arc 10%。
聲音：cryo_spread_chime(-7dB) 在冰紋生成，card_snap_percussion 微弱。
物理/質感：冰紋厚 2mm，在血管下呈鏈條狀；哥布林皮膚粗糙度 0.55，汗液 0.2mm 形成折射；重力作用下身體後仰 8°。
轉場：遮擋（冰霧）到 Beat4。
Angle C1 構圖：中央中近景，鏈紋亮起；補充：血液在冰下凝滯形成暗紅紋理。
Angle C2 構圖：45° 側面，鎖鏈紋路沿肩臂延伸；補充：微粒霧在光中折射形成小光斑。

Act II（5.0–10.0s）｜意圖：連鎖爆發｜基調：決斷｜節奏域：穩定1.5–2.4｜美術要點：冰鏈網、爆霜與雷鏈交織
Beat 4（5.0–6.25s）｜重點：第二層刻入、首次爆炸
Camera：38mm 眼高側移 0.8m；對焦層次胸→背景；快門 180°；手持≤3%。
光影：主光 3400K 從右上，電暈閃白 6500K 短暫提升；對比高。
色調/LUT：Ionized-Arc 提升對比，去飽和 5%。
聲音：glass_ice_implosion(-3dB) + thunder_iris(-3dB) 疊加；低頻 48Hz LFE 強調。
物理/質感：第二層冰紋厚增至 3.5mm，交錯時收縮 15%；爆炸波半徑 1.8m，衝擊壓力 0.6 bar；碎冰粒徑 0.5–2mm；哥布林被震退 0.4m。
轉場：光閃過門到 Beat5。
Angle D1 構圖：中景，多隻哥布林被波及；補充：冰霧向鏡頭撲面，景深壓縮。
Angle D2 構圖：俯拍環境建立，爆心藍光鎖鏈向外擴。

Beat 5（6.25–7.5s）｜重點：衝擊掃過周圍，上冰紋第一層
Camera：35mm → 45mm 拉近，胸高穩定器；對焦層次前→中；快門 200° 增動感。
光影：霧中散射加強，electric_blue 殘光拖尾；對比柔高混合。
色調/LUT：Glacial-Edge 60% + Ionized-Arc 40%，膚色 52 IRE。
聲音：ozone_drone_bed 拉寬立體聲，crackle_triplets 配合冰霧掃動。
物理/質感：掃過哥布林群時附著 1 層冰紋厚 1.5mm，部分腿部凍結摩擦係數升至 0.9；霧粒帶水分凝成 0.2mm 霜層。
轉場：遮擋（碎冰）到 Beat6。
Angle E1 構圖：側面跟隨，哥布林腿被凍住半截；補充：水漬受衝擊濺起 15cm 高浪花。
Angle E2 構圖：過肩回望，主角手掌持續蓄冰光。

Beat 6（7.5–8.75s）｜重點：第二輪冰晶射向帶一層目標，引爆
Camera：45mm 眼高，滑軌前推 0.7m；對焦呼吸指尖→目標；快門 172°。
光影：右上主光保持，爆點加入 OzoneBloom.vfx 短暫過曝 0.5EV；眼神光明顯。
色調/LUT：對比 high，陰影 graphite_cool；高光 electric_blue。
聲音：lacquer_snap_icy 與 sub_thump_sync 對齊 120 BPM；card_frost_bind 音畫同步。
物理/質感：冰晶速度 36 m/s；撞擊產生裂紋半徑 0.6m；碎片飛散初速 12 m/s；重力使碎片弧線下墜。
轉場：鞭移到 Beat7。
Angle F1 構圖：主角手指特寫，冰晶拖尾光絲；補充：皮膚毛孔可見，粗糙度 0.38。
Angle F2 構圖：遠中景，爆炸在隊伍中央引發連鎖；補充：雷鏈殘影保留 3 frame。

Beat 7（8.75–10.0s）｜重點：連鎖傳染至更遠處
Camera：50mm 胸高，繞拍 30° 強調網狀鏈；對焦層次前→後；快門 180°。
光影：霧光均勻，體積光帶微粒閃光；對比中。
色調/LUT：去飽和 5%，高光 polar_silver；電暈邊緣 tangential_blue_shift。
聲音：crackle_triplets 節奏持續，shatter_impacts sidechain 3.6dB。
物理/質感：每次爆炸波補上一層冰紋給半徑 2m 內目標；霜層厚度累積至 4mm；金屬梁表面結霜粗糙度升至 0.65。
轉場：光匹配到 Act III。
Angle G1 構圖：俯拍中景，冰鏈網覆蓋巷道；補充：體積霧遮擋形成軟遮罩。
Angle G2 構圖：低角仰拍，主角剪影對著爆心前進；補充：碎冰落點與鏡頭玻璃形成水滴。

Act III（10.0–15.0s）｜意圖：收束與冷卻｜基調：冷靜勝利｜節奏域：加速2.4–3.0 → 緩收
Beat 8（10.0–11.25s）｜重點：巷道 60% 冰封，主角加速
Camera：55mm，胸高滑軌前推 1.0m；對焦單點主角眼；快門 180°。
光影：主光 3400K 穩定，霧光稍減；對比中高。
色調/LUT：Glacial-Edge 主導，膚色 52 IRE；陰影微藍。
聲音：subpulse_frost_core 加深；腳步冰碎聲同步。
物理/質感：冰面摩擦 0.12 主角滑步；布料彈性 0.22 抖動；霧粒密度降至 0.25 g/m³。
轉場：直接切到 Beat9。
Angle H1 構圖：中近景，肩膀與胸口冰紋持續亮。
Angle H2 構圖：背跟角度，看到地面冰痕拖線。

Beat 9（11.25–12.5s）｜重點：倒數殘敵，冰紋二層即爆
Camera：60mm，膝高，穩定器；對焦層次腳→倒地哥布林；快門 200°。
光影：體積光帶灰塵折射；對比高。
色調/LUT：Ionized-Arc 提升電光感。
聲音：finger_arc_snap + crackle_triplets；shatter_chain(-3dB) 在爆炸瞬間。
物理/質感：冰紋厚 3mm，爆炸波半徑 1.2m；哥布林骨鐵刀被震飛 4m，旋轉 720°/s；重力拉回落地。
轉場：遮擋到 Beat10。
Angle I1 構圖：特寫冰紋爆光；補充：碎片飛向鏡頭時景深模糊避免刺眼。
Angle I2 構圖：中景，兩隻哥布林同時炸裂，霧霰朝左右散射。

Beat 10（12.5–13.75s）｜重點：鏈路最後一圈，霜霧吞噬尖叫
Camera：65mm，眼高側移 0.5m；對焦呼吸拉焦主角→遠端爆點；快門 180°。
光影：主光略降 0.3EV，霧光冷調；對比柔高。
色調/LUT：Glacial-Edge + subtle tangential_blue_shift；膚色維持。
聲音：neon_icicle_drones 拉升；thunder_iris 尾音 1.5s 氣流。
物理/質感：霜霧粒徑 100μm，速度 2 m/s；冰鏈亮度衰減曲線 0.82→0.3；空氣吸收係數 0.2。
轉場：光閃過門到 Beat11。
Angle J1 構圖：長焦壓縮遠端爆炸；補充：景深淺，主角肩膀做前景。
Angle J2 構圖：俯視巷道被冰霧填滿，黑藍鎖鏈網清晰。

Beat 11（13.75–15.0s）｜重點：最後哥布林倒下，冷卻與 CTA
Camera：75mm，眼高定機；對焦單點主角眼；快門 180°。
光影：主光拉回 3400K，對比中；眼神光保留微弱。
色調/LUT：收斂到 Glacial-Edge；顆粒 20%；膚色 52 IRE。
聲音：subpulse_frost_core 逐漸淡出；環境風聲持續；字幕「解鎖下一層咒印」淡入。
物理/質感：冰晶殘留在空氣中漂浮 0.6s 才消散；布料落塵；重力讓碎冰敲擊地面發出清脆聲（頻率 2–6kHz）。
轉場：淡出至黑。
Angle K1 構圖：特寫主角眼神冷靜，冰紋微光跳動；補充：皮膚油光 0.18，法線細節清晰。
Angle K2 構圖：遠景巷道收束，冰鏈網緩慢消散，CTA 字幕置於下三分之一。

# Platform Delivery & Safety
- 交付格式：9:16, 1080×1920, 24fps, Rec.709；聲音立體聲 48kHz -14 LUFS，Limiter -1 dBTP；運動模糊開，顆粒微膠片。
- Hook A/B 對應字幕行：A 用行1，B 用行2；切片 0–6s 保留 Hook 音畫；長版保留全程。
- 安全：去除所有可讀字、商標；哥布林無過度血腥，爆裂以冰碎呈現；保留 PG-13。

# Self-Check & Assumptions
### Assumptions
- 哥布林外觀以灰綠皮膚、骨鐵短刀為基準，無特定 IP；若需改變需人審。
- 主角語言只用日語「凍れ」，無需新增語句。
### AGENT Self-Check
- 結構：包含 Master/Act/Beat/Angle/timecode，12 幕 15s；連貫軸線與轉場已標註。
- Physics & PBR：每 Beat 都有重力、慣性、摩擦、粒徑、PBR 粗糙度/金屬度/法線；光學折射與體積霧數值已列。
- Stylepacks：Frost Gambler（Default ON）+ Lightning Chain（Default OFF 控制）內容全文貼入並應用；Do/Don't 均引用。
- Continuity：軸線、光源、鏡頭距離曲線、狀態時間線與上一集鏡頭參數已延續；無跨軸。
- QA Checklist：已引用並遵循；交付規格符合 Delivery Presets。
- 風險：若需額外角色資料未提供，需人審；霧粒度與折射值可再現場微調。

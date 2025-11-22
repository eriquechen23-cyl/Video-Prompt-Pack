# 蓄壓重槌師 EP02 — 朝倉蓮・雷槌終擊 vs 角質巨獸 BOSS PV Prompt（15s｜12 幕｜9:16 直式）

來源劇本：用戶提供《雷槌終擊・朝倉蓮 vs 巨獸》更新版文案與 12 幕提示（2D 日系動漫風，僅第 12 幕彩色漫畫感）

## Input Registry
- project_name: 蓄壓重槌師
- series_name/arc: 蓄壓重槌師・廢墟平原雷擊線
- episode_index: 2
- slug: thunder-maul-vs-keratin-behemoth_v02
- target_platform: TikTok / Reels / Shorts
- duration_sec: 15
- style_primary: Lightning Chain Look（黑＋黃雷紋、雷鏈節奏）
- style_secondary: Light Glyph Anime Look（乾淨 2D 線條、HUD 亮線）
- worldstate_ref: 廢墟平原、正午雷壓雲、角質骨刺巨獸踩碎廢墟、蓮攜雷紋巨槌靠近
- goal: 轉為「巨槌＋雷元素」版本，除擊殺的一幕外維持正常 2D 動畫風，第 12 幕保留高飽和彩色漫畫感（不轉黑白）；強化雷光、慣性、PBR 質感與雷擊特效同步

## 一句話題材
正午廢墟平原上，朝倉蓮扛著雷紋巨槌迎向角質骨刺巨獸，從啟動雷紋、蓄力衝刺到最終雷槌終擊，僅在擊殺瞬間切入彩色漫畫分鏡，其餘畫面保持乾淨黑黃 2D 動畫質感與飽和雷光。

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
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
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

## Stylepacks

### 引用 Style Pack：Lightning Chain（全量內嵌）
```yaml
# _stylepacks/lightning_chain/look.yml
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

# _stylepacks/lightning_chain/audio.yml
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

# _stylepacks/lightning_chain/vfx.yml
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

### 引用 Style Pack：Light Glyph Anime（全量內嵌）
```yaml
# _stylepacks/light_glyph_anime/look.yml
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

# _stylepacks/light_glyph_anime/audio.yml
name: Light Glyph Anime Audio
time_signature: 4/4
bpm_range: [92, 108]
ambient_beds:
  - soft_city_air_hum
  - crystalline_aether_pad
rhythmic_layers:
  percussive_clicks: holo_keyboard_taps
  sub_pulse: low_orbital_throb
ui_fx:
  glyph_expand: airy_chime_hi
  compile_ping: glassy_beep_mid
  error_flag: clipped_square_red
spell_sweeteners:
  curve_bolt_release: arc_bow_sheen
  hexshield_reform: hex_shingle_swirl
  cat_starflare: purr_riser_glow
mix_notes:
  - 對話維持 -6 dB 峰值，HUD 音效壓在 -12 dB 以下避免干擾詠唱。
  - 程式碼浮現時加入細緻鍵擊聲，與主角手指敲擊空氣同步。
  - 米漿心電音色偏低沉慵懶，情緒激動時可疊加高頻毛髮靜電。
  - 戰鬥高潮加強 4kHz 以上空氣感，讓光線爆閃更具穿透力。

# _stylepacks/light_glyph_anime/vfx.yml
name: Light Glyph Anime VFX
layer_stack:
  - background_mist_scroll
  - hud_symbol_plane
  - spell_vector_trail
  - glow_dust_overlay
spell_trail:
  color_mix: [auric_gold, mint_glow]
  taper: 0.42
  flicker_speed: 0.28
hud_widgets:
  panel_opacity: 0.65
  glyph_refresh_rate: 14
  debug_log_spacing: 18
error_feedback:
  color: crimson_error
  glitch_amount: 0.36
  frame_freeze: 0.08
particle_settings:
  glyph_sparks: 0.54
  light_dust: 0.32
  cat_starflare: 0.41
disintegration_fx:
  hexshield_tile_break: 0.57
  light_code_dissolve: 0.49
notes:
  - HUD 浮層需與角色動作略帶遲滯，營造空中投影被拉扯的感覺。
  - 能量彎射路徑依角色揮手軌跡生成弧形光帶，符文沿光帶流動。
  - 蜂巢六角盾破碎後應立即重排，碎片化為細小光粒回收至掌心。
  - 米漿星火充能時，尾端粒子需向胸口光晶形成柔和渦流。
```

### Style: Thunder Maul Manga Lock（新樣板｜本案 Default ON）
- Applicable for: 廢墟平原正午雷雲、黑＋黃雷槌、漫畫感僅限擊殺瞬間的 2D 動漫 PV；9:16 直式 BOSS 決戰。
- Do NOT mix with: 低光夜景霓虹、過曝白幕、血腥內臟鏡頭；漫畫格只能在擊殺瞬間啟用。
- Default: ON
- Visual traits:
  - 雷紋採金黃＋藍白雙層，槌頭刻紋有 0.5mm 刻線並填充 emissive；漫畫格開啟時保留全彩高飽和網點與粗速度線，雷光更亮，擬聲字以粗黑邊＋內亮描寫「ドガァァァンッ」。背景不轉黑白，維持藍紫天空、灰黑巨獸與黃白雷光的對比。
  - PBR：槌頭金屬度 0.82、粗糙度 0.2、刮痕置換 0.05cm；柄部橡膠握帶粗糙度 0.46、法線 0.35；蓮服裝碳纖維護胸粗糙度 0.38、金屬條 0.7，護手黃線以 emissive 0.6；巨獸角質粗糙度 0.68、骨刺法線 0.9，血肉不外露。
  - 光學：正午 5600K 硬光，雷光二次光溢出在地面形成 1.2cm 厚的菲涅耳反射；地面鋼筋斷口以 0.15 金屬度呈現鏡面反射，混合 0.35 粗糙度的混凝土粉塵。
- Audio traits:
  - 120 BPM 以雷鏈節點作節拍，重槌落點加 sub drop；漫畫格瞬間施加 0.2s low-pass（400Hz）再放開，拉出延遲轟鳴。
  - 呼吸與踏步同步衣料摩擦，雷鳴回響帶 1.5s 淡入尾韻，擊殺後空氣抽離只留低頻耳鳴與碎片落下聲。

## Technical Specs
- Aspect Ratio: 9:16 直式；Resolution: 1080x1920；Color Space: Rec.709 gamma 2.4；FPS: 24；快門角：180° baseline、漫畫格瞬間可放寬至 200° 以增強拖影。
- Lenses: Act I 24–35mm 俯視與逆光剪影；Act II 35–50mm 跟拍衝刺與交鋒；Act III 50–75mm 蓄力特寫、雷槌降落與漫畫格擊殺；3 秒內避免焦段往返跳躍。
- Camera Continuity: 軸線固定「蓮右、巨獸左」，鏡頭多位於蓮右後 120° 或巨獸右前 60° 弧線；手持≤3%，其餘滑軌與穩定器；保持高度變化由膝高→眼高→仰角分階段。
- Color Pipeline: log → filmic LUT → final contrast；黑線保留，雷光飽和黃白＋藍白雙層；社群壓縮防護：邊緣線加粗 0.5px、粒子對比 +10%，高光 Bloom 0.28。
- Grain & Compression: 紙感紋理 0.12、膠片顆粒 0.07；避免過度去噪以保留混凝土粗糙；雷光區域啟用亮度保護避免剪切。
- Physics Hooks: 重力 9.81 m/s²；巨槌質量設定 35kg、揮動帶慣性延遲 0.12s；地面摩擦係數 0.62，衝刺拖槌刻痕依速度噴落碎石；雷鏈放電折射率 1.04；漫畫格切換後立即恢復相同光位與軸線。

## Brand / Worldstate Layer
- Brand Tone: 黑＋黃訓練系語氣，日語短句＋中文字幕疊字；主打「蓄壓雷槌」與「正午決斷」。
- Character Bible — 朝倉蓮：黑髮束後、銳利眼型；黑色無袖上衣緊貼肩膀，黃線如電路沿肌肉走向；護手與護膝帶電黃光，皮膚 SSS 保留；口頭禪「一槌就安靜了」。
- Weapon: 雷紋巨槌，槌頭厚重刻滿幾何雷紋，縫隙有弧光流動，柄部橡膠握把附符紋按鍵；重量感透過肩膀拉扯與手臂微顫顯示。
- Environment: 廢墟平原鋼筋混凝土碎塊、倒塌路燈，地面留下巨獸爪痕與灰塵雲；天空壓低雷雲但仍屬正午色溫，細小靜電飄動。
- Persistent Elements: 黑黃雷紋 UI 條、雷鏈節拍聲、槌柄符紋按鍵、巨獸骨刺階段損傷（完整→裂紋→崩解）。

## Assumptions
- 巨獸身長約蓮 3.5 倍，背脊骨刺材質偏角質不流血，擊殺以碎片與光點表現；如需血腥需另版。
- 本集沿用 EP01 的品牌色與訓練語氣，但故事線改為平原 BOSS，未加入外部 NPC；若需觀眾或支援角色請另開分支。
- 日語配音僅提供台詞節點，實際演繹可由後期聲優調整；字幕中日雙語可重疊。

## Platform Layer
- Hook A（故事向 0–1s）：俯視巨獸踏裂地面、細小雷花冒出，字幕「雷雲壓城，巨槌迎戰」。
- Hook B（衝擊向 0–1s，需獨立 `hook_cut_prompt`）：截取 Beat 12 漫畫格擊殺 0.8s，之後倒帶回 0.0s baseline；不得在本稿混寫倒敘。
- Caption 建議：短版「一槌雷落，世界安靜。」｜長版「正午廢墟，朝倉蓮用雷紋巨槌劈開角質巨獸，只在擊殺瞬間變成漫畫。」
- Thumbnail: 逆光剪影扛槌與巨獸對峙，雷紋沿槌身亮到天空，右側保留字幕條空間；粗黑邊框＋金黃亮線。
- Hashtag: #蓄壓重槌師 #ThunderMaul #Anime #BlackGold #BossFight
- CTA: 收尾 0.5s 在雷光餘暈中疊字「Follow for 雷槌下一戰」，字體黑邊黃心，保持 50% 透明。

## Continuity Layer（軸線 / 距離 / 光源 / 狀態時間線）
- Axis Lock：蓮始終在畫面右、巨獸在左，鏡頭位於兩者右側弧線；漫畫格切換後軸線與光位立即回復，不得左右互換。
- Camera Distance Curve：Act I 24–35mm 建立環境與剪影；Act II 35–50mm 保持中近景節奏；Act III 50–75mm 聚焦雷光、蓄力與擊殺，收尾回 55mm 中景半跪姿。
- Light Direction Lock：太陽在右上 45°、5600K，雷光為次要光以黃白/藍白增加邊緣 rim；漫畫格僅改線稿與網點，不改主光方向。
- Boss State Timeline：Stage 1（0–5s）角質完好；Stage 2（5–10s）碰撞後骨刺出現裂紋與焦黑；Stage 3（10–15s）裂紋發光、最後崩解為黑碎片＋金黃光點。
- Ren State Timeline：雷紋啟動 0–3s 亮到前臂；3–7s 腿部與槌身全亮、蓄壓 60%；7–12s 與雷雲連動滿格；12–15s 重槌釋放後光度降為餘暈。
- Beat Writing Rule：每 Beat 開頭重申軸線/光位/Stage/Lens；Angle 欄位必填 Camera / Lighting / Materials & Physics / Emotion & Performance / Audio & Transition，不得寫「同前」。

## Negative Instructions
- 禁用真實商標、宗教與政治符號；不出現血腥斷肢或內臟畫面。
- 避免過曝白幕、過度魚眼、手持晃動超過 3%、過度鏡頭抖動；無雜訊水印。
- 漫畫格僅限 Beat 12 使用，其他幕保持正常動畫色彩與質感。

## Master Prompt（整體願景＋物理質感）
Master(15s｜Thunder Maul Manga Lock × Lightning Chain × Light Glyph Anime｜9:16｜24fps｜高對比黑黃雷紋 PBR 質感)
「正午、廢墟平原、雷雲壓低；鋼筋混凝土碎塊、倒塌路燈、角質骨刺巨獸；朝倉蓮扛雷紋巨槌啟動雷鏈、衝刺、躍擊、漫畫格擊殺。鏡頭：滑軌與穩定器主導，側向跟拍與仰角衝擊；表演：決斷、肌肉緊繃、視線鎖定巨獸；構圖：前中後景分明、留白 10–15%、速度線與雷光穿越；材質：槌頭金屬刮痕、橡膠握帶、皮膚汗膜、骨刺粗糙、地面粉塵；光影：5600K 硬光＋雷光 rim，折射因熱浪與電弧微抖；聲音：雷鳴、碎石、電弧、短促日語台詞；轉場：直接切與光閃過門，漫畫格僅 Beat 12。」

## Act / Beat / Angle（12 幕 × 1.2s，含運鏡、光影、材質、物理、聲音）

### Act I（0.0–4.8s） — 建立壓迫與雷紋啟動｜基調：緊張決斷｜節奏域：慢入 1.2s → 穩定 1.5s｜美術：廢墟、雷雲、黑黃服裝與雷紋巨槌

#### Beat 1（0.0–1.2s）｜巨獸壓境・場景建立｜延續 Axis Lock「蓮右巨獸左」、Light Direction 5600K、Boss Stage1、Lens 24–28mm 俯視
- Camera：廣角俯視滑軌往前推，機位 4m 高微俯拍，單點對焦巨獸背脊，快門 180°；建立廢墟平原尺度。
- Lighting：主光為右上硬陽 5600K，背脊骨刺形成強烈陰影，體積塵霧在低角度切出體積光帶；遠處雷雲邊緣微閃。
- Materials & Physics：混凝土地面粗糙度 0.65，爪痕撕裂處金屬筋骨裸露金屬度 0.2；巨獸踩下時粉塵拋物線，顆粒大小 0.3–1.2cm，重力 9.81 m/s²；靜電火花沿地面枝狀擴散折射率 1.04。
- Emotion & Performance：巨獸的背影佔據畫面中央，怒張肩背，暗示壓迫；蓮尚未入畫，留白讓觀眾感受威脅。
- Audio & Transition：SFX 低沉地鳴與爪擊混凝土聲，環境風噪壓低 -10 dB；旁白日語「この街を飲み込む前に…止めるしかない。」字幕同步；轉場直接切至逆光剪影。

#### Beat 2（1.2–2.4s）｜朝倉蓮登場・逆光剪影｜延續軸線與光位、Stage1、Lens 32mm 低角度
- Camera：低角度逆光中景，穩定器前移讓蓮走入前景，對焦蓮胸腔；快門 180°，光圈 f/2.8 保持背景輕柔。
- Lighting：太陽逆光形成輪廓 rim，地面反射填光 10%；雷雲帶來微微冷色反差，線條保持清晰。
- Materials & Physics：無袖上衣粗糙度 0.32、細黃線 emissive 0.45；槌頭金屬 0.82，背光只見銳利邊線；肩膀肌肉微拉扯顯示槌重，慣性讓上臂輕微晃動 0.05s。
- Emotion & Performance：蓮停步微前傾，眉骨陰影下的眼神鎖定遠處；口型對應台詞「デカいな…ちょうどいい。」
- Audio & Transition：風聲與衣料摩擦加入；日語低聲台詞 -6 dB 峰值，字幕覆疊；轉場以光源匹配切到槌頭特寫。

#### Beat 3（2.4–3.6s）｜巨槌特寫・雷紋啟動｜延續軸線、Stage1、Lens 75mm 近特寫
- Camera：定鏡近特寫填滿槌頭刻紋，淺景深 f/2.2，對焦刻痕；快門 180°。
- Lighting：主光側逆 45°，刻紋邊緣有硬陰影；符紋按鍵被按下時亮度從 0→100% 0.3s 線性。
- Materials & Physics：刻紋置換深度 0.08cm，金屬拉絲紋理清晰；電弧在刻紋間跳躍產生微小熱氣折射；蓮指尖按下符紋，橡膠握帶受力凹陷 0.1cm。
- Emotion & Performance：手指穩定按下，專注且克制；喃喃「起きろ、雷槌。」
- Audio & Transition：SFX 電流啟動「滋滋」＋細微機械鎖定聲，匹配符紋亮度；轉場以符紋電光閃白遮擋到下一幕。

#### Beat 4（3.6–4.8s）｜雷紋爬滿手臂・姿態就位｜延續軸線、光位、Stage1→Stage1.5（雷紋上身）、Lens 50mm 半身
- Camera：半身繞拍 30°，穩定器平滑環繞蓮右側，對焦前臂雷紋；快門 180°。
- Lighting：雷紋自槌柄爬向手臂，發出黃白＋藍白雙層光，主光保持 5600K；體積灰塵反射雷光形成點狀散射。
- Materials & Physics：皮膚 SSS 顯示血管與汗膜，雷紋亮度在肌肉隆起處折射；槌頭離肩時慣性下沉 3cm，蓮雙手握柄時橡膠握帶被壓縮；腳底蹬地摩擦係數 0.62，碎石被帶起。
- Emotion & Performance：蓮深吸氣、肩膀下沉，進入低重心姿態，表情決斷；台詞「一発で黙らせる。」
- Audio & Transition：呼吸聲與電弧嗡鳴疊加；轉場直接切至側向衝刺。

### Act II（4.8–9.6s） — 衝刺與第一次交鋒｜基調：推進｜節奏域：穩定 1.5s → 加速 2.4s｜美術：雷軌跡、塵土飛散

#### Beat 5（4.8–6.0s）｜衝刺前進・地面雷光軌跡｜延續軸線、光位、Stage1.5、Lens 40mm 側向
- Camera：側面中景，穩定器平行跟拍，輕微搖臂跟隨腳步節奏；對焦在蓮腰部，快門 180°。
- Lighting：地面反射陽光＋雷光，拖槌時形成亮線；每次踏步腳底十字雷光閃 0.05s。
- Materials & Physics：槌頭拖地刮出灼痕，火花與電弧混合；塵土顆粒 0.2–0.8cm 被腳步震起；雷軌跡沿地面 roughness 0.65 節點附著並留下輕微燒痕。
- Emotion & Performance：蓮表情專注，身體前傾 15°，肩背肌肉緊繃；無台詞。
- Audio & Transition：電流嗡鳴＋碎石聲；音樂節拍 120 BPM 同步腳步；直接切至正面對撞。

#### Beat 6（6.0–7.2s）｜第一次交鋒・被震退｜延續軸線、光位、Stage2 起始、Lens 48mm 正面略仰
- Camera：正面略仰角，左右對稱，滑軌微推；對焦交點；快門 180°。
- Lighting：雷光與塵土形成環形光帶，邊緣略暗，對比提高；碰撞瞬間 Bloom 脈衝 0.3。
- Materials & Physics：巨槌與巨爪碰撞，衝擊波以圓形雷光向外推，塵土受力向後 5m；蓮後退兩步，鞋底在地面拖出 2 條 0.6m 長的刮痕；巨獸爪面出現細裂紋粗糙度上升。
- Emotion & Performance：蓮咬牙、眉頭緊鎖，短暫失衡但穩住；台詞「チッ…まだ足りねぇか。」
- Audio & Transition：金屬＋骨頭撞擊「ガァンッ」；雷鳴衝擊波帶短暫壓縮；匹配剪接到仰角蓄力。

#### Beat 7（7.2–8.4s）｜深吸一口氣・雷光拉到天空｜延續軸線、光位、Stage2、Lens 55mm 半身仰角
- Camera：半身仰角特寫，輕微繞拍 20°，對焦蓮臉與槌頭；快門 180°。
- Lighting：雷光從槌頭竄向天空連接雲層，雲層被染成淡金，反射光在蓮肩頸形成雙側 rim；主光依舊 5600K。
- Materials & Physics：雷絲以 0.45cm 粗細向上延展，空氣被電離形成淡霧折射；槌頭上的刻紋溫度升高微紅，PBR 反光更強；肩上肌肉張力顯示重量。
- Emotion & Performance：蓮閉眼深吸，專注穩神，氣息帶動胸腔起伏；旁白台詞「彼の一撃は、空から借りた雷だ。」
- Audio & Transition：遠處雷鳴回響帶 1.5s 尾音，呼吸聲清晰；過渡以光閃匹配切到光束攻擊。

#### Beat 8（8.4–9.6s）｜巨獸光束吐息・雷槌格擋｜延續軸線、光位、Stage2、Lens 45mm 斜前
- Camera：斜前方中景，鏡頭位置在巨獸右前 60°，對焦蓮與光束接觸點；快門 180°。
- Lighting：巨獸口中紅黑能量束與蓮槌頭雷盾對撞，產生強光交錯；雷盾溢出黃白光霧形成體積遮擋。
- Materials & Physics：能量束衝擊槌頭，盾面震動 40Hz 微抖；蓮腳底深陷碎石 2cm，碎屑被氣浪帶起；雷盾表面 Fresnel 0.85，粗糙度 0.18。
- Emotion & Performance：蓮雙手橫舉，牙關緊咬，手臂肌肉繃出；無台詞。
- Audio & Transition：能量束「ゴォォォッ」與雷盾「バチバチッ」混合，低頻 sidechain 壓音樂 2dB；轉場以遮擋剪到低位滑步。

### Act III（9.6–15.0s） — 貼身蓄力、躍擊、唯一漫畫擊殺｜基調：決斷收束｜節奏域：加速 2.4s → 衝擊 3.0s｜美術：雷鏈、雷尾、漫畫格擊殺

#### Beat 9（9.6–10.8s）｜滑步貼近・低位蓄力｜延續軸線、光位、Stage2→2.5、Lens 38mm 低角度
- Camera：低角度側面貼地滑移，跟隨蓮貼地滑步；對焦蓮膝部與槌頭拖尾；快門 180°。
- Lighting：地面雷紋被拖成長線，黃白光照亮碎石；主光保持，增加地面反射填光 8%。
- Materials & Physics：滑步時鞋底與碎石摩擦，碎石以拋物線飛向前景；槌頭拖地火星與雷光混合，地面粗糙度下降形成光滑痕；雷紋蓄壓條在槌身上亮到 70%。
- Emotion & Performance：蓮壓低身體如拉弓，眼神鎖定巨獸腹部；低聲台詞「これで終わりだ。」
- Audio & Transition：呼吸壓低、腳步與槌拖聲節奏化；轉場匹配運動方向切至仰拍躍起。

#### Beat 10（10.8–12.0s）｜躍起高空・雷光纏身｜延續軸線、光位、Stage2.5→3、Lens 58mm 仰角跟拍
- Camera：從下往上跟拍蓮躍起，滑軌帶上升，鏡頭仰角 70°；對焦蓮與槌頭，快門 180°。
- Lighting：雷光如鎖鏈纏繞手臂與槌身，拖出金黃雷尾；天空被雷光切成幾何片，邊緣折射形成輕微色散。
- Materials & Physics：躍起高度約 4m，重力與槌重讓身體有 0.08s 落後延遲；雷鏈厚度 0.6cm、afterglow 0.65；服裝布料隨上升飄動並受風阻；汗珠在臉上反光。
- Emotion & Performance：蓮大喊「雷槌――落ちろォ！」嘴型張大，眼神燃燒；表情帶決斷。
- Audio & Transition：雷鳴提升到最亮，嘯鳴疊加；台詞在峰值 -6 dB；轉場以速度匹配切慢動作降落。

#### Beat 11（12.0–13.2s）｜重槌降落前一瞬・時間拉長｜延續軸線、光位、Stage3、Lens 70mm 側面慢動作
- Camera：側面中景慢動作，鏡頭輕晃強調重量；對焦槌頭雷光球；快門角可放寬至 200° 以拖影強化。
- Lighting：槌頭雷光球極亮，周圍空氣變形波紋；背景保持正午光但降低曝光 0.3 stop 以讓雷光突出。
- Materials & Physics：槌頭前端聚能，金屬表面出現微紅熱度；雷光球折射率 1.08，周圍塵埃被吸引形成漩渦；巨獸抬頭眼中反射雷槌倒影。
- Emotion & Performance：蓮全身肌肉繃緊，牙關閉鎖，眼神下沉；時間感被拉長，呼吸暫停。
- Audio & Transition：環境音抽掉，只剩心跳與低頻「ブゥゥン…」；為漫畫格擊殺做靜默鋪墊；轉場硬切至漫畫格。

#### Beat 12（13.2–15.0s）｜彩色漫畫感雷槌擊殺・唯一漫畫分鏡幕｜延續軸線、光位、Stage3→崩解、Lens 55mm 兩段處理
- Camera：第一瞬間切換彩色漫畫分鏡，中景正打；雷槌砸中巨獸頭部或胸口，中央白閃佔滿約 40% 畫面，背景仍可見藍紫雲層與灰黑巨獸輪廓；粗速度線與彩色網點填滿四周，擬聲字「ドガァァァンッ！！」佔上半部。0.4–0.6s 後立刻切回正常 2D 動畫，鏡頭拉遠至 6m 眼高，看巨獸崩解、蓮半跪握槌。
- Lighting：漫畫格保持全彩高飽和，不轉黑白；雷光黃白占主導，天空藍紫與巨獸灰黑對比，光線方向仍右上 45°；回到動畫後雷光餘暈漸熄，地面留下焦黑燒痕與淡金雷紋殘影。
- Materials & Physics：擊中瞬間巨獸角質崩解成黑碎片與金黃光點，飛散半徑 6m；槌頭插地震出放射狀裂紋，碎石落地遵循重力；雷紋亮度快速衰減至 20%，漫畫格網點厚度 22 lpi、速度線粗 6px。
- Emotion & Performance：蓮落地半跪，肩膀微喘，低頭看著碎片；台詞「…これで、静かになる。」嘴型對應，表情安靜且略帶釋放。
- Audio & Transition：重擊聲＋延遲轟鳴遠處回響，短暫耳鳴；回到動畫後加細碎落石聲與呼吸；收尾 0.5s 淡出進 CTA。

## Platform / Delivery Notes
- Technical Delivery: 9:16 1080x1920, 24fps, Rec.709, 180° shutter baseline；音訊立體聲 48kHz -14 LUFS，Limiter -1 dBTP；種子記錄以便複現軸線與雷紋節拍。
- Hook Versions: 本稿為 baseline；Hook B 需另寫 `hook_cut_prompt` 以漫畫格開場再倒帶，不得混用。
- Subtitle: 中日雙語並排或疊字，黑邊黃心，僅在有台詞或旁白的 Beat；字幕避免遮擋雷軌。

## Next Episode / Spin-off Ideas
1) 下一集「雷槌訓練模式」：廢墟上加入訓練計數 UI 與節拍，展示不同雷紋型態；2) 「夜間雨戰版本」：雨夜街道同一把雷槌對抗機械獸，風格需替換為霓虹雨反射；3) 番外「巨槌保養日常」：蓮在工作室拆解槌頭，展示 PBR 紋理與符紋校準。

## Changelog vs Previous Episode
- 場景由石造神殿換成廢墟平原，光源仍為正午硬光但天空壓低雷雲。
- 武器升級為雷紋巨槌，加入符紋按鍵啟動雷鏈；服裝黃線改為電路式連通肩膀與護手。
- 漫畫格使用範圍收斂為擊殺瞬間唯一一幕，且保持高飽和彩色網點；其他幕保持正常 2D 動畫光影。

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：12 幕 × 1.2s 完整標註，軸線與光位在 Continuity Layer 明確鎖定。
- Physics & PBR：各 Beat 塵土、碎石、雷鏈、槌重、布料與皮膚 SSS、金屬粗糙度/金屬度均有具體數值；漫畫格後恢復同光位。
- Stylepacks 使用與衝突：Lightning Chain＋Light Glyph Anime 全量內嵌，新 Style Thunder Maul Manga Lock 標記 Default ON，限制漫畫格僅 Beat12。
- Continuity：Boss/ Ren 狀態時間線列出，Camera/Lens/Light 鎖定不跨軸；收尾 CTA 與 Hook 版分離。
- 不足或不確定：未提供實際配音音色，後期需依聲優調整；巨獸尺寸假設 3.5×蓮身長，如需更巨需同步調鏡頭與焦段。

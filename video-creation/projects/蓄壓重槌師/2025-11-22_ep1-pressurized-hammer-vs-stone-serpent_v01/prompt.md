# 蓄壓重槌師 EP01 — 朝倉蓮 vs 石甲巨蛇 BOSS PV Prompt（15s｜12 幕｜9:16 直式）

來源劇本：scripts/2025-11-22_pressurized-hammer-vs-stone-serpent_v01/script.md

## Input Registry
- project_name: 蓄壓重槌師
- series_name/arc: 蓄壓重槌師・白日神殿線
- episode_index: 1
- slug: pressurized-hammer-vs-stone-serpent_v01
- target_platform: TikTok / Reels / Shorts
- duration_sec: 15
- style_primary: Light Glyph Anime Look（黑＋黃正午漫畫化強化）
- style_secondary: Zenith Noon Real Look（壓力感過曝光比，用於黑黃衝擊波曝光）
- worldstate_ref: 廢棄石造神殿、正午強光、石甲巨蛇盤踞破柱
- goal: 以蓄壓節奏＋黑黃衝擊波呈現訓練組數感，漫畫格擊殺收尾

## 一句話題材
正午岩地的廢棄神殿前，蓮穩步點亮黑黃戰紋，頂著毒霧蓄力，最後以漫畫格衝擊波把石甲巨蛇擊倒。

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

## Stylepacks

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
  - 線條乾淨，HUD 不吞線。
  - 冷灰霧藍主調，金黃薄荷點綴。
  - HUD 玻璃質感，臉部清晰。
  - 施法時眼與銀線脈動光。

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
  - 對話 -6 dB，HUD -12 dB。
  - 鍵擊聲與手指同步。
  - 高潮加強 4kHz 空氣感。

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
  - HUD 稍遲滯，光帶依揮手。
  - 蜂巢盾破碎立刻重排。
```

### Style: Hammered Noon Manga Burst（Default ON）
- Applicable: 正午黑黃重槌、漫畫格收尾 2D PV。
- Do NOT mix: 夜景霓虹或血腥破皮寫實。
- Visual: 黑線＋金黃；5500–5800K 硬光；漫畫格黑白速度線；PBR：石甲粗糙0.75/金屬0，槌金屬0.8粗糙0.18，戰甲法線0.35，護膝粗糙0.42。
- Audio: 重鼓100–108BPM；sub hit＋石屑爆聲；漫畫格耳鳴0.2s。

## Continuity Layer（連貫性）
- Axis：神殿在上，蓮右、蛇左；鏡頭在蓮右後 120° 弧線，不跨軸。
- Lenses：Act I 24–35、Act II 35–50、Act III 50–75mm，三秒內不跳遠近。
- Light：太陽右上45°，影向左下；漫畫格可短暫黑白。
- Boss：0–4 完整；4–8 裂片→大裂；8–15 裂紋發光，擊殺碎滿地。
- Ren：蓄壓條0–4微光、4–8 逐亮、8–12 滿格閃、擊殺清零；護膝6–9 警示，結尾微閃。
- Hook：baseline 線性，hook 版另檔。
- Beat：開頭先說延續軸/光，再寫唯一改動。

## Technical Specs
- 9:16｜24fps｜180°｜F2.8；
- Lenses 24/35/50/75；
- 色調 log→filmic，陰影微藍，高光暖，去飽和6%；
- 手持≤3%，粒子壓縮安全；
- 聲音 -14 LUFS，重鼓對齊腳步與槌擊。

## Platform Layer
- Hook A：蓄壓條逐亮配腳步「ドン」。
- Hook B：漫畫格「ドゴォン」0.8s。
- Caption：右側黑黃竪排標題。
- Thumb：蓮右、蛇左、衝擊波居中。

## Master Prompt
- 15s、2D 日系、9:16、24fps、黑黃硬光。
- 場景：廢石神殿、熱浪岩地、破柱塵土。
- 角色：朝倉蓮，黑甲＋黃護膝，黑黃戰槌。
- 敘事：蓄壓行進→兩槌→慢動作終槌＋漫畫格。
- 物理：重力9.8；摩擦0.6；毒霧左偏；衝擊波地面360°。
- PBR：石地粗糙0.7/金屬0；槌金屬0.82粗糙0.18；戰甲法線0.32；護膝粗糙0.45。
- 光：5600K 硬光，邊光金白；熱浪折射1%。
- 聲：風＋重鼓；衝擊波 sub hit；漫畫格耳鳴0.2s。
- 轉場：硬切；Beat08 羽化；Beat11 匹配剪 Beat12。

## Acts / Beats / Angles（12 幕 x 1.2s）

### Act I（0.0–3.6s） 建立｜節奏 1.5–2.0
- 美術：曬白石階、破柱、毒霧淡綠、黑黃主色。

Beat 01（0.0–1.2）
- 延續軸線，俯視 24mm 建立；S1；光源右上。
- Camera：滑軌俯視，層次拉焦；快門180。
- Lighting：硬光 5600K，影向左下；熱浪微折射。
- Materials & Physics：石甲粗糙0.75，毒霧衰減1.2s。
- Emotion & Performance：蛇壓低蓄勢；蓮未入畫。
- Audio & Transition：風＋「ドン」；硬切。

Beat 02（1.2–2.4）
- 延續軸線，低角 35mm 拉近蓮；S1。
- Camera：穩定器上推；單點蓮胸；快門180。
- Lighting：右肩邊光金白；汗反光。
- Materials & Physics：戰甲法線0.32；護膝0.45；腳步摩擦0.6。
- Emotion & Performance：踏階穩重。
- Audio & Transition：第二聲鼓；硬切。

Beat 03（2.4–3.6）
- 延續光位，蛇頭近景 35mm；S1。
- Camera：推近口部；對焦牙尖。
- Lighting：硬光在牙縫；口腔陰影。
- Materials & Physics：毒霧透明0.6，折射0.05。
- Emotion & Performance：蛇噴霧威脅。
- Audio & Transition：噴氣＋鼓；硬切。

### Act II（3.6–10.8s） 對打｜節奏 2.0–2.6｜焦段 35–50mm
- 美術：黑黃蓄壓紋、裂紋、石屑。

Beat 04（3.6–4.8）
- 延續 Beat03 軸線，側面 35mm；S1。
- Camera：側移胸高；對焦步伐。
- Lighting：右上硬光；蓄壓紋微亮。
- Materials & Physics：腳踩裂紋，石屑飛；熱浪0.01。
- Emotion & Performance：組數步伐；蓄壓20%。
- Audio & Transition：步步「ドン」；硬切。

Beat 05（4.8–6.0）
- 延續，原位推 50mm 仰角；S1→2。
- Camera：推近肩；對焦眼。
- Lighting：背光邊緣金白；背景暗。
- Materials & Physics：槌金屬0.82粗糙0.18；蓄壓70%。
- Emotion & Performance：深吸，專注。
- Audio & Transition：鼓加快；硬切。

Beat 06（6.0–7.2）
- 延續光位，3/4 中景 35mm；S2。
- Camera：橫砸拍點；對焦槌頭。
- Lighting：硬光閃白2frame；影保持。
- Materials & Physics：衝擊波360°，石碎彈跳；摩擦0.6。
- Emotion & Performance：第一槌穩；蛇震偏。
- Audio & Transition：重低音「ドゴン」；硬切。

Beat 07（7.2–8.4）
- 延續軸線，近景 50mm；S2。
- Camera：跟拍旋身；快門172 殘影。
- Lighting：邊光更強。
- Materials & Physics：裂紋擴散，碎石噴飛。
- Emotion & Performance：咬牙第二槌。
- Audio & Transition：雙重鼓；硬切。

Beat 08（8.4–9.6）
- 延續位置，膝近景 50mm；S2。
- Camera：胸高微搖；對焦護膝。
- Lighting：同光位，護膝紅黃閃。
- Materials & Physics：護膝0.45；膝微抖。
- Emotion & Performance：皺眉調姿。
- Audio & Transition：靜音＋心跳；羽化。

Beat 09（9.6–10.8）
- 羽化後正面仰 50mm；S3 準備。
- Camera：上揚；對焦眼。
- Lighting：背光過曝輪廓；蓄壓滿格閃。
- Materials & Physics：汗折射；UI 全亮。
- Emotion & Performance：微笑「最後一組」。
- Audio & Transition：半拍停再重鼓；硬切。

### Act III（10.8–15.0s） 高潮收束｜節奏 1.8→慢動作｜焦段 50–75mm
- 美術：黑黃光弧、漫畫格速度線、碎石雨。

Beat 10（10.8–12.0）
- 延續 Beat09，慢動作 75mm；S3。
- Camera：繞拍120°；對焦槌頭；快門200。
- Lighting：硬光持續，光弧拖尾。
- Materials & Physics：光軌＋熱浪；UI 滿格動畫。
- Emotion & Performance：跨步蓄力。
- Audio & Transition：鼓重返，心跳感；硬切漫畫格。

Beat 11（12.0–13.2）
- 漫畫格模式，左右保持；S3。
- Camera：50mm 特寫撞擊。
- Lighting：速度線黑白，中心彩色。
- Materials & Physics：石甲炸裂圓環，衝擊波分格；耳鳴0.2s。
- Emotion & Performance：全力揮擊。
- Audio & Transition：巨響「ドゴォン」＋耳鳴；匹配剪回 Beat12。

Beat 12（13.2–15.0）
- 回正常色，拉遠 35mm；S3 結束。
- Camera：中遠景後退；對焦蓮。
- Lighting：陽光穿塵，影一致。
- Materials & Physics：碎石遍地，護膝微閃。
- Emotion & Performance：呼氣站穩，留台詞空位。
- Audio & Transition：風聲＋輕鼓尾；黑黃淡出。

## Negative Instructions
- 不要血腥或斷肢；不要品牌 Logo；不要過度魚眼或搖晃；
- 請保持 PG-13；漫畫格閃白不超過 2 frame；
- 不要夜景或霓虹色溢出；避免可讀文字。

## Physics / Color / Delivery
- 衝擊 impulse 900N；熱浪折射層 0.3–1.2m；毒霧重力30%、擴散0.8；衝擊波 sprite 16x16 隨音量增 bloom。
- 配色：黑#0b0b0f、黃#ffc400、岩地#b8b1a5、毒霧#6c7a6f；蓄力條10格：Beat04–05 逐亮、Beat09 滿格、Beat11 清零；擬聲字粗黑框＋金黃光。
- 交付：PG-13；1080x1920；-14 LUFS；字幕安全區 10%；檔名 pressurized-hammer-ep01_master.mp4，附 LUT/粒子設定。

## QA Runbook（精簡）
- 時間碼：12 幕×1.2s（01–12）。
- LUT filmic，高光 <0.98，黑線銳度保留；粒子 <45k；鼓點峰值 -4 dB，耳鳴 -12 dB，毒霧 3–6kHz。

## AGENT Self-Check
- 結構：Master、Act/Beat/Angle、時間碼齊全。
- Physics & PBR：每 Beat 註明衝擊波、材質、重力、法線、粗糙度。
- Stylepacks：Light Glyph Anime 全文內嵌，Hammered Noon Manga Burst ON，無衝突。
- Continuity：軸線、光位、鏡頭距離、Stage 時間線皆鎖定；Hook 分離。
- 交付：9:16、24fps、PG-13、音畫同步與 LUT 設定列出。
- 風險：無跨軸；漫畫格僅 Beat11；粒子與顏色均控壓縮安全。

































































































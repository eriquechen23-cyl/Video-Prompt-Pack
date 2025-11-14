# Yecheng First Encounter — Master Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-14_yecheng-first-encounter_v01/script.md

## 一句話題材
燁程在陌生異世界苔岩間甦醒，仰望紫藍裂天與光之電路板時，森林中逐步亮起綠眼怪群，逼得他啟動光迴路術師職業初始化。

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

### Style Pack：Circuit Mage Arrival Look（`_stylepacks/circuit_mage/look.yml`）
```yaml
name: Circuit Mage Arrival Look
noise_reduction: neon_edge_cleanse
saturation: balanced_glow_skin
contrast_profile: luminous_midnight
color_palette:
  primaries: [cobalt_blue, electric_gold, smoked_slate]
  accents: [frosted_teal, warm_white]
  skin_tone: resilient_warm_amber
light_behaviour:
  rim_light: holo_trace
  bounce_fill: cool_gradient
line_enhancement: semi_soft_outline
motion_blur_shutter: 180
texture_pass: woven_carbon_mesh
notes:
  - 強調黑色與深藍服飾上的冷藍反光，保持金線路細節清晰。
  - 膚色維持小麥暖調，黑眼圈僅留柔和陰影，不要過度泛青。
  - 施法時金色線條需在眼睛與衣內銀路上產生同步閃爍。
  - 城市光源以低飽和霧霾藍＋暖白晶體對比，避免雜訊。
```

### Style Pack：Circuit Mage Arrival VFX（`_stylepacks/circuit_mage/vfx.yml`）
```yaml
name: Circuit Mage Arrival VFX
niagara_presets:
  - circuit_thread_launch
  - portal_ribbon_fold
  - hexshield_microburst
unity_vfx_graph:
  - CircuitMage.LightCompile.vfx
  - CircuitMage.HexShieldPop.vfx
houdini_flipbooks:
  - lightcode_stream_wrap
  - cat_starflare_pulse
shader_controls:
  iris_glow_trace: 0.58
  circuit_line_thickness: 0.34
  portal_warp_intensity: 0.67
  hud_ring_opacity: 0.42
bloom_profile:
  idle: 0.12
  channeling: 0.65
  release: 0.28
light_trail:
  tail_length: 0.55
  decay_speed: 0.36
static_charge_particles:
  density: 0.48
  color_mix: [electric_gold, frost_blue]
audio_sync_hooks:
  iris_ping: sync_to_mid_high
  portal_whoosh: sync_to_low_mid
  hud_scroll: sync_to_highspark
  cat_purr_flux: sync_to_low_rumble
notes:
  - 請確保金色線路在 HUD 展開時沿左手環逐格亮起，與胸前光晶同頻。
  - 入口炸裂需保留 0.2s 無聲光閃後再釋出電流噼啪，避免過曝。
  - 貓尾星火補魔時，尾端粒子向術師胸口流動形成細緻弧線，最後收束於光晶。
```

### Style Pack：Circuit Mage Arrival Audio（`_stylepacks/circuit_mage/audio.yml`）
```yaml
name: Circuit Mage Arrival Audio
core_layers:
  - midnight_city_air
  - console_key_ghosts
  - arcane_hum_loops
  - feline_star_purr
  - portal_low_riser
peak_events:
  - timestamp: hud_activation
    sfx: crystalline_ui_spin
    level_db: -8
    stereo_width: 130
  - timestamp: portal_burst
    sfx: circuit_warp_slam
    level_db: -5
    stereo_width: 150
  - timestamp: landing_impact
    sfx: echoing_bootfall
    level_db: -7
    stereo_width: 110
  - timestamp: mana_transfer
    sfx: starlit_particle_flow
    level_db: -9
    stereo_width: 90
sidechain:
  trigger_bus: portal_burst
  target_bus: ambience
  reduction_db: 4.5
low_freq_management:
  lfe_focus_hz: 48
  sub_trim_db: -10
mix_notes:
  - 鍵盤敲擊節奏需與術師指尖動作對拍，音量低於 -18 dBFS 作為記憶殘響。
  - Portal 爆裂後 0.3s 內加入帶空氣感的風噪以銜接異世界聲景。
  - 米漿心電感應聲採用慵懶男中音帶柔性混響（0.6s），在 Act III Beat 06 內提示詠唱節奏並保持內心旁白質感。
  - 燁龍基底詠唱錄製為清晰男中音，多段停頓需對應 HUD 語法亮度；字句峰值控制在 -14 dBFS 並於命中瞬間觸發次低頻推力。
  - 當尾巴星火補魔時，加入高頻顆粒閃爍聲並漸強至 -12 dBFS 後快速衰減。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Circuit Mage Anime 2D｜2.39:1｜24fps｜濕霧光迴路質感)
「暮色後的異世界苔岩盆地；紫藍裂縫天空、電路雲層、濕冷黑樹；燁程穿著皺襯衫甦醒並被綠眼怪群包圍，逼出光迴路術師初始化。
鏡頭：開場28mm 滑軌斜俯貼近地表→32mm 穩定器繞肩抬仰→35mm 仰視切換到POV掃描，緊張段落以55mm 手持<=3% 追隨怪物出場，最後65mm 微推鎖定 UI。
表演：燁程由迷惘、吐槽到冷汗戒備，視線在天空→樹影→虛空 UI；身體先撐起坐姿，再半蹲後退。
臉型/髮型：黑色短髮睡亂、眼下淡黑眼圈、領帶歪斜；膚色偏小麥帶潮濕光澤。
構圖：前景苔蘚與藤蔓、燁程居中偏左，怪物與裂縫佔後景層，保留15% 上方留白給 UI；動態：霧氣、樹葉震動、骨粉脫落、光電迴路流動。
寫實細節：襯衫沾泥與苔點、手掌黏濕砂礫、天空電流沿裂縫流轉、怪物骨板泛銹紅粉屑、UI 以 HUD 玻璃脈動。
無字幕、無商標/Logo/水印。」

鏡頭語法：28 建立空間｜32 繞肩覺醒｜35 POV 掃描｜55 怪物親密｜65 UI 壓縮；
光圈 {T2.4–T3.2 過渡，恐懼段落收至 T3.5 保景深}；快門角 {180° 全段；怪物震動段降至168°}；
對焦 {層次前→中→後／單點眼於燁程→呼吸拉焦至怪物眼→層次拉焦骨甲與 UI}。
光影：霧中側逆光＋裂縫天藍頂光，怪物出場附帶霧帶入體積光；色溫 {夜間霧藍3600K 混電弧4200K}；
對比 {柔轉中高}；眼神光 {由上方裂縫補一點反射}。
色調/LUT：陰影霧藍、苔蘚濕綠去飽和5%，骨甲銹紅與 UI 金青保留飽和，膚色維持暖琥珀。
聲音：midnight_city_air 混入潮濕風聲，arcane_hum_loops 與 console_key_ghosts 低頻對應天空電路，feline_star_purr 作為記憶殘響；circuit_warp_slam 於怪物踩地觸發，starlit_particle_flow 與 crystalline_ui_spin 對應 UI 彈出；音樂維持 96BPM 氛圍弦樂暗流。
轉場：泥粒飛濺遮擋→樹幹擦過鞭移→電弧閃光匹配→怪物骨粉羽化收束→HUD 漸顯。
安全：無可讀文字，UI 以符號與中文提示，怪物血跡控制為乾裂不流動。
```

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–6.0s）
意圖：建立燁程在異世界甦醒的困惑與環境落差
基調：驚惶迷惘
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：苔蘚岩地、濕潤砂礫、皺襯衫領帶、紫藍裂縫天空

#### Beat 1（0.0–2.4s）
重點：燁程甦醒並坐起
Blocking：燁程手抓苔蘚翻身→撐地坐起→整理領帶
Camera：
- 運鏡：28mm 滑軌斜俯由腳邊推至上半身
- 焦段/機位：28mm 膝高俯視→抬升至胸高
- 對焦：層次拉焦手指→臉
- 快門角：180；拍點：手抓苔蘚、身體坐起
光影：裂縫冷光作為背光，苔蘚反射青藍霧光
色調/LUT：陰影霧藍、襯衫去飽和5%，膚色暖琥珀
聲音：潮濕風聲、衣料摩擦、console_key_ghosts 微弱回響
轉場：燁程抬頭→Angle 2

Angle 1（0.0–1.2s）
構圖：前景苔蘚模糊，燁程中央偏左
內容：燁程側躺睜眼，手指抓砂礫
補充：苔蘚上水珠抖動
安全：無可讀字樣

Angle 2（1.2–2.4s）
構圖：三分線，燁程坐起置左
內容：燁程撐地坐起、理領帶
補充：領帶上泥點、呼吸霧氣
安全：服裝無Logo

#### Beat 2（2.4–4.8s）
重點：感知天空異常並吐槽
Blocking：燁程仰頭→站跪姿→吐槽
Camera：
- 運鏡：32mm 穩定器繞肩仰視
- 焦段/機位：32mm 眼高→仰角
- 對焦：單點燁程眼→呼吸拉焦天空電路
- 快門角：180；拍點：吐槽口型
光影：裂縫紫藍頂光，臉側被反射補暖
色調/LUT：天空高光偏電藍，雲層保霧感
聲音：arcane_hum_loops 隨電路增強，燁程低聲吐槽 -16 dBFS
轉場：吐槽語尾切至 POV

Angle 3（2.4–3.6s）
構圖：仰視中央，裂縫貫穿天際
內容：天空電路板閃動
補充：portal_ribbon_fold 沿裂縫流動
安全：無

Angle 4（3.6–4.8s）
構圖：中近景，燁程居右
內容：燁程皺眉吐槽 shader
補充：iris_glow_trace 微亮
安全：字幕無

#### Beat 3（4.8–6.0s）
重點：POV 掃描陌生森林
Blocking：視線左右掃→霧氣掠過
Camera：
- 運鏡：35mm 手持≤3% POV 左右擺動
- 焦段/機位：35mm 眼高
- 對焦：層次拉焦岩壁→樹幹→藤蔓
- 快門角：180；拍點：霧氣掠過
光影：霧中側光，藤蔓投影條紋
色調/LUT：濕綠偏冷，邊緣暈影
聲音：midnight_city_air 混森林濕氣聲，遠處獸吼預告 -20 dBFS
轉場：霧遮擋 → Act 2

Angle 5（4.8–6.0s）
構圖：POV 前景藤蔓半遮
內容：潮濕岩壁、黑樹、霧氣
補充：hud_ring_opacity 低亮粒子
安全：無

### Act 2（6.0–12.0s）
意圖：逐步揭示怪物威脅與包圍
基調：緊張恐懼
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：震動樹葉、綠光眼睛、骨甲瘦長怪

#### Beat 4（6.0–7.2s）
重點：第一聲低吼
Blocking：遠方樹影晃動→落葉震動
Camera：
- 運鏡：40mm 穩定器前推
- 焦段/機位：40mm 低角對樹線
- 對焦：層次拉焦霧→深處陰影
- 快門角：168；拍點：低吼爆點
光影：電弧閃亮樹幹，陰影中帶體積光
色調/LUT：陰影加深，霧藍偏冷
聲音：portal_low_riser 疊低吼，泥水震動聲
轉場：閃電照亮 → Beat 5

Angle 6（6.0–7.2s）
構圖：中央樹線
內容：樹梢抖動、落葉掉落
補充：static_charge_particles 隨低吼震
安全：無

#### Beat 5（7.2–9.6s）
重點：綠光眼睛陸續點亮
Blocking：單雙眼亮→鏡頭後拉顯更多
Camera：
- 運鏡：55mm 微推後拉
- 焦段/機位：55mm 眼高
- 對焦：單點第一雙眼→層次拉焦後排
- 快門角：168；拍點：每組眼亮起
光影：綠光映霧，樹幹受光形成斑駁
色調/LUT：背景壓暗，綠光保飽和
聲音：crystalline_ui_spin 低速化重製，錯誤提示節奏
轉場：最後一雙眼亮→Beat 6

Angle 7（7.2–8.4s）
構圖：三分線右側眼睛突出
內容：第一雙狹長綠眼
補充：iris_ping 對上亮起瞬間
安全：無

Angle 8（8.4–9.6s）
構圖：後拉廣角，眼睛分布全畫面
內容：多雙綠眼同時亮
補充：hud_scroll 軌跡在霧中掃過
安全：無

#### Beat 6（9.6–12.0s）
重點：怪物現身並包圍
Blocking：首隻踏出→更多怪物成半圓
Camera：
- 運鏡：55mm 手持≤3% 側移
- 焦段/機位：55mm 腰高偏右
- 對焦：單點首隻怪→呼吸拉焦燁程
- 快門角：168；拍點：腳踩泥、怪物互換視線
光影：裂縫藍光在骨甲上反射，側逆提升輪廓
色調/LUT：骨甲銹紅、泥地濕棕保持細節
聲音：circuit_warp_slam 變調為骨甲摩擦，portal_whoosh 低頻襯底
轉場：骨粉飛散遮擋 → Act 3

Angle 9（9.6–10.8s）
構圖：三分線左，怪物踏出
內容：骨甲怪露出全身
補充：light_trail 粒子沿指爪滴落
安全：血跡乾裂無液態

Angle 10（10.8–12.0s）
構圖：半圓構圖，燁程居中心
內容：三到五隻怪包圍
補充：decay_speed 控制粒子衰減
安全：無

### Act 3（12.0–15.0s）
意圖：強化壓迫感並引出職業初始化 UI
基調：恐懼決斷
節奏域：加速2.4–3.0 → 慢出0.8–1.5
美術要點：骨甲特寫、血鏽碎屑、光迴路 UI

#### Beat 7（12.0–13.2s）
重點：骨甲細節與呼吸聲
Blocking：鏡頭貼近骨板→碎屑落下
Camera：
- 運鏡：75mm 微推
- 焦段/機位：75mm 胸高
- 對焦：單點骨板→層次拉焦滴落碎屑
- 快門角：168；拍點：呼吸噴氣
光影：邊緣補光強調骨板高光
色調/LUT：銹紅飽和保持，背景壓暗
聲音：呼吸低頻、骨粉掉落、starlit_particle_flow 緩入
轉場：骨粉羽化 → Beat 8

Angle 11（12.0–13.2s）
構圖：極近特寫
內容：骨板裂縫、碎屑掉落
補充：static_charge_particles 伴碎屑
安全：血跡僅乾涸

#### Beat 8（13.2–15.0s）
重點：燁程退步並觸發 UI
Blocking：燁程後退一步→抬眼→UI 彈出
Camera：
- 運鏡：65mm 微推對焦臉→上移對準 UI
- 焦段/機位：65mm 眼高
- 對焦：單點眼睛→呼吸拉焦 UI
- 快門角：180；拍點：UI 彈出提示音
光影：裂縫光形成頂光，UI 自發金青光
色調/LUT：臉部暖琥珀，UI 金青高對比
聲音：arcane_hum_loops 增強，crystalline_ui_spin + starlit_particle_flow 疊加，呼吸急促
轉場：UI 光芒羽化收束

Angle 12（13.2–15.0s）
構圖：燁程中央偏左，上方留白給 UI
內容：燁程滿頭冷汗後退，UI 顯示「【職業初始化中：光迴路術師（Lv.1）】」
補充：hud_ring_opacity 由0.2→0.6，文字以電路筆畫描繪
安全：UI 僅顯中文提示，無商標

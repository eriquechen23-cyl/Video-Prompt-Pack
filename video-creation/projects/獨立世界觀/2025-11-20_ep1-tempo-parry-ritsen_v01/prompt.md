# Tempo Parry Showcase — Master Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-20_tempo-parry-ritsen_v01/script.md

## 一句話題材
城市決鬥場的夜空下，節拍格檔術士林律岑以節奏 HUD 讀取敵手攻勢，把魔法彈導成完美的光之螺旋，證明防禦才能掌控戰局拍點。

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

### Style Pack：Tempo Parry Beatshield Look（`_stylepacks/tempo_parry/look.yml`）
```yaml
name: Tempo Parry Beatshield Look
noise_reduction: tempo_edge_clean
saturation: cobalt_gold_balance
contrast_profile: sharp_mid_high
color_palette:
  primaries: [midnight_navy, graphite_charcoal, pulse_cyan]
  accents: [amber_gold, metronome_white]
  skin_tone: warm_bronze_precision
light_behaviour:
  rim_light: beat_synced_arc
  bounce_fill: stage_reflector
line_enhancement: precise_vector_outline
motion_blur_shutter: 172
texture_pass: woven_kevlar_mesh
notes:
  - 以深藍與石墨灰為基底，金色節拍刻痕需保持清晰筆刷感並沿衣緣依序點亮。
  - 半圓手套刻度環與 HUD 小節條必須能獨立調光，節奏強拍時升亮 15%。
  - 肌膚維持健康小麥色並保留汗光，避免過度去飽和造成蠟感。
  - 夜間決鬥場背景採冷藍氣霧，舞台燈打出節奏閃爍感，確保防禦光弧不被背景吞沒。
```

### Style Pack：Tempo Parry Beatshield VFX（`_stylepacks/tempo_parry/vfx.yml`）
```yaml
name: Tempo Parry Beatshield VFX
niagara_presets:
  - tempo_ring_spawn
  - beatshield_arc_swipe
  - metronome_echo_release
unity_vfx_graph:
  - TempoParry.ShieldCascade.vfx
  - TempoParry.FootstepNodes.vfx
houdini_flipbooks:
  - tempo_wave_slice
  - zero_beat_crack
shader_controls:
  beat_ring_opacity: 0.68
  hud_measure_scroll: 0.54
  parry_arc_length: 0.73
  footstep_glow_size: 0.45
bloom_profile:
  idle: 0.18
  channeling: 0.55
  release: 0.32
light_trail:
  tail_length: 0.48
  decay_speed: 0.41
static_charge_particles:
  density: 0.36
  color_mix: [pulse_cyan, amber_gold]
audio_sync_hooks:
  beat_click: sync_to_strong_hits
  shield_snap: sync_to_mid_accents
  heartbeat_drop: sync_to_zero_beat
notes:
  - 透明弧形護盾需呈半圓分段點亮，格檔瞬間留下 2 frame 的金色光帶。
  - 《六連・回聲環》腳步光圈與地面符文必須對齊，粒子沿腳步方向延遲 0.08s 才衰減。
  - 《零拍反擊》時，請在空中魔法彈邊緣加入細裂紋與倒流粒子，顏色略帶灰白以示靜音狀態。
```

### Style Pack：Tempo Parry Beatshield Audio（`_stylepacks/tempo_parry/audio.yml`）
```yaml
name: Tempo Parry Beatshield Audio
core_layers:
  - arena_low_rumble
  - pulse_drum_quarter
  - hud_tick_hicut
  - shield_sheen_air
  - zero_beat_heart
peak_events:
  - timestamp: parry_chain
    sfx: crystalline_clack_snap
    level_db: -7
    stereo_width: 120
  - timestamp: footstep_guard
    sfx: resonant_floor_ping
    level_db: -9
    stereo_width: 90
  - timestamp: zero_beat_release
    sfx: vacuum_heart_drop
    level_db: -6
    stereo_width: 140
sidechain:
  trigger_bus: pulse_drum_quarter
  target_bus: ambience
  reduction_db: 3.5
low_freq_management:
  lfe_focus_hz: 52
  sub_trim_db: -8
mix_notes:
  - BGM 設定 110BPM，四拍主鼓需與 HUD 強拍同步並留 0.1s 漸弱尾巴給格檔聲穿出。
  - 《六連・回聲環》腳步需加入金屬踏點與空腔共鳴，音量高於環境 3 dB。
  - 《零拍反擊》把所有層級快速抽掉，只保留心跳與單次吸氣聲，結束後以 shield_sheen_air 輕刷帶回音場。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Tempo Parry Anime 2D｜16:9｜24fps｜節奏感 HUD 光盾質感)
「近未來魔導都市夜間決鬥場；圓形符文場地、電弧雲、觀眾席霧光；林律岑以節拍格檔術讀取敵方攻勢，把魔法彈導成光之螺旋並反擊。
鏡頭：開場 26mm 俯視滑軌→30mm 仰視特寫→45mm 側向推移→32mm 俯視腳步→36mm 繞拍子彈時間→55mm 正面壓縮爆發，手持≤2% 用於心跳慢速段。
表演：律岑從深呼吸校準到冷靜微笑，視線鎖住對手攻擊節奏，手腕如指揮家打拍；台詞僅於反擊前輕聲說出宣示句。
臉型/髮型：短黑髮偏側瀏海、小麥膚色、深琥珀瞳孔收縮，眼下淡陰影。戴半指手套、半圓刻度環、細長耳掛與節拍器墜飾。
構圖：前景符文與 HUD 弧線、主體居中偏右，敵方魔法弧線佔後景，留白 15% 給 HUD；動態：電弧雲緩慢流動、觀眾席光點閃爍、護盾依節拍亮滅、腳步踩亮地圈。
寫實細節：外套不對稱金色刻痕沿著節拍順序亮起，半透明弧形護盾有玻璃質感並留短暫光帶，地面金屬石混材反射藍金色，HUD 小節條以 Icon 呈現拍點。
無字幕、無商標/Logo/水印。」

鏡頭語法：26–32mm 建立空間與 HUD｜45–55mm 捕捉格檔節奏｜65mm 等效壓縮用於光球收束；
光圈 {T2.4–T3.5；零拍段落收至 T3.8 以提升景深層次}；快門角 {全段 180°，子彈時間降至 150°，爆發段 172°}；
對焦 {單點眼→呼吸拉焦護盾→層次前中後追光球}。
光影：夜間冷藍基底＋側逆暖金 rim，體積光沿觀眾席打節奏閃，零拍段落短暫降低環境光 20%；色溫 {夜 3400K 混 4200K 電弧}；
對比 {中高}；眼神光 {由護盾反射補亮}。
色調/LUT：陰影微藍、護盾高光暖金、膚色優先保留血色，去飽和 4%。
聲音：arena_low_rumble 與遠方觀眾拍手為環境，pulse_drum_quarter＋hud_tick_hicut 對拍護盾亮滅，crystalline_clack_snap 與 shield_sheen_air 疊合格檔音，zero_beat_heart 在子彈時間放大，vacuum_heart_drop 觸發零拍切換。
轉場：霧氣 wipe→HUD 閃光匹配→鞭移（光彈）→護盾爆閃遮擋→回聲環圓形 iris→Logo 羽化。
安全：觀眾席模糊不可辨臉，HUD 以抽象符號表示百分比，無明確文字。
```

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立夜間決鬥場與律岑校準節拍的專注狀態
基調：緊張→沉著
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：圓形符文場地、觀眾席霧光、深藍外套、HUD 拍點

#### Beat 1（0.0–1.2s）
重點：開場俯視預備節拍
Blocking：空拍俯視慢慢下降，律岑與攻擊手對峙，觀眾聲淡出。
Camera：
- 運鏡：俯視滑軌下降
- 焦段/機位：26mm 高空→下降至 15m
- 對焦：層次前→中→後
- 快門角：180；拍點：BGM 第一拍
光影：冷藍體積光掃過場地，觀眾席模糊暖點
色調/LUT：陰影微藍、符文金邊高光
聲音：arena_low_rumble＋遠觀眾 murmur，pulse_drum_quarter 漸入
轉場：HUD 亮起光wipe → Beat 2

Angle 1
構圖：圓形場地置中，兩人對峙
內容：環境建立
補充：電弧雲慢動
安全：無可讀標誌

#### Beat 2（1.2–2.4s）
重點：眼神 HUD 對拍
Blocking：律岑抬手指敲刻度環，HUD 小節條亮起。
Camera：
- 運鏡：胸高仰視微推
- 焦段/機位：30mm 胸高
- 對焦：單點瞳孔
- 快門角：180；拍點：手指敲擊
光影：暖金 rim 打亮眼神光
色調/LUT：膚色暖琥珀，背景冷藍
聲音：hud_tick_hicut ×2、遠鼓保持節拍
轉場：手指落下遮擋 → Beat 3

Angle 2
構圖：律岑側臉佔畫面右側
內容：眼神 HUD 與刻度環
補充：瞳孔微縮
安全：無文字

#### Beat 3（2.4–3.6s）
重點：首波格檔
Blocking：對手射出首發魔法彈，律岑單手抬起彈開。
Camera：
- 運鏡：側向穩定器
- 焦段/機位：45mm 眼高
- 對焦：呼吸拉焦 魔法彈→護盾→律岑
- 快門角：180；拍點：格檔瞬間
光影：護盾亮暖金
色調/LUT：背景去飽和 5%，護盾飽和
聲音：crystalline_clack_snap、shield_sheen_air
轉場：反彈光軌鞭移 → Beat 4

Angle 3
構圖：兩人側面，護盾佔前景
內容：魔法彈被彈斜
補充：HUD 左下顯示節拍條
安全：HUD 無字

#### Beat 4（3.6–5.0s）
重點：四拍連鎖格
Blocking：連續三發不同角度攻擊，律岑一拍一格檔。
Camera：
- 運鏡：略俯滑軌
- 焦段/機位：32mm 俯視 30°
- 對焦：層次拉焦 3 段護盾
- 快門角：172；拍點：每拍格檔
光影：每道護盾依序亮起
色調/LUT：HUD 與護盾對比明顯
聲音：pulse_drum_quarter 強化＋格檔節奏
轉場：地面光圈點亮 → Act 2

Angle 4
構圖：律岑在畫面中央，護盾成弧列
內容：三連格檔
補充：空氣中波紋
安全：無可讀資訊

### Act 2（5.0–10.0s）
意圖：展現腳步陣與零拍反擊的準備
基調：決斷、緊繃
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：六連光圈、子彈時間 HUD、胸前 0 Beat 法陣

#### Beat 5（5.0–6.2s）
重點：腳步格檔鋪場
Blocking：律岑踩入六格光圈，每步格擋垂直攻擊。
Camera：
- 運鏡：俯視穩定器跟隨
- 焦段/機位：32mm 俯視 60°
- 對焦：單點足部→地圈
- 快門角：180；拍點：每一步
光影：地圈同步亮滅
色調/LUT：地面青藍、光圈金白
聲音：resonant_floor_ping＋脈衝鼓
轉場：鏡頭拉近胸口 → Beat 6

Angle 5
構圖：律岑腳步為中心
內容：六連光圈踩踏
補充：粒子沿腳步延遲
安全：地面符文無字

#### Beat 6（6.2–7.4s）
重點：子彈時間凝止
Blocking：鏡頭繞行，時間慢下，律岑閉眼深吸氣。
Camera：
- 運鏡：36mm 環繞→子彈時間
- 焦段/機位：胸高
- 對焦：呼吸拉焦 背景攻擊→律岑
- 快門角：150；拍點：心跳
光影：環境 dim 20%，背光強調輪廓
色調/LUT：整體去飽和 8%，僅心跳 HUD 亮紅
聲音：vacuum 靜音＋zero_beat_heart
轉場：胸口法陣亮起 → Beat 7

Angle 6
構圖：律岑中景，攻擊停在四周
內容：子彈時間
補充：HUD 變心跳波形
安全：無文字

#### Beat 7（7.4–8.6s）
重點：《零拍反擊》啟動
Blocking：胸前浮現 0 Beat 魔法陣，律岑右手切下拍點，攻擊邊緣裂開。
Camera：
- 運鏡：胸口近景微推
- 焦段/機位：50mm 胸高
- 對焦：單點手勢
- 快門角：150；拍點：手刀落下
光影：魔法陣暖金閃，背景仍冷藍
色調/LUT：手部暖亮
聲音：vacuum_heart_drop＋吸氣聲
轉場：時間恢復硬切 → Beat 8

Angle 7
構圖：胸口魔法陣置中
內容：手刀切拍、裂紋展開
補充：HUD 顯示 0 Beat Icon
安全：無文字

#### Beat 8（8.6–10.0s）
重點：節奏性的多重格檔爆發
Blocking：時間恢復，多層護盾按節奏連鎖。
Camera：
- 運鏡：正面微魚眼穩定器
- 焦段/機位：35mm 眼高
- 對焦：層次護盾→律岑→彈道
- 快門角：172；拍點：護盾節拍
光影：護盾輪流亮滅成螺旋
色調/LUT：光弧鮮亮，背景保持冷調
聲音：格檔連打 combo、pulse_drum_quarter 全開
轉場：光弧導向側面 → Act 3

Angle 8
構圖：律岑正面居中，護盾形成圓環
內容：多層格檔
補充：彈開軌跡成螺旋
安全：無可讀資訊

### Act 3（10.0–15.0s）
意圖：展現前進中的格檔舞步與反擊收束
基調：勝利、自信
節奏域：加速2.4–3.0 → 穩定1.5–2.4
美術要點：回聲光環、能量光球、觀眾拍手 HUD、角色 Logo

#### Beat 9（10.0–11.2s）
重點：格檔之舞前進
Blocking：律岑踩著六連光圈前進，肩線穩，手肘畫弧格擋。
Camera：
- 運鏡：側向跟拍
- 焦段/機位：40mm 腰高
- 對焦：呼吸拉焦腳步→上半身
- 快門角：180；拍點：腳步
光影：地圈光從前往後點亮
色調/LUT：膚色暖，背景冷
聲音：resonant_floor_ping 每步＋觀眾拍手節奏
轉場：腳步踩出回聲光環 → Beat10

Angle 9
構圖：側面三分線
內容：律岑行進格檔
補充：被彈開的魔法彈光弧掃過觀眾席
安全：觀眾模糊

#### Beat 10（11.2–12.8s）
重點：能量收束並台詞
Blocking：被彈開的攻擊收束於右手前，律岑低聲說「節奏，該換你聽了。」
Camera：
- 運鏡：半環繞至側前
- 焦段/機位：55mm 胸高
- 對焦：單點手心光球
- 快門角：172；拍點：台詞口型
光影：光球強亮，臉上暖金反射
色調/LUT：光球高飽和金白
聲音：vacuum 結束後 shield_sheen_air 帶動，台詞可用低聲旁白處理
轉場：光球射向前方 → Beat11

Angle 10
構圖：律岑偏右，手心光球置左前
內容：收束能量、台詞
補充：回聲光環在身後旋轉
安全：台詞以音訊呈現，畫面無文字

#### Beat 11（12.8–14.0s）
重點：塵埃散去展示勝利
Blocking：光球打在對手腳邊炸出煙塵，對手倒地裝備冒火花。
Camera：
- 運鏡：中遠景仰角
- 焦段/機位：35mm 膝高仰視
- 對焦：層次律岑→倒地對手
- 快門角：180；拍點：煙塵散
光影：煙霧受光形成射束
色調/LUT：煙塵冷灰，HUD 顯示完美格檔 Icon
聲音：arena_low_rumble＋觀眾歡呼節奏拍手
轉場：HUD Icon 變 Logo → Beat12

Angle 11
構圖：律岑站右前景，對手倒左後
內容：勝利姿態
補充：手套刻度環回到初始亮度
安全：HUD 僅 Icon

#### Beat 12（14.0–15.0s）
重點：角色 Logo 收尾
Blocking：律岑側身，右手在空中敲四拍，Logo 與魔法陣浮現。
Camera：
- 運鏡：定鏡微推
- 焦段/機位：50mm 胸高
- 對焦：單點臉部
- 快門角：180；拍點：第四拍微笑
光影：背後 Logo 以脈衝亮起
色調/LUT：背景深藍，Logo 金白
聲音：pulse_drum_quarter 收束四拍＋觀眾拍手
轉場：羽化至黑 → End

Angle 12
構圖：律岑置右，Logo 居中
內容：角色 Pose 與 Logo
補充：節拍器墜飾晃動
安全：Logo 為抽象圖騰無文字

---

## Audio 運行備忘
- 以 Tempo Parry Beatshield Audio 為主，維持 110BPM；確保格檔聲與 HUD 拍點完全同步。
- 子彈時間段落將 ambient 層級降 -10 dB，保留 zero_beat_heart 與吸氣聲後再漸入。
- 觀眾拍手以節奏拍（clap on 2 & 4）處理，避免人聲語句。

## QA Checklist（提交前自檢）
- [ ] 情緒與運鏡符合節奏段落，焦段/對比/轉場與 Master Prompt 一致。
- [ ] 膚色維持 55–65 IRE，小麥膚有汗光，眼神光由護盾補亮。
- [ ] 轉場（HUD 閃光、鞭移、羽化）皆已設計並記錄觸發拍點。
- [ ] Style Pack 控制參數與節拍器 HUD 已記錄，音畫同步門檻對齊 110BPM。
- [ ] 畫面內無可讀字樣或品牌，觀眾席臉部皆處於模糊區域。
- [ ] 交付規格保持 16:9｜24fps，音訊 -14 LUFS，Limiter -1 dBTP。

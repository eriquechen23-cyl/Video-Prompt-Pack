# 《天頂荒原》BOSS PV — 天頂裁決龍・赫利昂（15s｜12 幕）

來源設定：天頂裁決龍・赫利昂（白天 × 正午決戰 × 寫實電影風）Boss PV 概念稿。

## 一句話題材
永遠鎖死在正午的荒原上，冒險者誤闖晷心裂谷，喚醒天頂裁決龍・赫利昂，親眼見證影子被剝奪與太陽裁決墜落。

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

### Style Pack：Zenith Noon Real Audio（`_stylepacks/zenith_noon_realism/audio.yml`）
```yaml
name: Zenith Noon Real Audio
core_layers:
  - baked_desert_wind
  - heat_buzz_harmonics
  - distant_metal_creak
  - granular_sandfall
impact_events:
  - cue: solar_pressure_drop
    sfx: subsonic_column_crush
    level_db: -4
    width: 140
  - cue: gnomon_lock
    sfx: glass_ring_sweep
    level_db: -7
    width: 120
  - cue: thermal_wing_cut
    sfx: vacuum_slice_thump
    level_db: -6
    width: 150
  - cue: helio_dive
    sfx: hypersonic_descend_roar
    level_db: -2
    width: 160
voiceover:
  language: zh-TW
  tone: solemn_genderless
  treatment: band_limit_mid_high
mix_notes:
  - 風聲需維持 -18 dBFS 底噪並含金屬共振尾音，對應封印結構。
  - 光柱與日晷事件必須 sidechain 風聲 3 dB，凸顯衝擊。
  - 結尾旁白僅 0.7s，定位中央，殘響 0.3s 後歸於靜音。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Zenith Noon Realism｜2.39:1｜24fps｜玻璃灼光寫實)
「正午被鎖死的《天頂荒原》晷心裂谷；白曝岩層、流動熱浪、失去影子的砂塵；冒險者闖入禁區，引出天頂裁決龍・赫利昂自太陽中分離並啟動審判。」
鏡頭：開場以24mm 俯視滑軌下推→32mm 穩定器側跟→50mm 仰視主觀→85mm 長焦拉近龍角→24mm 繞拍空中全景→135mm 壓縮龍眼→混用手持≤3% 追逐地面光圈→32mm 低角見光柱→36mm 主觀光籠→50mm 側向熱浪→35mm 遠仰→70mm 俯衝跟拍，最後以 LOGO 靜幀。
表演：冒險者群從緊繃屏息到被光壓掀飛；龍保持冷冽審判氣息，尾晷展開如儀式；旁白於結尾以無情聲線吐字「影子，在這裡是違法的」。
臉型/髮型：冒險者戴沙布、汗濕面罩，膚色被曝成暖白，眼睛微瞇抵禦強光；龍無血肉表情，以熾白金虹膜主導。
構圖：大量中央對稱與日晷圓盤留白15%；前景砂塵、人物剪影，後景永恒太陽；動態：熱浪、砂塵上拋、光柱震盪、日晷光籠旋轉。
寫實細節：岩石表面呈半熔玻璃，人物衣料被光壓貼體，鱗片內部流動熾橙金屬；空氣扭曲造成背景折射飄移。
無字幕、無商標/Logo/水印。

鏡頭語法：24 建立空間→32 人物緊跟→50–85 仰視/壓迫→135 壓縮威嚇→35–70 動作收束；
光圈 {T4 日景維持銳利，爆發段降至 T3.2 拉開景深}；快門角 {180° 全段，熱浪切割時降至 144° 強化清晰}；
對焦 {層次前→中→後於建立段；單點眼於龍；呼吸拉焦光圈地標→人物}。
光影：唯一天頂硬光 5600K，地面反射白金跳光；影子被抹平僅留灰階殘影。
色調/LUT：依 Zenith Noon Real Look，去飽和 3%，高光貼近純白，暗部為暖沙色，龍腹熾橙提供唯一飽和色。
聲音：baked_desert_wind 與 heat_buzz_harmonics 持續；subsonic_column_crush、glass_ring_sweep、vacuum_slice_thump、hypersonic_descend_roar 依招式觸發；音樂以 90BPM 管弦＋低音合成維持張力。
轉場：熱浪扭曲匹配→砂塵遮擋→光柱閃白硬切→玻璃裂紋鞭移→白光羽化進 LOGO。
安全：人像遮面、無可讀旗幟、所有標記為抽象刻度。
```

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立天頂荒原的無影壓迫與赫利昂甦醒的儀式感
基調：緊繃敬畏
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：晷心裂谷、白曝岩層、冒險者沙布裝備、鎖死太陽的光環

#### Beat 1（0.0–1.2s）
重點：白曝荒原建立
Blocking：從高空俯視裂谷→鏡頭緩慢下降
Camera：
- 運鏡：24mm 俯視滑軌下推
- 焦段/機位：24mm 700m 高空俯拍
- 對焦：層次拉焦天頂→裂谷
- 快門角：180；拍點：熱浪扭動
光影：硬頂光 5600K，岩層反射刺白
色調/LUT：白金高光貼近剪切，暗部僅暖沙線條
聲音：baked_desert_wind + heat_buzz_harmonics；遠景金屬嗡鳴-20 dBFS
轉場：熱浪遮擋→Beat2

Angle 1
構圖：中央裂谷，前景為空中熱浪紋
內容：無影荒原與晷心裂縫
補充：zenith_ground_glimmer 造成空氣折射
安全：無文字

#### Beat 2（1.2–2.4s）
重點：冒險者在無影地面前行
Blocking：側跟腳步→鏡頭切至鞋尖與砂塵
Camera：
- 運鏡：32mm 穩定器側向跟拍
- 焦段/機位：32mm 膝高
- 對焦：單點靴子→呼吸拉焦腳邊灰痕
- 快門角：180；拍點：鞋跟落地
光影：地表跳光映在靴子上；無陰影
色調/LUT：布料去飽和 3%，砂塵暖白
聲音：腳踩碎石＋granular_sandfall；隊員喘息側錄 -18 dBFS
轉場：腳步停下→Beat3

Angle 2
構圖：三分線右，靴子切入
內容：砂塵被踢起卻無影
補充：微小砂粒在空中漂浮
安全：無 Logo

#### Beat 3（2.4–3.6s）
重點：主觀仰視被鎖住的太陽
Blocking：冒險者抬頭→太陽被光環束縛
Camera：
- 運鏡：50mm 手持≤3% 主觀仰角
- 焦段/機位：50mm 眼高仰視
- 對焦：呼吸拉焦光環刻度
- 快門角：180；拍點：耳鳴開始
光影：太陽光環硬光，邊緣脈衝
色調/LUT：高光純白，僅刻度留橘線
聲音：環境聲壓低，僅高頻嗡鳴 -12 dBFS
轉場：暗影分離→Beat4

Angle 3
構圖：中央太陽，光環刻度清晰
內容：太陽被硬質光環鎖住
補充：apex_sky_veil 熱霧震動
安全：無

#### Beat 4（3.6–5.0s）
重點：龍影從太陽分離
Blocking：光環裂開→赫利昂輪廓抽離
Camera：
- 運鏡：85mm 長焦拉近
- 焦段/機位：85mm 仰視
- 對焦：單點龍角
- 快門角：180；拍點：龍角完全分離
光影：背光輪廓強烈，龍體自發橘紅
色調/LUT：龍角金白，背景純白
聲音：distant_metal_creak 逐漸放大
轉場：光芒閃白→Act2

Angle 4
構圖：龍角剪影與太陽重疊
內容：赫利昂玻璃鱗片折射
補充：molten_gold_edges 發光
安全：無

### Act 2（5.0–12.0s）
意圖：展示赫利昂的審判流程與玩家受困
基調：壓迫→爆發
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：玻璃鱗片、日晷尾、光柱、光籠、熱浪翼刃

#### Beat 5（5.0–6.2s）
重點：赫利昂全景懸停
Blocking：鏡頭繞過裂谷，龍展翼
Camera：
- 運鏡：24mm 空中繞拍
- 焦段/機位：24mm 俯視至平視
- 對焦：層次拉焦背脊→尾晷
- 快門角：180；拍點：尾晷展開
光影：太陽背光造成輪廓光，尾晷投射光紋
色調/LUT：龍體白金，尾部橘紅脈動
聲音：音樂加入低頻鼓點；baked_desert_wind 被 sidechain 2 dB
轉場：尾晷閃光→Beat6

Angle 5
構圖：龍置中央，尾晷鋪滿前景
內容：玻璃翅膀內流動熾橙
補充：wing_trail_shader 折射天空
安全：無

#### Beat 6（6.2–7.4s）
重點：龍眼審視冒險者
Blocking：龍眼收縮→倒映地面
Camera：
- 運鏡：135mm 靜止特寫
- 焦段/機位：135mm 平視
- 對焦：單點瞳孔→反射人物
- 快門角：144；拍點：瞳孔收縮
光影：眼內白金光線閃爍
色調/LUT：眼白過曝，瞳孔僅一條白線
聲音：心跳重擊 + heat_buzz_harmonics 拉高
轉場：心跳停頓→Beat7

Angle 6
構圖：極近特寫，龍眼佔滿畫面
內容：冒險者倒映在瞳孔
補充：reflection_cache 開始充能
安全：無人臉細節

#### Beat 7（7.4–8.6s）
重點：光壓審判落點鎖定
Blocking：地面浮現光圈→影子被抽走
Camera：
- 運鏡：32mm 俯視穩定器
- 焦段/機位：32mm 5m 高俯視
- 對焦：層次拉焦地紋→人物
- 快門角：180；拍點：影子消失
光影：地面光紋如刻度
色調/LUT：地紋白金，人物被平面光淹沒
聲音：glass_ring_sweep 初段，腳步停滯聲
轉場：光紋中心閃→Beat8

Angle 7
構圖：俯視中央光圈
內容：冒險者被鎖定在光圈內
補充：砂塵被壓低
安全：無

#### Beat 8（8.6–9.8s）
重點：光柱砸落掀起碎石
Blocking：光柱落下→主角被掀飛
Camera：
- 運鏡：36mm 低角側拍
- 焦段/機位：36mm 膝高
- 對焦：呼吸拉焦人物→光柱
- 快門角：144；拍點：衝擊波
光影：白金光柱佔滿畫面
色調/LUT：場景幾近純白僅殘留橘紅碎屑
聲音：subsonic_column_crush + hypersonic_descend_roar 前奏
轉場：碎石遮擋→Beat9

Angle 8
構圖：人物居左，被光柱掀飛
內容：地表凹陷、碎石飛散
補充：silica_dust_updraft 包覆鏡頭
安全：面部被護目遮掩

#### Beat 9（9.8–10.9s）
重點：晷心監牢籠罩視角
Blocking：透明光籠圍住觀點→光條旋轉
Camera：
- 運鏡：35mm 主觀 360° 旋轉
- 焦段/機位：35mm 眼高
- 對焦：單點最近光條→層次拉焦外圍岩壁
- 快門角：180；拍點：光條掃過鏡頭
光影：光條切割岩石發出橘白光
色調/LUT：透明光籠帶橘色內發光
聲音：glass_ring_sweep 主段 + high BPM 電子節奏 110BPM
轉場：光條擦過→Beat10

Angle 9
構圖：POV 內視，光條形成圓籠
內容：日晷刻度旋轉，岩面熔化
補充：sundial_cage_geometry 24 片同步
安全：無可讀符號

#### Beat 10（10.9–12.0s）
重點：熱亂流翼刃剖開山壁
Blocking：龍振翼→透明熱刃掃過
Camera：
- 運鏡：50mm 側向跟隨熱刃
- 焦段/機位：50mm 胸高
- 對焦：層次拉焦翼尖→遠處山壁
- 快門角：144；拍點：岩壁裂開
光影：熱浪透明，邊緣折射
色調/LUT：背景變形如水面
聲音：vacuum_slice_thump + 岩石崩落
轉場：裂縫匹配→Act3

Angle 10
構圖：熱刃由右往左掃，後景山壁
內容：岩壁慢動作裂成兩半
補充：zenith_ground_glimmer 強化折射
安全：無

### Act 3（12.0–15.0s）
意圖：展示赫利昂終結技與標題揭示
基調：神聖恐懼
節奏域：加速2.4–3.0 → 慢出0.8–1.5
美術要點：太陽輪廓、白曝天空、LOGO 火焰字

#### Beat 11（12.0–13.3s）
重點：赫利昂回到太陽前蓄勢
Blocking：龍飛至太陽前→背脊骨刺逐一亮起
Camera：
- 運鏡：35mm 遠距仰角拉遠
- 焦段/機位：35mm 低角
- 對焦：層次拉焦龍→太陽
- 快門角：180；拍點：骨刺全亮
光影：整體過曝，只剩輪廓
色調/LUT：畫面幾乎純白，僅骨刺橘線
聲音：音樂堆疊至高潮，heat_buzz_harmonics 極強
轉場：白光溢出→Beat12

Angle 11
構圖：龍與太陽成同心圓
內容：胸口核心如熔爐燃起
補充：wing_trail_shader 留下長尾
安全：無

#### Beat 12（13.3–15.0s）
重點：日焰俯衝撞擊與 LOGO
Blocking：龍化火槍俯衝→畫面全白→LOGO 浮現
Camera：
- 運鏡：70mm 高速跟拍後急停
- 焦段/機位：70mm 仰角→正視
- 對焦：單點龍胸→白光→LOGO
- 快門角：200；拍點：撞擊與旁白
光影：全白過曝後轉黑底火焰字
色調/LUT：白光收斂成火焰邊 LOGO
聲音：hypersonic_descend_roar 全幅爆發→瞬間靜音→旁白低語 -8 dBFS
轉場：白光羽化→黑底 LOGO

Angle 12
構圖：先中央俯衝線，後 LOGO 居中
內容：龍尾焰拖出長軌跡→《天頂荒原》與「BOSS：天頂裁決龍・赫利昂」標題
補充：火焰邊緣帶熔金質感
安全：標題為繁中金屬字無品牌

## QA 自檢（10/10）
- [x] 結構完整：Master Prompt、Style Packs、Act → Beat → Angle 共 12 幕時間軸明確。
- [x] 敘事一致：世界永恆正午、赫利昂審判流程與 LOGO 結束皆承接原設定。
- [x] 視聽細節：鏡頭焦段、熱浪折射、聲音 cue（solar_pressure_drop 等）完整可操作。
- [x] 風格準確：全片限制白天正午，引用 Zenith Noon Realism 三個 style pack 定義過曝質感。
- [x] 格式精準：依專案規範建立日期路徑、中文命名、無額外檔案。
- [x] QA Checklist 條目逐一檢核，無遺漏或衝突。

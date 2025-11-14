# Curve Bolt Training — Tactical Curve Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-14_curve-bolt-training_v01/script.md

## 一句話題材
在廢墟模擬場的 15 秒戰術演練中，熟練法師 Lyra 以〈能量彎射〉預判敵動、繞牆連射並收束為光針穿透魔像核心，示範 CURVE、STABILITY 與 RHYTHM 的中期掌握。


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

### Style Pack：Thread Weaver Look（`_stylepacks/thread_weaver/look.yml`）
```yaml
name: Thread Weaver Look
lut: Obsidian-Elemental
saturation_adjust: -0.03
contrast: tensile_highlight
highlights: argent_arc_lite
shadows: abyssal_violet
affinity_glow: filament_prism_trace
texture: armored_silk_wrap
chromatic_aberration: micro_split_spool
notes:
  - 強化絲線在暗處的金屬微光，確保多元素光澤在 30° 側光下也能辨識。
  - 服裝以烏黑硬化披風結合金屬指虎，保留纖維細節與戰損髒污層。
  - 元素脈衝需沿絲線向外漸層：雷偏青白、霜偏蒼銀、火偏熾橘紅。
```

### Style Pack：Thread Weaver VFX（`_stylepacks/thread_weaver/vfx.yml`）
```yaml
name: Thread Weaver VFX
niagara_presets:
  - filament_arc_bind
  - frost_thread_fracture
  - ember_coil_dragnet
  - shadow_suture_finisher
unity_vfx_graph:
  - ThreadWeaver.ArcBind.vfx
  - ThreadWeaver.FrostShatter.vfx
  - ThreadWeaver.EmberReel.vfx
  - ThreadWeaver.VoidSnare.vfx
houdini_flipbooks:
  - filament_burst_arc
  - cryo_thread_crack
  - ember_thread_cinders
  - void_slice_afterimage
shader_settings:
  filament_core_emit: 0.56
  cryo_rime_density: 0.62
  ember_heat_ramp: 0.71
  void_slice_alpha: 0.44
spline_controls:
  tension_min: 0.28
  tension_max: 0.82
  noise_jitter: 0.19
bloom_control:
  idle: 0.10
  trigger_peak: 0.74
  cooldown: 0.32
audio_sync:
  arc_pulse: sync_to_midband
  frost_snap: sync_to_highspark
  ember_reel: sync_to_lowrumble
  void_cut: sync_to_fullmute
notes:
  - 絲線須保留 1px 外擴光暈避免 aliasing，收束時縮短 0.2s 使拉扯更俐落。
  - 霜裂爆破加入碎冰＋金屬碎片混合軌跡，落地粒子 1.5s 內淡出。
  - 影斷終結時加入低透明殘影剪裁，配合攝影機微震 2frame。
```

### Style Pack：Thread Weaver Audio（`_stylepacks/thread_weaver/audio.yml`）
```yaml
name: Thread Weaver Audio
core_layers:
  - dusk_industrial_air
  - filament_tension_hum
  - frost_crystal_pads
  - ember_subpulse_throb
  - void_tail_riser
peak_events:
  - timestamp: arc_bind_trigger
    sfx: braided_arc_whip
    level_db: -8
    stereo_width: 120
  - timestamp: frost_thread_break
    sfx: crystal_shear_shatter
    level_db: -4
    stereo_width: 150
  - timestamp: ember_coil_snap
    sfx: furnace_wire_screech
    level_db: -5
    stereo_width: 110
  - timestamp: void_finisher_cut
    sfx: ribbon_void_slice
    level_db: -3
    stereo_width: 90
low_freq_management:
  sub_ceiling_db: -9
  lfe_emphasis: 52Hz
sidechain:
  trigger_bus: filament_hits
  target: ambience_pad
  reduction_db: 4.0
notes:
  - 雷屬束縛層混入電弧噼啪與張力摩擦聲，維持 6kHz 以上亮度。
  - 霜裂爆破需加入碎冰滑落至地的環繞音，延長 0.6s 的尾韻。
  - 影斷斬擊瞬間抽空中頻，利用 -100ms pre-delay 形成真空感後再回復。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Thread Weaver｜2.39:1｜24fps｜銀紫廢墟戰術質感)
「薄霧覆蓋的石造廢墟訓練場；碎石迷宮、半塌牆體、沉睡魔像靶；熟練法師 Lyra 以預判軌跡的〈能量彎射〉繞牆攻擊並將能量收束成光針終結魔像。
鏡頭：24mm 廣角穩定器前推建立迷宮，轉35mm 側滑貼地弧線，再以50mm 過肩與65mm 壓縮鎖定弱點與核心爆閃；節奏段落保持穩定器 0–3% 微動。
表演：Lyra 目光專注、動作俐落；呼吸與步伐緊扣節拍，最後以知曉勝利的輕笑收束。
臉型/髮型：Lyra 銀灰馬尾、堅定輪廓、成年武裝姿態。
構圖：前中後層立體掩體，Lyra 置於三分線；動態：碎石被踩起、光線沿牆拖曳、粒子霧回流。
寫實細節：硬化皮革護臂反射銀紫光、石柱裂痕與焦黑刮痕、地面碎屑被能量掃成弧形。
無字幕、無商標/Logo/水印。」

鏡頭語法：24 建立空間｜35 預判軌跡｜50 過肩戰術｜65 壓縮終結；
光圈 {T2.8–T4}；快門角 {200°}；
對焦 {層次前→中→後／單點光束頭部／呼吸拉焦步伐對位}。
光影：晨後冷光穿霧 + 體積光切割；色溫 {日5200–5600K}；
對比 {中高}；眼神光 {透過反射護臂保留}。
色調/LUT：{陰影帶蒼紫、金屬高光蒼銀、去飽和4% 保留石粉肌理}。
聲音：環境風帶砂礫摩擦、碎石被踩與護甲摩擦；音樂 {96BPM 節奏層與氛圍墊交織}；噪音控制於 -6 dB 峰值。
轉場：掩體遮擋與光線殘影直接切換，核心爆閃段落採 0.4s 羽化。
安全：魔像靶無人形血腥、場景僅抽象刻紋、亮度 ≤100 nits。
```


## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.0s）
意圖：建立戰術場景與預判伏筆
基調：決斷中帶緊張
節奏域：慢入0.8–1.5
美術要點：碎石迷宮、銀紫護臂、沉睡魔像靶

#### Beat 1（0.0–2.0s）
重點：踏入場域與目標啟動
Blocking：Lyra 踏入廢墟迷宮，魔像靶啟動並開始移動
Camera：
- 運鏡：24mm 穩定器前推
- 焦段/機位：24mm 微高轉眼高
- 對焦：層次拉焦碎石→Lyra→遠處魔像
- 快門角：200；拍點：魔像眼光亮起
光影：冷晨光穿霧，側逆光勾輪廓
色調/LUT：陰影蒼紫、高光蒼銀
聲音：core_layers 與 96BPM 節拍同時進場，魔像鎖扣聲對齊拍點
轉場：魔像影子遮擋 → Beat 2

Angle 1（0.0–1.0s）
構圖：廣角三分線，Lyra 偏左前景
內容：踏入廢墟的環境建立
補充：靴底碾動碎石揚起粉塵
安全：地面紋理無符號

Angle 2（1.0–2.0s）
構圖：中景中央，魔像位於右後方
內容：魔像啟動掃視
補充：牆體裂縫透出冷光
安全：魔像表面僅抽象刻紋

#### Beat 2（2.0–4.0s）
重點：預描能量軌跡
Blocking：Lyra 半蹲貼地，沿地面寫下預判弧線等待魔像踏入
Camera：
- 運鏡：35mm 側滑貼地
- 焦段/機位：35mm 腰高貼近軌跡
- 對焦：單點光帶→預判落點
- 快門角：200；拍點：光帶停於空點
光影：體積光掃過弧線，地面反射銀紫
色調/LUT：去飽和4%，保留石粉質感
聲音：arc_bind_trigger 隨光線啟動，ember_subpulse_throb 強化腳步預期
轉場：光帶上升成過門 → Act 2

Angle 3（2.0–3.0s）
構圖：對角線引導，Lyra 位於左側
內容：Lyra 貼地寫弧線
補充：手套紋理映出銀紫流光
安全：能量不接觸鏡頭

Angle 4（3.0–4.0s）
構圖：沿弧線低角度前進
內容：預判落點等待目標
補充：魔像影子跨進光帶等待區
安全：光效亮度受控

### Act 2（4.0–9.0s）
意圖：展示繞掩體攻擊與節奏連鎖
基調：緊張轉為掌握
節奏域：穩定1.5–2.4
美術要點：斷牆火花、波浪弧線、護臂殘影

#### Beat 3（4.0–6.0s）
重點：繞掩體命中側面弱點
Blocking：Lyra 斜甩弧光貼牆行進，穿入魔像側面
Camera：
- 運鏡：50mm 過肩
- 焦段/機位：50mm 胸高
- 對焦：單點光束頭部
- 快門角：200；拍點：穿入弱點
光影：牆面反射火花，銀紫拖尾
色調/LUT：對比提升 5%，火花橘紅提亮
聲音：furnace_wire_screech 突出擦壁，crystal_shear_shatter 收束共振
轉場：火花鞭移 → Beat 4

Angle 5（4.0–5.0s）
構圖：過肩三分線，牆體占右側
內容：第一發弧光貼牆
補充：石屑沿牆剝落
安全：火花控制於 100 nits

Angle 6（5.0–6.0s）
構圖：壓縮特寫，魔像側面中央
內容：光線鑽入側面弱點
補充：金屬紋理隆起銀紋
安全：無破碎肢體畫面

#### Beat 4（6.0–9.0s）
重點：節奏連鎖三連射
Blocking：Lyra 踩節拍連發三條弧線，波浪形掃過不同高度
Camera：
- 運鏡：35→50mm 平滑跟隨
- 焦段/機位：35mm 側面→50mm 追蹤
- 對焦：呼吸拉焦步伐→弧線
- 快門角：200；拍點：每次出手
光影：連續拖尾形成波浪殘影
色調/LUT：陰影保持蒼紫，高光帶蒼銀脈動
聲音：ember_subpulse_throb 打出「嗒、嗒、嗒」，sidechain 壓 ambience 4 dB
轉場：弧線殘影淡出 → Act 3

Angle 7（6.0–7.0s）
構圖：側面中景，Lyra 步伐踩節拍
內容：第一拍連鎖起勢
補充：身後留下一道淡殘影
安全：角色成年設定

Angle 8（7.0–9.0s）
構圖：追蹤波浪軌跡，弧線三重曝光
內容：三連曲線掃掠掩體
補充：光軌高低錯落顯節奏
安全：亮度不超規

### Act 3（9.0–15.0s）
意圖：展示收束精度與戰術收尾
基調：決斷轉收束
節奏域：穩定1.5–2.4 過渡至慢入0.8–1.5
美術要點：光針穿核、粒子霧、殘光回收

#### Beat 5（9.0–11.0s）
重點：光針穿透核心
Blocking：最後一發弧光在接近核心時收束成細針，蒼銀爆閃
Camera：
- 運鏡：65mm 緊貼光束
- 焦段/機位：65mm 眼高
- 對焦：單點光針→核心
- 快門角：200；拍點：收束與刺入
光影：核心爆閃蒼銀光波，周遭粉塵被推散
色調/LUT：高光蒼銀抬 6%，陰影維持冷紫
聲音：void_slice_afterimage 抽空中頻後接 crystal_shear_shatter 與 ember_coil_snap
轉場：粒子霧遮擋 → Beat 6

Angle 9（9.0–9.8s）
構圖：光束後方對角線
內容：弧光收縮成光針
補充：殘光被吸回中心
安全：亮度 ≤100 nits

Angle 10（9.8–11.0s）
構圖：核心特寫，中央構圖
內容：蒼銀爆閃與金屬暈染
補充：關節卡榫鬆動冒出蒸汽
安全：魔像為非生物目標

#### Beat 6（11.0–15.0s）
重點：魔像瓦解與戰術收束
Blocking：魔像化成粒子霧消散，Lyra 揮手收回殘光
Camera：
- 運鏡：35mm 穩定器環繞 90° 後回正
- 焦段/機位：35mm 胸高 → 正面
- 對焦：層次拉焦粒子→Lyra 表情
- 快門角：200；拍點：殘光回收
光影：粒子霧反射銀紫，殘光回流到護臂刻紋
色調/LUT：去飽和4%，粒子帶蒼銀光暈
聲音：ember_coil_dragnet 餘波與 core_layers 漸退，風聲回歸
轉場：尾韻淡出 → 結束

Angle 11（11.0–13.0s）
構圖：半身三分線，粒子漂浮在前
內容：魔像瓦解成粒子霧
補充：粒子沿 3D 聲道移動
安全：畫面無血腥

Angle 12（13.0–15.0s）
構圖：環繞停於正面，Lyra 居中
內容：揮手清除殘光並吐氣收束
補充：護臂刻紋吸收殘光，地面留暗痕
安全：無符號、亮度符合標準

---

## 聲音層與事件對應
- 環境層：dusk_industrial_air 結合碎石滾動聲，節拍對齊 96BPM，Beat 4 期間 sidechain 降 4 dB。
- 能量層：filament_tension_hum 全段作基底，Beat 3–5 提升 2 dB，核心爆閃後於 Beat 6 內回落。
- 節奏層：ember_subpulse_throb 作為戰術心跳，三連射段落以 96BPM ×1.0 速度強調節奏點。
- 氛圍墊：frost_crystal_pads 自 5.5s 淡入補光，Beat 6 減至 -14 dB 只留空氣感。
- 事件音效：
  - 1.6s 魔像啟動觸發 ember_coil_snap -6 dB。
  - 4.6s 貼牆拋射觸發 furnace_wire_screech，立體聲寬 110°。
  - 8.1s 三連射結束觸發 braided_arc_whip，尾音 0.3s。
  - 9.7s 收束成光針觸發 void_slice_afterimage，瞬間抽空中頻。
  - 10.4s 核心爆閃觸發 crystal_shear_shatter -5 dB，再接 ember_coil_snap 低頻。
- 音樂：Thread Weaver Score 96BPM，Beat 4 提升 1.5 dB 支撐節奏，Beat 6 緩降 3 dB 交付餘韻。

## QA Checklist（拍前勾選）
- [ ] 焦段與機位（24/35/50/65mm）已標註並對應節奏轉折。
- [ ] Thread Weaver Look LUT 套用，陰影蒼紫不超過 0.2 gamma 偏移。
- [ ] 牆面與護臂紋理僅抽象刻紋，無可讀文字或標誌。
- [ ] 事件音效峰值 ≤ -4 dB，整體混音 -14 LUFS，光針爆閃持續 <0.5s。
- [ ] 粒子霧模擬與光線亮度記錄於製片表，亮度 ≤100 nits。
- [ ] Sidechain、BPM 標記與鏡頭運動速率同步表已完成。

## 交付備註
- 交付格式：2.39:1｜24fps｜ProRes 4444，提供節奏標記與事件音效時間碼。
- 粒子霧使用 Thread Weaver VFX ember_coil_dragnet 預設調整壽命 1.8s，確保消散乾淨。
- 三連射段落穩定器震幅 ≤3%，步伐踩點需對齊 96BPM；地面粉塵密度 0.45，保留腳步紋理。
- 中期訓練標語：戰術節奏讓光轉彎。

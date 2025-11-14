# Curve Bolt Training — Maestro of Curves Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-14_curve-bolt-training_v01/script.md

## 一句話題材
在黑暗靜室的 15 秒展示裡，大師 Caelan 以呼吸雕刻多條〈能量彎射〉，同時操控假動作、延遲爆發與束縛變化，展現 CURVE、STABILITY、FOCUS 與 RHYTHM 的終極掌控力。


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
Master(15s｜Thread Weaver｜2.39:1｜24fps｜黑曜靜室雕光質感)
「月夜後段的黑暗靜室；薰香白煙、石制靶陣、懸浮能量絲；大師 Caelan 閉眼呼吸雕刻多條〈能量彎射〉，以假動作與延遲爆發同時制伏三具魔像靶。
鏡頭：24mm 定鏡建立靜室呼吸，再轉35mm 環繞光筆，50mm 低角貼地追光、65mm 壓縮鎖定核心與束縛；穩定器環繞 ≤2% 微動。
表演：Caelan 呼吸沉穩、指尖細膩勾勒，睜眼時視線柔和直面鏡頭，口白淡聲收筆。
臉型/髮型：Caelan 成年長袍造型，黑髮束後、面容寧定。
構圖：中央構圖突出掌心光點，後景以靶影與煙霧分層；動態：薰香煙絲、光線分岔、粒子回流。
寫實細節：黑曜長袍布紋、銀絲刺繡反射、地面粉塵被光掃起後細緻落下。
無字幕、無商標/Logo/水印。」

鏡頭語法：24 靜室呼吸｜35 光筆旋繞｜50 假動作回刺｜65 壓縮共鳴終結；
光圈 {T2.0–T2.8}；快門角 {180°→200°}；
對焦 {呼吸拉焦掌心→多靶層次→單點核心→回收光點}。
光影：單一上方體積光切割 + 光線自發光，色溫 {夜3400K 混銀光}；
對比 {高}；眼神光 {最後睜眼時以反射補光保留}。
色調/LUT：{陰影深紫偏黑曜、高光蒼銀提亮、去飽和5% 維持肌理}。
聲音：void_cut 低頻壓力、filament_tension_hum 與 ember_coil_dragnet 疊出雕刻節奏，語音收束於 -8 dB 峰值；音樂以氛圍弦樂 90BPM 緩推。
轉場：光線殘影直接切與粒子遮擋交替，延遲爆發段採 0.4s 羽化。
安全：靶體皆為非生物魔像、薰香煙霧無宗教符號、亮度控制 ≤95 nits。
```


## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.0s）
意圖：建立靜室氛圍與呼吸雕光基調
基調：孤獨而專注
節奏域：慢入0.8–1.5
美術要點：黑暗靜室、薰香煙絲、黑曜長袍

#### Beat 1（0.0–2.0s）
重點：呼吸牽引光絲初現
Blocking：Caelan 盤坐靜息，呼吸牽動掌心微光，薰香煙霧緩升
Camera：
- 運鏡：24mm 定鏡微推
- 焦段/機位：24mm 眼高
- 對焦：呼吸拉焦掌心→胸口
- 快門角：180；拍點：光點隨呼吸拉長
光影：單一頂光柔化邊緣，煙霧折射銀紫
色調/LUT：陰影深紫，高光蒼銀
聲音：void_cut 低頻鋪底，filament_tension_hum 隨呼吸起伏
轉場：呼吸停頓→ Beat 2

Angle 1（0.0–1.0s）
構圖：中央構圖，留白 20%
內容：黑暗靜室中盤坐大師與掌心心跳光點
補充：薰香白煙自下而上流動
安全：無符號、成年角色

Angle 2（1.0–2.0s）
構圖：胸口近景，光點置中
內容：呼吸讓光絲伸縮成草稿線
補充：衣料微動與光痕殘留
安全：畫面無刺眼光

#### Beat 2（2.0–4.0s）
重點：指尖引動多條光軌甦醒
Blocking：Caelan 勾指喚醒光痕，光線分岔書寫空間
Camera：
- 運鏡：35mm 穩定器 90° 環繞
- 焦段/機位：35mm 胸高
- 對焦：層次拉焦掌心→懸浮光線
- 快門角：190；拍點：指尖勾動
光影：光線自體發光照亮臉部邊緣
色調/LUT：陰影保持深紫，高光銀白
聲音：filament_arc_bind 精準入場，薰香「滋滋」清晰
轉場：光軌分岔掃過鏡頭 → Act 2

Angle 3（2.0–3.0s）
構圖：半身三分構圖，光線環繞前景
內容：指尖一勾，多條光線甦醒
補充：鏡頭環繞帶出光線層次
安全：光軌不直射鏡頭

Angle 4（3.0–4.0s）
構圖：環繞視角，光線構成空中書法
內容：多段分岔與筆畫交錯
補充：光線不碰撞，煙霧穿梭其間
安全：亮度控制 ≤90 nits

### Act 2（4.0–9.0s）
意圖：展示假動作回刺與多目標控制
基調：決斷帶優雅
節奏域：穩定1.5–2.4
美術要點：貼地光軌、魔像靶、光繩束縛

#### Beat 3（4.0–6.0s）
重點：假動作與回刺穿心
Blocking：光線先掠過靶體再貼地折返，第二次刺向核心
Camera：
- 運鏡：50mm 低角貼地追蹤
- 焦段/機位：50mm 膝高
- 對焦：單點光軌→魔像胸口
- 快門角：200；拍點：折返抬頭
光影：地面粉塵被光拖起形成光粉尾
色調/LUT：陰影深紫，光尾蒼銀偏亮
聲音：ribbon_void_slice 左右擺動，粉塵摩擦聲微顫
轉場：光針停頓 → Beat 4

Angle 5（4.0–5.0s）
構圖：低角度對角線構圖
內容：假動作貼地滑行離靶
補充：光線擦過魔像頭頂留亮痕
安全：靶體無破損細節

Angle 6（5.0–6.0s）
構圖：低角推進到靶心
內容：光針折返刺向核心但先停住
補充：地面光粉被掀起
安全：亮度控制 ≤95 nits

#### Beat 4（6.0–9.0s）
重點：同時束縛多目標並標記節點
Blocking：光針維持刺入不爆，另一條光繩纏住第二靶，第三靶被光標記
Camera：
- 運鏡：35mm 半身側移再拉遠
- 焦段/機位：35mm 胸高→腰高
- 對焦：層次拉焦光針→光繩→多靶
- 快門角：200；拍點：光繩收緊
光影：光繩沿螺旋發光，粒子沿纏繞方向流動
色調/LUT：銀紫互補，保持高對比
聲音：braided_arc_whip 延遲落下，心跳式低頻標示節點亮起
轉場：節點亮度提升 → Act 3

Angle 7（6.0–7.0s）
構圖：65mm 特寫，核心置中
內容：光針緩入核心刻出圓形刻痕
補充：刻痕邊緣顫動
安全：魔像為無機構造

Angle 8（7.0–8.0s）
構圖：束縛靶中景，螺旋構圖
內容：光繩纏繞第二靶四肢
補充：電流質感沿繩流動
安全：亮度與電弧安全

Angle 9（8.0–9.0s）
構圖：半身拉遠，三靶同框
內容：所有光線尾端連回掌心
補充：光線像樂譜延伸
安全：場景無危險標誌

### Act 3（9.0–15.0s）
意圖：呈現延遲共鳴爆發與收筆口白
基調：莊嚴收束
節奏域：穩定1.5–2.4 → 慢入0.8–1.5
美術要點：螺旋爆發、銀灰粒子、掌心收筆光點

#### Beat 5（9.0–11.0s）
重點：延遲爆發的共鳴瞬間
Blocking：節點依序亮起後同時爆發，魔像剝離成粒子
Camera：
- 運鏡：65mm 壓縮中景
- 焦段/機位：65mm 眼高
- 對焦：單點節點→粒子外擴
- 快門角：200；拍點：共鳴爆閃
光影：螺旋能量以銀白拉伸，粒子帶尾跡
色調/LUT：高光抬 6%，陰影保持深紫
聲音：ember_coil_snap 與 void_cut 抽空中頻，之後高頻殘響環繞
轉場：粒子飄散遮擋 → Beat 6

Angle 10（9.0–11.0s）
構圖：中央構圖，爆發中心置中
內容：節點亮起後同時螺旋爆散
補充：多重曝光顯示前後瞬間
安全：亮度 ≤95 nits

#### Beat 6（11.0–15.0s）
重點：回收所有光線並以口白收筆
Blocking：Caelan 睜眼，光絲回流掌心並口述口號，光點熄滅
Camera：
- 運鏡：35mm 正面穩定器微推
- 焦段/機位：35mm 胸高→臉部
- 對焦：層次拉焦粒子→眼神→掌心光點
- 快門角：190；拍點：口白結束光點熄滅
光影：粒子如雪飄落照亮臉部，掌心最後亮點提供眼神光
色調/LUT：陰影柔化 2%，保持銀紫主調
聲音：高頻泛音左右飄移，台詞 -8 dB 清晰，其他層漸 fade out
轉場：光點熄滅 → 結束

Angle 11（11.0–13.0s）
構圖：臉與掌心近景，三分線
內容：Caelan 睜眼召回光絲
補充：銀灰粒子如雪飄落
安全：語音清楚無其他內容

Angle 12（13.0–15.0s）
構圖：掌心極近特寫，口形入畫
內容：光點縮成一點後熄滅並說出口白
補充：薰香煙霧在黑暗中流散
安全：無過亮閃光

---

## Audio Layering & Cue Notes
- **基底氛圍**：void_cut 深層低頻搭配 dusk_industrial_air 稍微留空，營造密室壓力。
- **呼吸節奏**：filament_tension_hum 在 0–4s 隨呼吸起伏，6–9s 改以脈衝標記節點亮起。
- **重點事件**：
  - 2.8s filament_arc_bind 提升 2 dB，凸顯光線甦醒。
  - 4.5s ribbon_void_slice 左右聲道 120° 擺動對應假動作。
  - 8.2s braided_arc_whip 延遲 0.1s 進場，形成束縛緊縮感。
  - 9.6s ember_coil_snap + void_cut 抽空中頻 400–2kHz，之後 0.6s 內回復。
- **人聲處理**：僅保留 13–15s Caelan 的台詞，使用乾聲貼近收音，輕量混響 1.2s。
- **混音守則**：側鏈由 filament_hits 觸發壓 ambience 3 dB，Limiter 設 -1 dBTP，輸出 -14 LUFS。

## QA Checklist 自評
- [x] 結構完整：Master Prompt + Scene Blocks + Audio Notes + QA。
- [x] 敘事一致：呼吸→假動作→多靶→共鳴→口白連貫。
- [x] 視聽細節：攝影焦段、光影、聲音事件明確可執行。
- [x] 風格準確：Thread Weaver Look/VFX/Audio 樣板完全嵌入。
- [x] 格式精準：時間軸、命名、轉場與安全規範對齊。

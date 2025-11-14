# Curve Bolt Training — First Arc Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-14_curve-bolt-training_v01/script.md

## 一句話題材
在灰白石質訓練場中，學徒 Arin 從抖動的銀紫弧光起步，在導師 Mira 的呼吸節奏指引下於 15 秒內首次以〈能量彎射〉命中靶心並穩定收束。 

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
Master(15s｜Thread Weaver｜2.39:1｜24fps｜銀紫纖維魔導質感)
「黎明後的灰白石質訓練場；漂浮粉塵、靜懸圓靶、淡霧陽光；學徒 Arin 以抖動的銀紫光絲練習〈能量彎射〉，在導師 Mira 指導下調整呼吸命中靶心。
鏡頭：開場24mm微高角俯視建立空場，轉35mm胸高雙人對照，再以50mm與65mm緊貼手勢與靶心；節奏段落加入5%手持抖動後回穩。
表演：Arin 肩膀微聳、眼神緊張轉為專注，呼吸由急促趨向平穩；Mira 姿態沉穩，手勢細緻引導。
臉型/髮型：Arin 深棕短髮、額前碎髮貼汗；Mira 長髮束起，面容成熟。
構圖：三分線安排人物偏左，靶在遠處中線；動態：粉塵漂浮、光絲殘影、碎石落下。
寫實細節：訓練袍布料磨損、掌心銀紫能量呼吸式明滅、牆面焦黑刮痕。
無字幕、無商標/Logo/水印。」

鏡頭語法：24 建立空間｜35 指導互動｜50 過肩緊張｜65 壓縮命中；
光圈 {T2.8–T4}；快門角 {200°}；
對焦 {層次前→中→後／單點掌心與靶心／呼吸拉焦於導師手勢}。
光影：側逆晨光穿霧形成體積光；色溫 {日5200–5600K}；
對比 {柔中帶高}；眼神光 {保留於銀紫反射}。
色調/LUT：{陰影偏紫、髮絲與布料保留肌理、高光帶冷銀光／去飽和3%}。
聲音：環境風刷過石牆、粉塵落地、衣料細摩；音樂 {氛圍墊底＋輕弦脈搏 78BPM}；噪音控制於 -6 dB 峰值。
轉場：粉塵遮擋與光絲殘影直接切換、節奏回穩處採羽化0.5s。
安全：無宗教符號、靶面僅幾何紋、粉塵濃度安全。
```

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.0s）
意圖：建立場域與初次失控
基調：緊張悸動
節奏域：慢入0.8–1.5
美術要點：灰白石板、圓形靶、銀紫弧光、淡霧粉塵

#### Beat 1（0.0–2.0s）
重點：首次彎射失控
Blocking：Arin 站定抽氣，甩手放出不穩弧線擦過石柱
Camera：
- 運鏡：24mm 滑軌微推後壓至半身
- 焦段/機位：24mm 微高角轉眼高
- 對焦：層次拉焦粉塵→Arin→弧線
- 快門角：200；拍點：弧光擦柱瞬間
光影：側逆光穿霧帶銀紫折射
色調/LUT：陰影紫藍、高光冷銀
聲音：dusk_industrial_air＋filament_tension_hum 漸強，弧線噗噗爆鳴突出
轉場：粉塵遮擋 → Beat 2

Angle 1（0.0–1.0s）
構圖：三分線，Arin 偏左前景，靶模糊於右後方
內容：環境建立廣角
補充：粉塵飄浮與淡霧層疊
安全：無符號、靶面僅幾何裂紋

Angle 2（1.0–2.0s）
構圖：中央半身，弧光對角劃出
內容：試射軌跡半身特寫
補充：石柱被擦出焦黑刮痕伴火花
安全：弧光亮度 ≤100 nits

#### Beat 2（2.0–4.0s）
重點：導師矯正與模仿進步
Blocking：Mira 入畫調整手肘手腕，示範弧線，Arin 模仿後落點穩定
Camera：
- 運鏡：35mm 穩定器靠近手部
- 焦段/機位：35mm 胸高雙人
- 對焦：呼吸拉焦 Mira 指尖→Arin 手勢
- 快門角：200；拍點：模仿弧線落靶
光影：柔側光覆蓋兩人掌心，高光落在教學弧線
色調/LUT：膚色優先，高光銀紫
聲音：void_tail_riser 細揚，Mira 低語；hum 變均勻
轉場：手勢遮擋 → Act 2

Angle 3（2.0–3.0s）
構圖：雙人中景，Mira 偏右
內容：導師矯正姿勢
補充：示範弧線半透明疊於空氣
安全：角色服飾無徽記

Angle 4（3.0–4.0s）
構圖：手部特寫，上下留白 15%
內容：Arin 勾指再射落點收斂
補充：光粒逐顆散落，尾跡柔和
安全：能量集中於靶，無濺射觀眾

### Act 2（4.0–8.0s）
意圖：失衡後重新掌握節奏
基調：緊繃轉穩
節奏域：穩定1.5–2.4
美術要點：背後石牆焦痕、粉塵被光掃出軌跡

#### Beat 3（4.0–6.0s）
重點：急於連射造成危險
Blocking：Arin 未等穩定即連甩三次，弧光交錯其中一條擦耳而過撞牆
Camera：
- 運鏡：50mm 手持 5% 晃動
- 焦段/機位：50mm 過肩背後
- 對焦：單點弧光分岔→耳旁
- 快門角：200；拍點：擦耳火花
光影：光束亂竄拉出閃爍殘影，牆面焦黑
色調/LUT：對比提高，火花橘紅點綴
聲音：sidechain 壓低環境，只留急促呼吸與噗啵；furnace_wire_screech 強調擦壁
轉場：火花閃白 → Beat 4

Angle 5（4.0–5.0s）
構圖：過肩視角，三條弧光交錯
內容：連射失衡過肩鏡
補充：弧光尾焰像扭曲繩索
安全：能量未碰觸攝影機視點

Angle 6（5.0–6.0s）
構圖：超近特寫，弧光擦過耳後
內容：耳際驚險瞬間
補充：肩上袍子被熱浪掀動，碎屑濺落
安全：火花亮度受控，無灼傷畫面

#### Beat 4（6.0–8.0s）
重點：導師帶回呼吸與節奏
Blocking：Mira 手掌示範節奏，Arin 深吸對齊心跳緩慢勾指
Camera：
- 運鏡：50mm 正面穩定器
- 焦段/機位：50mm 胸口近景轉手指特寫
- 對焦：呼吸拉焦胸腔→手指→掌心光脈搏
- 快門角：200；拍點：每次心跳延伸
光影：側光柔化，掌心光隨呼吸脈動
色調/LUT：陰影回歸柔和，銀紫脈搏清晰
聲音：frost_crystal_pads 淡入，hum 與呼吸同步
轉場：呼吸節奏淡切 → Act 3

Angle 7（6.0–7.0s）
構圖：正面胸口近景，Mira 手勢入畫
內容：節奏示範與調息
補充：胸腔起伏帶動衣襬
安全：保持成人面容

Angle 8（7.0–8.0s）
構圖：手指特寫，留白 10%
內容：光絲依心跳延伸
補充：遠處砂石聲漸淡
安全：掌心能量穩定無爆散

### Act 3（8.0–15.0s）
意圖：首次成功命中與收束
基調：緊張轉為盼望與收斂
節奏域：穩定1.5–2.4 過渡至慢入0.8–1.5
美術要點：靶心焦煙、掌心殘光、粉塵軌跡

#### Beat 5（8.0–11.0s）
重點：成形弧線命中靶心
Blocking：光絲雕刻優雅弧線朝靶，命中後僅收縮光波
Camera：
- 運鏡：65mm 追蹤光絲至靶
- 焦段/機位：65mm 眼高貼光束
- 對焦：單點光絲頭部→靶心
- 快門角：200；拍點：命中瞬間
光影：靶前浮塵被光波推開，尾跡銀紫
色調/LUT：去飽和3%，高光帶冷藍
聲音：braided_arc_whip 精準觸發，crystal_shear_shatter 壓低，音樂抬頭後收斂
轉場：靶心焦煙作遮擋 → Beat 6

Angle 9（8.0–9.0s）
構圖：光絲引導對角線
內容：沿弧線追蹤的環境移動
補充：殘光尾跡像被雕刻
安全：靶面無文字

Angle 10（9.0–11.0s）
構圖：靶心中央特寫
內容：光絲命中後焦煙擴散
補充：石粉沿裂縫緩落
安全：亮度控制於100 nits 以下

#### Beat 6（11.0–15.0s）
重點：餘震與收束的靜默
Blocking：Arin 看著掌心殘光，汗珠滑落；Mira 點頭示意收束，Arin 握拳熄滅光點
Camera：
- 運鏡：35mm 半身回到Arin，再微後仰定鏡
- 焦段/機位：35mm 胸高 → 眼高後仰
- 對焦：呼吸拉焦手掌→臉部→靶場粉塵軌跡
- 快門角：200；拍點：光點熄滅
光影：晨光柔化，殘光像小光環
色調/LUT：膚色柔和，陰影帶紫
聲音：呼吸放緩，filament_tension_hum 成尾韻，音場 fade out
轉場：尾韻淡出 → 結束

Angle 11（11.0–13.0s）
構圖：半身三分線，掌心居中偏下
內容：掌心殘光與汗珠
補充：汗沿眉骨成細線
安全：角色成年特徵明確

Angle 12（13.0–15.0s）
構圖：雙人中景，鏡頭微後仰
內容：收束動作與靜默靶場
補充：粉塵軌跡在空中緩慢漂移
安全：畫面無其他標誌

---

## 聲音層與事件對應
- 環境層：dusk_industrial_air 提供訓練場風刷聲；側鏈於 Beat 3 降 4 dB。
- 能量層：filament_tension_hum 全程作基底，Beat 1–2 提升 1.5 dB，Beat 4 依呼吸做 0.5Hz 起伏。
- 氛圍墊：frost_crystal_pads 於 Beat 4–6 漸入，音量 -12 dB 起步。
- 事件音效：
  - 1.2s、1.7s 彎射失控觸發 ember_coil_snap → 噗鳴對應。
  - 5.4s 擦耳觸發 furnace_wire_screech，立體聲寬 110°。
  - 8.6s 弧線穩定進靶觸發 braided_arc_whip，尾音 0.4s。
  - 10.2s 靶心收束調用 crystal_shear_shatter -8 dB，快速收尾。
- 音樂：Thread Weaver Score 78BPM 氛圍弦樂，Beat 3 sidechain 壓 4 dB，Beat 5 短暫抬頭 2 dB 後回歸。

## QA Checklist（拍前勾選）
- [ ] 確認三階段鏡頭焦段與快門角設定對應節奏。
- [ ] LUT 套用 Thread Weaver Look，陰影紫階不超過 0.2 gamma。
- [ ] 靶面無可讀符號，牆面焦痕僅抽象線條。
- [ ] 事件音效峰值 ≤ -4 dB，整體混音 -14 LUFS。
- [ ] 弧光亮度受控於 100 nits 以下，避免閃爍。
- [ ] 種子值、sidechain 設定與節奏標記記錄於製片表。

## 交付備註
- 交付格式：2.39:1｜24fps｜ProRes 4444
- 需附上節奏標記表與音效觸發時間碼。
- 製作備註：Beat 3 手持晃動限 5%，Beat 4 後鏡頭需回穩；粉塵粒子密度 0.35，確保呼吸動態可見。

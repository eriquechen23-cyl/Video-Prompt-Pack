# 絲線操控者 × 多元素絞殺｜寫實 3A 動作分鏡 Prompt（15s 控場職業循環）

## 一句話題材
用暗銀絲線交織雷霜火影，先控場聚怪再一次收線殲滅。

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

### Audio Pack 指引（`_core/audio_pack.md`）
```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
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
lens_distortion: subtle_barrel_lock
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
Master(15s｜Thread Weaver Look｜16:9｜24fps｜硬派多元素寫實)
「夜間風雨侵蝕的巨型造船塢；金屬吊架、雨霧、地面積水反光；絲線操控者以指節暗銀絲線控場聚怪後絞殺。」
鏡頭：穩定器滑軌結合半肩繞拍，技能引爆時穿插鞭移與子彈時間切換。
表演：冷冽專注，手腕細膩扭動，視線精準鎖定聚集的敵人核心。
臉型/髮型：依上傳五官特徵，短髮側分被雨壓伏，瀏海貼附額前。
構圖：前中後層次＋三分線留白 15%，絲線在空中勾勒對角；動態：風驟雨滴、電弧、霜霧、火花、影殘。
寫實細節：硬質防護披風帶雨痕，金屬指虎纏繞絲線，場地鐵銹與積水倒影，敵人裝甲燒蝕與結霜細節。
無字幕、無商標/Logo/水印。

鏡頭語法：24–35 空間｜50–75 親密｜100–135 壓縮；
光圈 {T2.0–T2.8}；快門角 {180°/200–240°}；
對焦 {單點眼/層次前→中→後}。
光影：{側逆/體積/霓虹混光}；色溫 {夜3000–3800K}；
對比 {高}；眼神光 {保留}。
色調/LUT：{自然肌理/膚色優先/陰影微藍・高光暖/去飽和5–10%}。
聲音：環境/腳步/衣料/風/遠人聲（-6 dB 峰值）；音樂 {節奏輕推}。
轉場：{直接切/光源匹配/鞭移/羽化0.4–0.8s}。
安全：無品牌/無可讀文件/群眾臉不近特寫/連戲與時序一致。
```

## Scene Blocks

### Act 1（0.0–3.6s）
意圖：建立
基調：緊張
節奏域：慢入0.8–1.5
美術要點：夜間造船塢、濕潤鋼骨架、積水倒影、暗銀絲線纏繞指節

#### Beat 1（0.0–1.2s）
重點：職業登場與絲線質感建立
Blocking：主角自右後方入畫，步伐平穩，左手指尖甩出半圈絲線
Camera：
- 運鏡：滑軌平推
- 焦段/機位：28mm 肩後
- 對焦：單點鎖定指節絲線
- 快門角：200；拍點：絲線掠過鏡頭前緣
光影：側逆光勾勒絲線金屬反光
色調/LUT：陰影微藍，膚色保持 55 IRE
聲音：雨滴敲擊鋼板、絲線摩擦「唦」聲
轉場：絲線掃過鏡頭造成鞭移

Angle A
構圖：三分線，主角佔左前景，背景起重機與燈光模糊
內容：指節纏線、雨霧逆光
補充：絲線輕微振動帶出粒子
安全：場景僅主角

#### Beat 2（1.2–2.4s）
重點：暗銀絲線元素光澤提示
Blocking：主角停步，右手抬起，指尖絲線浮現雷霜火三色微光
Camera：
- 運鏡：穩定器微推近
- 焦段/機位：60mm 胸高
- 對焦：單點鎖定絲線交叉點
- 快門角：180；拍點：元素光依序點亮
光影：頂燈霓虹混光打在掌背，元素光補 rim light
色調/LUT：高光暖中帶冷色邊緣
聲音：細微電流嗡鳴混合結霜低頻
轉場：光線閃爍遮擋切

Angle B
構圖：中央近景，絲線形成對角線
內容：元素光脈衝沿線流動
補充：雨霧被電弧蒸發形成薄煙
安全：無可讀字

#### Beat 3（2.4–3.6s）
重點：敵群靠近，戰鬥張力升起
Blocking：鏡頭轉至前方，三名重甲敵人踩著積水逼近
Camera：
- 運鏡：滑軌後退抬升
- 焦段/機位：32mm 眼高
- 對焦：層次拉焦 主角→敵人前排
- 快門角：200；拍點：敵人舉盾撞水
光影：體積光穿過雨霧照亮敵人裝甲
色調/LUT：去飽和 5%，保留敵人核心紅光
聲音：厚重腳步、遠處警報低鳴
轉場：敵人揮兵器製造遮擋

Angle C
構圖：前中後層次，敵人佔中景
內容：積水濺起與護甲細節
補充：雨滴在鏡頭前形成散景
安全：僅敵人

### Act 2（3.6–7.2s）
意圖：敘事
基調：決斷
節奏域：穩定1.5–2.4
美術要點：雷紋束場、地面電弧、束縛節點

#### Beat 4（3.6–4.8s）
重點：雷紋束場啟動
Blocking：主角踏前半步，左手下壓像收緊風箏線
Camera：
- 運鏡：穩定器繞拍 45°
- 焦段/機位：35mm 胸高
- 對焦：層次拉焦 腳下雷紋→敵人腿部
- 快門角：200；拍點：雷紋點亮
光影：地面電弧發光沿絲線擴散
色調/LUT：雷光青白提高 10%，背景保持冷紫
聲音：低頻電流漸起
轉場：電弧閃光匹配切

Angle D
構圖：中央俯視微仰角
內容：地面雷紋陣與敵人腳踝纏線
補充：電火花節點在雨水中爆濺
安全：無可讀字

#### Beat 5（4.8–6.0s）
重點：敵人被束縛與感電
Blocking：絲線從地底竄出繞住敵人手腳，身體被拉向圓心
Camera：
- 運鏡：滑軌側推
- 焦段/機位：50mm 腰高
- 對焦：單點鎖定中心敵人
- 快門角：180；拍點：絲線收緊爆出電火花
光影：青白電弧沿絲線往上跳躍
色調/LUT：對比提高，電弧高亮
聲音：連續「啪！啪！啪！」感電爆裂
轉場：電弧鞭移切至慢動作

Angle E
構圖：中央，敵人被絲線拉成弓形
內容：絲線勒緊造成火花節點
補充：雨霧被蒸成白煙
安全：場景僅敵人

#### Beat 6（6.0–7.2s）
重點：束場穩定並打斷施法
Blocking：遠處施法者被電弧擊中停滯
Camera：
- 運鏡：穩定器前推
- 焦段/機位：75mm 胸高
- 對焦：單點鎖定施法者面部
- 快門角：180；拍點：施法姿勢被打斷
光影：雷光映出臉部高對比陰影
色調/LUT：膚色保持自然，背景冷藍
聲音：電流嗡鳴持續，伴隨護甲嘎吱
轉場：雷光閃爍羽化 0.5s

Angle F
構圖：中央特寫
內容：敵人臉部抽搐與絲線鎖點
補充：微小電火花沿面甲滑落
安全：敵人無可讀標誌

### Act 3（7.2–10.8s）
意圖：轉折
基調：緊張
節奏域：穩定1.5–2.4
美術要點：霜絲裂界、冰域擴散、碎冰粒子

#### Beat 7（7.2–8.4s）
重點：霜絲裂界鋪場
Blocking：主角右手甩出半圓絲線，冰霜沿地面擴散
Camera：
- 運鏡：滑軌低位側移
- 焦段/機位：30mm 膝高
- 對焦：層次拉焦 絲線→冰霜波紋
- 快門角：200；拍點：冰霜接觸地面
光影：冷藍體積光沿霜紋爬升
色調/LUT：高光偏銀白，地面藍綠混合
聲音：冰霜蔓延「卡滋」聲
轉場：冰霜掃過鏡頭羽化

Angle G
構圖：前景絲線，中景冰域，後景敵群
內容：冰霜線框向外擴散
補充：白霧翻湧貼地移動
安全：無文字

#### Beat 8（8.4–9.6s）
重點：敵人被冰封減速
Blocking：冰霜沿敵人腿部往上封鎖，動作被卡住
Camera：
- 運鏡：穩定器微抬視角
- 焦段/機位：55mm 胸高
- 對焦：單點鎖定腿部冰晶
- 快門角：180；拍點：冰晶封鎖瞬間
光影：冰晶折射燈光形成碎亮點
色調/LUT：冰晶保持 120 nits，高光暖色壓低
聲音：冰層增厚的低頻壓力聲
轉場：冰晶裂紋延伸做遮擋

Angle H
構圖：三分線，冰封敵人佔右側
內容：腿部至胸口被霜殼包覆
補充：呼出白霧凝結於鏡頭
安全：敵人無標誌

#### Beat 9（9.6–10.8s）
重點：霜絲裂界第二段引爆破甲
Blocking：主角猛然一扯絲線，冰殼炸裂
Camera：
- 運鏡：手持 3% 內快速收縮
- 焦段/機位：70mm 胸高
- 對焦：呼吸拉焦 絲線→碎冰
- 快門角：200；拍點：冰殼破碎
光影：碎冰反射周遭燈光
色調/LUT：高光暖度下降，碎冰泛冷銀
聲音：清脆碎裂疊加金屬斷裂
轉場：碎冰粒子作遮擋切

Angle I
構圖：中央特寫
內容：碎冰與護甲碎片向外飛散
補充：慢速鏡頭中碎片拖出殘影
安全：無可讀字

### Act 4（10.8–15.0s）
意圖：收束
基調：決斷
節奏域：加速2.4–3.0
美術要點：燼輪絞殺火輪、影線殘影、終結殘光

#### Beat 10（10.8–12.0s）
重點：燼輪絞殺拉敵
Blocking：主角將絲線甩成燃燒圓環，上方火輪灑落火星
Camera：
- 運鏡：穩定器繞拍 60°
- 焦段/機位：40mm 胸高
- 對焦：層次拉焦 火輪→被拖拽的敵人
- 快門角：200；拍點：火輪形成
光影：火焰照亮雨霧形成橙色暈光
色調/LUT：火光暖度升至 2300K，背景保持冷藍對比
聲音：火焰呼嘯與鎧甲摩擦刺耳聲
轉場：火光鞭移銜接下一段

Angle J
構圖：中央俯視
內容：火輪上方，敵人被拖向中心
補充：地面留焦黑軌跡
安全：場景僅戰鬥

#### Beat 11（12.0–13.2s）
重點：DOT 火焰灼燒持續
Blocking：敵人被拉到中心，絲線像燒紅鐵絲勒緊
Camera：
- 運鏡：滑軌前推進入近景
- 焦段/機位：85mm 胸高
- 對焦：單點鎖定絲線勒緊部位
- 快門角：180；拍點：火焰脈動
光影：火光閃爍照亮蒸汽
色調/LUT：蒸汽泛暖白，背景冷色保留
聲音：燃燒噼啪與敵人痛呼被壓低
轉場：火花四散作遮擋

Angle K
構圖：中央近景
內容：絲線勒緊、灼燒痕跡
補充：蒸汽伴火光脈動
安全：敵人裝甲無標誌

#### Beat 12（13.2–15.0s）
重點：傀影斷線終結收割
Blocking：主角放低雙手，絲線化為影子散開，握拳瞬間敵人被看不見的線切割倒下
Camera：
- 運鏡：穩定器前推後快速拉遠
- 焦段/機位：50mm 先親密後 105mm 壓縮
- 對焦：層次拉焦 主角→敵人倒下
- 快門角：200；拍點：暗紫節點同時亮起
光影：暗紫殘光閃現後熄滅，地面殘留殘影圈
色調/LUT：瞬間降低飽和，再回復原本對比
聲音：空氣被抽空後的靜默，接著敵人倒地金屬撞擊
轉場：鏡頭拉遠並羽化 0.4s 收束

Angle L
構圖：前景主角背影，倒地敵人散佈中心
內容：暗紫線框熄滅與地面殘影
補充：雨霧重新灑落，畫面緩慢回歸常速
安全：無品牌資訊


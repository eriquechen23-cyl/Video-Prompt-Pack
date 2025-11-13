# 2025-02-21 Night Particle Parkour v01 Prompt

## Core References

### Global Prompt Template（video-creation/_core/global_prompt.md）
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

### Scene Block Template（video-creation/_core/scene_block.md）
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

### VFX 通用 Pack（video-creation/_core/vfx_pack.md）
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

### Audio Pack 指引（video-creation/_core/audio_pack.md）
```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```

## Style Packs

### Real Cinema Lens Set（video-creation/_stylepacks/real_cinema/lensset.yml）
```
name: Real Cinema Lens Set
primary_focals: [35, 50, 75]
shutter_angle: 180
dolly:
  move: glide_in
  speed_ratio: 0.8
handheld_usage: 0.03
support: slider_or_stabilizer
usage_notes:
  - 室內情緒戲採滑軌緩推
  - 側向平移保持視線連續
  - 聚焦於自然膚質呈現
```

### Real Cinema Look（video-creation/_stylepacks/real_cinema/look.yml）
```
name: Real Cinema Look
lut: Skin-Priority
saturation_adjust: -0.05  # 去飽和 5–8%
skin_tone_ire: 60
contrast: soft
highlights: warm
shadows: cool_blue
texture: natural_grain
notes:
  - 膚色優先校正
  - 微膠片顆粒
  - 高光暖、陰影微藍
```

### Real Cinema Safety Checklist（video-creation/_stylepacks/real_cinema/safety.yml）
```
name: Real Cinema Safety Checklist
rules:
  - 避免可讀字與商標曝光
  - 群眾不近特寫，維持隱私
  - 保持自然膚質與光比
  - 記錄 LUT 與種子以利 QA
```

### Urban Switch FX Look（video-creation/_stylepacks/urban_switch_fx/look.yml）
```
name: Urban Switch FX Look
noise_reduction: balanced_motion
saturation: neutral_skin_pop
line_enhancement: motion_defined
color_palette:
  primaries: [charcoal, neon_lime, crimson]
  accents: [steel_blue, tungsten_warm]
  skin_tone: preserved
motion_blur_shutter: 170
exposure_bias: +0.2
notes:
  - 保留夜間城市對比，皮膚自然略暖
  - 動作拖影需兼顧服裝切換殘影
  - 配合雨霧與火星可用 Fresnel rim light
  - 建議同場景多機位以利無縫隱剪
```

### Particle Switch Sweep（video-creation/_stylepacks/particle_switch_sweep/vfx.yml）
```
name: Particle Switch Sweep
engines:
  ue5:
    niagara_presets:
      - ribbon_glow_trail
      - speedline_slice
      - embers_pulse_spark
  unity:
    vfx_graph:
      - SweepWrap.vfx
      - VelocityStreaks.vfx
  houdini_flipbooks:
    - micro_dust_burst
    - spark_sheet_loop
    - volumetric_glow_pulse
shader_controls:
  fresnel_edge: 0.6
  bloom_cap: 0.68
  dissolve_bandwidth: 0.18
  speedline_opacity: 0.72
transitions:
  - 粒子拂掃遮擋切換服裝，沿動作方向掃過維持 6–8 帧重疊
  - 殘影合體於換裝後 3 帧內收束，避免雙影漂移
  - 空氣塵粒與速度線協助動態過門，不做硬切
safety:
  - 粒子貼合模型法線，禁止穿透皮膚與道具
  - 火花亮度控制在 120 nits，避免過曝
  - 無文字、無商標、無介面 HUD 元素
notes:
  - 換裝 ≤5 套，以色溫與材質差異呈現，不添加圖案
  - 粒子顏色以暖橘核心、冷藍外緣，呼應 Real Cinema 夜景
  - Bloom 攻擊 0.15s、釋放 0.25s，配合音樂節奏 112 BPM
```

## 主提示（可直接貼給生成器）
「夜間城市實景、寫實電影風、16:9、24fps、自然膚色、動態景深；主角一路跑酷並於奔跑中以光粒子瞬換衣，全片禁止可讀文字、品牌、商標與浮水印。光影特效：微粒光帶、速度線、空氣塵粒、火花與泛光脈衝；轉場以粒子拂掃或殘影合體，不做硬切。鏡頭遵循 Real Cinema Lens Set 35/50/75mm 與穩定支援，Bloom ≤0.68，粒子沿服裝法線貼合（換裝總套數 ≤5）。」

---

## 影片結構總覽
- 時長：15 秒
- 幕數：8 幕，每幕 1.8–2.0 秒
- 服裝：A→E 共五套素面服飾，禁止 Logo、文字、商標
- 換裝節奏：幕 2、4、6、8 完成四次換裝，幕 1 為初始造型 A
- 影像安全：遵循 Real Cinema Safety 規範，控制曝光與 Bloom，保持自然膚色

---

## 幕別分解

### 幕 1｜0.0–1.8s｜濕地起跑（服裝 A：墨黑貼身連身衣）
- **意圖**：建立夜景與節奏基調。
- **Camera**：Steadicam 貼地前推 20cm 高；35mm 微仰角維持 1.2m 距離；快門角 180°；對焦從鞋尖拉至胸口。
- **Performance**：跑者蹲起推地，吐出冷霧，眼神專注前方。
- **Lighting**：街燈與霓虹反射控制在 90 IRE 以下，地面濕痕呈冷藍，膚色保持自然。
- **VFX**：Particle Switch Sweep 的 ribbon_glow_trail 從腳底拖出暖橘核心、冷藍外緣粒子，速度線低透明度疊加；此幕不換裝。
- **Transition**：粒子沿地面延展成光帶掃向鏡頭，帶入下一幕。

### 幕 2｜1.8–3.6s｜欄杆翻越換裝 B（服裝 B：深灰防風外套）
- **意圖**：首次換裝與高度變化。
- **Camera**：穩定器腰高 35mm，跟著欄杆翻越；快門角 172°；對焦手部→胸口→落地腳。
- **Performance**：抓欄翻身，手掌實際壓欄杆，落地雙膝緩衝。
- **Lighting**：欄杆上方補暖光、側逆光勾輪廓；偏光濾鏡控亮反射。
- **VFX**：粒子拂掃包覆軀幹 6 幀完成 A→B 換裝；sparks 刷過欄杆觸點，Bloom 控制 0.65。
- **Transition**：落地濺起的粒子遮擋掃過畫面，帶入牆跑。

### 幕 3｜3.6–5.4s｜牆跑殘影（維持服裝 B）
- **意圖**：強化速度感與殘影語彙。
- **Camera**：50mm 平移貼牆；對焦牆面紋理後拉至眼神；快門角 185°。
- **Performance**：貼牆跑兩步後蹬離，肩背轉向光源。
- **Lighting**：冷色洗牆燈與背後暖霓虹對比，陰影保留青藍層次。
- **VFX**：vector speedline_slice 沿牆延伸；殘影 0.2s 延遲後合體，粒子收束於身後。
- **Transition**：殘影合體時產生光脈衝，變成通往屋頂的粒子階梯。

### 幕 4｜5.4–7.2s｜屋頂跨越換裝 C（服裝 C：午夜藍輕量外套）
- **意圖**：展示高度跳躍與第二次換裝。
- **Camera**：臂架側跟 35mm；快門角 168°；對焦起跳腿→半空→落地。
- **Performance**：由屋檐跨向對面天台，半空伸展，落地穩定。
- **Lighting**：屋頂邊緣補光，遠景車流形成暖色 Bokeh，膚色自然。
- **VFX**：半空 volumetric_glow_pulse 包覆軀幹完成 B→C 換裝，粒子沿關節貼合；速度線朝前拉伸。
- **Transition**：落地塵粒掃向鏡頭進入 FPV 視角。

### 幕 5｜7.2–9.0s｜消防梯 FPV（維持服裝 C）
- **意圖**：帶入沉浸式視角與環境貼合。
- **Camera**：FPV 等效 24mm，先俯衝後抬頭；快門角 180°；Hyperfocal 對焦。
- **Performance**：手抓鐵梯迅速下滑，再側身鑽出。
- **Lighting**：梯內柔光填補陰影，金屬高光控制在 95 IRE 內。
- **VFX**：micro_dust_burst 粒子受風湧動，速度線貼梯壁；無換裝。
- **Transition**：背後粒子掃過鏡頭形成動態遮擋，切入地面滑行。

### 幕 6｜9.0–10.8s｜滑地穿桿換裝 D（服裝 D：炭灰連帽）
- **意圖**：展示低位動作與第三次換裝。
- **Camera**：手持倒退 35mm，鏡頭高度 30cm；快門角 176°；對焦腳部→手部→上半身。
- **Performance**：膝蓋收起滑行過管，手掌擦地帶起水霧。
- **Lighting**：地面沿滑行方向設冷藍 LED 灯帶，火花亮度控制在 120 nits。
- **VFX**：滑行時 ribbon_glow_trail 自地面竄升包覆 C→D，sparks 沿管道迴旋；Bloom 0.65。
- **Transition**：掠地光帶向上捲曲成螺旋，帶入樓梯。

### 幕 7｜10.8–12.6s｜螺旋樓梯下行（維持服裝 D）
- **意圖**：沉穩節奏預告終局。
- **Camera**：手持沿中心桅杆下降；50mm 壓縮樓梯；快門角 192°；對焦頭部→腳步。
- **Performance**：連續踩踏金屬階面並回頭看終點。
- **Lighting**：階面暖光、中央冷光形成對比，保留膠片顆粒感。
- **VFX**：VelocityStreaks 形成螺旋速度線，殘影合一後粒子聚向胸前光點。
- **Transition**：胸前光點脈動放大成遮罩，準備最終定格。

### 幕 8｜12.6–15.0s｜屋頂終點換裝 E（服裝 E：石墨灰長風衣）
- **意圖**：完成最終換裝與定格。
- **Camera**：滑軌回拉並微升降；75mm 目高構圖；快門角 200°；對焦胸口光點→眼神→城市光河。
- **Performance**：急停後轉身面向鏡頭，胸口光點脈動 0.5s，表情沉著。
- **Lighting**：城市遠景形成暖色光河，前景冷色 rim light，膚色自然。
- **VFX**：volumetric_glow_pulse 收束完成 D→E 換裝，第五套服裝；粒子熄滅後保留微塵懸浮。
- **Transition**：定格 1.0s 後粒子淡出至黑場，保持無文字、無商標。

---

## 製作備忘
- 攝影：Real Cinema Lens Set 35/50/75mm 為主，依幕別切換穩定器、臂架、滑軌與 FPV，手持晃動控制在 3% 內。
- 光影控制：依 Real Cinema Look 去飽和 5–8%，Bloom 峰值≤0.68；粒子亮度與節奏遵循 Particle Switch Sweep FX 設定。
- 服裝管理：A→E 素面服飾，材質分別為防水彈性布、磨砂外套、輕量風衣、連帽機能衣與長風衣，確保無 Logo。
- VFX Pipeline：UE5 Niagara 與 Unity VFX Graph 作為主要粒子工具，Houdini Flipbook 製作火花與塵粒；換裝節點預留 8 幀 Handle 方便無縫接軌。
- 音效：遵循 Audio Pack 指引混合腳步、衣料、風切與遠處城市低鳴，112 BPM 對齊粒子脈衝節奏。
- QA：檢查 Bloom、粒子貼合、服裝連戲與鏡位穩定；確認全片無可讀文字、品牌、浮水印並記錄種子與 LUT。

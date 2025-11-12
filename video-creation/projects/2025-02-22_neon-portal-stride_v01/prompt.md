# 2025-02-22 Neon Portal Stride v01 Prompt

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

### Sci-Fi Realism Look（video-creation/_stylepacks/sci_fi_realism/look.yml）
```
name: Sci-Fi Realism Look
lut: Neutral+BlueShadows
contrast: medium_high
highlight_control: neon_balance
reflection_priority: metal_glass
color_temperature_range: [3600, 4200]
bloom:
  base: 0.2
  peak: 0.6
notes:
  - 允許霓虹混光，保留暗部細節
  - 金屬與玻璃反射優先處理
  - 夜景需維持主體分離
```

### Sci-Fi Realism VFX（video-creation/_stylepacks/sci_fi_realism/vfx.yml）
```
name: Sci-Fi Realism VFX
niagara_presets:
  - 能量環
  - 粒子回彈
  - SDF 發光邊緣
unity_vfx_graph:
  - EnergyRing.vfx
  - ReboundParticles.vfx
  - SDFGlowEdge.vfx
houdini_flipbooks:
  - electric_arc
  - impact_smoke
bloom_control:
  idle: 0.2
  trigger_peak: 0.6
  cooldown: 0.3
audio_sync:
  low_freq_pulse: drives_emission_rate
  transient_hit: adds_burst
notes:
  - 將 Audio 閾值設在 -12 dB 觸發發射率上升
  - 冷卻階段以粒子密度逐步下降呈現
```

## 主提示（可直接貼給生成器）
「寫實電影風、16:9、24fps、微膠片質感；主角從晨間舊巷弄一路向前穿越校園走廊、黃昏雨中十字路口、夜間地鐵月台，最終抵達霓虹未來城天橋。每經過門框或光縫即完成一次 Cloth-morph 無縫換裝，粒子與光暈化作時間縫隙。鏡頭遵循 Real Cinema Lens Set 滑軌與穩定器語法，色調融合 Real Cinema Look 與 Sci-Fi Realism Look，Bloom 峰值≤0.6。禁止任何商標、可讀字樣、浮水印；保留自然光與真實環境聲層次。」

---

## 影片參數概述
- 時長：15 秒（24fps）
- 畫幅：16:9，鏡頭焦段依場景切換 24/35/50mm，個別段落以 35mm 為主軸
- 色溫遞進：5200K（晨巷）→6000K（午間走廊）→6500K（雨路口與地鐵）→6500K+霓虹混光（未來城）
- 快門角：全片 180° 基準，穿越瞬間加速至 0.85× 再回 1.1×
- 音場：實錄環境聲 + 細膩 Foley（衣料、腳步、雨聲、列車風壓）
- 安全：全服裝素面無圖樣，場景清除可辨識招牌與文字

---

## 0–15s 分鏡與換裝節點

### 0–3s｜舊巷弄·晨｜服裝 A：復古卡其外套＋布鞋
- **Camera**：近景 35mm Steadicam 隨步前移，眼高略低（1.5m），微向上仰角 5°；快門角 180°；光圈 T2.4 形成柔淺景深。
- **Action**：主角抬手撫過斑駁磚面，指尖感受粗糙質地；外套衣領被晨光掀起。
- **Sound**：遠處機車引擎「嗡」掠過，空氣帶微涼呼吸聲。
- **VFX/Transition**：塵埃粒子在光束中漂浮，手勢穿入塵光形成 Flowmap Dissolve 遮罩，帶出下一場景。
- **Trigger**：指尖觸牆後掀外套衣領，布料擦過聲觸發第一段 Cloth-morph。

### 3–6s｜校園走廊·午｜服裝 B：學生風襯衫 → 輕薄雨衣套裝
- **Camera**：走廊側向滑軌 35mm，Whip Pan 貼門框完成轉場，粉塵顆粒逆光漂浮；快門角 176°。
- **Action**：袖口甩動，布料「沙沙」刷過欄杆，主角快步穿過門框。
- **Sound**：鞋底踩過磨石地板回音，遠處學生聊天低語層。
- **VFX/Transition**：Whip Pan 時門框變成光縫，粒子沿門縫噴湧；襯衫在甩袖中 Cloth-morph 成半透明雨衣。
- **Trigger**：甩袖與跨門同時，布料貼換導入雨衣與防水靴。

### 6–9s｜雨中十字路口·黃昏｜服裝 C：都市機能外套（素面）
- **Camera**：50mm 跟拍腳部起步跨過水窪，鏡頭抬升至胸口；快門角 188° 捕捉雨滴拖影。
- **Action**：收傘後大步跨越斑馬線，雨水濺起「啪」聲，呼吸嗅到淡淡金屬味。
- **Sound**：細雨、車流噪與遠處紅綠燈提示聲壓低混合。
- **VFX/Transition**：霓虹倒影拉出速度線，路口行道燈形成流動光幕包覆主角，完成雨衣→機能外套的 Cloth-morph。
- **Trigger**：傘柄收合並掃過鏡頭形成遮擋，光幕作為遮罩引導至地鐵入口。

### 9–12s｜地鐵月台·夜｜服裝 D：都會西裝風（簡潔剪裁）
- **Camera**：側跟 35mm，列車駛過帶起風貼臉；快門角 180°，拉鍊動作時短暫降至 170° 增強清晰度。
- **Action**：主角抓緊背帶，列車燈帶頻閃；車門邊緣變成光門。
- **Sound**：列車風壓、廣播回聲、鞋底與月台摩擦。
- **VFX/Transition**：車門光線作遮罩，粒子從拉鍊處向上流動完成機能外套→簡潔西裝換裝。
- **Trigger**：抬手拉上拉鍊，伴隨粒子 Bloom 脈衝，門縫切到霓虹天橋。

### 12–15s｜霓虹未來城天橋·夜深｜服裝 E：未來纖維戰術服
- **Camera**：滑軌回拉 50mm → 75mm，鏡頭抬升俯瞰，保留城市低鳴如海；快門角 192° 強調殘影。
- **Action**：主角停下回望，後方殘影追上本體合一，胸口微光呼吸。
- **Sound**：遠處城市低頻「呼」與風聲融合，保留環境聲為主，僅微量合成墊底。
- **VFX/Transition**：殘影 Flowmap Dissolve 合體，微 Bloom 脈衝收束；天橋護欄霓虹形成最後光門定格。
- **Trigger**：胸前微光脈動完成最終換裝，鏡頭抬升定格 1 秒。

---

## VFX / 技術備註
- 轉場語法：門框、塵光束、雨幕、列車邊緣與霓虹護欄作遮罩；Flowmap Dissolve + Chromatic Aberration 5%；換場速度比 0.85× → 1.1× 平滑過渡。
- Cloth-morph：採 Match Move，換裝動作分別為撫牆→甩袖→收傘→拉鍊→胸光，保證服裝貼合且無跳幀；換裝粒子使用 Sci-Fi Realism VFX 的能量環與粒子回彈預設，顏色暖白核心搭配冷藍外緣。
- 粒子：雨滴、塵埃、霓虹光暈採 Niagara 粒子與 Houdini Flipbook（electric_arc、impact_smoke）；過門時添加微 Bloom 脈衝（峰值 0.58，攻擊 0.12s，釋放 0.24s）。
- 攝影：依 Real Cinema Lens Set 切換 24/35/50mm（天橋拉至 75mm），快門角 180° 基準；手持晃動控制 <3%；穩定器與滑軌交錯使用。
- 色彩：Real Cinema Look 為基底去飽和 5%，霓虹場景覆疊 Sci-Fi Realism Look 之 neon_balance，高光暖、陰影冷藍；顆粒維持自然膠片質感。
- 聲音：以環境實錄為主（巷弄機車、校園腳步、雨聲、列車風、城市低鳴），微量合成墊底；遵循 Audio Pack 動態範圍，雨聲與粒子觸發對應 -12 dB 閾值發射率。
- 合規：所有服裝與道具素面，場景內標誌與文字需打光或後期處理移除；確保無浮水印或字幕。

---

## 製作備忘
- 前期場勘：確認巷弄、校園、路口、地鐵、天橋動線可連續拍攝，保留自然環境聲並申請拍攝許可。
- VFX Pipeline：預拍乾淨版方便 Flowmap 融合；每個換裝節點預留 8–10 幀 Handle，粒子遮罩對齊演員動作；Chromatic Aberration 僅在換場 4 幀內使用，避免整段色散。
- 服裝管理：五套服飾依場景準備乾燥/防水版本，確保無任何 Logo；雨段服裝預備備用以防濕透影響 Cloth-morph。
- 音效錄製：巷弄與校園採立體聲環境收音，路口與地鐵補錄 Foley（雨伞收合、拉鍊、布料刷動），天橋加低頻「呼」聲以收束。
- QA Checklist：確認每場換裝無跳幀、無可讀字，Bloom 控制在 0.6 以下，粒子不穿透角色；紀錄最終色溫、LUT、粒子參數與速度變化曲線。

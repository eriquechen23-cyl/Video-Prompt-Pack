# 冰脈裂地 Prompt（15s VFX 動作鏡頭）

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

### Style Pack：Sci-Fi Realism Look（`_stylepacks/sci_fi_realism/look.yml`）
```yaml
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

### Style Pack：Sci-Fi Realism VFX（`_stylepacks/sci_fi_realism/vfx.yml`）
```yaml
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

### Style Pack：Sci-Fi Realism Audio（`_stylepacks/sci_fi_realism/audio.yml`）
```yaml
name: Sci-Fi Realism Audio
bpm: 96
low_freq_pulse:
  range_hz: [40, 80]
  modulation: emission_rate
transient_layer:
  description: 金屬感瞬音對應能量釋放
  gain: -8
drone_bed:
  texture: synth_pad
  width: stereo_wide
mix_guidelines:
  lufs: -14
  true_peak: -1
  sidechain: vfx_trigger
notes:
  - 低頻脈衝驅動能量護盾亮度
  - 觸發瞬間添加 transient 以提升張力
```

---

## Master Prompt 實際填寫
```
Master(15s｜Sci-Fi Realism｜2.39:1｜24fps｜冰晶銳利寫實)
「午夜冰原裂谷入口；焦裂玄武岩地層／浮動冰霧／遠處極光絲帶；冰系武者跺地引爆冰脈，霜紋沿地狂奔並拔起晶牆包覆前方。
鏡頭：滑軌前推接微側移。
表演：決斷怒吼，雙臂帶出霜霧，視線鎖定前方威脅。
臉型/髮型：依上傳五官特徵，束髮因寒風微擺。
構圖：前中後分層；動態：冰紋流動與晶體生長，後景極光慢速律動。
寫實細節：皮革戰靴積雪、外套結霜纖維、裂地粉塵與冰晶反光。
無字幕、無商標/Logo/水印。」

鏡頭語法：起手 28mm 空間 → 45mm 親密 → 壓縮 105mm 收束；
光圈 T2.8 漸收至 T4；快門角 180° 隨冰脈爆裂時短暫收至 160°；
對焦：角色單點眼 → 呼吸拉焦冰紋 → 前中後層次掃描。
光影：側逆光＋極光填光；色溫 3600–4000K；
對比 高；眼神光 保留。
色調/LUT：膚色優先，陰影微藍・高光暖，去飽和7%。
聲音：環境震動、碎冰崩落、冷風呼鳴；音樂 氛圍弦樂＋低頻脈衝。
轉場：直接切入，結尾以霜霧遮擋轉黑 0.6s。
安全：僅主角入鏡，無可讀文字，時序連戲一致。
```

## Scene Block（15s 單場景）
```
Act 1（0–15s）
意圖：決斷式釋放冰系防禦
基調：緊張→決斷
節奏域：慢入0.8–1.5 → 加速2.6 → 收束1.8s
美術要點：焦裂黑地、發光冰脈、晶牆紋理、冷霧顆粒

Beat 1（0–5s）
重點：蓄力跺地引發初始冰紋
Blocking：角色入畫站定 → 右腳抬高 → 重踩地面
Camera：
- 運鏡：滑軌緩推
- 焦段/機位：28mm 眼高
- 對焦：單點鎖腳部
- 快門角：180°；拍點：腳掌落地瞬間
光影：冰藍腳底補光＋側逆光描輪廓；對比中高；眼神光輕保留
色調/LUT：膚色優先，陰影微藍 12%，高光暖 8%
聲音：低頻脈衝預告＋地底轟鳴；音樂 BPM 96 慢入；衣料摩擦
轉場：直接切入過去黑場

Angle A
構圖：中央偏下，留白 15% 於上方極光
內容：中近景腳落地，霜霧被震開
補充：微粒雪塵向鏡頭飄落，地面細裂紋閃光
安全：無標誌

Beat 2（5–10s）
重點：冰紋流竄穿越畫面並拔起晶牆
Blocking：角色前傾推手指向前；冰脈環繞腳下向前奔
Camera：
- 運鏡：滑軌前推接微側移包住冰紋動線
- 焦段/機位：45mm 胸高
- 對焦：呼吸拉焦 隨冰紋前進
- 快門角：180°
光影：冰紋自發冷光補亮地面，極光反射晶體
色調/LUT：陰影微藍 10%，高光暖 6%
聲音：冰裂擴散、霜霧噴湧、角色低聲咒語
轉場：冰紋跑向鏡頭造成動態遮擋

Angle B
構圖：前中後三層，冰紋作為前景流線
內容：中景角色＋前景冰紋追蹤
補充：地面裂縫逸散冷霧，微粒向兩側飛濺
安全：無可讀字

Beat 3（10–15s）
重點：晶牆拔地而起後崩落雪霧
Blocking：角色雙臂撐起防禦姿態 → 牆升至頭頂 → 頂端碎裂成雪霧
Camera：
- 運鏡：半繞拍 35% 弧度後收至 105mm 壓縮
- 焦段/機位：開場 70mm 眼高 → 結尾 105mm 俯 10°
- 對焦：層次拉焦 角色→晶牆→碎片
- 快門角：爆裂瞬間 160°，餘段 180°
光影：晶牆折射極光；崩落時背光穿霧形成體積光
色調/LUT：陰影微藍 8%，高光暖 5%
聲音：冰牆咆哮崩碎＋雪霧落地；音樂 transient 強化破裂瞬間
轉場：霜煙充滿鏡頭羽化至黑

Angle C
構圖：中央主體，晶牆拱出形成保護弧
內容：角色仰視晶牆，碎片在前景掠過
補充：霜煙 Flipbook 疊加，地面殘留冰紋冷光跳動
安全：僅主角
```

## VFX 技術細節
- Flowmap 擴散：以角色腳掌落點為 UV 中心，0–5s 低頻震動驅動 Flowmap 線條向外脈衝，5–10s 加速並在冰紋頂端疊加 Fresnel 边缘光。
- 頂點位移結晶：Niagara Mesh Particles 驅動晶體網格；在 8–12s 以高度圖推頂點，補充內部次表面散射，崩解時切換至 Vertex Animation Texture 使碎片折射極光。
- Flipbook 霜煙：Houdini 生成 16×16 Flipbook，10–15s 於晶牆崩落時分三層播放，前景透明度 0.65，後景 0.4，並以風向噴射向鏡頭。
- 觸覺強化：地面震感透過 Camera Shake（低頻 0.8 振幅）與 Screen-space 小幅偏移呈現。

## 感官與動作對應
- 觸覺：跺地瞬間畫面輕震，地面裂縫伴隨細碎石粉彈起。
- 嗅覺：冷霧帶鹹味提示冰霜來自深海裂隙，於角色呼吸時在 Foley 中補入。
- 動作節點：跺地 → 冰紋擴張 → 冰牆升起 → 崩落雪霧，節奏隨 0–5 / 5–10 / 10–15s 明確段落推進。

## 音訊設計
- 根據 Sci-Fi Realism Audio pack：BPM 96、低頻 40–80Hz 與冰紋亮度同步；瞬音層 -8 dB 於晶牆崩裂時觸發。
- Foley：靴踩硬冰、裂縫爆鳴、風中細雪擦聲，保持動態範圍 -18 至 -6 dBFS。
- 混音：Limiter -1 dBTP，整體 -14 LUFS；側鏈連動 VFX 觸發以騰出瞬時能量峰值。

## 交付備註
- 時長 15s、2.39:1、24fps ProRes 4444；附 5.1 stems（環境／Foley／音樂／VFX）。
- 器材：可用 UE5 Sequencer + Niagara 或 Unity HDRP + VFX Graph，需支援 Flowmap 與 VAT。
- QA：確認無版權元素、極光貼圖採 CC0，角色造型符合上傳參考。

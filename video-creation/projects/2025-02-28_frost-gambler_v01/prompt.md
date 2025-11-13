# 霜牌幻術師 × 冰霜爆破｜寫實遊戲風 Prompt（15s 動作戰鬥分鏡）

## 一句話題材
用爆破撲克牌先凍結，再粉碎敵人。

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

### Style Pack：Frost Gambler Look（`_stylepacks/frost_gambler/look.yml`）
```yaml
name: Frost Gambler Look
lut: Glacial-Edge
saturation_adjust: -0.04
contrast: crisp_frostbite
highlights: polar_silver
shadows: abyssal_cyan
affinity_glow: refracted_iceband
texture: reinforced_leather_parka
chromatic_aberration: subtle_prismatic_shear
lens_distortion: micro_pincushion
notes:
  - 夜間場景以冰藍與月白為主軸，維持主角膚色在 50 IRE 以免過冷。
  - 撲克牌邊緣的霜紋需呈現半透明折射感，貼附時帶輕微霜霧。
  - 冰霜爆炸使用冷色體積光，控制亮度避免蓋過 HUD 細節。
```

### Style Pack：Frost Gambler VFX（`_stylepacks/frost_gambler/vfx.yml`）
```yaml
name: Frost Gambler VFX
niagara_presets:
  - card_frost_bind
  - shatter_chainwave
  - hud_cryo_reticle
unity_vfx_graph:
  - Gambler.FrostLatch.vfx
  - Gambler.CryoDetonate.vfx
  - Gambler.IceDustBloom.vfx
houdini_flipbooks:
  - ice_platelet_burst
  - frost_wave_shell
  - card_frag_glassmix
shader_settings:
  rune_edge_emit: 0.48
  cryo_rime_spread: 0.67
  shatter_impulse: 0.61
  debris_velocity_random: 0.52
sdf_settings:
  armor_surface_wrap: 0.34
  hud_lockbox_radius: 0.18
  shatter_offset_delay: 0.14
bloom_control:
  idle: 0.12
  trigger_peak: 0.68
  cooldown: 0.29
audio_sync:
  card_tap: sync_to_crunch
  freeze_trigger: rising_glass_ping
  shatter: cascading_cryo_blast
notes:
  - 霜爆需以 0.25s 延遲呈現冰紋擴散，粒子密度從中心快速外推。
  - 粉碎階段加入玻璃碎片混合冰晶，落地時 1.8s 內緩慢淡出。
  - HUD 準星以淡藍光脈動顯示冷卻狀態，避免與主體混淆。
```

### Style Pack：Frost Gambler Audio（`_stylepacks/frost_gambler/audio.yml`）
```yaml
name: Frost Gambler Audio
core_layers:
  - polar_wind_bed
  - neon_icicle_drones
  - card_snap_percussion
  - subpulse_frost_core
peak_events:
  - timestamp: card_flick
    sfx: lacquer_snap_icy
    level_db: -11
    stereo_width: 80
  - timestamp: freeze_bloom
    sfx: cryo_spread_chime
    level_db: -7
    stereo_width: 120
  - timestamp: shatter_chain
    sfx: glass_ice_implosion
    level_db: -3
    stereo_width: 160
low_freq_management:
  sub_ceiling_db: -8
  lfe_emphasis: 48Hz
sidechain:
  trigger_bus: shatter_impacts
  target: ambience_pad
  reduction_db: 3.6
notes:
  - 風聲需帶霜霧顆粒感，與環境金屬殘響交錯。
  - 凍結瞬間加入水晶延音，強調時間凝結效果。
  - 粉碎爆炸搭配低頻衝擊與高頻碎裂層次，保持節奏俐落。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Frost Gambler Look｜16:9｜24fps｜冷霜爆破寫實)
「午夜霓虹映照的廢墟廣場；積水倒影、冰霧冷風、遠處殘垣霜霧；霜牌幻術師以冰霜撲克牌定身怪物並引爆粉碎。」
鏡頭：穩定器滑軌結合半肩視角，爆破瞬間以鞭移與子彈時間切換。
表演：冷靜決斷、指尖俐落彈牌、視線鎖定鎖定目標。
臉型/髮型：依上傳五官特徵，黑髮微濕後梳，鬢角被冷風掀起。
構圖：前中後層次＋三分線，HUD 留白 15%；動態：風卷冰霧、水窪波紋、碎冰粒子。
寫實細節：防寒長外套內藏銀藍襯裡、皮手套覆霜、撲克牌冰紋符文、怪物金屬縫補與冰殼質感。
無字幕、無商標/Logo/水印。

鏡頭語法：24–35 空間｜50–75 親密｜100–135 壓縮；
光圈 {T2.0–T2.8}；快門角 {180°/200–240°}；
對焦 {單點眼/層次前→中→後}。
光影：{側逆/霓虹混光}；色溫 {夜3000–3800K}；
對比 {高}；眼神光 {保留}。
色調/LUT：{自然肌理/膚色優先/陰影微藍・高光暖/去飽和5–10%}。
聲音：環境/腳步/衣料/風/遠人聲（-6 dB 峰值）；音樂 {節奏輕推}。
轉場：{直接切/光源匹配/鞭移/羽化0.4s}。
安全：無品牌/無可讀文件/群眾臉不近特寫/連戲與時序一致。
```

## Scene Blocks

### Act 1（0.0–4.8s）
意圖：建立
基調：緊張
節奏域：慢入0.8–1.5
美術要點：夜晚廢墟廣場、水窪霓虹倒影、寒氣白霧、防寒長外套與霜紋撲克牌

#### Beat 1（0.0–1.2s）
重點：寒氣登場與職業氛圍
Blocking：主角背影自左側入畫，步伐緩慢，呼出白霧停留
Camera：
- 運鏡：滑軌平推
- 焦段/機位：32mm 肩後
- 對焦：單點鎖定主角上半身
- 快門角：200；拍點：白霧停頓
光影：側逆霓虹映出冷藍 rim light
色調/LUT：陰影微藍，皮膚保持 50 IRE
聲音：極冷風聲與腳步濺水，指尖敲牌「嗒嗒」回響
轉場：直接切至半身特寫

Angle A
構圖：三分線，主角佔左前景，霓虹倒影延伸
內容：主角背影、濕地面反射
補充：鏡頭前偶有霜霧掠過造成柔焦
安全：場景僅主角

#### Beat 2（1.2–2.4s）
重點：冰霜撲克牌特寫
Blocking：主角停步，手腕旋轉洗牌，眼神冷靜望向前方
Camera：
- 運鏡：穩定器微推近
- 焦段/機位：55mm 胸高
- 對焦：單點鎖定牌邊冰紋
- 快門角：180；拍點：冰紋亮起
光影：霓虹冷光沿牌邊掃過
色調/LUT：膚色優先，冰紋淡藍高亮
聲音：撲克牌摩擦聲與冷風掠過布料
轉場：手勢遮擋切向前方

Angle B
構圖：中央偏右，手勢佔前景
內容：牌邊霜紋蔓延
補充：指尖揚起微霜粒子
安全：無可讀字

#### Beat 3（2.4–3.6s）
重點：怪物逼近營造威脅
Blocking：鏡頭轉向前方陰影，怪物踏水而出
Camera：
- 運鏡：滑軌後退抬升
- 焦段/機位：28mm 眼高
- 對焦：層次拉焦 前排怪物→發光核心
- 快門角：200；拍點：核心閃動
光影：冷色頂光＋核心微弱橙光
色調/LUT：去飽和5%，保留核心暖色對比
聲音：低沉嘶吼伴隨水花濺起
轉場：怪物揮臂造成鞭移回主角

Angle C
構圖：中央對稱，怪物群佔畫面
內容：金屬縫補皮膚與胸口核心
補充：水滴飛濺形成冷光散射
安全：僅怪物

#### Beat 4（3.6–4.8s）
重點：鎖定第一個目標
Blocking：回到主角背後視角，拇指推出一張牌
Camera：
- 運鏡：半肩視角微前推
- 焦段/機位：45mm 肩後
- 對焦：層次拉焦 手→HUD→怪物胸口
- 快門角：180；拍點：準星收束
光影：HUD 淡藍光映在雨霧中
色調/LUT：HUD 控制在 110 nits 冷藍
聲音：心跳低頻與風聲呼嘯
轉場：羽化0.4s 進入慢動作

Angle D
構圖：中央準星框定怪物
內容：HUD 準星與發光牌邊
補充：冷霧在鏡頭前掠過
安全：HUD 無文字

### Act 2（4.8–8.4s）
意圖：敘事
基調：決斷
節奏域：穩定1.5–2.4
美術要點：冰霜殘影、淡藍粒子、怪物裝甲結霜

#### Beat 5（4.8–6.0s）
重點：第一次投擲 — 霜爆預告
Blocking：主角彈出卡牌，進入慢動作跟拍
Camera：
- 運鏡：滑軌直線跟隨
- 焦段/機位：60mm 平視
- 對焦：呼吸拉焦 手→飛行牌
- 快門角：200；拍點：牌離指尖
光影：牌邊拉出藍白殘影
色調/LUT：高光偏銀白，陰影保持冷藍
聲音：尖銳「咻」聲伴微粒破風
轉場：動態匹配帶向怪物

Angle E
構圖：過肩視角，牌沿視線飛出
內容：飛行卡牌與藍光軌跡
補充：細小冰晶沿軌跡飄散
安全：畫面乾淨

#### Beat 6（6.0–7.2s）
重點：貼牌＋冰霜陣式展開
Blocking：卡牌貼在怪物胸口，符文亮起
Camera：
- 運鏡：穩定器快推至胸口特寫
- 焦段/機位：85mm 胸高
- 對焦：單點鎖定卡牌
- 快門角：180；拍點：陣紋擴散
光影：淡藍符紋投射體積光
色調/LUT：冰紋亮度 120 nits，裝甲保留金屬細節
聲音：細碎「噼啪」結冰聲
轉場：符紋閃光作遮擋切

Angle F
構圖：中央特寫
內容：卡牌符紋與裝甲霜層
補充：冷霧從接觸面飄散
安全：無文字

#### Beat 7（7.2–8.4s）
重點：第一次爆破 — 全身凍結
Blocking：霜爆向外炸開，怪物凝結成冰雕
Camera：
- 運鏡：子彈時間環繞 120°
- 焦段/機位：40mm 環繞
- 對焦：層次拉焦 爆心→冰殼邊緣
- 快門角：200；拍點：衝擊波擴散
光影：冰霜衝擊波帶霧狀高光
色調/LUT：高光偏月白，陰影深藍
聲音：悶爆「砰」＋低頻震動
轉場：直接切至主角廣角

Angle G
構圖：中央怪物成冰雕，周圍粒子填滿中景
內容：半徑數公尺淡藍衝擊波
補充：地面水窪凍成放射狀冰紋
安全：僅怪物

### Act 3（8.4–12.0s）
意圖：轉折
基調：緊張
節奏域：加速2.4–3.0
美術要點：多張卡牌扇形殘影、連鎖凍結與粉碎冰塵

#### Beat 8（8.4–9.6s）
重點：多目標投擲 — 廣域凍結
Blocking：主角雙手扇形拋出多張牌
Camera：
- 運鏡：穩定器側移帶弧線
- 焦段/機位：35mm 胸高
- 對焦：層次拉焦 手→空中牌→目標
- 快門角：200；拍點：牌群展開
光影：牌背冷光拖出弧形軌跡
色調/LUT：藍白殘影強調扇形
聲音：卡牌破風疊加
轉場：動態匹配跟進怪物

Angle H
構圖：中央主角，扇形牌佔前景
內容：多張卡牌飛向不同怪物
補充：冰羽粒子散落
安全：畫面乾淨

#### Beat 9（9.6–10.8s）
重點：第二次爆破 — 粉碎連鎖起點
Blocking：主角食指點擊 HUD，引爆最近怪物
Camera：
- 運鏡：肩後視角微拉近
- 焦段/機位：50mm 肩後
- 對焦：層次拉焦 手→HUD→目標
- 快門角：180；拍點：牌面閃光
光影：冰殼內部亮起尖銳銀光
色調/LUT：粉碎瞬間高對比
聲音：清脆「鏘」＋碎片飛散聲
轉場：爆炸粒子遮擋切到其他怪物

Angle I
構圖：中央準星鎖定被引爆怪物
內容：冰殼與身體同時炸裂
補充：碎片飛濺至鏡頭前形成擦痕
安全：畫面僅怪物

#### Beat 10（10.8–12.0s）
重點：群體粉碎 — 爆牌連鎖
Blocking：其他怪物依序爆裂成冰塵
Camera：
- 運鏡：滑軌快速推進穿越爆炸
- 焦段/機位：28mm 眼高
- 對焦：層次拉焦 爆炸前景→後排
- 快門角：240；拍點：每次連鎖爆破
光影：冷色霧氣輪流亮起
色調/LUT：冰晶塵霧反射霓虹
聲音：連續爆裂與冰屑落地「叮叮」
轉場：最後一次爆光作遮擋切

Angle J
構圖：中央深景，連鎖爆破形成透視
內容：碎冰與卡牌碎片漫天飛舞
補充：地面快速覆蓋冰晶層
安全：無旁人

### Act 4（12.0–15.0s）
意圖：收束
基調：決斷
節奏域：穩定1.5–2.4 → 慢入0.8
美術要點：精英怪物半結冰、漂浮牌環、終結冰爆與收尾冰塵

#### Beat 11（12.0–13.5s）
重點：精英怪物 — 集束霜爆預備
Blocking：半結冰的精英怪衝向主角，牌環集結
Camera：
- 運鏡：穩定器後退配合抬升
- 焦段/機位：40mm 胸高
- 對焦：層次拉焦 怪物→漂浮牌
- 快門角：200；拍點：牌環鎖定
光影：牌環淡藍脈動照亮冷霧
色調/LUT：怪物半身冰鎖與裸露金屬對比
聲音：鐵鎖拖曳聲＋牌環嗡鳴
轉場：主角指尖一捻觸發閃光

Angle K
構圖：中央怪物，牌環形成環狀前景
內容：漂浮撲克牌旋轉
補充：地面殘牌同時升起
安全：僅怪物與主角

#### Beat 12（13.5–15.0s）
重點：終結畫面 — 霜碎餘光
Blocking：精英怪瞬間凍成冰雕並粉碎，主角收牌
Camera：
- 運鏡：慢動作推進至主角側面
- 焦段/機位：65mm 半身
- 對焦：單點鎖定主角，碎片前景散焦
- 快門角：180；拍點：碎冰掠過鏡頭
光影：爆光漸弱，殘留冰屑反射霓虹
色調/LUT：冰屑呈銀藍星點，背景去飽和
聲音：粉碎轟鳴漸淡，只剩風掃冰屑摩擦
轉場：淡出至黑

Angle L
構圖：主角居中偏右，前景碎片飛舞
內容：主角收起剩餘撲克牌
補充：冰屑擦過鏡頭留下霜痕
安全：畫面乾淨

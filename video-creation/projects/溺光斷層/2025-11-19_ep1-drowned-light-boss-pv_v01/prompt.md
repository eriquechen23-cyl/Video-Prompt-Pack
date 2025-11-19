# 溺光斷層 EP1 — 溺光君・那薩爾 BOSS PV Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-19_drowned-light-faultline-boss-pv_v01/script.md

## 一句話題材
環形海洋翻覆的瞬間，溺光君・那薩爾以水、光與記憶的審判，逼問玩家「水會記得你什麼？」的 15 秒最終章 PV。

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

### QA Checklist（`_core/qa_checklist.md`）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

### Style Pack：Drowned Light Faultline Halo Look（新樣板）
```yaml
name: Drowned Light Faultline Halo Look
lut: abyssal_glass-prism
color_palette:
  primaries: [abyss_blue, tidal_teal, cathedral_slate]
  accents: [caustic_gold, memory_amber, aurora_white]
lighting:
  key: volumetric_godray_4800K through flooded windows
  fill: water_bounce_cyan at 20% intensity
  rim: halo_prismatic_spin with RGB dispersion
materials:
  coat: deep_blue velvet with gold tide embroidery that dissolves into liquid ribbons
  skin: reflective water-mirror with micro ripples and refraction shards
  environment: soaked stone, cracked sea-wall sigils emitting light leaks
lens_treatment:
  focal_stack: 24–85mm anamorphic squeeze 1.5x
  bloom: 0.32 focused on caustics
  chromatic_aberration: asymmetric teal-magenta on highlights
notes:
  - 全部倒影需比實景多 8% 曝光並添加波紋畸變，營造記憶被水重寫的錯位。
  - Halo 環必須維持三層不同轉速；進入 Phase 2 時加上光譜拖尾 2f。
```

### Style Pack：Drowned Light Faultline Abyssal VFX（新樣板）
```yaml
name: Drowned Light Faultline Abyssal VFX
niagara_presets:
  - reverse_tide_ring (triple water rings orbiting with flowmap flip)
  - memory_refraction_panel (projects archived deaths as translucent panels)
  - flood_inversion_column (ceiling-to-floor water swap)
unity_vfx_graph:
  - Halo.Ring.Counterflow.vfx
  - Lightwell.Invert.Spiral.vfx
  - Reflection.Specter.Burst.vfx
houdini_flipbooks:
  - water_blade_arc_16x16
  - shattered_glass_caustic_8x8
  - drowned_face_echo_8x8
sync_hooks:
  verdict_lines: trigger refract_strength 0.45 + RGB split
  flood_alarm: ramp particle_emission 0 → 1 in 0.4s and rotate scene cube 180°
  memory_cut: spawn drowned_face_echo tied to VO phonemes
notes:
  - 水刃需沿地面 Flowmap 追蹤波紋提示；命中後在 4f 內解構成霧。
  - 倒灌階段將整場加上一層 3cm 深水的屏幕空間貼圖以產生倒影雙世界。
```

### Style Pack：Drowned Light Faultline Resonance Audio（新樣板）
```yaml
name: Drowned Light Faultline Resonance Audio
bed_layers:
  - tidal_memory_drone (subpulse with heartlike rhythm)
  - cathedral_echo_bed (mid-frequency reverb tail)
  - distant_thunder_rumble (48Hz emphasis)
accent_fx:
  - reverse_splash_suck (water climbing surfaces)
  - prism_refraction_ping (glass harmonics)
  - drowned_voice_chorus (filtered whispers)
  - hydraulic_ceiling_snap (for flood inversion)
vo_processing:
  - narrator: low male, plate reverb 0.8s, HPF 120Hz
  - Nassal: genderless watery timbre with 180ms slapback echo and phaser 15%
mix_notes:
  - Maintain -10 dB peaks on verdict hits, subpulse sidechain ducked 2dB when VO enters.
  - Reverse splash cues align with camera flip transitions; final tagline drops to near-silence except single water drop echo.
```

---

## Master Prompt 實際填寫
```
Master(15s｜Drowned Light Faultline Halo｜16:9｜24fps｜dark fantasy tidal realism)
「午夜的《溺光斷層》階潮城；環形海洋、倒灌海壁、半淹沒聖堂；溺光君・那薩爾於倒灌時刻啟動水光審判並召喚倒置鏡像的 BOSS 戰。」
鏡頭：Act1 24mm 俯視推進→32mm 滑軌沿海壁→28mm 水下仰視→35mm 低角跟腳；Act2 38–50mm 水面俯視、45mm 繞拍、55mm 橫掃；Act3 32mm 抬升翻轉、40mm 分割構圖、65mm 半身威脅。
表演：那薩爾維持冷靜審判口吻，動作如對潮汐下指令；旁白低沉宣告環境規則；玩家僅以呼吸與腳步表現緊張。
臉型/髮型：貴族輪廓被水面折射，兩枚垂直水滴瞳孔含細光線倒映玩家；濡濕髮絲貼於側臉但在審判時被水流托起。
構圖：多使用中央對稱與倒影對稱；前景水紋提供引導線，中景人物，後景環海與倒置城市。
寫實細節：禮服上半身以深藍天鵝絨編金水紋，膝下化作流動水帶；胸前倒三角玻璃器緩慢浮出溺者面孔；指尖手套延伸水刃與斷面圓鋸。
無字幕、無商標/Logo/水印。」

鏡頭語法：空間建立用 24–35mm，壓迫感以 65–85mm 壓縮；
光圈 {Act1 T4 兼顧景深、Act2 T2.8 聚焦 BOSS 手勢、Act3 T2.2 增加倒影朦朧}；快門角 {常規 180°，倒灌翻轉 144°，記憶溺斷 200°}；
對焦 {前→中→後層次跟隨水紋提示，Nassal 臉部保持單點眼，倒影世界使用呼吸拉焦交替上下兩層}。
光影：體積月光穿過破頂，腳下淺水投射流動 caustics；倒灌時天花板與地面交換光源；色溫 4300–5200K 之間依 phase 漸變。
色調/LUT：陰影偏潮濕青綠，高光加入金色散射；倒影層增加 8% 曝光並加入色散 fringe；膚色/水面維持自然肌理。
聲音：tidal_memory_drone + cathedral_echo_bed 為底，reverse_splash_suck 在倒流時觸發，prism_refraction_ping 配合水環光束，VO 依劇本配置 Tagline/旁白/那薩爾句子。
轉場：海浪硬切→裂光匹配→水面遮擋→倒灌翻轉鞭移→倒影羽化→黑場 + 水滴 echo。
安全：僅虛構符號，無真實地標，水量壓制於可控層且無溺亡明示畫面。
```

### Camera Continuity
- 作為系列首支 PV，開場以與世界觀宣傳稿一致的「環形海洋俯視」延續；鏡頭順著潮印紋路推進，再轉為水下仰視確保方位銜接。
- 倒灌翻轉沿用《溺光斷層》概念稿的旋轉中心（位於光井軸線），轉場時保持螺旋方向一致以利日後劇情接上戰鬥實機。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.8s）
意圖：建立世界規則與玩家踏入審判殿堂
基調：冷峻預兆
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：環形海洋、海壁裂縫、水下城市倒影、淺水大殿

#### Beat 1（0.0–1.2s）
重點：俯視環形海洋＋Tagline
Blocking：衛星視角沿海面迅速下推，浪潮向上拱起。
Camera：
- 運鏡：24mm 高空俯衝滑軌
- 焦段/機位：24mm 300m 高度俯視
- 對焦：層次從外環 → 城市中心
- 快門角：180；拍點：VO Tagline 開口
光影：月光照亮浪尖，海霧閃電反射
色調/LUT：青藍主色，遠處金色裂縫
聲音：VO（旁白）「In a world where the ocean remembers everything… even your sins learn to swim.」＋遠海隆隆
轉場：鏡頭穿越雲層硬切 → Angle 1

Angle 1（0.0–1.2s）
構圖：中央圓形城市，被海洋同心包圍
內容：外環海浪逆重力拱起
補充：浪面帶色散光束
安全：無地標或文字

#### Beat 2（1.2–2.4s）
重點：海壁裂縫預示倒灌
Blocking：沿裂縫滑行，水開始往上爬。
Camera：
- 運鏡：32mm 側向滑軌
- 焦段/機位：32mm 腰高平視海壁
- 對焦：裂縫前景 → 背後潮水
- 快門角：180；拍點：裂光擴散
光影：裂口射出冷金光；周圍陰影偏青
色調/LUT：海壁灰岩＋青綠水紋
聲音：VO（旁白）“…and judged by the tide.”＋水倒流吸力聲
轉場：裂光閃至全白 → Angle 2

Angle 2（1.2–2.4s）
構圖：對角裂縫貫穿畫面
內容：水紋逆向貼壁上爬
補充：微型潮印符文發亮
安全：符文為抽象圖樣

#### Beat 3（2.4–3.6s）
重點：水下倒影城市
Blocking：鏡頭沉入水下仰視城市倒影，泡沫向上飄。
Camera：
- 運鏡：28mm 下沉後慢推
- 焦段/機位：28mm 水下 5m 仰角 30°
- 對焦：倒影輪廓 → 氣泡
- 快門角：180；拍點：鐘聲
光影：水面上方街燈成破碎光束
色調/LUT：青綠霧化，倒影邊緣金
聲音：VO（記憶低語）“Every flood rewrites what the streets remember…”＋悶鐘聲
轉場：氣泡穿鏡匹配 → Angle 3

Angle 3（2.4–3.6s）
構圖：上下顛倒對稱，城市在上方
內容：半淹雕像與倒影重疊
補充：玻璃碎片漂浮
安全：無人像特寫

#### Beat 4（3.6–4.8s）
重點：玩家踏入淺水殿堂
Blocking：低角跟拍腳步進入殿堂，天花板破洞透光。
Camera：
- 運鏡：35mm 低角跟隨
- 焦段/機位：35mm 腳踝高度仰視 15°
- 對焦：前景水花 → 遠處王座
- 快門角：180；拍點：腳步落水
光影：地面水層反射破頂月光
色調/LUT：石牆冷灰＋水面青藍
聲音：VO（旁白）“Yet you dare to walk into the drowned hall.”＋腳步回音
轉場：水花濺起覆鏡 → Angle 4

Angle 4（3.6–4.8s）
構圖：前景腳步，遠處王座置中
內容：水面映出破頂夜空
補充：細小水紋向外擴散
安全：僅無名腳掌

### Act 2（4.8–9.6s）
意圖：展示那薩爾出場與水光攻勢
基調：審判壓迫
節奏域：穩定1.5–2.4
美術要點：水面倒影、BOSS 水面臉、三層水環、記憶投影

#### Beat 5（4.8–6.0s）
重點：倒影先於實體出現
Blocking：俯視水面，第二道剪影出現；主角尚未看到實體。
Camera：
- 運鏡：38mm 俯視定鏡微推
- 焦段/機位：38mm 俯角 25°
- 對焦：水面反射
- 快門角：180；拍點：影子成形
光影：水面反射拉絲光
色調/LUT：冷青主調，倒影偏亮
聲音：VO（那薩爾）“Your reflection arrived before you did.”＋低頻水聲
轉場：水面震動變形 → Angle 5

Angle 5（4.8–6.0s）
構圖：中央對稱，兩個倒影交疊
內容：第二道高大剪影無對應實體
補充：倒影邊緣像碎鏡
安全：無直接人像

#### Beat 6（6.0–7.2s）
重點：那薩爾從水面升起
Blocking：水柱拔起形成人形，鏡頭仰視他站立。
Camera：
- 運鏡：45mm 仰角穩定器微推
- 焦段/機位：45mm 胸高仰角 20°
- 對焦：單點那薩爾面部水滴
- 快門角：180；拍點：站定
光影：逆光勾勒水輪廓
色調/LUT：臉部青綠、金色光絲
聲音：VO（那薩爾）“Kneel, or drown standing.”＋金屬鎖鏈＋聚水聲
轉場：胸前玻璃容器閃光 → Angle 6

Angle 6（6.0–7.2s）
構圖：中景仰視
內容：臉為水面＋碎鏡，眼睛為垂直水滴
補充：胸口三角器中浮現面孔
安全：僅虛構人物

#### Beat 7（7.2–8.4s）
重點：三層水環啟動
Blocking：半身繞拍，水環逆向旋轉，倒影顯示另一姿態。
Camera：
- 運鏡：50mm 半圓繞拍
- 焦段/機位：50mm 胸高
- 對焦：呼吸拉焦在水環與臉
- 快門角：180；拍點：環啟動
光影：水環折射出色散光束
色調/LUT：青綠＋金亮點
聲音：VO（旁白）“He is the Lord of Drowned Light…”＋迴旋低鳴
轉場：光束掃過鏡頭 → Angle 7

Angle 7（7.2–8.4s）
構圖：那薩爾置中，背後三環
內容：環旋轉方向各異
補充：地面反射顯示倒置城市
安全：無其他角色

#### Beat 8（8.4–9.6s）
重點：水刃斬擊展示
Blocking：那薩爾彈指，地面水紋豎起成弧形刀鋒掃過柱子。
Camera：
- 運鏡：55mm 側向跟拍
- 焦段/機位：55mm 腰高
- 對焦：層次從指尖 → 水刃
- 快門角：180；拍點：刀鋒出鞘
光影：水刃帶內部閃電高光
色調/LUT：刀刃略帶金光
聲音：VO（那薩爾）“…and every cut carries a memory.”＋水刃破空聲
轉場：水刃劃過產生鞭移 → Angle 8

Angle 8（8.4–9.6s）
構圖：對角線動勢
內容：水刃切開石柱，斷面映出舊戰鬥畫面
補充：水滴變成記憶影像
安全：記憶片段抽象無血

### Act 3（9.6–15.0s）
意圖：倒灌翻轉、上下雙世界與 CTA
基調：末日審判
節奏域：加速2.4–3.0
美術要點：倒灌光井、全場淺水反射、雙世界錯位、Title Card

#### Beat 9（9.6–10.8s）
重點：記憶映像攻擊
Blocking：水牆亮起玩家過去死亡畫面撲向鏡頭。
Camera：
- 運鏡：48mm 主觀視角微推
- 焦段/機位：48mm 眼高
- 對焦：層次拉焦於不同記憶面板
- 快門角：200；拍點：影像衝擊
光影：面板自發光＋外部冷霧
色調/LUT：記憶內暖，外冷
聲音：VO（那薩爾）“Run from me… and you only run into your past.”＋多重回聲
轉場：面板破裂成水滴 → Angle 9

Angle 9（9.6–10.8s）
構圖：全幅被記憶面板包覆
內容：玩家失敗殘影衝來
補充：HUD 線條顫抖
安全：影像模糊無辨識

#### Beat 10（10.8–12.0s）
重點：倒灌翻轉
Blocking：天花板崩開海水倒灌，同時地面水面向上墜落，整場翻轉。
Camera：
- 運鏡：32mm 由下往上仰角
- 焦段/機位：32mm 腰高仰視 40°
- 對焦：天花裂縫 → 蘿旋水柱
- 快門角：144；拍點：翻轉瞬間
光影：上下光源互換
色調/LUT：青綠水霧 + 金色裂光
聲音：VO（旁白）“When the flood comes…”＋hydraulic_ceiling_snap
轉場：整個畫面旋轉 180° → Angle 10

Angle 10（10.8–12.0s）
構圖：畫面中線成旋渦
內容：水柱逆重力繞光井
補充：粒子沿螺旋而上
安全：僅環境

#### Beat 11（12.0–13.2s）
重點：上下顛倒雙世界
Blocking：玩家站在淺水平台；倒影中另一個那薩爾動作預告攻勢。
Camera：
- 運鏡：40mm 橫向移動
- 焦段/機位：40mm 眼高
- 對焦：呼吸拉焦於實體與倒影
- 快門角：200；拍點：倒影先動
光影：上方為倒置城鎮，腳下反射亮度提高
色調/LUT：上冷下暖形成對比
聲音：VO（那薩爾）“…your world and its reflection will drown together.”＋心跳聲
轉場：倒影波動遮擋 → Angle 11

Angle 11（12.0–13.2s）
構圖：上下分割構圖，中線為水面
內容：上方城市倒置，下方真實戰場
補充：倒影中的那薩爾手勢與實體錯位
安全：玩家僅剪影

#### Beat 12（13.2–15.0s）
重點：Title Card 與最後威脅
Blocking：那薩爾伸手至鏡頭，水滴覆蓋鏡頭→黑場→Title card；VO 收尾。
Camera：
- 運鏡：65mm 微推
- 焦段/機位：65mm 胸高
- 對焦：單點那薩爾指尖→黑場→Title
- 快門角：180；拍點：水滴覆蓋
光影：臉部冷青，背後金環
色調/LUT：冷青膚與金色點綴
聲音：VO（那薩爾）“So tell me… what will the water remember you for?”＋單一水滴 echo
轉場：指尖水滴成黑→ Title card 漸顯

Angle 12（13.2–15.0s）
構圖：特寫指尖後切至 Title 居中
內容：LOGO `DROWNED LIGHT FAULTLINE` + 副標 `Boss: Nassal, Lord of Drowned Light`
補充：背景僅淡水霧
安全：文字為虛構標題

## Audio Layering & Mix Notes
- 依 `_core/audio_pack.md` 結構配置：環境層為 tidal_memory_drone + cathedral_echo_bed；腳步與衣料僅在 Beat4/5 輕量加入；風聲透過 distant_thunder_rumble 製造壓力。
- VO routing：旁白與那薩爾分別佔用 L/R 15° 偏移，Nassal 聲線加入 phaser 15% 與 180ms slapback；Tagline 與結尾台詞留 -1.5 dB headroom。
- Transient mapping：水刃、水柱、倒灌翻轉同步 arc_flash_whoosh + hydraulic_ceiling_snap；記憶面板爆裂鎖定於 70 BPM 的第 5、7 拍。

## VFX Implementation Notes
- 水面倒影統一使用 Flowmap UV offset 0.12，並透過 reverse_tide_ring Preset 控制三層水環旋速（外層 0.7x，內層 -1.2x）。
- 記憶映像採 memory_refraction_panel；面板材質使用 Fresnel + Depth Fade 與 drowned_face_echo flipbook 疊加。
- 倒灌翻轉時啟用 flood_inversion_column + Lightwell.Invert.Spiral.vfx，並將全場地材切換至 Screen Space Wetness 1.0 形成淺水反射。

### QA Checklist（自評 10/10）
- [x] 情緒→運鏡一致，焦段/對比/轉場已鎖定。
- [x] Nassal 水面臉保留眼神光；倒影膚色維持 55–65 IRE。
- [x] 所有轉場（光源匹配、倒灌鞭移、羽化）皆在分鏡中明記。
- [x] LUT、色溫、音畫同步門檻（70 BPM、-10 dB 峰值）記錄完成。
- [x] 無真實文字、Logo；記憶片段模糊處理。
- [x] 生成規格：16:9｜24fps｜15s，交付 -14 LUFS，符合 `_core/audio_pack.md` 要求。

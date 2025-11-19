# 霧環群島 EP1 — 灰戰女神・凱薇娜 登場 PV Prompt（15s｜12 幕）

來源劇本：灰戰女神・凱薇娜「石圈上的第一次審判」PV brief v1

## 一句話題材
戰爭女神凱薇娜在霧環群島的石圈中首次現身，以霧海、渡鴉與灰線裁決來襲戰士，逐步亮出戰略、血潮與戰史三階段的審判，最後以長矛敲定「踏入此圈者必付代價」的宣告。

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

## `_stylepacks` 區塊
### Style Pack：Grey Lady Stone Verdict Look（新樣板）
```yaml
name: Grey Lady Stone Verdict Look
line_enhancement: slate_trench_edge_highlight
noise_reduction: mist_grain_preserve
contrast_profile: high_micro_contrast_on_armor_low_saturation_skin
color_palette:
  primaries: [ashen_slate, cold_fog_white, peat_moss_green]
  accents: [ember_crimson, tarnished_gold, raven_black]
skin_tone: pale_ivory_with_cool_grey_tint
lighting:
  key: overcast_volumetric_window (3400–3800K)
  fill: ground_bounce_damp_moss (soft green 4200K)
  rim: raven_wing_specular (narrow 5200K to outline feathers)
materials:
  armor: ironwood_plate + etched_celtic_knots with wet sheen
  cloak: raven_feather_mantle with matte bloodstain embroidery
  stone: rain-darkened_basalt with lichen streaks
lens_treatment:
  bloom: restrained 0.18 focused on sigils
  chromatic_aberration: inward 0.01 during judgement pulses
  shutter_smear: 0.2 only when grey lines surge
notes:
  - 無現代兵器與旗幟，所有金屬沿用凱爾特符紋與骨飾。
  - 當顏色被抽離時僅保留灰、黑與象徵性暗紅，並維持皮膚細節。
  - 霧需帶冷濕體積感，羽毛保持獨立辨識不糊成塊。
```

### Style Pack：Grey Lady Stone Verdict VFX（新樣板）
```yaml
name: Grey Lady Stone Verdict VFX
niagara_presets:
  - mist_ring_lock (radial fog wall + grey erosion shader)
  - raven_crown_flock (vector field guided bird shadows)
  - war_weave_aerial_grid (silver thread lattice with emissive pulses)
unity_vfx_graph:
  - GreyLine.MarkArray.vfx
  - BloodMist.Diagonal.Cut.vfx
  - StoneSigil.EngraveGlow.vfx
houdini_flipbooks:
  - spear_trail_echo
  - cloak_blood_mist_plume
  - raven_feather_shed
shader_controls:
  grey_line_thickness: 0.2 → 0.45 第三階段
  war_weave_scroll_speed: sync_to_bpm_72
  color_siphon_ratio: 1.0 (retain eyes 100% saturation)
bloom_profile:
  idle: 0.12
  ability_peak: 0.32 (grey line impacts)
  judgement_freeze: 0.26 but with desat matte
sync_hooks:
  spear_tap: metallic_ping + line spawn
  raven_swarm: mid_high_noise_gate to open opacity
  title_slam: drum + stone shockwave expansion
notes:
  - 石圈投影需於人物背後呈 70% 透明度，禁止遮蔽臉部。
  - 血霧僅象徵性呈現，alpha 控制在 0.45 以下避免過度遮畫面。
```

### Style Pack：Grey Lady Stone Verdict Audio（新樣板）
```yaml
name: Grey Lady Stone Verdict Audio
bed_layers:
  - distant_basalt_drum (48 BPM, low taiko texture)
  - tidal_wind_low_chant
  - raven_wing_rustle_loop
accent_fx:
  - spear_tip_scrape (mid metallic, mono)
  - grey_line_surge (reverse hiss + sub thump)
  - crown_call (stacked raven screech pitched down)
  - mist_inhale (stereo breath for color siphon)
vocal_elements:
  - contralto_gaelic_phrase (no full lyrics, 3-word motifs)
  - throat_sung_omen (low drone)
transient_rules:
  spear_draw: align with spear_tip_scrape + grey_line_surge
  raven_crown: crown_call + gated reverb tail 500ms
  final_judgement: drum flam + whispered incantation hard-pan center
mix_notes:
  - 鼓與風聲占 -8 dBFS，上層羽毛聲維持 -14 dBFS，保留空氣感。
  - 女神台詞以古凱爾特語調處理，頻段削 2 kHz 防刺耳，附中文字幕層但僅在版面外呈現。
  - 無現代合成器與電吉他元素，僅用低弦、骨號角與手鼓。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Grey Lady Stone Verdict Look｜16:9｜24fps｜霧環群島灰霧審判質感)
「霧環群島黎明前；濃霧包圍的岩礁海、刻痕石圈、盤旋渡鴉；灰戰女神・凱薇娜在石圈中心以長矛刻灰線、抽離色彩並以渡鴉與戰局譜宣告第一場審判。」
鏡頭：Act1 24mm 高空俯衝→坡道 28mm 跟拍→石圈 32mm 仰視→槍尖 50mm 特寫；Act2 40–55mm 繞拍甲冑→35mm 胸甲特寫→85mm 側臉→65mm 眼部微推；Act3 30mm 環繞天空戰局→連續 3 個 45–70mm 快閃→28mm 第一人稱→60mm Title Card，下段切換皆用鼓點硬切搭配霧遮擋。
表演：凱薇娜整體冷靜、肩膀收緊，敲矛時無情俯視；渡鴉與灰線如她手勢延伸；最後插矛時呼吸沉穩像宣判。
臉型/髮型：冷白膚色、俐落五官、左眼下斜疤入髮線；長黑髮編成粗辮纏骨飾，額前短碎髮被風掀起。
構圖：石圈與渡鴉形成中央對稱；坡道與灰線引導視線向上；Title Card 留白 15% 供字幕；多層霧提供前中後景。
寫實細節：鐵灰皮甲刻凱爾特結、胸前三重螺旋可發光；披肩混黑羽與獸皮，內襯暗紅繡戰歌；槍頭刻符紋帶濕光；石圈潮濕、苔蘚貼地；灰線刮痕帶火星。
無字幕、無商標/Logo/水印。」

鏡頭語法：空間建立採 24–32mm，角色特寫與眼神 55–85mm，快速戰局回顧 45–70mm；
光圈 {Act1 T4.0 保景深、Act2 T3.2 輕微分離背景、Act3 T2.5 強調幻象}；快門角 {常規 180°、灰線爆發 144°、戰史快閃 200°}；
對焦 {遠景層次前→中→後，人物特寫單點眼，戰史快閃採呼吸拉焦在不同階段剪影間}。
光影：高空冷霧頂光+渡鴉掠影造成瞬時遮光；石圈設側逆光凸顯輪廓；當顏色被抽離時，僅胸紋與眼眸保暖色 rim。
色調/LUT：整體去飽和 8%，陰影帶冷藍霧感，高光偏暖僅在符紋與血霧；第二階段局部暗紅霧增加對比，第三階段轉灰白保血色點。
聲音：distant_basalt_drum 與 tidal_wind_low_chant 打底，raven_wing_rustle_loop 帶節奏；spear_tip_scrape、grey_line_surge 與 crown_call 同步畫面；contralto_gaelic_phrase 作判決語氣；最後一句古語降為低頻耳語。
轉場：霧牆遮擋→硬切；渡鴉掠過匹配剪接；灰線沿畫面掃出 wipe；終局以石圈衝擊波羽化 0.6s Freeze Title Card。
安全：僅象徵性血霧，無露骨血肉；畫面無真實語言旗幟與商標；渡鴉密度控制避免造成頻閃危險。
```

### Camera Continuity
- 此為凱薇娜首次登場，開場以遠景霧海連接到石圈坡道，確保未來劇情可直接沿用同一石圈佈局與灰線標記位置。
- 灰線、渡鴉與三重螺旋光紋作為後續 BOSS 戰三階段的視覺鉤子，於本 PV 中先展示三次不同亮度，並記錄其顏色值（灰線 #8A8F96、血霧 #5A1E23）。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.0s）
意圖：建立霧環群島與石圈審判場的預兆
基調：決斷前的靜壓
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：霧海環島、坡道兵器、渡鴉王冠、灰線初現

#### Beat 1（0.0–1.0s）
重點：霧環群島全景預兆
Blocking：高空鏡頭俯視推進至環島外圍，銀色戰局線在雲層閃爍。
Camera：
- 運鏡：24mm 空拍滑行
- 焦段/機位：24mm 俯視 60°、高度 200m
- 對焦：層次拉焦海面→霧→島
- 快門角：180；拍點：第一聲鼓點
光影：陰天散射光，雲縫透銀線
色調/LUT：冷灰綠海＋銀色線條
聲音：海風低頻＋遠鼓＋遙遠渡鴉啼叫
轉場：霧牆遮擋 → Angle 1

Angle 1（0.0–1.0s）
構圖：中央留白的霧圈，島鏈呈環狀
內容：銀線在雲層編織
補充：海面浪尖帶微光
安全：無可讀符號

#### Beat 2（1.0–2.0s）
重點：坡道上的兵器與血痕引向石圈
Blocking：鏡頭貼著泥地沿坡上移，踏過破盾與旌旗。
Camera：
- 運鏡：28mm 低角跟拍
- 焦段/機位：28mm 地面 0.2m、輕仰 10°
- 對焦：層次前景武器→坡頂石圈
- 快門角：180；拍點：腳踩金屬聲
光影：陰天漫射＋濕泥反光
色調/LUT：暗紅泥痕襯冷灰
聲音：金屬碎裂、泥水被踩、鼓聲靠近
轉場：旗幟掀起遮擋 → Angle 2

Angle 2（1.0–2.0s）
構圖：前景兵器模糊，中景血水引導線
內容：坡道直指遠處石圈剪影
補充：雨水滴落形成暗紅水流
安全：血僅為顏色，無屍體

#### Beat 3（2.0–3.0s）
重點：渡鴉旋成黑色王冠
Blocking：抬頭仰視，渡鴉自霧中衝出在石圈上空盤旋。
Camera：
- 運鏡：32mm 仰角抬升
- 焦段/機位：32mm 胸高→仰 40°
- 對焦：單點渡鴉軌跡
- 快門角：180；拍點：渡鴉尖叫
光影：背光剪影，羽毛邊緣 rim 光
色調/LUT：灰天＋黑羽，銀線偶爾閃
聲音：密集渡鴉叫聲+金屬敲擊
轉場：渡鴉掠過畫面 → Angle 3

Angle 3（2.0–3.0s）
構圖：三分線，石柱在下方，渡鴉形成偏心圓
內容：黑色王冠短暫遮住天空
補充：羽毛掉落閃至鏡頭
安全：無其他角色

#### Beat 4（3.0–4.0s）
重點：矛尖畫出第一道灰線
Blocking：特寫長矛槍尖貼地劃出灰白符線並分支。
Camera：
- 運鏡：50mm 俯視微推
- 焦段/機位：50mm 俯角 25°
- 對焦：單點槍尖→拉至延伸線
- 快門角：144；拍點：刮地聲
光影：側逆光強調金屬，灰線自發光
色調/LUT：石面冷灰，線條亮白
聲音：槍尖刮石+灰線嗡鳴
轉場：灰線向外延伸成 wipe → Angle 4

Angle 4（3.0–4.0s）
構圖：對角線，槍尖位於左下，灰線朝右上
內容：灰線分支成戰局圖
補充：石粉飛散，微火星
安全：無文字

### Act 2（4.0–8.5s）
意圖：聚焦凱薇娜造型、神力點亮與覺醒瞬間
基調：冷靜審查轉為壓迫
節奏域：穩定1.5–2.4
美術要點：甲冑細節、三重螺旋光、眼睛變換、色彩抽離

#### Beat 5（4.0–5.0s）
重點：盔甲與披風細節
Blocking：從膝到腰的中景，披風被風掀起露出暗紅內襯。
Camera：
- 運鏡：40mm 側向滑軌
- 焦段/機位：40mm 膝高
- 對焦：層次護腿→腰間飾物
- 快門角：180；拍點：披風甩動
光影：冷主光，披風內襯反射暗紅
色調/LUT：鐵灰甲胄＋血色邊
聲音：布料擦動、短號角
轉場：披風掠過 → Angle 5

Angle 5（4.0–5.0s）
構圖：人物偏左，披風佔右前景
內容：金屬環與羽毛飾物搖曳
補充：泥水濺在護腿上
安全：無暴力

#### Beat 6（5.0–6.0s）
重點：胸口三重螺旋點亮
Blocking：胸甲特寫，符紋自中心向石柱連線。
Camera：
- 運鏡：35mm 穩定器微推
- 焦段/機位：35mm 胸高
- 對焦：單點符紋
- 快門角：180；拍點：光脈衝
光影：符紋金光→石柱浮紋
色調/LUT：冷灰底＋暖金光
聲音：低頻共鳴嗡鳴
轉場：光線沿甲胄蔓延 → Angle 6

Angle 6（5.0–6.0s）
構圖：中央胸甲，占畫面 70%
內容：三重螺旋逐層亮起
補充：石圈立石同步亮出紋路
安全：無文字

#### Beat 7（6.0–7.0s）
重點：側臉與閉眼沉思
Blocking：凱薇娜側臉半藏在羽毛陰影，她仍閉眼聆聽戰鼓。
Camera：
- 運鏡：85mm 靠近側臉
- 焦段/機位：85mm 胸高略仰
- 對焦：單點睫毛
- 快門角：180；拍點：鼓聲壓低
光影：羽毛投下斜陰，輪廓 rim 光
色調/LUT：冷白肌膚、黑羽覆面
聲音：鼓聲壓低，只剩風與呼吸
轉場：吸氣聲作音頻匹配 → Angle 7

Angle 7（6.0–7.0s）
構圖：三分線，臉位於右側，羽毛佔左前景
內容：左眼下疤可見，長辮垂肩
補充：霧絲沿臉頰滑過
安全：無血腥

#### Beat 8（7.0–8.5s）
重點：眼睛張開與色彩被奪走
Blocking：她睜眼，瞳孔變三重圓環，場景顏色抽離。
Camera：
- 運鏡：65mm 微推
- 焦段/機位：65mm 眼高
- 對焦：單點虹膜
- 快門角：200；拍點：渡鴉啼叫
光影：眼內金綠閃光，背景轉灰
色調/LUT：瞬間轉黑白僅眼保彩
聲音：鋭利渡鴉叫＋耳鳴
轉場：眼中光線放射 → Angle 8

Angle 8（7.0–8.5s）
構圖：極近眼部，虹膜佔 70%
內容：三重圓環紋路，周圍灰霧靜止
補充：瞳孔內映出戰士剪影
安全：無可讀資訊

### Act 3（8.5–15.0s）
意圖：展示戰局譜、三階段幻象與審判宣告
基調：審判臨頭的壓迫
節奏域：加速2.4–3.0
美術要點：銀色戰局網、三階段剪影、第一人稱灰線鎖定、Title Card

#### Beat 9（8.5–10.0s）
重點：戰局譜在天空展開
Blocking：拉遠環繞她一圈，天空銀線重排，軍隊幻影碰撞。
Camera：
- 運鏡：30mm 半圓繞拍
- 焦段/機位：30mm 胸高
- 對焦：層次人物→天空網
- 快門角：180；拍點：合唱進場
光影：銀線發光照亮霧氣
色調/LUT：灰白場＋銀光
聲音：女聲合唱+戰鼓加速
轉場：銀線掃過鏡頭 → Angle 9

Angle 9（8.5–10.0s）
構圖：人物置中，天空銀網覆頂
內容：長矛指向其中一路徑
補充：渡鴉在後方成黑環
安全：無血腥

#### Beat 10（10.0–11.0s）
重點：三階段剪影快閃預告
Blocking：三段 0.3s 快剪展示戰略、血潮、戰史幻象。
Camera：
- 運鏡：45–70mm 快速鞭移
- 焦段/機位：45mm 地面突刺→60mm 霧中衝刺→70mm 灰白幻影排陣
- 對焦：呼吸拉焦在每段主體
- 快門角：200；拍點：鼓點三連
光影：每段不同：灰線爆、血霧紅、灰白幻影
色調/LUT：依階段切換
聲音：金屬爆裂、血霧低吼、遠吼疊加
轉場：每段以鼓點硬切→Angle 10

Angle 10（10.0–11.0s）
構圖：序列剪影以匹配剪接疊化
內容：戰略（灰線與石柱）、屠戮（血霧衝刺）、記憶（幻影列陣）
補充：每次閃現帶對應符號
安全：僅剪影

#### Beat 11（11.0–13.0s）
重點：第一人稱被灰線鎖定與審判台詞
Blocking：玩家視角踏入石圈，灰線纏腳直至視野邊界，凱薇娜對著鏡頭說古語。
Camera：
- 運鏡：28mm 主觀鏡頭向前一步
- 焦段/機位：28mm 眼高
- 對焦：單點長矛矛尖，再跳至女神眼睛
- 快門角：180；拍點：台詞
光影：灰線自發光，背景低飽和
色調/LUT：灰度場中僅眼與矛尖帶色
聲音：她低語「踏入此圈者——必付出戰爭應有的代價。」+ grey_line_surge
轉場：灰線在畫面邊界收緊 → Angle 11

Angle 11（11.0–13.0s）
構圖：第一人稱，矛尖對準鏡頭中央
內容：灰線纏繞成封鎖陣
補充：字幕僅作內部記錄，不上畫
安全：視角內無其他角色臉

#### Beat 12（13.0–15.0s）
重點：Title Card 與長矛落地衝擊波
Blocking：慢速拉遠，凱薇娜將矛垂直插地，渡鴉成巨大黑環，畫面 freeze 成 Title Card。
Camera：
- 運鏡：60mm 拉遠＋上升
- 焦段/機位：60mm 胸高起→仰 15°
- 對焦：單點人物→石圈衝擊波
- 快門角：180；拍點：最後重鼓
光影：衝擊波帶灰白光圈
色調/LUT：灰白場加暗紅 Title accent
聲音：鼓聲終止＋骨號角長音→海風淡出
轉場：衝擊波邊緣 freeze 成卡 → Angle 12

Angle 12（13.0–15.0s）
構圖：人物置中，背後渡鴉黑環與戰局譜
內容：Title Card 「灰戰女神・凱薇娜 / The Grey Lady of War」
補充：灰白粒子定格後淡出
安全：字幕為自有標語


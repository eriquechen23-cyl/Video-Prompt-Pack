# 獨立世界觀 EP1 — 黑龍守門人 PV Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-20_guardian-or-calamity_v01/script.md

## 一句話題材
正午的黑龍從雲層墜落、解構為東亞肌肉青年，龍鱗披風尚在顫動，他抬眼盯向鏡頭時，沒人確定他是守門人還是災禍本身。

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

### 交付參數預設（`_core/delivery_presets.md`）
```
畫幅：{16:9｜9:16｜1:1}
解析度：{1920×1080｜1080×1920｜2048×2048}
幀率：{24/30/48/60}（如需輕慢動：拍 48–60，輸出 24）
防抖：{開/關}；運動模糊：開；顆粒：微膠片
色彩：Rec.709（交付版）／LOG（調色版）
聲音：立體聲 48kHz；-14 LUFS（YouTube），-1 dBTP
種子：{固定/隨機（記錄）}；連戲：開；時序一致：開
```

### Style Pack：Zenith Noon Real Look（`_stylepacks/zenith_noon_realism/look.yml`）
```yaml
name: Zenith Noon Real Look
lut: Zenith-Overexpose-HDR
saturation_adjust: -0.03  # 去飽和 3%
contrast: high_linear
highlight_rolloff: hard_clip_with_bloom
shadow_floor: lifted_sand  # 影子被抹平
white_point: 1.05  # 刻意過曝
texture: tempered_glass_scale
specular_detail: molten_gold_edges
heat_warp_pass: micro_ripple_sheet
notes:
  - 強化正午過曝質感，暗部保留極少量沙紋，不產生藍色陰影。
  - 鱗片表面需呈現多層玻璃反射並含熾橙內發光。
  - 景深受熱浪影響需保持邊緣抖動，勿套柔焦濾鏡。
```

### Style Pack：Zenith Noon Real VFX（`_stylepacks/zenith_noon_realism/vfx.yml`）
```yaml
name: Zenith Noon Real VFX
heat_haze_layers:
  - id: zenith_ground_glimmer
    distortion: 0.42
    speed: 1.6
  - id: apex_sky_veil
    distortion: 0.28
    speed: 0.9
solar_column_profile:
  core_color: fff8cf
  rim_color: ffad45
  falloff: exponential_hard
  particles: silica_dust_updraft
wing_trail_shader:
  refractive_index: 1.23
  thickness_cm: 65
  ember_specks: 0.18
sundial_cage_geometry:
  slices: 24
  rotation_speed_rps: 0.85
  cut_beam_width_cm: 8
reflection_cache:
  afterglare_delay_s: 2.2
  intensity_scale: 1.35
notes:
  - 光柱與光籠採體積陰影貼圖而非 2D billboard，以利真實折射。
  - 翅膀熱浪需在遠景造成背景折射，並帶動砂塵短暫懸浮。
  - 尾巴日晷展開時，光條必須對應地面刻度動畫並可作為腳本判定區域。
```

### Style Pack：Zenith Noon Real Audio（`_stylepacks/zenith_noon_realism/audio.yml`）
```yaml
name: Zenith Noon Real Audio
core_layers:
  - baked_desert_wind
  - heat_buzz_harmonics
  - distant_metal_creak
  - granular_sandfall
impact_events:
  - cue: solar_pressure_drop
    sfx: subsonic_column_crush
    level_db: -4
    width: 140
  - cue: gnomon_lock
    sfx: glass_ring_sweep
    level_db: -7
    width: 120
  - cue: thermal_wing_cut
    sfx: vacuum_slice_thump
    level_db: -6
    width: 150
  - cue: helio_dive
    sfx: hypersonic_descend_roar
    level_db: -2
    width: 160
voiceover:
  language: zh-TW
  tone: solemn_genderless
  treatment: band_limit_mid_high
mix_notes:
  - 風聲需維持 -18 dBFS 底噪並含金屬共振尾音，對應封印結構。
  - 光柱與日晷事件必須 sidechain 風聲 3 dB，凸顯衝擊。
  - 結尾旁白僅 0.7s，定位中央，殘響 0.3s 後歸於靜音。
```

### Style Pack：Real Cinema Lens Set（`_stylepacks/real_cinema/lensset.yml`）
```yaml
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

### Style Pack：Real Cinema Safety Checklist（`_stylepacks/real_cinema/safety.yml`）
```yaml
name: Real Cinema Safety Checklist
rules:
  - 避免可讀字與商標曝光
  - 群眾不近特寫，維持隱私
  - 保持自然膚質與光比
  - 記錄 LUT 與種子以利 QA
```

---

## Master Prompt 實際填寫
```
Master(15s｜Zenith Noon Realism × Real Cinema｜16:9｜24fps｜烈陽墜龍寫實質感)
「正午郊區廢墟；烈日、砂塵衝擊浪、崩裂街口裂紋；黑龍從雲層墜落解構成東亞肌肉青年披著龍鱗披風，抬眼質疑是守門還是災禍。」
鏡頭：Act1 24–35mm 仰角滑軌跟墜→Beat3 35mm 地平線低角→Beat4 75mm 頭部近特寫→Act2 32–50mm 俯視與背部推→Beat8 75mm 側臉近→Act3 45–65mm 正面中景→Beat12 75mm 半身推近定格。
表演：墜地前龍形帶侵略氣勢；變身後青年呼吸沉穩、眉心緊繃，最後直視鏡頭時情緒收束於審視與隱約威脅之間。
臉型/髮型：東亞短髮、臥蠶明顯、下頜線清楚，瞳孔由縱向獸瞳收斂成正常黑瞳，一眼保留淡藍反光。
構圖：陽光與塵土形成前中後層，裂紋圓陣佔後景 40%；留白 10–15% 讓光圈與鱗片飛散有餘裕。
寫實細節：龍鱗呈多層玻璃反射帶熾橙內光，披風附著肩鎖骨形成護甲；皮膚帶汗光與塵土；地面碎瓦與街牌晃動。
無字幕、無商標/Logo/水印。」

鏡頭語法：空間建立 24–35mm，表情與肌理 50–75mm，衝擊瞬間可用 85mm 壓縮；
光圈 {Act1 T4→Act2 T2.8→Act3 T2.4 收斂景深}；快門角 {墜落 200° 拖影、常規 180°、黑環吞光 144° 強化脈動}；
對焦 {墜落軌跡單點→衝擊後層次前→中→後→Beat8 單點眼→Beat12 呼吸拉焦胸甲}。
光影：烈日頂光＋塵霧散射，黑環吞光段僅局部降光形成冷白邊緣；鱗片反射帶熾橙內光與熱浪扭曲。
色調/LUT：去飽和 3%，高對比，白點推高 1.05，陰影抬起保持沙色；膚色維持自然微暖、鱗片冷白邊緣。
聲音：baked_desert_wind＋heat_buzz_harmonics 為底，墜落用 helio_dive；衝擊以 solar_pressure_drop 觸發低頻，黑環時 vacuum_slice_thump；結尾旁白 0.7s 帶 band-limit 處理。
轉場：墜落衝擊砂塵遮擋切→黑環吞光羽化 0.5s→鱗片旋轉匹配切→披風掀起鞭移→最後視線定格 0.5s 輕羽化停。
安全：無可讀街牌與真實品牌，群眾不入特寫，保持光比與 LUT 記錄。
```

### Camera Continuity
- 以烈日過曝質感維持全程一致，黑環吞光段僅局部降低亮度但不轉夜色，確保世界觀鎖定「白天」設定。
- 鱗片披風的反射與熱浪在各鏡需保持一致頻率（約 1.6 Hz 微抖），避免連戲跳動。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立正午墜龍異象與衝擊
基調：決斷前的緊張
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：烈日、雲層撕裂、砂塵衝擊波

#### Beat 1（0.0–1.25s）
重點：正午天空被巨大陰影壓暗
Blocking：鏡頭從地面仰望，陰影迅速放大吞掉光線。
Camera：
- 運鏡：24mm 仰角滑軌上推
- 焦段/機位：24mm 地面 0.2m，仰視 25°
- 對焦：單點雲層裂縫→影子
- 快門角：200；拍點：陰影覆蓋瞬間
光影：烈日被陰影截斷，邊緣留冷白光
色調/LUT：白點過曝，陰影抬起呈沙色
聲音：baked_desert_wind 底＋遠處金屬共振
轉場：陰影壓暗遮擋 → Angle 1

Angle 1（0.0–1.25s）
構圖：中央垂直引導線，留白 15%
內容：龍影從雲層裂開落下
補充：熱浪微抖、雲絲被撕裂
安全：無可讀元素

#### Beat 2（1.25–2.5s）
重點：黑龍穿越雲層鱗片反光
Blocking：側面跟拍俯衝龍翼大幅拍擊。
Camera：
- 運鏡：35mm 側向穩定器跟拍
- 焦段/機位：35mm 胸高並行
- 對焦：單點龍頭→翼端
- 快門角：180；拍點：翼拍擊
光影：烈日勾冷白邊，鱗片內熾橙
色調/LUT：高對比，陰影沙色
聲音：helio_dive 下潛咆哮＋wing trail 風切
轉場：龍翼遮擋切 → Angle 2

Angle 2（1.25–2.5s）
構圖：三分線，龍頭佔左，翼展拉滿
內容：墨黑鱗片、白霧衝擊尾
補充：熱浪扭曲背景
安全：無可讀文字

#### Beat 3（2.5–3.75s）
重點：墜地爆炸土浪
Blocking：龍撞地，衝擊波掃過前景路牌與草。
Camera：
- 運鏡：28mm 地平線低角固定
- 焦段/機位：28mm 地面 0.4m，水平
- 對焦：層次前→衝擊中心
- 快門角：200；拍點：衝擊瞬間
光影：塵土遮陽，邊緣仍留白光
色調/LUT：沙色霧化、白點保持
聲音：solar_pressure_drop 低頻＋碎石散落
轉場：塵土遮擋 → Angle 3

Angle 3（2.5–3.75s）
構圖：前景路牌晃動，中景土浪，背景爆點
內容：衝擊波掠過鏡頭
補充：碎石飛濺、塵霧顆粒
安全：路牌無可讀字

#### Beat 4（3.75–5.0s）
重點：黑環吐息吞光
Blocking：龍頭抬起吐出向外擴散黑色光環。
Camera：
- 運鏡：75mm 半身近景微推
- 焦段/機位：75mm 膝高仰視 15°
- 對焦：單點龍眼→黑環前緣
- 快門角：144；拍點：黑環擴散
光影：中央暗化、邊緣烈日對比
色調/LUT：白點仍高，中心冷暗
聲音：vacuum_slice_thump 吞光＋風壓
轉場：黑環羽化 0.5s → Angle 4

Angle 4（3.75–5.0s）
構圖：中央對稱，龍口與光環為圓心
內容：黑環吞光、鱗片反光
補充：熱浪扭曲邊緣
安全：僅抽象能量

### Act 2（5.0–10.0s）
意圖：龍形崩解與青年現身
基調：悸動與神秘
節奏域：穩定1.5–2.4
美術要點：漂浮鱗片、肌肉線條、龍鱗披風

#### Beat 5（5.0–6.25s）
重點：龍形裂開鱗片旋浮
Blocking：俯視鏡頭看龍形玻璃碎裂，鱗片繞圈，中心亮出人形。
Camera：
- 運鏡：32mm 俯視懸停
- 焦段/機位：32mm 空中 6m 俯拍
- 對焦：層次鱗片→人形光
- 快門角：180；拍點：鱗片解構
光影：黑環內暗、鱗片邊緣冷白
色調/LUT：去飽和，白點保持
聲音：glass_ring_sweep＋鱗片旋轉氣音
轉場：鱗片旋轉匹配切 → Angle 5

Angle 5（5.0–6.25s）
構圖：中央人形，鱗片環繞成圓
內容：龍形碎裂，鱗片漂浮
補充：熾橙內光透出
安全：無可讀元素

#### Beat 6（6.25–7.5s）
重點：雙腳落地、鱗片滑落
Blocking：腳掌踏入碎石，幾片鱗片落旁叮噹轉動。
Camera：
- 運鏡：50mm 低角跟腳落
- 焦段/機位：50mm 地面 0.15m 仰 10°
- 對焦：單點腳踝→滑落鱗片
- 快門角：180；拍點：腳落地
光影：烈日斜側光勾腳踝汗光
色調/LUT：膚色自然、鱗片冷白邊
聲音：碎石摩擦＋鱗片金屬響
轉場：鞋邊鱗片擦過遮擋切 → Angle 6

Angle 6（6.25–7.5s）
構圖：三分線，腳掌佔右下
內容：腳落地、鱗片滑落旋轉
補充：塵土微震，熱浪扭曲
安全：無可讀符號

#### Beat 7（7.5–8.75s）
重點：龍脊化披風上肩
Blocking：背對鏡頭站立，鱗片沿脊柱流動攀上肩形成披風與護肩。
Camera：
- 運鏡：45mm 背部中近景微推
- 焦段/機位：45mm 胸高後方 2m
- 對焦：層次下背→肩甲鱗片
- 快門角：180；拍點：鱗片定型
光影：烈日側逆光畫出冷白邊線
色調/LUT：高對比，熱浪扭曲
聲音：鱗片貼合低鳴＋風聲
轉場：披風掀起鞭移 → Angle 7

Angle 7（7.5–8.75s）
構圖：中央背線，鱗片披風展弧
內容：寬肩、脊背線、鱗片攀附
補充：光點反射、塵土被風卷
安全：無可讀字樣

#### Beat 8（8.75–10.0s）
重點：側臉特寫，獸瞳收斂
Blocking：青年半側回頭，瞳孔從縱向收回圓形，人眼露出臥蠶。
Camera：
- 運鏡：75mm 側臉近景穩定器微推
- 焦段/機位：75mm 胸高，側 35°
- 對焦：單點眼睛
- 快門角：180；拍點：瞳孔收斂
光影：烈日側光，眼下臥蠶明顯
色調/LUT：膚色微暖、鱗片冷反光
聲音：heat_buzz_harmonics 收束＋短促呼吸
轉場：眼內反光匹配切 → Angle 8

Angle 8（8.75–10.0s）
構圖：三分線臉佔右側
內容：短髮、臥蠶、眼中龍光消散
補充：汗珠微亮，背景塵霧虛化
安全：成年特寫

### Act 3（10.0–15.0s）
意圖：揭示圓陣與選擇，收束於疑問
基調：緊張懸而未決
節奏域：穩定1.5–2.4
美術要點：裂紋圓陣、鱗片披風、熱浪與光裂縫

#### Beat 9（10.0–11.25s）
重點：守門圖案與正反光線
Blocking：正面中景，背後地面裂紋形成半光半黑的圓形封印／入口。
Camera：
- 運鏡：45mm 正面穩定器微推
- 焦段/機位：45mm 腰高
- 對焦：單點胸口→後方圓陣
- 快門角：180；拍點：圓陣亮起
光影：一半烈日白光，一半黑暗裂縫
色調/LUT：對比強，白點保持
聲音：gnomon_lock 光環 sweep＋遠城低鳴
轉場：圓陣裂縫遮擋 → Angle 9

Angle 9（10.0–11.25s）
構圖：中央人物，後景圓陣佔 40%
內容：一半白光、一半深淵裂紋
補充：塵粒漂浮，熱浪扭曲線條
安全：無可讀符號

#### Beat 10（11.25–12.5s）
重點：披風掀起露出胸鎧
Blocking：他踏前一步，龍鱗披風掀起，胸肌與鎖骨線條亮出，鱗片微震。
Camera：
- 運鏡：50mm 微仰角中近景
- 焦段/機位：50mm 胸高前 1.5m 仰 10°
- 對焦：單點鎖骨→披風鱗片
- 快門角：180；拍點：披風掀起
光影：烈日頂光，鱗片邊緣冷白
色調/LUT：膚色自然，鱗片熾橙內光
聲音：披風摩擦＋細微震動嗡鳴
轉場：披風遮擋鞭移 → Angle 10

Angle 10（11.25–12.5s）
構圖：三分線人物偏右，披風占左
內容：披風掀起、胸鎧與鎖骨
補充：鱗片顫動、塵土被帶起
安全：無可讀元素

#### Beat 11（12.5–13.75s）
重點：掌心光決定命運
Blocking：運鏡繞側，掌心亮起難辨救贖或毀滅色光，遠處城市半毀半存。
Camera：
- 運鏡：60mm 側向繞拍 90°
- 焦段/機位：60mm 胸高側後 2m
- 對焦：單點掌心→遠景城市
- 快門角：180；拍點：掌心亮起
光影：掌心混色光，背景一側明、一側暗
色調/LUT：對比高，熱浪扭曲遠景
聲音：subsonic_column_crush 低頻墊＋遠處警報殘響
轉場：掌心光遮擋羽化 → Angle 11

Angle 11（12.5–13.75s）
構圖：人物位於右前，背景城市分明暗兩側
內容：掌心光芒、披風流動
補充：塵粒被光吸引，熱浪晃動
安全：無可讀招牌

#### Beat 12（13.75–15.0s）
重點：上半身終極特寫與懸念
Blocking：鏡頭微推半身正面，胸腔起伏，龍鱗披風貼合；一眼映藍天、一眼映黑裂縫，嘴角難辨笑或冷笑，最後 0.5s 微停。
Camera：
- 運鏡：75mm 半身正面推近
- 焦段/機位：75mm 胸口到頭頂，眼高
- 對焦：呼吸拉焦胸甲↔瞳孔
- 快門角：180；拍點：視線直盯
光影：烈日打亮肌理，鱗片邊緣冷白與熾橙內光
色調/LUT：白點高、膚色微暖，鱗片冷暖混合
聲音：聲音全部收束，僅保留呼吸與 0.7s 旁白：「守門人，還是災禍？」殘響 0.3s 歸靜
轉場：定格 0.5s 輕羽化收束

Angle 12（13.75–15.0s）
構圖：半身中央，留白 10%
內容：直視鏡頭、胸腔起伏、雙眼異色反光
補充：汗珠與塵粒閃光
安全：無可讀文字，成年特寫


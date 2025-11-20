# Dragon Scale Stormfall — Master Prompt（15s｜10 幕）

來源劇本：用戶提供「黑龍化身東亞肌肉男披龍鱗」分鏡描述

## 一句話題材
黑龍沿雷光俯衝墜地後崩解成鱗片與光環，凝聚為披著龍鱗披風的東亞壯碩男子，以低沉龍吼質問召喚者要毀滅還是拯救。

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

### Style Pack：Dragon Scale Storm Look（新樣板）
```yaml
style: Dragon Scale Storm Look
applicability: 黑龍化身、雷電降臨、披風鎧甲式變身
constraints: 不與喜劇或糖果色調風格混用；維持寫實肌理與陰影對比
palette:
  base: [obsidian_black, charcoal_scale, midnight_blue]
  accents: [storm_white, molten_gold]
character:
  body: east_asian_mesomorphic; chest_shoulders_defined; skin_tone: warm_olive_with_scars
  eyes: vertical_gold_iris with faint glow synced to thunder hits
  hair: black_wind_swept, damp at tips
armor:
  scales: asymmetrical_black_gold overlap across clavicle, deltoid, upper back forming cloak tail
  cloak: scale_cape segmented, responds to wind and breath like living membrane
  texture: dry matte scales with metallic rims; underside shows sinew and smoked leather fibers
lighting:
  key_fill: cold_storm_rim 3200–3600K; fill from lightning reflections; backlight accent rim in gold when power peaks
  volumetrics: drifting ash and mist swallowed by expanding black ring
notes:
  - 肌肉線條需保留汗光與微血管，避免塑膠感。
  - 披風狀龍鱗需有微幅波紋與粒子溢散，像龍影殘留。
  - 黑環吞光段落維持輪廓邊光，確保變身動線可讀。
  - 代表元素：縱向金瞳、黑金龍角光環。
```

### Style Pack：Lightning Chain Look（`_stylepacks/lightning_chain/look.yml`）
```yaml
name: Lightning Chain Look
lut: Ionized-Arc
saturation_adjust: 0.12
contrast: high
highlights: electric_blue
shadows: graphite_cool
texture: rain_slick_leather
chromatic_aberration: tangential_blue_shift
lens_distortion: controlled_pincushion
notes:
  - 強調藍白電弧的高亮輪廓，保留肌膚 52 IRE 微暖
  - 地面濕潤反光需加入局部高光刷動
  - 霧氣與電暈採用分層曝光避免過曝
```

### Style Pack：Lightning Chain VFX（`_stylepacks/lightning_chain/vfx.yml`）
```yaml
name: Lightning Chain VFX
niagara_presets:
  - 圓弧雷鏈生成
  - 電暈過曝脈衝
  - 地面枝狀放電
unity_vfx_graph:
  - ArcLoop.vfx
  - ChainLeap.vfx
  - OzoneBloom.vfx
houdini_flipbooks:
  - lightning_flash_cluster
  - ozone_mist_swirl
  - finger_arc_ignition
shader_settings:
  bolt_core_thickness: 0.45
  afterglow_decay: 0.65
  spark_density: 1.8
  refraction_ripple_intensity: 0.3
sdf_settings:
  stickiness: 0.25
  jump_arc_delay: 0.15
  impact_scorch_radius: 1.2
bloom_control:
  idle: 0.18
  trigger_peak: 0.82
  cooldown: 0.3
audio_sync:
  zap_triggers: align_arc_leaps
  bass_hit: accent_phase_interference
notes:
  - 雷鏈跨目標時需保留殘影拖曳 3 frame
  - 地面放電使用形狀配對剪與光閃過門銜接
  - HUD 元素需與鏈路節點一一對應，避免漂移
```

### Style Pack：Lightning Chain Audio（`_stylepacks/lightning_chain/audio.yml`）
```yaml
name: Lightning Chain Audio
core_layers:
  - ozone_drone_bed
  - crackle_triplets
  - sub_thump_sync
peak_events:
  - timestamp: ignition
    sfx: finger_arc_snap
    level_db: -6
    stereo_width: 100
  - timestamp: convergence
    sfx: thunder_iris
    level_db: -3
    stereo_width: 140
rhythmic_grid:
  bpm: 120
  subdivision: eighths
  swing: 0.04
sidechain:
  trigger_bus: impact_bus
  target: ozone_drone_bed
  reduction_db: 2
dynamics:
  crest_factor: 10
  transient_protection_db: -1
notes:
  - 120 BPM 節奏需呼應每 0.5s 電弧節點亮起
  - 扣指瞬間加上金屬尖銳高頻 6kHz
  - 殘光收束後留 1.5s 氣流與餘電尾音
```

---

## Master Prompt 實際填寫
```
Master(15s｜Dragon Scale Storm Realism｜16:9｜24fps｜雷雨中龍鱗變身質感)
「夜間廢墟荒原的雷暴；翻湧烏雲、雷光縫隙、焦黑碎石；黑龍沿雷柱俯衝墜地後崩解成鱗片光環，凝聚為披龍鱗的東亞壯碩男子低聲質問召喚者。
鏡頭：開場 20mm 仰視遠景→240mm 長焦追隨→18mm 雲底仰角→28mm 地面略低→32mm 俯視黑環→35mm 側後圍繞→45mm 半身低角→50mm 側面環繞→65mm 近景略仰→85mm 唇部特寫，手持≤2% 只用於爆風震動。
表演：男子由龍吼轉為沉穩呼吸，眉眼冷凝，最後帶出輕微嘲諷笑意與壓低聲線台詞。
臉型/髮型：東亞輪廓、濃眉、削頰線條，濕黑髮往後掃；縱向金瞳；鬢角帶焦黑粉塵。
構圖：開場留 20% 天空裂縫，主體多置中偏右，披風與雷光形成斜向導線，留白給雷鏈與黑環；動態：雲層翻湧、碎石震動、鱗片粒子逆落、披風波紋。
寫實細節：龍鱗呈黑金邊緣且帶粗糙肌理，肩披風如鎧甲片層延伸至腰，胸腹肌保留汗光與血管；黑環吞光時僅保留輪廓 rim；雷電折射在鱗片上形成冷白筆刷。
無字幕、無商標/Logo/水印。」

鏡頭語法：18–32mm 建立空間與衝擊波｜35–50mm 捕捉變身與肌肉細節｜65–85mm 對視與台詞；
光圈 {T2.4–T3.5；黑環段落收至 T4.0 以拉深景深層次}；快門角 {暴風段 180°、崩解段 150–172°、台詞 180°}；
對焦 {層次拉焦 雲→龍→人形；變身段落呼吸拉焦鱗片→眼瞳}。
光影：夜間 3200–3600K 冷色主控，雷光瞬間打出冷白 rim，變身完成時額外加暖金反射；對比 {中高}；眼神光 {由鱗片反射補亮}。
色調/LUT：陰影微藍、鱗片高光冷白＋金邊，膚色優先保暖，去飽和 6%。
聲音：ozone_drone_bed 與風沙為環境，crackle_triplets＋圓弧雷鏈對應墜落與崩解，thunder_iris 配合黑環擴散，finger_arc_snap 與皮膚鱗化的脆聲同步；低沉龍吼疊低頻混響，台詞保持近講感。
轉場：雷光匹配切→鱗片粒子遮擋→黑場羽化→披風拂面遮擋→唇部特寫硬切黑。
安全：無可讀字樣與標誌，地面焦黑裂紋不呈現文字。
```

## Scene Blocks（10 Angles｜總長 15s）

### Act 1（0.0–4.5s）
意圖：建立雷暴氛圍與黑龍降臨壓迫
基調：緊張、敬畏
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：撕裂夜空、雷光縫隙、巨大龍翼剪影

#### Beat 1（0.0–1.5s）
重點：夜空被雷光撕開
Blocking：遠景仰拍，雲層翻湧出縫隙，黑影現形。
Camera：
- 運鏡：滑軌微推仰視
- 焦段/機位：20mm 低角仰望
- 對焦：層次拉焦 雲→縫隙
- 快門角：180；拍點：雷光閃擊
光影：冷藍雲層，雷光炸亮邊緣
色調/LUT：陰影微藍、雷光冷白
聲音：ozone_drone_bed＋遠雷隆隆
轉場：雷光匹配 → Beat 2

Angle 1
構圖：天空占八成，裂縫居中偏左
內容：環境建立、黑影輪廓
補充：風卷雲絲向外拉
安全：無文字

#### Beat 2（1.5–3.0s）
重點：黑龍俯衝佔滿畫面
Blocking：長焦跟拍黑龍沿光柱下墜，翼展遮天。
Camera：
- 運鏡：長焦追隨
- 焦段/機位：240mm 高空同向
- 對焦：呼吸拉焦 龍頭→翼尖
- 快門角：180；拍點：翼拍
光影：雷光勾出鱗片冷白邊
色調/LUT：黑鱗與冷光對比
聲音：crackle_triplets 對應翼拍，sub_thump_sync 每次雷擊
轉場：翼尖鞭移 → Beat 3

Angle 2
構圖：龍翼斜切畫面，尾巴拖弧
內容：俯衝動態
補充：尾痕拖出白色氣流
安全：無文字

#### Beat 3（3.0–4.5s）
重點：穿破雲底貼臉掠過
Blocking：雲下仰角等待，龍腹掠過鏡頭上方。
Camera：
- 運鏡：手持≤2% 仰視定點
- 焦段/機位：18mm 雲下仰角
- 對焦：單點龍腹→殘影
- 快門角：180；拍點：低吼
光影：雷光從雲縫上打成 rim
色調/LUT：鱗片冷白高光
聲音：低沉龍吼疊 thunder_iris 尖峰
轉場：落地衝擊遮擋 → Act 2

Angle 3
構圖：龍腹掠過上方，觀眾視角居底
內容：近距離壓迫
補充：霧氣被帶出逆風
安全：無文字

### Act 2（4.5–9.0s）
意圖：落地衝擊與吞光轉化，堆疊超自然
基調：震撼→神秘
節奏域：穩定1.5–2.4
美術要點：黑環吞光、粒子崩解、鱗片逆落

#### Beat 4（4.5–6.0s）
重點：落地衝擊波擴散
Blocking：黑龍重擊地面，碎石與灰塵環狀掀起。
Camera：
- 運鏡：地面略低穩定器
- 焦段/機位：28mm 膝高仰視
- 對焦：層次 拉焦 龍頭→衝擊波前緣
- 快門角：180；拍點：落地瞬間
光影：雷光短曝，地面火星亮點
色調/LUT：背景低飽和，衝擊波冷白
聲音：sub_thump_sync＋碎石落地；finger_arc_snap 作為落地裂聲
轉場：黑環向鏡頭遮擋 → Beat 5

Angle 4
構圖：龍身居中，衝擊波占前景圓弧
內容：衝擊波與碎石
補充：塵土向外翻滾
安全：無文字

#### Beat 5（6.0–7.5s）
重點：黑環吞光成純黑舞台
Blocking：衝擊波化成黑色光環擴散，場景光被吸收。
Camera：
- 運鏡：俯視緩下降
- 焦段/機位：32mm 俯視 60°
- 對焦：單點黑環邊緣光
- 快門角：172；拍點：黑環達極限
光影：僅留暗金輪廓與冷白輪廓
色調/LUT：去飽和 8%，輪廓高亮
聲音：ozone_drone_bed 降低，thunder_iris 拉長尾巴
轉場：粒子自下而上逆落 → Beat 6

Angle 5
構圖：黑環置中，龍形剪影在中央
內容：吞光瞬間
補充：邊光勾勒龍翼
安全：無文字

#### Beat 6（7.5–9.0s）
重點：龍身崩解收束成人形
Blocking：鱗片脫離龍體逆向落下貼在聚合的人形上，龍角碎為旋轉光環。
Camera：
- 運鏡：側後 3/4 繞行
- 焦段/機位：35mm 胸高
- 對焦：呼吸拉焦 鱗片雨→肩胸
- 快門角：150；拍點：光環形成
光影：冷白邊光＋鱗片微金反射
色調/LUT：黑金對比鮮明
聲音：crackle_triplets 降低密度，scale 滴落聲混 metallic sprinkle
轉場：鱗片貼合遮擋 → Act 3

Angle 6
構圖：右後側強調肩背，鱗片流線包覆
內容：崩解變身
補充：光環繞在人形上方
安全：無文字

### Act 3（9.0–15.0s）
意圖：展示龍鱗披風肌肉男子與對視台詞
基調：決斷、自信
節奏域：加速2.4–3.0 → 穩定1.5–2.4
美術要點：黑金鱗片披風、濕黑髮、縱向金瞳、焦黑地面

#### Beat 7（9.0–10.5s）
重點：肌肉線條成形
Blocking：黑霧散去，男子上半身現形，鱗片貼在鎖骨與胸腹。
Camera：
- 運鏡：半身低角微推
- 焦段/機位：45mm 胸高略仰
- 對焦：單點胸肌→頸部
- 快門角：172；拍點：鱗片最後貼合
光影：冷光主，鱗片邊緣暖金反射
色調/LUT：膚色暖、鱗片冷白邊
聲音：心跳低頻＋鱗片鎖扣聲
轉場：披風波紋 wipe → Beat 8

Angle 7
構圖：男子置中偏右，上半身佔畫面
內容：肌肉與鱗片細節
補充：皮膚汗光與細微蒸汽
安全：無文字，成年註記

#### Beat 8（10.5–12.0s）
重點：龍鱗披風展開
Blocking：男子側轉，披風被風撐開露出背肌，鱗片波紋閃光。
Camera：
- 運鏡：側面 45° 環繞推近
- 焦段/機位：50mm 腰高
- 對焦：呼吸拉焦 披風→背肌→側臉
- 快門角：172；拍點：披風最大張角
光影：背光冷白 rim，披風邊緣溢出金粒
色調/LUT：背景焦黑、鱗片冷白＋金邊
聲音：披風摩擦聲＋輕微電弧閃
轉場：披風掃過遮擋 → Beat 9

Angle 8
構圖：側身三分線，披風佔畫面左側
內容：披風波紋與背肌
補充：地面裂紋仍冒煙
安全：無文字

#### Beat 9（12.0–13.5s）
重點：金色龍瞳對視
Blocking：男子抬頭，看向遠方，瞳孔收縮閃光。
Camera：
- 運鏡：胸口以上近景略仰
- 焦段/機位：65mm 胸高仰視
- 對焦：單點瞳孔
- 快門角：180；拍點：瞳孔縮放
光影：側逆光形成瞳內金線
色調/LUT：臉部暖，背景冷
聲音：ozone_drone_bed 留空＋披風摩擦聲
轉場：視線移向鏡頭遮擋 → Beat 10

Angle 9
構圖：頭肩近景，面向右上
內容：對視瞬間
補充：髮絲被風掀起
安全：無文字

#### Beat 10（13.5–15.0s）
重點：一句話鉤子與黑場
Blocking：鏡頭推向唇部，男子微笑低聲說出台詞：「既然叫我下來，就別打算全身而退。」結束瞬間切黑。
Camera：
- 運鏡：胸高微推至唇特寫
- 焦段/機位：85mm 胸高
- 對焦：單點唇線→喉結
- 快門角：180；拍點：口型出聲
光影：口鼻前有雷光反射，背景漆黑
色調/LUT：唇部暖金反射
聲音：低沉龍吼殘響混近講聲，尾端抽成黑場餘電
轉場：硬切黑場留 Logo 位

Angle 10
構圖：唇部特寫居中
內容：台詞與微笑
補充：黑場前地面龍影一閃
安全：無文字

---

## Audio 運行備忘
- 以 Lightning Chain Audio 為節奏框架，120 BPM 對齊雷鏈與鱗片貼合節奏；黑環吞光時暫停 crackle_triplets 僅留 ozone_drone_bed。
- 龍吼使用低頻延時與 pitch shift 疊加，避免與人聲台詞頻段互相遮蔽；台詞保持 -6 dB 峰值，混響 0.8s。
- 落地與衝擊段增加 sub_thump_sync 與地面枝狀放電的火星聲，尾端黑場留下 1.5s 餘電尾音銜接 Logo。

## QA Checklist（提交前自檢）
- [ ] 運鏡節奏符合 0.5–1.5s 段落，焦段/對比與 Master Prompt 對齊。
- [ ] 鱗片與肌膚陰影保留紋理，眼神光由雷光與鱗片反射補足。
- [ ] 轉場（雷光匹配、鱗片遮擋、羽化黑場）已設計且時間軸標記完成。
- [ ] Lightning Chain Look/VFX/Audio 參數套用且黑環吞光段降低飽和與亮度。
- [ ] 畫面內無可讀字樣或品牌，龍影與地面裂紋僅為圖騰質感。
- [ ] 交付規格保持 16:9｜24fps，音訊 -14 LUFS，Limiter -1 dBTP。

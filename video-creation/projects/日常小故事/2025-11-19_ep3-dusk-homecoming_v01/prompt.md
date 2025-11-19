# 日常小故事 EP3 — 黃昏回家的臥蠶肌肉青年帥哥 × 深灰英短米漿貓・15 秒 8 幕 Prompt（15s｜8 幕）

來源 brief：依使用者提供的 8 幕劇情，呈現 25 歲健身教練型臥蠶肌肉青年與深灰英短「米漿」的黃昏回家療癒日常，加入青年外觀設定模組。

## 一句話題材
黃昏時分的健身教練下班回家被英短迎接，從玄關到客廳一路放鬆並被貓治癒，15 秒 8 幕紀錄人貓互相療癒的節奏。

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
☐ 情緒→運鏡已選定；焦段/對比/轉場一致
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

## `_stylepacks` 區塊
### Style Pack：Mijiang Warm Cinema Look（`_stylepacks/mijiang_warm_cinema/look.yml`）
```yaml
name: Mijiang Warm Cinema Look
lut: Ember-Soft-Negative
white_balance_reference: 3200K_lamp
contrast: gentle_low_mid
highlight_tone: honey_amber
shadow_tone: indigo_soft_cool
skin_tone_ire: 58-62
saturation_adjust: -0.03
grain_profile: fine_35mm_400T
bloom: localized_palm_glow
notes:
  - 夜間室內保留暖黃主光與藍冷陰影對比
  - 皮膚與貓毛維持柔亮層次，不可過曝
  - 適度保留顆粒感與光暈，塑造溫馨電影質感
```

### Style Pack：Mijiang Warm Cinema Lighting（`_stylepacks/mijiang_warm_cinema/lighting.yml`）
```yaml
name: Mijiang Warm Cinema Lighting
key_light:
  source: tungsten_table_lamp
  color_temp: 3000K
  modifier: opal_dome_diffuser
fill:
  source: bounced_practical
  color_temp: 4200K
  intensity_ratio: 0.35
backlight:
  source: hidden_led_strip
  color_temp: 4600K
  notes: 用於勾勒貓耳與掌心邊緣
practicals:
  - name: corridor_window_sunset
    description: 4300K 黃昏窗光切入走廊形成長陰影
  - name: tv_cool_edge
    description: 客廳電視提供微弱冷藍 rim 勾邊
atmosphere:
  haze_level: 0.04
  particles: suspended_dust_soft
notes:
  - 走廊階段維持夕陽逆光，入屋後轉為暖燈＋窗餘暈
  - 控制對比，保留臥蠶與貓毛細節
  - 冰水段加局部高光凸顯水珠
```

### Style Pack：Mijiang Warm Cinema Lens Set（`_stylepacks/mijiang_warm_cinema/lensset.yml`）
```yaml
name: Mijiang Warm Cinema Lens Set
primary_focals: [28, 35, 48, 75]
shutter_angle: 180
depth_of_field: shallow_T2.0-T2.8
dolly:
  move: slider_glide_in
  speed_ratio: 0.7
handheld_usage: 0.02
support: slider_or_tripod_breath
focus_method: layered_pull_subject_to_pet
usage_notes:
  - 28mm 捕捉走廊與客廳全貌，保持暖色空間層次
  - 35/48mm 讓人與貓貼近又留出呼吸感
  - 75mm 用於臥蠶、貓呼嚕等細節特寫
```

### Style Pack：Mijiang Warm Cinema Audio（`_stylepacks/mijiang_warm_cinema/audio.yml`）
```yaml
name: Mijiang Warm Cinema Audio
music:
  palette: lo_fi_guitar_with_piano_voicing
  bpm: 72
  progression: tired_major_sus4_to_rest
ambience:
  layers:
    - corridor_evening_air
    - apartment_hvac_low_hum
    - distant_city_muffle
foley:
  - gym_bag_brush
  - key_in_lock_click
  - sneaker_rubber_floor
  - ice_cubes_clink_glass
  - cat_headbump_soft_thud
  - cat_purr_close_mic
voice:
  type: soft_spoken_whisper
  treatment: close_mic_soft_reverb
mix_targets:
  loudness: -14_LUFS
  peak: -1_dBTP
  dynamic_range: -18_to_-6_dBFS
notes:
  - 前段吉他節奏保持輕快但帶疲憊呼吸聲
  - 中段加入冰水與呼嚕層提升親密度
  - 結尾放大呼嚕並壓低音樂做關機感
```

### Style Pack：Mijiang Warm Cinema Safety Checklist（`_stylepacks/mijiang_warm_cinema/safety.yml`）
```yaml
name: Mijiang Warm Cinema Safety Checklist
rules:
  - 貓咪衝刺與跳躍需控制高度，鏡頭距離≥50cm
  - 冰水段避免出現品牌瓶身或可讀標籤
  - 沙發段確保青年與貓姿勢放鬆無擠壓
  - 除對白字幕外畫面不得出現手機、電腦可讀內容
  - 收音時維持環境舒適溫度，避免冷氣直吹貓
```

## Master Prompt（15s｜寫實暖調 PV｜16:9｜23.98fps｜暖黃臥室電影質感）
「黃昏後的台北公寓走廊與客廳；長陰影走廊、玄關小地毯、淺灰沙發與茶几；25 歲健身教練型肌肉青年扛著運動包回家，被深灰英短米漿衝撞迎接，換裝、喝冰水、躺在沙發與貓同步呼吸並坦白「是我被你治癒」。
鏡頭：滑軌＋穩定器，僅 2% 手持模擬貓視角晃動。
表演：青年先是疲憊又鬆口氣，被貓蹭後笑出聲；米漿動作理直氣壯、呼嚕漸大。
臉型/髮型：依《青年外觀基本設定》短髮臥蠶肌肉青年，深灰英短圓臉黃眼。
構圖：前中後層次與窗口逆光留白 15%，胸口段採淺景深凸顯臥蠶與貓呼吸。
寫實細節：深色運動 T 與汗痕、灰跑鞋、玻璃杯水珠、貓毛黏上淺色居家 T、沙發毛毯與散落運動包、窗簾被冷氣帶動。
聲音：72 BPM Lo-fi 吉他＋鋼琴疊疲憊氣音，疊加鑰匙、門軸、冰塊碰撞、貓呼嚕與遠冷氣聲；轉場以光源匹配與遮擋。
安全：無品牌、無螢幕內容、僅顯成人男性，貓咪保持安全互動。」

### Camera Continuity
- 走廊與玄關 28mm 低角滑行→玄關內 35mm 低角接手，逆光色溫 4300K，鏡頭高度維持膝至腰部平順過門。
- 客廳段改用 48mm 胸高貼近互動，沙發呼吸段 75mm 近景以 T2.0 控制淺景深，保持臥蠶與貓毛同焦。
- 最後拉遠 24mm 外景→客廳全景，色溫 3000K 室內 + 3300K 黃昏殘光，慢速拉鏡成收束。

## Scene Blocks（15s｜8 幕 × 約 1.9s）

### Act 1（0.0–4.0s）
意圖：建立黃昏歸家節奏與迎接儀式
基調：輕快中帶疲憊的溫柔
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：夕陽走廊、深色運動裝、玄關地毯、逆光

#### Beat 1（0.0–2.0s）
重點：黃昏走廊的背影回家
Blocking：青年肩扛運動包沿公寓走廊走向鏡頭，手臂仍帶訓練後泵感，窗邊夕陽灑進。
Camera：
- 運鏡：手持 28mm 背後跟拍模擬好友視角，穩定器平滑 98% + 2% 呼吸晃
- 焦段/機位：28mm 背後胸高
- 對焦：單點背肌→層次拉至鑰匙手
- 快門角：180；拍點：鑰匙舉起前呼氣
光影：夕陽逆光4300K 混走廊室內 3600K，肩膀 rim light
色調/LUT：膚色優先、陰影帶柔藍，背景留暖黃 flare
聲音：Lo-fi 吉他前奏＋呼吸聲；腳步與包帶摩擦
轉場：右肩入鏡遮擋 → Beat2

Angle 1
構圖：青年置中，走廊線條引導門口
內容：單肩包、汗痕在 T 恤成淡痕
補充：窗外夕陽在地上投長條光
安全：無住戶資訊

#### Beat 2（2.0–4.0s）
重點：玄關重逢，米漿衝撞
Blocking：門開瞬間逆光切入，玄關地毯上的米漿立刻衝向青年，頭「砰」撞腿並繞鞋。
Camera：
- 運鏡：低角 35mm 穩定器，貓視角輕晃
- 焦段/機位：35mm 地面高度 30cm
- 對焦：層次從門縫光→貓→青年小腿
- 快門角：200；拍點：貓頭撞腿
光影：逆光切線＋室內暖燈 3200K，貓毛 rim 亮
色調/LUT：高光暖金，地毯灰藍
聲音：門鎖嗒聲、青年帶笑「我回來——」、貓呼嚕漸起
轉場：貓尾掃過鏡頭做遮擋

Angle 2
構圖：玄關地毯為前景，青年小腿右側，貓自左入
內容：米漿尾巴豎成感嘆號
補充：鞋面灰塵被貓蹭起
安全：地毯無圖樣字

### Act 2（4.0–10.0s）
意圖：進入家中建立親暱 routine
基調：療癒與放鬆
節奏域：穩定1.5–2.4
美術要點：玄關暖光、廚房吧台、冰水杯、淺色居家 T、沙發

#### Beat 3（4.0–6.0s）
重點：解鞋帶與問候
Blocking：青年蹲下解鞋帶，臉帶疲態但微笑，手指順勢滑到米漿背上。
Camera：
- 運鏡：48mm 胸高側面微推
- 焦段/機位：48mm 眼平偏側
- 對焦：單點青年臉→拉到貓背
- 快門角：180；拍點：「今天學生乖不乖？」
光影：玄關暖光 3200K 打臉，背後夕陽餘光 rim
色調/LUT：膚色暖、貓毛灰藍
聲音：青年對白、貓呼嚕回應
轉場：青年抬頭順勢站起帶鞭移

Angle 3
構圖：青年臉占右三分線，貓在左下
內容：臥蠶在黃光下柔軟
補充：指節梳過貓短毛
安全：鞋無 logo

#### Beat 4（6.0–7.8s）
重點：倒冰水與疲憊臥蠶特寫
Blocking：換上淺色寬鬆 T，青年在桌邊倒滿冰水，一口喝下半杯並長呼氣。
Camera：
- 運鏡：先 75mm 近拍玻璃杯→匹配剪切 48mm 半身
- 焦段/機位：75mm 桌面；48mm 胸高
- 對焦：單點水珠→喉結
- 快門角：180；拍點：杯子放下瞬間
光影：桌面局部高光，脖頸留汗光
色調/LUT：高光暖白、陰影柔冷
聲音：冰塊碰杯聲、吞嚥音、音樂 softer
轉場：杯子下放遮擋切沙發

Angle 4
構圖：玻璃杯置左三分線，水珠沿杯壁
內容：青年喉結上下滑動
補充：T 恤布料貼出胸肌線
安全：無品牌杯

#### Beat 5（7.8–10.0s）
重點：沙發巡視與貓踩腹肌
Blocking：青年半躺沙發，米漿從大腿踩到腹肌，停頓回望。
Camera：
- 運鏡：35mm 正面中景穩定
- 焦段/機位：35mm 眼高
- 對焦：層次貓爪→青年腹部
- 快門角：180；拍點：「欸欸，慢一點。」輕笑
光影：客廳暖燈 3000K＋電視冷藍 4300K 勾邊
色調/LUT：暖冷對比，貓毛亮
聲音：沙發布料摩擦、貓踩踏節奏
轉場：貓停在胸口後向上移動→匹配至 Beat6

Angle 5
構圖：青年腿成對角線，貓沿線前進
內容：貓爪踩腹時青年微收腹
補充：手托住貓避免滑落
安全：沙發布料素面

### Act 3（10.0–15.0s）
意圖：收束於胸口同步呼吸與心聲
基調：沈靜療癒
節奏域：穩定1.5–2.4 → 慢出0.8–1.5
美術要點：淺景深胸口、呼嚕聲、青年臥蠶特寫、客廳廣角

#### Beat 6（10.0–11.5s）
重點：胸口小毯子與一呼一吸
Blocking：米漿蜷在青年胸口，尾巴垂在手臂旁，青年手掌輕搭背上。
Camera：
- 運鏡：75mm 側面近景，緩慢滑動 5cm
- 焦段/機位：75mm 胸高
- 對焦：單點貓背→呼吸拉至青年手
- 快門角：180；拍點：呼吸同步
光影：暖燈主光＋電視冷邊
色調/LUT：高光暖、背景虛化
聲音：貓呼嚕放大，音樂壓低
轉場：保持同構圖→Beat7

Angle 6
構圖：胸口與貓佔滿畫面，背景虛
內容：尾巴輕晃後歸於胸口
補充：手指無意識梳毛
安全：無字樣

#### Beat 7（11.5–13.0s）
重點：臥蠶與眼神的告白
Blocking：青年低頭望貓，指尖在背上畫圈並低聲告白。
Camera：
- 運鏡：75mm 臉部特寫略仰拍，貓耳在畫面下緣
- 焦段/機位：75mm 近景
- 對焦：單點眼神，保持臥蠶清晰
- 快門角：144；拍點：「結果回到家，是我被你治癒。」
光影：3000K 暖光柔化臥蠶，眼神光保留
色調/LUT：膚色 60 IRE，陰影暖褐
聲音：聲線壓低、呼吸放慢
轉場：語尾呼吸作聲學羽化 → Beat8

Angle 7
構圖：青年臉佔右三分線，貓耳隱約露出
內容：臥蠶形成柔弧線
補充：眼裡反射窗光
安全：無字幕

#### Beat 8（13.0–15.0s）
重點：客廳全景收束與「今天關機」
Blocking：鏡頭拉遠至窗外，青年半躺睡去，米漿睡得更沉，電視光暗且冷氣吹動窗簾。
Camera：
- 運鏡：24mm 從客廳內平滑拉遠至窗外，略微俯視
- 焦段/機位：24mm 胸高起始→窗外
- 對焦：層次青年→玻璃反射
- 快門角：144；拍點：尾巴最後晃動
光影：室內暖燈 3000K vs 外部晚霞 3300K，電視冷光壓暗
色調/LUT：外冷內暖，窗框做前景
聲音：電視遠背景音＋冷氣運轉，音樂和弦收尾，最後浮現「今天關機。」字卡
轉場：淡出結束

Angle 8
構圖：窗框包覆沙發，茶几、運動包與貓構成三角
內容：白字「今天關機。」緩緩浮現
補充：窗簾被冷氣輕晃
安全：字卡無 logo

## 聲音與音樂備註
- 音樂：Lo-fi fingerstyle 吉他主導，加入 Rhodes piano 疲憊和弦，第 6 幕後漸收僅留低頻鋼琴與貓呼嚕。
- Foley：鑰匙插鎖、門軸、布料、鞋帶摩擦、玻璃杯冰塊、吞嚥、沙發布料、貓踩踏、呼嚕與冷氣氣流；第 2 幕貓撞腿需加柔軟 thud。
- Voice：青年對白「我回來——」「今天學生乖不乖？」「欸欸，慢一點」「你知道嗎......是我被你治癒。」收音貼近，其他段落僅保留氣音。

## 青年外觀基本設定（《黃昏回家》主角）
**年齡與身份感**
- 25 歲，體能／健身教練型日常英雄，工作模式看起來酷但在家極溫柔。

**臉部與五官**
- 偏長瓜子臉，下顎線清楚帶少年感。
- 單眼皮或內雙，眼型細長，眼尾微微上挑。
- 臥蠶存在感強，是標誌；疲憊時略深讓人覺得柔軟。
- 眉毛中等偏濃，眉形乾淨微上揚。
- 鼻樑挺不誇張，嘴唇中等厚度，自然帶微笑弧。
- 膚色健康小麥，長期戶外與健身的均勻膚色。

**髮型與細節**
- 深棕接近黑色短髮，兩側稍推短，頂部略長自然往後抓帶微亂。
- 鬢角乾淨，可有極淡鬍渣增添成熟感但不邋遢。

**體型與姿態**
- 身高視覺約 178–182 公分，肩膀寬、鎖骨清楚。
- 胸肌、背肌、手臂線條明顯，屬於實用派肌肉；前臂有隱約青筋。
- 走廊／玄關保持肩膀微展、訓練後泵感；沙發段徹底鬆弛陷入靠背。

**服裝（本 PV 專用）**
1. 回家前段（幕 1–3）：深色貼身運動 T 或速乾衣＋深色運動長褲/七分褲；黑灰跑鞋有使用痕跡；黑色運動錶或矽膠腕帶。
2. 換裝後（幕 4–8）：淺色寬鬆 T（米白/淺灰/淡暖色）＋深灰或藏青居家短褲；衣料可沾少量貓毛。

**一眼辨識要素**
- 有臥蠶、短髮、寬肩肌肉線條的溫柔青年。
- 肌肉線條撐起衣料但表情鬆弛，抱著深灰英短米漿時進入被治癒模式。
- 招牌構圖：半躺沙發，胸口一團深灰英短同步呼吸。

## QA Checklist（交付前自評）
- [ ] 運鏡焦段連戲：走廊 28mm→玄關 35mm→客廳 35/48mm→特寫 75mm→全景 24mm。
- [ ] 膚色 58–62 IRE，臥蠶與貓毛細節保留，汗光控制。
- [ ] 轉場依序使用遮擋、匹配光源、語氣羽化與淡出，無突兀切換。
- [ ] 音樂 BPM 72、呼嚕聲層次、對白音量記錄完畢，音畫同步。
- [ ] 畫面無品牌與可讀字樣，字卡僅顯示「今天關機。」。
- [ ] 交付規格：4K 16:9、-14 LUFS 立體聲。

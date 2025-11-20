# 日常小故事 EP8 — 《哈幾雪地犯蠢廣告》：肌肉帥哥 × 哈士奇 × 雪地迷因・15 秒 10 幕 Prompt（15s｜10 幕）

來源 brief：依使用者提供的雪地日常故事與 10 幕 PV 設定，拍出肌肉帥哥帶哈幾玩雪球，從運動大片感一路翻車成雪地迷因的 15 秒竪屏短片，強調「我很帥，犯蠢只是特效」的反差幽默。

## 一句話故事大綱
冬日下午雪堤公園，肌肉青年與哈士奇哈幾拍出宛如運動廣告的開場，卻因哈幾滑倒、自爆與雪糊臉，把帥氣瞬間拉成 meme，留下笑到彎腰的日常。

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
手感鉤子：蓄力提示→觸發→回饋（聲/光/震）→冷卻可視化（顏色 or 粒子度下降）

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
### Style Pack：Snow Meme Nordic Look（`_stylepacks/snow_meme_nordic/look.yml`）
```yaml
name: Snow Meme Nordic Look
lut: Crisp-Cool-Daylight
white_balance_reference: 5600K_snow_overcast
contrast: medium_soft
highlight_tone: pearl_white_with_warm_edge
shadow_tone: slate_blue
skin_tone_ire: 55-60
saturation_adjust: -0.05
grain_profile: clean_digital_with_soft_bloom
bloom: snow_glow_micro
notes:
  - 保留雪面細節與犬毛層次，避免過曝
  - 高光略暖以平衡雪地冷感，呈現日韓寫實廣告質感
```

### Style Pack：Snow Meme Nordic Lighting（`_stylepacks/snow_meme_nordic/lighting.yml`）
```yaml
name: Snow Meme Nordic Lighting
key_light:
  source: winter_overcast_sky
  color_temp: 5400K
  intensity_ratio: 1.0
fill:
  source: snow_bounce
  color_temp: 5200K
  intensity_ratio: 0.6
backlight:
  source: low_sun_edge_or_practical_lamp_glow
  color_temp: 4800K
  notes: 為狗毛和雪霧加 rim 勾邊
atmosphere:
  haze_level: 0.03
  particles: light_snowflakes
notes:
  - 全程保持柔和漫射，讓雪、毛與臉部都有細節
  - 風向自河面吹向草地，毛髮有微微倒伏動態
```

### Style Pack：Snow Meme Nordic Lens Set（`_stylepacks/snow_meme_nordic/lensset.yml`）
```yaml
name: Snow Meme Nordic Lens Set
primary_focals: [24, 35, 50, 80]
shutter_angle: 180
depth_of_field: moderate_T2.8-T4
camera_support: handheld_phone_style_with_soft_ibis
handheld_usage: 0.05
movement:
  dolly: gentle_forward_push
  note: 慢動作拋球與滑倒段落可短暫穩定器
focus_method: single_point_to_layered_pull_on_dog
usage_notes:
  - 24/35mm 建立雪地空間與跑動速度感
  - 50/80mm 用於哈幾臉部特寫與雪糊臉 meme
```

### Style Pack：Snow Meme Nordic Audio（`_stylepacks/snow_meme_nordic/audio.yml`）
```yaml
name: Snow Meme Nordic Audio
music:
  palette: warm_lofi_strings_with_brushes
  bpm: 82
  progression: hopeful_major_to_comic_break
ambience:
  layers:
    - distant_city_muffle_winter
    - riverside_wind_soft
    - falling_snow_soft_hits
foley:
  - snow_pack_crunch
  - jacket_zipper_pull
  - glove_drop
  - dog_pant_and_snort
  - snowball_swoosh
  - slip_slide_whoosh
voice_fx:
  type: record_scratch_short_for_meme_cut
  placement: 7.8-8.2s when dog flips
mix_targets:
  loudness: -14_LUFS
  peak: -1_dBTP
  dynamic_range: -18_to_-6_dBFS
notes:
  - 前半保持溫暖弦樂，翻車瞬間插入 record scratch +鼓點停拍
  - 結尾留空 0.3s 讓觀眾笑聲或字幕停留
```

### Style Pack：Snow Meme Nordic Safety Checklist（`_stylepacks/snow_meme_nordic/safety.yml`）
```yaml
name: Snow Meme Nordic Safety Checklist
rules:
  - 哈士奇跑動與滑倒皆為模擬，不得呈現受傷；鏡頭距離≥70cm
  - 避免出現品牌服飾或咖啡杯 Logo；牽繩、項圈僅有「HAJI」名牌
  - 雪地鏡頭保持 horizon 水平，避免造成暈眩
  - 手機手持感允許微晃但不得突兀跳剪
```

## Master Prompt（15s｜寫實日韓雪地廣告 × 哈士奇迷因｜9:16｜24fps｜柔和日光與雪反射質感）
「冬日下午的河堤雪地公園；覆雪草坡、遠處朦朧高樓、緩慢飄雪；東亞肌肉青年穿深色羽絨外套與針織帽，提牽繩拿保溫咖啡，與黑白冰藍眼哈士奇哈幾玩丟雪球，畫面從運動大片感突然被哈幾滑倒、自爆雪球與雪糊臉變成迷因。」
鏡頭：9:16 手機手持 5% 微晃為主，偶用滑軌穩定跟雪球與跑動，慢動作捕捉拋球與翻車。
表演：青年酷帥帶笑，從帥氣拋球到笑到彎腰；哈幾先是封面狗專注→滑倒當機→立刻裝沒事→雪糊臉還自豪。
臉型/髮型：25 歲短髮健身青年、肩臂線條明顯；哈士奇黑白毛、冰藍眼、鼻樑白線、藍色項圈「HAJI」。
構圖：三分線與前中後景，雪地留白 15–20%，狗為主角；飄雪與呼氣形成前景粒子，背景高樓淺景深。
寫實細節：雪面腳印、雪球破碎、毛流隨風倒伏、咖啡杯熱氣、呼氣白霧；無品牌。
聲音：82 BPM 溫暖 lo-fi 弦樂，翻車處加 record scratch 與鼓點斷拍；雪踩聲、雪球破碎、狗喘與搖鈴項圈、遠處風聲；轉場以鞭移或遮擋。
安全：無可讀 Logo，犬隻安全距離，滑倒為可愛翻滾非受傷。

### Camera Continuity
- 全片維持 24–50mm 竪屏手持，拋球弧線用 24–35mm 滑軌推，哈幾臉部與雪糊臉用 50–80mm 靠近。
- 色溫 5400–5600K 為主，雪反射提供填光，人物膚色略暖，對比中柔；保持眼神光與毛邊緣 rim。
- 慢動作段（拋球、滑倒）將快門角 200–240 提升動態清晰度，其他保持 180；音樂拍點對應拋球出手與滑倒瞬間。

## Scene Blocks（15s｜10 幕 × 約 1.5s）

### Act 1（0.0–7.5s）
意圖：建立廣告感與拋球衝刺，鋪墊翻車
基調：暖冷混合的爽感中帶輕鬆
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：覆雪草坡、遠樓霧感、青年深色羽絨＋灰帽、藍項圈哈士奇

#### Beat 1（0.0–1.5s）
重點：雪地全景像廣告片頭
Blocking：空拍/高位緩推向青年與哈幾，兩人背對鏡頭站在雪堤
Camera：
- 運鏡：滑軌推＋微俯視
- 焦段/機位：24mm 俯拍胸高
- 對焦：層次前→中→後
- 快門角：180；拍點：鏡頭推近兩人
光影：均勻雪天漫射，柔和對比
色調/LUT：膚色優先、陰影微藍、高光暖 5%
聲音：風聲＋遠城環境，音樂前奏進
轉場：直接切到哈幾特寫

Angle 1
構圖：兩人置中，雪堤作前景線，遠樓在上方留白
內容：青年握牽繩與咖啡，哈幾站得筆直
補充：飄雪粒子前景
安全：去Logo、清理行人臉

#### Beat 2（1.5–3.0s）
重點：哈幾帥臉特寫
Blocking：鏡頭低角度推近哈幾正面，耳朵抖動
Camera：
- 運鏡：手持微晃前推
- 焦段/機位：50mm 膝高仰
- 對焦：單點眼→呼吸拉焦鼻尖
- 快門角：180；拍點：耳朵抖
光影：雪反射填光，柔和高光
色調/LUT：陰影微藍、高光暖
聲音：音樂拉出鋼琴層，細微狗喘
轉場：遮擋到青年捏雪球

Angle 1
構圖：哈幾臉佔滿畫面，三分線對準眼睛
內容：冰藍眼、鼻樑白線，背後雪堤虛化
補充：呼氣白霧淡淡
安全：無可讀標籤

#### Beat 3（3.0–4.5s）
重點：青年捏雪球的準備
Blocking：青年蹲下脫手套、雙手合雪捏球；哈幾半身入畫
Camera：
- 運鏡：手持側移
- 焦段/機位：35mm 胸高
- 對焦：單點手→拉到狗眼
- 快門角：180；拍點：雪球成型
光影：左側雪反射主光，羽絨反光
色調/LUT：膚色優先、去飽和5%
聲音：雪咯吱聲、青年輕笑「看好囉，HAJI」
轉場：鞭移跟雪球飛出

Angle 1
構圖：手在中央，狗頭在右三分線
內容：咖啡杯在前景模糊，手套落在雪面
補充：輕微呼氣霧、雪顆粒
安全：無品牌杯標

#### Beat 4（4.5–6.0s）
重點：完美弧線慢動作拋球
Blocking：青年拋出雪球，鏡頭跟隨雪團飛行
Camera：
- 運鏡：滑軌 + 小幅鞭移追球
- 焦段/機位：24–35mm 眼高
- 對焦：單點雪球飛行
- 快門角：200；拍點：出手瞬間
光影：雪團受側光，背景藍灰天空
色調/LUT：陰影微藍、高光暖
聲音：音樂鼓點加重，雪球破風聲
轉場：匹配切到哈幾奔跑

Angle 1
構圖：雪球在前景中央，背景壓縮成柔和 bokeh
內容：弧線清晰，青年在後方模糊帥氣
補充：雪粉飄散
安全：無額外文字

#### Beat 5（6.0–7.5s）
重點：哈幾狼系帥跑
Blocking：哈幾從左側爆衝向前，鏡頭貼跑
Camera：
- 運鏡：低角度側跟拍手持
- 焦段/機位：28mm 膝高
- 對焦：層次拉焦頭→肩→尾
- 快門角：200；拍點：腳步踩雪
光影：雪面反射照亮毛流，微逆光勾邊
色調/LUT：膚色優先、陰影微藍
聲音：雪被踢起的連續聲，音樂鼓點
轉場：直接切到滑倒慢動作

Angle 1
構圖：哈幾佔右三分線，前景雪被踢起
內容：耳朵向後壓、藍眼鎖定前方
補充：雪浪線形成動態 leading line
安全：鏡頭距離>70cm

### Act 2（7.5–15.0s）
意圖：翻車與迷因化收束
基調：搞笑反差、暖心日常
節奏域：穩定1.5–2.4 → 加速2.4–3.0 收尾
美術要點：雪飛濺、雪糊臉、青年笑到彎腰、字幕迷因

#### Beat 6（7.5–9.0s）
重點：經典滑倒
Blocking：哈幾前腳踩坑滑倒，身體半翻，雪炸起
Camera：
- 運鏡：中景穩定器微慢動作
- 焦段/機位：35mm 胸高
- 對焦：單點頭部
- 快門角：220；拍點：腳滑瞬間
光影：雪花反光，對比中柔
色調/LUT：陰影微藍、高光暖
聲音：record scratch + 鼓點斷拍，雪炸聲
轉場：硬切俯視四腳朝天

Angle 1
構圖：哈幾在中央，雪花佔滿前景
內容：腿空中、嘴微張
補充：慢動作雪粒清晰
安全：強調無受傷

#### Beat 7（9.0–10.5s）
重點：四腳朝天 3 秒當機
Blocking：俯視哈幾躺著不動 0.5s，眼珠轉動 reboot
Camera：
- 運鏡：俯拍定鏡
- 焦段/機位：50mm 俯拍
- 對焦：單點眼睛
- 快門角：200；拍點：眼珠微動
光影：雪面反光作填光
色調/LUT：膚色優先、陰影微藍
聲音：音樂暫停空拍，輕微風聲
轉場：向右平移切到起身

Angle 1
構圖：狗居中，四爪外展
內容：半臉埋雪，藍眼瞪大
補充：呼氣霧形成小煙
安全：去可讀字樣

#### Beat 8（10.5–12.0s）
重點：假裝沒事重啟封面狗
Blocking：哈幾翻身坐好，抬頭挺胸，尾巴一甩
Camera：
- 運鏡：低角度推近
- 焦段/機位：35mm 膝高仰
- 對焦：單點眼→拉到胸口
- 快門角：180；拍點：坐穩瞬間
光影：雪反射補光，邊緣有暖 rim
色調/LUT：陰影微藍、高光暖
聲音：音樂重新進入主題，雪摩擦聲
轉場：遮擋到雪糊臉特寫

Angle 1
構圖：哈幾在右三分線，背景雪堤柔焦
內容：臉上還掛著幾塊雪
補充：尾巴甩動帶起雪粉
安全：鏡頭距離適中

#### Beat 9（12.0–13.5s）
重點：雪糊臉特寫，青年無言拍攝
Blocking：特寫哈幾臉黏滿雪點，後景青年舉手機半蹲
Camera：
- 運鏡：手持微晃
- 焦段/機位：80mm 眼高
- 對焦：單點狗眼，後景青年虛化
- 快門角：180；拍點：狗眨眼
光影：雪反射＋暖膚色，對比柔
色調/LUT：膚色優先、去飽和5%
聲音：青年忍笑的鼻息，音樂留空 0.2s
轉場：直接切到迷因收尾

Angle 1
構圖：狗臉占滿畫面，下方預留字幕空間
內容：雪像貼紙黏在眉毛與鬍子
補充：名牌「HAJI」模糊可見
安全：無品牌

#### Beat 10（13.5–15.0s）
重點：迷因收尾與字幕鉤子
Blocking：中景拉遠，青年左側笑到彎腰，哈幾右側維持帥坐，突然舔掉臉上雪
Camera：
- 運鏡：手持微拉遠
- 焦段/機位：35mm 眼高
- 對焦：層次拉焦青年→狗→字幕
- 快門角：180；拍點：舔雪瞬間
光影：柔和日光，雪面 bounce 塑型
色調/LUT：陰影微藍、高光暖
聲音：音樂可愛收尾，笑聲淡入
轉場：收束停格 0.2s

Angle 1
構圖：青年左三分線彎腰，狗右三分線坐姿；上下留白給字幕
內容：畫面文字「雪地廣告拍攝現場」「三秒之後變成迷因。」
補充：飄雪持續，咖啡杯蒸氣
安全：字幕為後製字卡，無其他可讀內容


# 日常小故事 EP7 — 《米漿上司的年度考績》：貓老闆 × AI 貓翻譯器 × POV・15 秒 10 幕 Prompt（15s｜10 幕）

來源 brief：依使用者提供的 10 幕情節，呈現健身完回家的肌肉工程師被深灰英短「米漿」用 AI 貓翻譯器做年度考績的 15 秒竪屏短片，強調貓老闆迷因與遲夜加班的 cozy apartment 氛圍。

## 一句話故事大綱
健身完回家的肌肉工程師熬夜改 bug，結果真正來幫他做年度考績的，是坐在螢幕前、用 AI 貓翻譯器發表 KPI 評語的深灰英短米漿上司。

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

## Master Prompt（15s｜寫實日常 Meme｜9:16｜24fps｜手持手機夜間暖冷混光質感）
「夜晚的台北現代感小公寓書桌旁；暖黃桌燈、冷藍螢幕光、木質桌面與散落筆記本水瓶；25 歲東亞男性軟體工程師健身後穿深色寬鬆 T 與短褲熬夜改 bug，深灰英短米漿化身 4 公斤貓上司跳上桌，用 AI 貓翻譯器在螢幕角落發布 KPI 評語，迫使他放下鍵盤順毛認命。
鏡頭：手持 3% 自然晃動為主，搭配滑軌微推拉保持 POV 親密感。
表演：工程師疲憊專注→被貓擋螢幕的無奈微笑→接受摸貓考績的投降感；貓冷靜審視、偶爾小喵、最後呼嚕蓋章。
臉型/髮型：短黑髮、眼袋明顯、肩臂線條健壯；深灰英短圓臉大金眼、短腿微胖。
構圖：9:16 三分線為主，前景鍵盤/貓爪、後景暖冷分層，留白 15% 給字幕與 UI 泡泡。
寫實細節：桌面木紋、塑膠水瓶、廉價外接螢幕無品牌界面、貓毛照亮邊緣光、肌肉線條在 T 恤下若隱若現。
聲音：72 BPM lo-fi 吉他＋輕 percussion，偶有木魚感點子；鍵盤敲擊、滑鼠、貓喵與呼嚕、桌燈電流環境聲；轉場以遮擋或螢幕光匹配。
安全：全程無真實品牌或可讀程式碼，僅有 meme 字卡與假 UI。」

### Camera Continuity
- 全片保持 28–48mm 竪屏 POV 手持，僅在貓爪近拍時用 75mm T2.0 拉近，快門角 180–200，呼吸拉焦在貓→人之間跳轉。
- 色溫夜間 3000–3800K，桌燈為主光，螢幕冷光補邊，貓毛與手臂留邊緣光；對比柔高混合。
- UI 泡泡始終出現在畫面左下角「AI Cat Manager」框，字幕置底細字。

## Scene Blocks（15s｜10 幕 × 約 1.5s）

### Act 1（0.0–4.5s）
意圖：建立加班氛圍與貓上司伏筆
基調：疲憊中帶幽默
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：暖黃桌燈＋冷藍螢幕、木質桌、散落筆記本、水瓶

#### Beat 1（0.0–1.5s）
重點：POV 鉤子與手打程式
Blocking：側面中景手持，工程師快打鍵盤，眉頭緊皺，螢幕光映出眼袋；畫面中心浮現大字「POV：你的直屬上司只有 4 公斤重」，0.3s 後滑到頂部成 meme 標題。
Camera：
- 運鏡：手持 35mm 胸高微晃
- 焦段/機位：35mm 側面略俯
- 對焦：單點螢幕邊緣→拉至手指
- 快門角：180；拍點：字幕滑動時
光影：桌燈 3000K 打臉，螢幕 3800K 藍光做 rim
色調/LUT：膚色優先、陰影微藍、高光暖
聲音：鍵盤敲擊、Lo-fi 前奏、微弱空調
轉場：螢幕邊緣遮擋下切 Beat2

Angle 1
構圖：工程師位於右三分線，螢幕佔左側，字幕居上
內容：肌肉線條在袖口映出，水瓶模糊在前景
補充：螢幕界面為 generic code editor 模糊無可讀碼
安全：無品牌、字幕為自製字卡

#### Beat 2（1.5–3.0s）
重點：桌邊貓影提示
Blocking：略低角近拍鍵盤與桌面，下緣掠過一小團深灰毛球尾巴掃過桌面，工程師仍專注敲鍵。
Camera：
- 運鏡：手持 28mm 低角滑入
- 焦段/機位：28mm 桌面高度
- 對焦：單點鍵盤→尾巴掃過時輕拉
- 快門角：200；拍點：尾巴掃過
光影：桌燈反射在鍵帽，尾巴邊緣被螢幕勾亮
色調/LUT：暖冷混合，鍵帽高光柔
聲音：鍵盤聲＋尾巴掃動布面沙沙
轉場：尾巴遮擋向上抬鏡至 Beat3

Angle 2
構圖：鍵盤置中，尾巴從右下掃過，左側留白給字幕
內容：字幕小字「我：這版一定要在今晚前改完…」
補充：桌面筆記本散開，無可讀文字
安全：鍵盤無 logo

#### Beat 3（3.0–4.5s）
重點：米漿跳上桌擋螢幕
Blocking：跟隨貓的跳躍上升，米漿落在鍵盤前方遮住螢幕中間，坐下盯著畫面；左下角浮出簡單 UI 框「AI Cat Manager」。
Camera：
- 運鏡：手持 35mm 抬升並微推
- 焦段/機位：35mm 眼高隨貓上升
- 對焦：層次鍵盤→貓臉
- 快門角：180；拍點：貓落地瞬間
光影：螢幕背光勾出貓輪廓，桌燈做側光
色調/LUT：貓毛灰藍，背景暖
聲音：桌面輕震、貓落地悶聲
轉場：貓臉朝鏡頭硬切 Beat4

Angle 3
構圖：貓佔中央，螢幕模糊在後，UI 框在左下
內容：貓尾懸空微晃，鍵盤被壓住
補充：螢幕 code 模糊無字
安全：UI 為無 logo 自製

### Act 2（4.5–10.5s）
意圖：貓老闆提出 KPI 評語，工程師無奈投降
基調：搞笑審判感
節奏域：穩定1.5–2.4 → 加速2.4–3.0（貓爪踩鍵）
美術要點：AI 泡泡、螢幕假 Performance Review、鍵盤被踩

#### Beat 4（4.5–6.0s）
重點：第一次貓語翻譯
Blocking：貓正面特寫，微抬下巴對螢幕「喵」；UI 泡泡彈出：「為什麼你還在工作？罐罐 KPI 完成了嗎？」
Camera：
- 運鏡：手持 50mm 微前推
- 焦段/機位：50mm 眼平
- 對焦：單點貓眼，背景散開
- 快門角：180；拍點：喵聲瞬間
光影：螢幕冷光打眼，桌燈暖光填充
色調/LUT：高光暖、陰影帶藍
聲音：輕微木魚敲擊配合泡泡彈出，喵聲貼近
轉場：貓眨眼遮擋切 Beat5

Angle 4
構圖：貓臉佔滿中央，泡泡在左下
內容：金色瞳孔反射螢幕碼流
補充：毛尖被 rim 光勾亮
安全：泡泡文字僅自製字幕

#### Beat 5（6.0–7.5s）
重點：工程師崩潰微笑
Blocking：中景側拍，工程師抬眼看貓，嘴角無奈上揚；底字幕：「我：…上司，我還有兩個 bug 沒修完。」
Camera：
- 運鏡：手持 35mm 稍向右繞 10°
- 焦段/機位：35mm 胸高
- 對焦：呼吸拉焦貓→人臉
- 快門角：180；拍點：嘴角上揚
光影：暖光打臉，螢幕冷邊勾貓毛
色調/LUT：膚色優先，貓毛灰藍
聲音：鍵盤停下，輕笑聲疊音樂
轉場：工程師手推鍵盤向旁遮擋→Beat6

Angle 5
構圖：人與貓對角線相望，字幕置底
內容：手指停在鍵帽上
補充：水瓶前景模糊閃光
安全：無品牌

#### Beat 6（7.5–9.0s）
重點：貓踩鍵盤評分
Blocking：俯拍特寫貓爪踩過鍵帽，每踩一下 UI 泡泡刷新：「本季表現：對貓服從度 A+」「休息紀律 D-」。
Camera：
- 運鏡：手持 75mm 俯拍輕晃，微推跟隨爪
- 焦段/機位：75mm 俯視
- 對焦：單點貓爪，鍵帽淺景深
- 快門角：200；拍點：每次踩下
光影：螢幕反射在鍵帽，貓爪邊緣亮
色調/LUT：冷暖交錯，鍵帽高光控低
聲音：鍵帽輕響、泡泡彈聲、lo-fi 節奏稍加速
轉場：鍵帽被推向鏡頭遮擋→Beat7

Angle 6
構圖：鍵盤填滿畫面，泡泡在左下分兩行
內容：爪毛壓平鍵帽彈回
補充：鍵帽字母模糊不可讀
安全：無品牌

#### Beat 7（9.0–10.5s）
重點：螢幕假 Performance Review
Blocking：近景俯角拍桌面與螢幕，原 code 模糊成 generic editor，右側浮現假的「Performance Review」介面；AI 泡泡總結：「結論：立刻下線，改來幫我順毛。」
Camera：
- 運鏡：手持 35mm 俯角微推
- 焦段/機位：35mm 俯拍螢幕
- 對焦：層次螢幕→泡泡→貓耳
- 快門角：180；拍點：泡泡彈出
光影：螢幕冷光主導，桌燈暖光填木紋
色調/LUT：螢幕偏冷，桌面暖
聲音：UI 提示音、鍵盤滑開聲
轉場：螢幕亮度下降匹配切 Beat8

Angle 7
構圖：螢幕與桌面 50/50，泡泡置左下
內容：Performance Review 介面無品牌純色塊
補充：貓耳尖露出下邊緣
安全：所有文字為自製假 UI

### Act 3（10.5–15.0s）
意圖：接受命運，轉為療癒收束
基調：溫馨投降
節奏域：穩定1.5–2.4 → 慢出0.8–1.5
美術要點：順毛動作、呼嚕聲、螢幕休眠

#### Beat 8（10.5–12.0s）
重點：放棄工作改順毛
Blocking：側面中景，工程師嘆氣笑，把鍵盤推開，雙手把貓抱近胸口順毛；底字幕「我：OK，我的 OKR 就是伺候你。」
Camera：
- 運鏡：手持 35mm 緩慢後滑
- 焦段/機位：35mm 胸高
- 對焦：呼吸拉焦手→貓臉
- 快門角：180；拍點：手托貓
光影：桌燈暖光主導，螢幕亮度降為冷邊
色調/LUT：暖中帶藍，膚色柔
聲音：鍵盤滑動聲、貓喵轉呼嚕、音樂回到柔和
轉場：手臂抱起做遮擋→Beat9

Angle 8
構圖：人貓緊貼居右，左側留空給字幕
內容：鍵盤被推到畫面左側模糊
補充：手臂肌肉線條出現
安全：字幕自製

#### Beat 9（12.0–13.5s）
重點：貓老闆簽名（呼嚕）
Blocking：貓臉特寫，半闔眼開始咕嚕，像蓋章同意；小字：「米漿上司：✅ 員工情緒穩定化完成」。
Camera：
- 運鏡：手持 75mm 微前推
- 焦段/機位：75mm 近景
- 對焦：單點貓眼，鼻尖略糊
- 快門角：144；拍點：呼嚕起始
光影：邊緣光勾耳朵，桌燈柔亮
色調/LUT：陰影微藍，高光暖
聲音：呼嚕聲貼耳，音樂音量再降
轉場：呼嚕聲做聲學羽化→Beat10

Angle 9
構圖：貓臉佔中央，字幕小字置右下
內容：鬍鬚微動
補充：毛髮顆粒感保留
安全：無品牌

#### Beat 10（13.5–15.0s）
重點：收尾梗與結尾卡
Blocking：拉成中遠景，工程師靠椅背抱著貓，螢幕暗下或休眠；上方再次浮現收尾文字「真正的考績面談：『今天有沒有照顧好貓上司？』」，畫面淡出。
Camera：
- 運鏡：手持 28mm 稍微拉遠平移
- 焦段/機位：28mm 胸高→微俯
- 對焦：層次人貓→屏幕暗面反光
- 快門角：180；拍點：文字浮現
光影：桌燈餘光＋窗外微弱街燈冷邊
色調/LUT：暖冷平衡，背景柔糊
聲音：音樂收尾和弦，呼嚕延伸再淡出
轉場：淡出黑結束

Angle 10
構圖：人貓居中偏右，螢幕暗作左側塊面，文字置頂
內容：公寓一隅含窗簾輕晃
補充：桌面筆記本與水瓶成前景三角
安全：無品牌、字卡自製

## 聲音與音樂備註
- 音樂：維持 72 BPM lo-fi 吉他＋輕 percussion，Beat4 喵聲時加木魚點，Beat6 鍵盤踩踏時節奏加一層 hi-hat，Beat8 之後漸降音量只留和弦與呼嚕。
- Foley：鍵盤敲擊、滑鼠點、筆記本摩擦、貓跳桌悶聲、貓爪踩鍵、椅子輕移、桌燈電流底噪；呼嚕要貼近胸前收音。
- Voice/Sub：螢幕上 meme 字卡＋ AI 泡泡使用簡體字型風格但仍自製，工程師對白兩句（Beat2 自語、Beat5 抱怨）用近講收音；貓喵聲小而近。

## 縮圖文字建議
1. 真正老闆：只有 4 公斤
2. 上班被人罵　下班被貓考績

## Hashtag 建議
#米漿 #深灰英短 #貓老闆 #工程師日常 #mevsmycat #SORAshorts #貓奴KPI

## 交付 QA 自檢
- [ ] 情緒與運鏡節奏符合「加班→審判→投降」邏輯，焦段 28–75mm 與快門角 180–200 一致。
- [ ] 膚色 58–62 IRE，貓毛保留層次，眼神光有保留；暖冷混光比例符合 stylepack。
- [ ] 轉場以遮擋、光匹配與淡出完成，不留突兀切。
- [ ] LUT、光比、音畫同步門檻記錄到位，鍵盤與 UI 無可讀品牌與真實程式碼。
- [ ] 生成設定與交付規格（9:16｜24fps｜15s）一致，安全檢查通過。

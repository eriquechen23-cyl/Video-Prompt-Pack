# 英短藍貓的厚臉皮示愛 Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-15_british-shorthair-boldlove_v01/script.md

## 一句話題材
表面高冷的英短藍貓米漿在你加班時厚著臉皮攻佔鍵盤，用呼嚕和翻肚逼你投降陪玩。

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

### Style Pack：Mijiang Warm Cinema Audio（`_stylepacks/mijiang_warm_cinema/audio.yml`）
```yaml
name: Mijiang Warm Cinema Audio
music:
  palette: lo_fi_strings_with_mallets
  bpm: 68
  progression: warm_minor_to_major_lift
ambience:
  layers:
    - hvac_low_hum
    - distant_city_muffle
    - soft_room_air
foley:
  - cloth_shift_subtle
  - finger_snap_resonant
  - cardboard_rustle
  - cat_paw_wood_taps
  - cat_purr_close_mic
voice:
  type: whispered_roll_call
  treatment: close_mic_soft_reverb
mix_targets:
  loudness: -14_LUFS
  peak: -1_dBTP
  dynamic_range: -18_to_-6_dBFS
notes:
  - 保留高頻空氣感避免房間過乾
  - 貓呼嚕聲後段可漸進成主導層
  - 音樂和光線變化需保持 0.9× 節奏同步
```

### Style Pack：Mijiang Warm Cinema Lens Set（`_stylepacks/mijiang_warm_cinema/lensset.yml`）
```yaml
name: Mijiang Warm Cinema Lens Set
primary_focals: [32, 48, 75]
shutter_angle: 180
depth_of_field: shallow_T2.0-T2.8
dolly:
  move: slider_glide_in
  speed_ratio: 0.75
handheld_usage: 0.02
support: slider_or_tripod_breath
focus_method: layered_pull_foreground_to_subject
usage_notes:
  - 32mm 建立環境光圈，保持前中後層次
  - 48mm 拍攝人與貓互動，視線貼近但穩定
  - 75mm 捕捉手部與毛髮細節，控制呼吸式拉焦
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
  - name: floor_reflection
    description: 木地板反射暖光形成淡光圈
  - name: sigil_glow
    description: 地面光陣散發淡金光補亮暗部
atmosphere:
  haze_level: 0.05
  particles: suspended_dust_soft
notes:
  - 暖黃實光搭配冷調背景，營造陰影安全感
  - 控制對比避免完全漆黑，保留細節可供追焦
  - 光陣亮度需可動畫控，與呢喃節奏同步
```

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

### Style Pack：Mijiang Warm Cinema Safety Checklist（`_stylepacks/mijiang_warm_cinema/safety.yml`）
```yaml
name: Mijiang Warm Cinema Safety Checklist
rules:
  - 避免實際火焰或高溫燈具接近動物
  - 所有道具紙箱貼紙需模糊或移除文字
  - 保持人類臉部低於 50% 曝光，主角為米漿
  - 記錄光陣亮度與動畫參數以利 QA 重製
  - 收音時預留貓咪舒適距離，避免驚嚇
```

## Master Prompt
Master(15s｜Mijiang Warm Cinema｜16:9｜24fps｜柔焦膠片)
「夜間居家工作桌；黑色機械鍵盤、冷藍螢幕溢光、暖黃桌燈；英短藍貓闖入鍵盤以肉墊佔位逼停工作。
鏡頭：滑軌與定鏡交替，局部手持≤2%。
表演：你從專注到投降的無聲反應，米漿由高冷轉換為撒嬌翻肚。
臉型/髮型：人類保持低曝光，只見手與下顎線。
構圖：前中後層疊，保留 15% 冷藍留白；動態：貓尾掃動、桌燈微晃、空調帶動紙張。
寫實細節：黑曜質感鍵帽、英短短毛蓬鬆、螢幕藍光映射指節與桌面。
無字幕、無商標/Logo/水印。」
鏡頭語法：24–35 空間、50–75 親密切換；光圈 T2.0–T2.8；快門角 180°；
對焦：單點眼＋層次前→中→後呼吸拉焦。
光影：暖燈作主、螢幕冷光作邊緣，色溫夜間 3000–3600K；對比柔；眼神光保留。
色調/LUT：膚色優先、陰影微藍、高光暖、去飽和 5%。
聲音：空調軟送風、鍵盤觸發、貓咪呼嚕與肉墊落桌；無人聲（voice layer muted）。
轉場：直接切配合動作節點，必要時遮擋滑動 0.5s。
安全：無可讀文件、保留貓舒適距離、桌面道具去商標。

## 分鏡（12 幕｜約 15s）

### Act 1（0.0–4.0s）
意圖：建立工作氛圍與貓咪侵入
基調：暖中帶冷、療癒期待
節奏域：慢入 1.2s
美術要點：黑鍵盤、冷藍螢幕暈光、灰藍毛團對比暖燈

#### Beat 1（0.0–1.0s）
重點：鍵盤雨聲開場
Blocking：雙手飛快敲擊，螢幕溢光
Camera：
- 運鏡：俯視定鏡
- 焦段/機位：32mm 俯拍
- 對焦：單點鍵帽中區
- 快門角：180；拍點：打字節奏落在 4 拍
光影：冷藍主光映亮指節，桌燈暖光輔助
色調/LUT：陰影微藍、高光暖
聲音：持續「噠噠」鍵擊＋柔和空調風，無人聲
轉場：直接切 → Beat 2

Angle A
構圖：俯視三分線，雙手佔中央
內容：鍵盤工作中景
補充：螢幕光在桌面形成倒影
安全：螢幕內容離焦

#### Beat 2（1.0–2.0s）
重點：灰藍影子靠近
Blocking：畫面下緣闖入灰藍毛耳與尾
Camera：
- 運鏡：同角度微推近
- 焦段/機位：32→48mm 漸進
- 對焦：層次前→中
- 快門角：180；拍點：尾巴掠過畫面
光影：螢幕冷光描邊毛耳
色調/LUT：陰影微藍，去飽和 5%
聲音：鍵擊維持，附加輕柔貓咪「喵」氣音（不含人聲）
轉場：遮擋滑移接 → Beat 3

Angle B
構圖：三分線，貓影佔下緣
內容：入畫提示
補充：尾巴在畫面邊緣掃出殘影
安全：桌面紙張無字

#### Beat 3（2.0–3.0s）
重點：肉墊著地
Blocking：米漿跳上桌，肉墊落桌停在鍵盤前
Camera：
- 運鏡：側邊手持≤2% 跟拍
- 焦段/機位：48mm 桌面高度
- 對焦：單點貓爪
- 快門角：180；拍點：肉墊「咚」觸地
光影：暖燈打亮毛束，冷光成邊緣
色調/LUT：高光暖
聲音：低沈「咚」＋鍵帽微響
轉場：直接切 → Beat 4

Angle C
構圖：前景鍵盤、中景貓爪
內容：跳上桌特寫
補充：毛尖顫動
安全：鍵帽無字

#### Beat 4（3.0–4.0s）
重點：屁股坐滿鏡頭
Blocking：米漿面向螢幕坐下，背對鏡頭
Camera：
- 運鏡：低角度定鏡
- 焦段/機位：32mm 鍵盤前方
- 對焦：單點毛尾根部
- 快門角：180；拍點：重量壓下
光影：螢幕冷光沿毛流勾邊
色調/LUT：陰影微藍
聲音：鍵盤被壓出連續「嗶——」
轉場：直接切 → Beat 5

Angle D
構圖：中央滿框灰藍毛
內容：貓背佔滿畫面
補充：兩側縫隙露出被壓扁鍵帽
安全：畫面無文字

### Act 2（4.0–8.0s）
意圖：高冷外表轉為撒嬌
基調：高冷轉暖
節奏域：穩定 1.5s
美術要點：螢幕亂碼、呼嚕震動、手貓互動

#### Beat 5（4.0–5.0s）
重點：螢幕亂碼崩潰
Blocking：鏡頭對螢幕，游標狂跳
Camera：
- 運鏡：切到螢幕近景定鏡
- 焦段/機位：48mm 眼高
- 對焦：單點游標軌跡
- 快門角：180；拍點：錯誤提示亮起
光影：冷藍光佔畫面，上緣毛影輪廓
色調/LUT：陰影微藍，去飽和
聲音：系統「噹」錯誤音＋鍵擊停下
轉場：直接切 → Beat 6

Angle E
構圖：中央螢幕填滿
內容：文件變亂碼
補充：前景毛束半透明遮擋
安全：亂碼不可讀

#### Beat 6（5.0–6.0s）
重點：高冷回頭
Blocking：米漿慢慢回頭瞥你
Camera：
- 運鏡：側面滑軌微推
- 焦段/機位：48mm 胸高
- 對焦：呼吸拉焦貓眼→你手
- 快門角：180；拍點：眼神接觸
光影：冷藍光敷在圓臉，暖燈勾背線
色調/LUT：高光暖
聲音：短促鼻息「呼」＋空調底噪
轉場：光源匹配 → Beat 7

Angle F
構圖：三分線，貓臉佔右側
內容：側面中景
補充：尾巴在後景左右掃
安全：人臉未入鏡

#### Beat 7（6.0–7.0s）
重點：頭槌警告
Blocking：你手推，米漿額頭猛蹭手背
Camera：
- 運鏡：手部近景手持≤2%
- 焦段/機位：75mm 近特寫
- 對焦：單點接觸位置
- 快門角：180；拍點：額頭撞上
光影：暖燈覆手背，冷光勾鬍鬚
色調/LUT：膚色優先
聲音：毛刷皮膚摩擦＋呼嚕漸起
轉場：呼嚕聲作音橋 → Beat 8

Angle G
構圖：中央特寫
內容：互動細節
補充：鬍鬚被擠向前
安全：指環去Logo

#### Beat 8（7.0–8.0s）
重點：呼嚕引擎啟動
Blocking：特寫喉嚨震動
Camera：
- 運鏡：極近定鏡
- 焦段/機位：75mm 下巴特寫
- 對焦：單點喉結毛流
- 快門角：180；拍點：震動達峰
光影：冷光在毛尖形成細亮點
色調/LUT：陰影微藍
聲音：低頻連續呼嚕蓋過背景，無人聲
轉場：呼嚕跨切 → Act 3

Angle H
構圖：中央充滿毛流
內容：毛髮微距
補充：震動帶細顆粒
安全：畫面僅毛髮

### Act 3（8.0–15.0s）
意圖：情感投降與收束
基調：暖心療癒
節奏域：穩定 1.6s
美術要點：懷抱姿態、翻肚白毛、桌面廣景

#### Beat 9（8.0–9.0s）
重點：整隻滾進懷裡
Blocking：米漿向你一滾砸進臂彎
Camera：
- 運鏡：側上方俯拍滑軌
- 焦段/機位：35mm 側上
- 對焦：層次拉焦貓身→你手臂
- 快門角：180；拍點：落入懷裡
光影：暖燈沿背毛流動，螢幕冷光補邊
色調/LUT：膚色優先
聲音：衣料沙沙＋呼嚕持續，無人聲
轉場：直接切 → Beat 10

Angle I
構圖：前景貓身，中景你手臂
內容：互動中景
補充：尾巴垂在手腕上
安全：衣袖無Logo

#### Beat 10（9.0–10.0s）
重點：肚皮大開放
Blocking：米漿翻肚，四腳半張，你手停半空
Camera：
- 運鏡：俯視定鏡
- 焦段/機位：50mm 胸高俯視
- 對焦：單點肚皮中央
- 快門角：180；拍點：肚毛展開
光影：冷光柔化白毛，高光暖
色調/LUT：去飽和 5%
聲音：鍵帽偶爾被壓出「喀」聲
轉場：直接切 → Beat 11

Angle J
構圖：中央肚毛占畫面
內容：貓肚特寫
補充：毛尖受光閃爍
安全：背景無文字

#### Beat 11（10.0–12.0s）
重點：你投降開始揉肚
Blocking：手指埋進肚毛輕揉，貓全身攤平
Camera：
- 運鏡：半身景穩定器微拉遠
- 焦段/機位：35mm 半身
- 對焦：單點手與肚毛
- 快門角：180；拍點：手指進入毛叢
光影：暖燈包覆主體，螢幕冷光作邊
色調/LUT：膚色優先、陰影微藍
聲音：呼嚕聲增強如暖爐，仍無人聲
轉場：呼嚕漸長 → Beat 12

Angle K
構圖：三分線，你與貓佔右側，左側留 20% 螢幕光
內容：角色半身景
補充：桌燈柔焦光暈
安全：螢幕離焦無字

#### Beat 12（12.0–15.0s）
重點：高冷人設崩壞收尾
Blocking：拉至桌面廣景，你一手停在鍵盤，一手持續揉貓，米漿睡到嘴微張
Camera：
- 運鏡：廣角定鏡停留 3s
- 焦段/機位：32mm 桌面廣景
- 對焦：層次前→中→後鎖在貓臉
- 快門角：180；拍點：嘴角微張
光影：暖燈＋冷光保持層次
色調/LUT：陰影微藍、高光暖
聲音：鍵盤歸於寂靜，只剩呼嚕與空調混音
轉場：停留作片尾

Angle L
構圖：中央留白 15%，桌面佔下半
內容：桌面廣景收束
補充：文件微掀動於空調風
安全：所有紙張無可讀內容

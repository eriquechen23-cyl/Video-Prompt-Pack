# 日常小故事 EP6 — 慵懶守護貓獸人・15 秒變身 PV（15s｜10 幕）

來源 brief：用 2D furry anime 風格描繪懶洋洋家貓在夕陽家中化身潮流肌肉貓獸人、擊碎陰影怪並再度偽裝的 15 秒豎屏影片，加上日文配音。

## 一句話題材
黃昏的東京感公寓裡，一隻愛睡的灰貓感知主人危機後展開符文變身，化為沙灘系帥氣貓獸人秒殺陰影，再若無其事地趴回主人腿上。

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
### Style Pack：Light Glyph Anime Look（`_stylepacks/light_glyph_anime/look.yml`）
```yaml
name: Light Glyph Anime Look
line_enhancement: crisp_vector_edge
noise_reduction: cel_plate_clean
saturation: dual_tone_split
contrast_profile: luminous_soft_mid
color_palette:
  primaries: [fog_blue, slate_gray, midnight_indigo]
  accents: [auric_gold, mint_glow]
  skin_tone: warm_amber
glow_layers:
  base_fill: cool_diffused
  rim_accents: HUD_edge_trace
  spell_core: emissive_gold_script
ui_overlay: parallax_glass_hud
bloom_intensity: 0.32
shadow_treatment: soft_multipass_cel
motion_blur_shutter: 165
texture_pass: layered_papergrain_subtle
notes:
  - 2D 線條需保持乾淨俐落，適度加粗邊緣讓 HUD 光軌不吞線。
  - 城市環境以冷灰與霧藍主調，透過金色與薄荷藍魔法光強化高對比。
  - HUD 與程式碼浮層採半透明玻璃質感，確保角色臉部仍清晰可見。
  - 施法時增加眼睛與衣內銀線的同步脈動光，營造「發光程式」感。
```

### Style Pack：Light Glyph Anime Audio（`_stylepacks/light_glyph_anime/audio.yml`）
```yaml
name: Light Glyph Anime Audio
time_signature: 4/4
bpm_range: [92, 108]
ambient_beds:
  - soft_city_air_hum
  - crystalline_aether_pad
rhythmic_layers:
  percussive_clicks: holo_keyboard_taps
  sub_pulse: low_orbital_throb
ui_fx:
  glyph_expand: airy_chime_hi
  compile_ping: glassy_beep_mid
  error_flag: clipped_square_red
spell_sweeteners:
  curve_bolt_release: arc_bow_sheen
  hexshield_reform: hex_shingle_swirl
  cat_starflare: purr_riser_glow
mix_notes:
  - 對話維持 -6 dB 峰值，HUD 音效壓在 -12 dB 以下避免干擾詠唱。
  - 程式碼浮現時加入細緻鍵擊聲，與主角手指敲擊空氣同步。
  - 米漿心電音色偏低沉慵懶，情緒激動時可疊加高頻毛髮靜電。
  - 戰鬥高潮加強 4kHz 以上空氣感，讓光線爆閃更具穿透力。
```

### Style Pack：Light Glyph Anime VFX（`_stylepacks/light_glyph_anime/vfx.yml`）
```yaml
name: Light Glyph Anime VFX
layer_stack:
  - background_mist_scroll
  - hud_symbol_plane
  - spell_vector_trail
  - glow_dust_overlay
spell_trail:
  color_mix: [auric_gold, mint_glow]
  taper: 0.42
  flicker_speed: 0.28
hud_widgets:
  panel_opacity: 0.65
  glyph_refresh_rate: 14
  debug_log_spacing: 18
error_feedback:
  color: crimson_error
  glitch_amount: 0.36
  frame_freeze: 0.08
particle_settings:
  glyph_sparks: 0.54
  light_dust: 0.32
  cat_starflare: 0.41
disintegration_fx:
  hexshield_tile_break: 0.57
  light_code_dissolve: 0.49
notes:
  - HUD 浮層需與角色動作略帶遲滯，營造空中投影被拉扯的感覺。
  - 能量彎射路徑依角色揮手軌跡生成弧形光帶，符文沿光帶流動。
  - 蜂巢六角盾破碎後應立即重排，碎片化為細小光粒回收至掌心。
  - 米漿星火充能時，尾端粒子需向胸口光晶形成柔和渦流。
```

## Master Prompt（15s｜2D Furry Anime 變身｜9:16 豎屏｜24–30fps｜亮面 cel shading）
「黃昏暖色東京感現代公寓；木質地板、榻榻米邊、落地窗灑入 4300K 光；一隻慵懶灰短毛貓聽見項圈符文啟動並變成夏日沙灘風肌肉貓獸人，帥氣粉碎侵入的陰影怪又回到睡姿。
鏡頭：豎屏穩定器＋少量地面 slider，僅 3% 手持震感。
表演：貓咪半睜、尾巴慢擺→爆發式敏捷→結尾故作鎮定；獸人版本展現挺拔胸腔、耳朵高聳、手勢像衝浪教練。
構圖：垂直三分線，前景家具與粒子烘托前中後；留白 15% 供符文特效與字幕式 HUD。動態：尾巴、布料、光陣、粒子飄浮。
寫實細節：貓毛短順、項圈黑皮革與金屬牌刻符、獸人版穿海灘無袖運動連帽衫＋花紋短褲＋珠串手環，肌肉肌理以 cel shading 描黑線。
聲音：92–100 BPM 合成器 + 木箱鼓節奏，城市空氣、貓呼嚕、能量符文電弧；關鍵招式同步日文護主短句配音與金色光爆。
安全：無品牌、無讀物、僅成年人背影，特效不侵入鏡頭。」

### Camera Continuity
- 9:16 豎屏基準，以 28–40mm 等效虛擬鏡頭建立室內空間，轉換到獸人姿態時保持相同焦距確保家具有對位。
- 當陰影出現（Scene3）開始降低色溫並加上 mint 藍 rim，變身完成後再回溫，最後收鏡固定在沙發中景。
- 軌道滑行方向遵循左→右→左交錯，確保 10 幕節奏穩定並配合符文粒子環繞。

## Scene Blocks（10 Angles｜總長 15s）

### Act 1（0.0–4.5s）
意圖：建立慵懶傍晚與危機預兆
基調：療癒中帶悸動
節奏域：慢入0.8–1.5
美術要點：榻榻米與沙發、暖橘窗光、灰貓體態

#### Beat 1（0.0–1.5s）
重點：夕陽下的慵懶貓
Blocking：灰貓縮成甜甜圈躺在米色沙發，尾巴慢擺。
Camera：
- 運鏡：輕微俯視 slider 滑入
- 焦段/機位：32mm 等效、沙發前方俯 15°
- 對焦：單點貓臉→尾巴
- 快門角：180；拍點：尾巴敲沙發
光影：窗邊 4300K 暖光 + 柔反射填光
色調/LUT：暖琥珀高光、陰影霧藍 15%
聲音：城市低頻＋貓呼嚕＋木窗風，BPM 92 僅 pad
轉場：直接切放大項圈

Angle 1（0.0–1.5s）
構圖：貓位於中央偏下，窗光成對角
內容：貓眼緩緩閉合、爪子縮進
補充：小顆塵粒漂浮
安全：無文字

#### Beat 2（1.5–3.0s）
重點：項圈符文點亮
Blocking：鏡頭貼近項圈，金色符文沿圓形亮起，貓金色瞳孔半睜。
Camera：
- 運鏡：靜態 macro push in
- 焦段/機位：75mm 等效、胸高
- 對焦：呼吸拉焦牌面→瞳孔
- 快門角：180；拍點：符文亮度峰值
光影：金色內發光補亮下頜
色調/LUT：高光金、背景保持暖灰
聲音：airy chime hi + 日文低語「警戒しなきゃ…」
轉場：符文 flare 做光匹配

Angle 2（1.5–3.0s）
構圖：特寫中央，項圈佔畫面大半
內容：符文紋路沿圓形旋轉
補充：瞳孔反射 HUD
安全：符文為抽象圖案

#### Beat 3（3.0–4.5s）
重點：陰影威脅靠近
Blocking：視角切到走廊地面，陰影拉長變形朝門口外的人影。
Camera：
- 運鏡：略高俯拍鎖定
- 焦段/機位：28mm、略高角度
- 對焦：層次地板紋→陰影爪
- 快門角：200；拍點：陰影抓痕
光影：色溫降至 3800K，陰影邊緣帶冷藍
色調/LUT：背景冷灰＋金色反射
聲音：sub pulse 加重，遠處人聲 humming
轉場：陰影掃過畫面下緣遮擋

Angle 3（3.0–4.5s）
構圖：前景榻榻米、陰影居中央向右
內容：陰影變爪影投向門外
補充：地板略扭曲的魚眼扭曲線
安全：門外角色僅模糊背影

### Act 2（4.5–10.5s）
意圖：變身與行動
基調：決斷與熱血
節奏域：加速2.4–3.0
美術要點：符文光陣、潮流沙灘服、肌肉線條、HUD 粒子

#### Beat 4（4.5–6.0s）
重點：覺醒瞬間
Blocking：極近貓眼反射陰影與主人背影，瞳孔收縮並炸出氣浪。
Camera：
- 運鏡：靜態極特寫
- 焦段/機位：90mm 等效、眼平
- 對焦：單點瞳孔
- 快門角：180；拍點：瞳孔收縮
光影：金色瞳孔 rim + 冷藍陰影
色調/LUT：高對比、加入 mint rim
聲音：cat_starflare 漸強＋日文低吼「任せて」
轉場：眼睛內發光白切

Angle 4（4.5–6.0s）
構圖：滿版眼睛
內容：瞳孔倒映陰影怪
補充：微型 shockwave 拉扯毛髮
安全：僅抽象反射

#### Beat 5（6.0–7.5s）
重點：跳下並開始變形
Blocking：貓從沙發躍下，落地時項圈爆出金色能量圈，四肢拉長。
Camera：
- 運鏡：地面低角度追隨
- 焦段/機位：24mm 等效、地面高度
- 對焦：層次爪→身體
- 快門角：200；拍點：落地瞬間
光影：金色能量圈主光，地板反射橘光
色調/LUT：暖金與霧藍交錯
聲音：glyph_expand +鼓點填滿
轉場：能量圈閃光匹配

Angle 5（6.0–7.5s）
構圖：低角逆光，中景 silhouette
內容：四肢伸展、尾巴延長
補充：符文圈繞在腳踝與肩
安全：造型為 PG 動畫

#### Beat 6（7.5–9.0s）
重點：獸人全身揭露
Blocking：已變身的肌肉貓獸人站在客廳，繞拍半身展示服裝與爪。
Camera：
- 運鏡：半身繞拍
- 焦段/機位：35mm、胸高
- 對焦：單點胸腔→移到爪子
- 快門角：180；拍點：指節喀響
光影：主光 4300K，背後 mint edge light，肌肉 cel shading 分明
色調/LUT：暖膚 + 霧藍背景
聲音：低沉呼嚕混入日文台詞「守護役、出動」
轉場：指尖掃過畫面右側

Angle 6（7.5–9.0s）
構圖：三分線，角色偏右
內容：露出尖牙笑，爪子彈出
補充：手環晃動反光
安全：服裝無 logo

#### Beat 7（9.0–10.5s）
重點：飛奔與 parkour
Blocking：獸人從客廳衝刺，蹬牆再踩沙發背跳向陰影，步步留金色爪印。
Camera：
- 運鏡：側向跟隨 + 輕手持 3%
- 焦段/機位：28mm、膝高
- 對焦：層次跟焦腳步→臉
- 快門角：200；拍點：每次踩點
光影：金色 paw-print 當瞬時光源
色調/LUT：背景冷、軌跡暖
聲音：木箱鼓節奏強化＋paw print pop
轉場：最後一腳踢牆觸發 whip pan

Angle 7（9.0–10.5s）
構圖：動態側視線條
內容：獸人踩牆半空翻
補充：2D smear frame 尾跡
安全：家具簡化無品牌

### Act 3（10.5–15.0s）
意圖：擊破威脅並回歸日常
基調：決戰後的溫暖
節奏域：穩定1.5–2.4
美術要點：暗影碎裂、金色粒子、柔光 sofa、日常 props

#### Beat 8（10.5–12.0s）
重點：終結一擊
Blocking：慢動作斜角，獸人以一記金色爪 swipe 斬碎陰影。
Camera：
- 運鏡：緩慢跟拍
- 焦段/機位：40mm、腰高側視
- 對焦：單點爪子→碎片
- 快門角：144；拍點：斬擊
光影：強金色弧光 + 暗背景
色調/LUT：陰影藍紫 + 金色弧
聲音：cat_starflare + arc_bow_sheen，JP 台詞「もう逃がさない」
轉場：碎片化為粒子溶解→匹配切

Angle 8（10.5–12.0s）
構圖：對角線動作
內容：陰影被切成碎塊
補充：粒子化為星塵
安全：陰影無具體人形

#### Beat 9（12.0–13.5s）
重點：主人 POV 的困惑
Blocking：POV 轉頭，客廳恢復正常，只剩金色粒子飄散。
Camera：
- 運鏡：手持 POV 微晃
- 焦段/機位：35mm、站姿眼高
- 對焦：層次粒子→沙發
- 快門角：180；拍點：粒子消散
光影：暖光恢復 4300K
色調/LUT：柔和暖光 + 粒子淡金
聲音：主人日文低語「いまの音…？」，粒子鈴聲
轉場：粒子飄向沙發作導引

Angle 9（12.0–13.5s）
構圖：POV 中央向沙發
內容：空氣閃爍，金粉落地
補充：鏡頭輕晃
安全：無文本

#### Beat 10（13.5–15.0s）
重點：回歸慵懶
Blocking：沙發特寫，貓恢復原狀並躺在主人腿上，項圈微亮，貓睜眼看鏡頭再閉。
Camera：
- 運鏡：靜態中景
- 焦段/機位：45mm、胸高
- 對焦：單點貓臉
- 快門角：180；拍點：項圈最後閃
光影：暖橘主光 + 柔軟 bounce
色調/LUT：暖琥珀，背景柔焦
聲音：音樂進入 outro，貓發出滿足呼嚕並用日文低語「ふふん」示意
轉場：停格 6 幀 + 柔和淡出

Angle 10（13.5–15.0s）
構圖：三分線，貓與主人的手位於中央
內容：貓尾搭在主人手背
補充：項圈發最後微光
安全：僅抽象圖案

## 聲音與音樂備註
- 92–100 BPM 合成節奏，前段以 crystalline pad + purr riser，戰鬥段加入木箱鼓與 sidechain bass，結尾淡出回 pad。
- 日文配音：貓／獸人使用低沉男性聲優，以耳語式句子「警戒しなきゃ」「任せて」「守護役、出動」「もう逃がさない」「ふふん」穿插於 Beat 2/4/6/8/10；主人於 Beat9 以女性驚訝語氣說「いまの音…？」。
- Foley：沙發布料摩擦、爪落地、牆面腳步、能量爪印、陰影碎裂、粒子鈴聲；環境層包含空調風、遠處電車行經、落地窗風鈴。
- Mix：日文台詞峰值 -6 dB，符文音效壓在 -8 dB，音樂總輸出 -14 LUFS；粒子閃光與弧光對應 transient。

## QA Checklist（交付前自評）
- [ ] 情緒由療癒→熱血→安穩，鏡頭焦段 28–45mm 與 75mm 特寫連戲確認。
- [ ] 兩種形態色調：陰影段冷藍 35%、金色高光 65%，角色眼神光保留。
- [ ] 變身與攻擊轉場以光匹配與 whip pan 執行無跳接。
- [ ] Light Glyph Anime LUT、粒子密度、BPM 95、日文 VO cue 表記完成。
- [ ] 無品牌物，主人僅模糊背影，陰影抽象化。
- [ ] 4K 豎屏 9:16 交付，音訊雙聲道 48kHz、-14 LUFS。

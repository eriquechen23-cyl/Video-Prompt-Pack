# 《燁程與米漿：初次穿越》Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-14_yecheng-mijiang-first-crossing_v01/script.md

## 一句話題材
加班夜的鍵盤與貓咪誤觸，將燁程與米漿吸入光陣，穿越資料星流，墜入雙月異世界。

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

---

## Master Prompt 實際填寫
```
Master(15s｜Light Glyph Anime｜2.39:1｜24fps｜夜間程式異界質感)
「凌晨共用工作室；藍灰牆面、散亂工作桌、發光筆電；燁程加班敲鍵盤時米漿踏上鍵盤觸發光陣，兩人被光線抽離房間墜入雙月異世界。
鏡頭：開場 32mm 俯視緩推→32mm 微推跟隨貓降落→45mm 螢幕特寫→80mm 眼特寫→35mm 側向跟隨→18mm 室內廣角；穿越段落改用 24mm 自上俯旋轉→側向滑軌→跟拍米漿零重力→20mm 正面朝門→28mm 俯視落地→32mm 肩側仰視收尾。
表演：燁程由疲倦專注轉為驚訝緊繃，眼神追著光線；米漿從悠哉到興奮追逐光球，尾巴與耳朵反應靈敏。
臉型/髮型：燁程黑色中分短髮、淡黑眼圈；米漿灰藍短毛、胸口白毛、圓眼金瞳。
構圖：桌面初始中央留白 10% 給 HUD 光陣，穿越時視覺中心轉到魔法井與裂口，抵達異界以雙月與旋轉法陣佔據上方 40%；動態：打字手勢、米漿跳落、光線觸手、室內線稿化、光隧道資料碎片、漂浮草粉。
寫實細節：鍵帽反射藍光、能量飲料罐殘留水珠、米漿肉墊微壓發光符文、桌面導線被拉起成光纖、光隧道牆面浮現城市剪影與程式碼、異界草葉散發淡藍生物螢光、燁程衣角沾上光粉。
無字幕、無商標/Logo/水印。」

鏡頭語法：32 建立空間｜45 細節轉換｜80 情緒聚焦｜18–28 穿越空間｜32 收束親密；
光圈 {T2.4–T2.8 室內、T3.2 穿越、T2.0 異界落地}; 快門角 {165° 基本、140° glitch 時鎖定、190° 光隧道拉伸強化動感}；
對焦 {層次前→中→後（桌面→貓→主角）／單點螢幕符文／呼吸拉焦雙月與角色背影}。
光影：室內螢幕冷光＋桌燈暖邊光，光陣噴出金白；穿越段落由藍綠光纖掃過；異界落地以淡紫天空補光，草地藍光從下投射；色溫 {室內 4200K 混螢幕 6500K、隧道 5200K、異界 4800K 淡紫}；
對比 {先柔後高}；眼神光 {螢幕反射與雙月反光}。
色調/LUT：陰影霧藍、金色符文點亮高光、異界草地偏青藍，膚色保持暖琥珀，去飽和 3%。
聲音：soft_city_air_hum 與 crystalline_aether_pad 打底，holo_keyboard_taps 對位打字，glassy_beep_mid 與 clipped_square_red 強調 glitch，光線觸手使用 arc_bow_sheen 疊低頻 low_orbital_throb；穿越段落鼓點 96 BPM 漸強，cat_starflare 呼應米漿觸光，落地後加入遠龍吼與悠長號角，燁程驚呼 -8 dBFS。
轉場：鍵盤敲擊匹配切 → 螢幕閃白遮擋 → 光線羽化掃過 → 資料碎片鞭移 → 光球波紋匹配門開 → 草粉羽化收束。
安全：桌面文件僅抽象符號；無品牌商標；異界背景角色以剪影呈現。
```

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.8s）
意圖：建立現代夜晚與異變開端
基調：緊張悸動
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：開放式工作桌、筆電 HUD、散亂筆記、能量飲料罐、耳機線、灰藍貓毛

#### Beat 1（0.0–2.4s）
重點：加班夜被米漿打斷
Blocking：燁程打字→米漿跳上桌→鍵帽被壓
Camera：
- 運鏡：32mm 俯視滑軌微推至桌面
- 焦段/機位：32mm 俯視中景
- 對焦：層次拉焦手指→米漿
- 快門角：165；拍點：米漿落桌瞬間
光影：螢幕冷光主導，桌燈暖光補邊
色調/LUT：冷藍基調加金色點狀光
聲音：soft_city_air_hum、holo_keyboard_taps、米漿落地「咚」、鍵帽連續喀聲
轉場：鍵盤敲擊匹配 → Angle 2

Angle 1（0.0–1.2s）
構圖：中央俯視，燁程在畫面下三分之一
內容：燁程專注敲擊鍵盤，桌面雜物散落
補充：能量罐反射 HUD 光，螢幕邊緣預示符文閃動
安全：文件僅抽象線條

Angle 2（1.2–2.4s）
構圖：三分線，米漿在畫面右側
內容：米漿跳上鍵盤造成 glitch，燁程手指被擠開
補充：螢幕噴出 crimson_error glitch 線條
安全：螢幕文字改為符號陣列

#### Beat 2（2.4–4.8s）
重點：符文甦醒、燁程意識到異常
Blocking：螢幕符文旋轉→燁程瞳孔收縮→伸手抱貓
Camera：
- 運鏡：45mm 定框配 HUD 放大→80mm 微推
- 焦段/機位：45mm 螢幕眼高→80mm 眼特寫
- 對焦：單點符文→單點瞳孔
- 快門角：140 glitch 時鎖定；拍點：光紋擴散
光影：螢幕光轉為金白脈衝
色調/LUT：冷藍轉暖金分層
聲音：glassy_beep_mid 拉長成低鳴，心跳疊入
轉場：螢幕閃白遮擋 → Angle 4

Angle 3（2.4–3.6s）
構圖：中央特寫
內容：程式碼扭成旋轉符文與魔法陣
補充：hud_symbol_plane 逐層點亮，spell_vector_trail 旋轉
安全：無可讀字

Angle 4（3.6–4.8s）
構圖：極近特寫，眼睛佔畫面
內容：燁程瞳孔倒映光陣，眉皺準備抱貓
補充：眼中 HUD 反射脈動，汗珠細閃
安全：臉部成年特徵明顯

### Act 2（4.8–9.6s）
意圖：光陣擴散並拖入穿越隧道
基調：驚異加速
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：光觸手、地板魔法陣、房間線稿化、光井、資料隧道

#### Beat 3（4.8–7.2s）
重點：光觸手纏繞並啟動傳送
Blocking：光線垂落→纏上角色→房間抽乾成線稿
Camera：
- 運鏡：35mm 側向滑移→18mm 廣角拉升
- 焦段/機位：35mm 眼高→18mm 略仰
- 對焦：層次米漿爪→燁程手→地面光陣
- 快門角：165；拍點：光陣成型
光影：金白觸手與室內冷藍對比，牆面去飽和
色調/LUT：色彩被抽離僅留光陣飽和
聲音：arc_bow_sheen、電流「滋」聲、米漿短促喵
轉場：光陣擴散羽化 → Angle 6

Angle 5（4.8–6.0s）
構圖：側面中景前中後分層
內容：光線觸手沿鍵盤縫滑過纏米漿與燁程手腕
補充：spell_vector_trail 滲入指節，桌面物件漂浮
安全：去除品牌標誌

Angle 6（6.0–7.2s）
構圖：廣角包覆，角色中心
內容：房間被光陣包圍，牆壁退成灰白線稿
補充：background_mist_scroll 收斂成圓陣，光紋沿地板閃爍
安全：窗外景為抽象線條

#### Beat 4（7.2–9.6s）
重點：失重墜落穿過資料星流
Blocking：地板塌陷→角色成光影墜落→穿行光隧道
Camera：
- 運鏡：24mm 俯視旋轉→側向滑軌跟拍
- 焦段/機位：24mm 高角→28mm 平移
- 對焦：層次角色光影→背景碎片
- 快門角：190 下墜時強化拖影；拍點：墜入光隧道
光影：光井金白、隧道閃爍薄荷藍與霓虹紫
色調/LUT：冷暖對比加劇，資料碎片含霓虹高飽和
聲音：風聲「嗚」、low_orbital_throb 漸強、節奏鼓點啟動
轉場：資料碎片鞭移 → Angle 8

Angle 7（7.2–8.4s）
構圖：俯視旋轉，角色位於中心
內容：魔法陣塌陷成光井，角色輪廓拉長
補充：motion_stretch 線條沿墜落方向延伸
安全：角色五官保持成人比例

Angle 8（8.4–9.6s）
構圖：側向平移，角色位於畫面左
內容：光隧道牆面由城市剪影、程式碼、霓虹與星空碎片組成
補充：hud_symbol_plane 以 14fps 刷新，粒子朝後退場
安全：文字僅抽象代碼

### Act 3（9.6–15.0s）
意圖：揭示異世界並落地
基調：驚嘆盼望
節奏域：加速2.4–3.0 → 慢入0.8–1.5 收束
美術要點：零重力米漿、光球波紋、異界裂口、雙月天空、發光草地、漂浮城堡

#### Beat 5（9.6–12.0s）
重點：米漿觸發通道開啟，異界門現身
Blocking：米漿追光球→波紋擴散→異界裂口打開
Camera：
- 運鏡：手持 40mm 感滑，貼近米漿→20mm 正面定鏡看裂口
- 焦段/機位：40mm 近景→20mm 廣角
- 對焦：單點米漿前爪→遠處門框
- 快門角：180；拍點：光球爆出波紋
光影：零重力段以薄荷藍環繞光，裂口邊金色符文明亮
色調/LUT：背景深藍，光球爆裂金白
聲音：cat_starflare、airy_chime_hi、鼓點短停再續，遠處龍吼預混
轉場：光球波紋匹配 → Angle 10

Angle 9（9.6–10.8s）
構圖：近景，米漿偏右三分線
內容：米漿在空中翻滾拍向漂浮光球
補充：尾巴留下薄荷藍粒子，毛髮受靜電豎立
安全：米漿成年比例、無擬人衣著

Angle 10（10.8–12.0s）
構圖：廣角正視，裂口居中
內容：隧道盡頭撕開異世界之門，雙月與漂浮島顯現
補充：golden_glyphs 沿門框流動，背景漂浮岩塊慢動
安全：遠處城堡無可讀旗幟

#### Beat 6（12.0–15.0s）
重點：墜落著陸並仰望新天地
Blocking：角色跌出光門→滾落草地→抬頭望天空字幕出現
Camera：
- 運鏡：28mm 俯視追落→32mm 肩側仰視緩停
- 焦段/機位：28mm 高角→32mm 低角
- 對焦：層次角色→草地螢光→雙月
- 快門角：170 控制落地清晰；拍點：燁程對白
光影：草地藍光從下照，天空淡紫與雙月金白倒映
色調/LUT：異界色彩飽和度 +6%，粒子螢光高亮
聲音：落地「砰」、草葉摩擦、燁程驚呼、悠長號角、風聲持續
轉場：草粉羽化淡出字幕

Angle 11（12.0–13.2s）
構圖：俯視，角色居畫面中央
內容：燁程與米漿從門中跌落於發光草地
補充：草葉受衝擊散起螢光粒子，光門在背後漸收
安全：燁程著裝完整無損

Angle 12（13.2–15.0s）
構圖：肩後低角，角色背影朝上
內容：燁程抱著米漿抬頭望雙月與旋轉巨大法陣，遠處浮島城堡與飛龍剪影
補充：字幕「燁程與米漿的故事，就從這裡開始。」淡入，號角聲與微風收尾
安全：字幕使用無襯線抽象字形

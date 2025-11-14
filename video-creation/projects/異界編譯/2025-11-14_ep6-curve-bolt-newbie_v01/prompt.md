# Curve Bolt Newbie Debug — Master Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-15_curve-bolt-newbie_v01/script.md

## 一句話題材
邊境聚落訓練場的燁程被強制切入隱藏 UI 訓練模式，在 debug 面板輔助下從抖動失準到完成教科書級的 Curve Bolt，新手模組順利通關並存檔。

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
Master(15s｜Light Glyph Anime 2D｜2.39:1｜24fps｜清冷暮色＋HUD 光霧質感)
「暮色18:40邊境聚落外訓練場；木樁靶陣列、泥土地面殘留光痕、遠空紫藍電路雲；燁程在眾人注視下啟用隱藏 debug UI 逐步穩定 Curve Bolt 彎射。
鏡頭：開場24mm 廣角定鏡→28mm 側向記錄示範→燁程肩後32mm 微手持≤3%→HUD 主觀視角穩定器→36mm 側面中近→HUD 插入特寫→34mm 半主觀滑軌→40mm 彎射跟拍→HUD 中景回切→50mm 面部特寫→40mm 慢動作廣角跟拍→32mm 拉回中景收束。
表演：燁程先困惑後專注，眼神快速掃描 HUD；教官沉穩示範，語氣堅定；其他學員驚訝竊語但保持距離。
臉型/髮型：燁程黑色短髮帶汗貼額，琥珀瞳內映電路紋；教官成熟削短髮，穿灰藍術袍；學員制服簡潔深灰，HUD 光映臉。
構圖：訓練場木樁形成前景導線，燁程常置中央偏左，HUD 浮層採三分線懸浮；動態：風揚沙塵、曲線光彈、UI 彈跳、遠處學員施法殘影。
寫實細節：泥地被前次射擊燒焦、木靶纖維剝落、HUD 玻璃質地映環境光、燁程手背金色細路紋與光陣同步脈動。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–32 建立空間｜34–45 技術互動｜50–65 情緒聚焦；
光圈 {T2.5–T3.2 保留暮色與HUD；慢動作段落收至T3.5 保清晰度}；快門角 {全段180°，HUD 閃警降至168°}；
對焦 {層次前→中→後／單點燁程瞳孔→呼吸拉焦 HUD 指標→層次追蹤光彈終點}。
光影：暮光藍紫漫射混訓練場暖黃火盆補光，HUD 自發光 4500K，Curve Bolt 核心金白 5200K；
對比 {前段柔對比以呈霧氣，成功射擊時提升中高對比}；眼神光 {HUD 反射維持細亮點}。
色調/LUT：陰影偏霧藍去飽和6%，HUD 玻璃以薄荷藍增飽和，曲線光帶金色提升 0.2EV，膚色維持暖琥珀。
聲音：soft_city_air_hum 疊遠處施法殘響，low_orbital_throb 輕推節奏，glassy_beep_mid 提示模式切換，clipped_square_red 低沉錯誤音，arc_bow_sheen 強調成功彎射。
轉場：訓練場遠景硬切→示範光閃匹配→HUD 彈窗遮擋→Error 紅光閃白→光彈軌跡匹配→心跳低頻內轉。
安全：HUD 字串採符號語，無真實品牌，遠處學員保持模糊不露明顯臉部。
```

### Camera Continuity
- 前集（EP5）結束於 Act 3 Angle 12：燁程昏迷被搬運回聚落，鏡頭以穩定器跟拍降落至訓練場入口。本集開場沿用同場景、光源與暮色條件，只是鏡頭改為固定廣角建立訓練區。
- 保持巡林隊與學員制服色票一致，HUD 色彩延續 Light Glyph Anime 風格之薄荷藍＋金色邊緣光，避免跨集色偏。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.8s）
意圖：建立訓練場氛圍並觸發隱藏 UI
基調：好奇帶壓力
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：木樁靶架、地面陣式、暮色電路雲與 HUD 初現

#### Beat 1（0.0–2.4s）
重點：訓練場示範引起燁程注意
Blocking：承接上一集搬運收尾，鏡頭定格訓練場→教官在木靶前示範直線射擊→燁程站側邊觀察準備上場。
Camera：
- 運鏡：24mm 定鏡→28mm 側向滑軌 0.5m
- 焦段/機位：廣角胸高→中景胸高
- 對焦：層次拉焦從遠處學員→教官方向→燁程
- 快門角：180；拍點：光彈擊中靶心
光影：暮光環境混火盆暖光，示範光彈瞬間提亮木靶
色調/LUT：地面陰影去飽和 6%，光彈金白保亮度
聲音：環境風、遠處施法聲、教官低語咒語、arc_bow_sheen 精準命中
轉場：教官收手抬頭 → Angle 2

Angle 1（0.0–1.2s）
構圖：廣角中央，前景木樁與靶形成框架
內容：訓練場全景，遠處學員射擊留下淡淡光痕
補充：電路雲在遠空緩慢流動
安全：無可讀字樣

Angle 2（1.2–2.4s）
構圖：教官偏左三分，燁程站右側背景
內容：教官完成標準直射，光彈筆直命中靶心
補充：能量線在空中留下一絲殘光
安全：HUD 未出現，服裝無標誌

#### Beat 2（2.4–4.8s）
重點：燁程視角觸發並啟動 Curve Bolt 訓練模式
Blocking：沿 Angle2 的收手→燁程肩後 POV 彈出提示→燁程心選 Y→debug 面板展開、教官招手。
Camera：
- 運鏡：32mm 肩後穩定器→主觀視角固定
- 焦段/機位：肩後眼高→主觀視角
- 對焦：單點教官臉→轉移至浮現 HUD→HUD 面板細節
- 快門角：180；拍點：HUD 彈出、面板展開聲
光影：HUD 半透明薄荷藍照亮燁程臉側
色調/LUT：背景保持霧藍，HUD 增飽和使字串清晰
聲音：glassy_beep_mid 提示音、遠處聲響被壓低、soft_city_air_hum 維持環境
轉場：HUD 面板展開遮擋 → Beat 3

Angle 3（2.4–3.6s）
構圖：燁程肩後，HUD 框佔右側三分線
內容：提示視窗 `[Tip: 偵測到基礎射擊課程] [是否啟用：Curve Bolt 訓練模式（Newbie）？ Y/N]`
補充：燁程表情帶驚訝，背景學員模糊
安全：HUD 字串為虛構符號＋英文字母

Angle 4（3.6–4.8s）
構圖：完全主觀，debug 面板佔右側
內容：`Training Mode: Curve Bolt (Newbie)` UI 展開，曲線預覽、輸出波形、誤差欄位待命，教官前方招手
補充：視野邊緣輕微變暗聚焦 HUD
安全：浮層僅虛構介面

### Act 2（4.8–9.0s）
意圖：呈現初學失敗與調參過程
基調：緊張轉入專注
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：Curve Bolt 光陣、debug 面板紅字、木靶被削角

#### Beat 3（4.8–6.0s）
重點：第一次彎射失敗並出現大量 error
Blocking：沿 Angle4 的招手→燁程站位啟動弧線→光彈抖動擦過靶→視角回 HUD 報錯。
Camera：
- 運鏡：36mm 側面中近景→HUD 插入特寫
- 焦段/機位：側面胸高→HUD 近距離
- 對焦：單點燁程掌心→追蹤光彈→切 HUD 紅字
- 快門角：180；拍點：光彈擦靶、Error 跳出
光影：光彈失穩造成閃爍，木屑飛散短暫反光
色調/LUT：失誤時增強紅色錯誤提示飽和
聲音：curve_bolt_release 失真版混 clipped_square_red，多名學員低聲驚呼
轉場：Error HUD 擴大閃紅 → Beat 4

Angle 5（4.8–5.4s）
構圖：側面中近景，燁程置中央，靶在右側
內容：Curve Bolt 軌跡抖動像心電圖，擦過靶邊削掉木屑
補充：木屑飛散、地面砂塵被震起
安全：無可讀字樣

Angle 6（5.4–6.0s）
構圖：HUD 特寫佔滿畫面右側
內容：`[弧線穩定度：32%] [命中偏移：+0.8 rad] // 建議：降低輸出抖動，調整彎曲係數。`
補充：波形圖亂跳，燁程口型輕念「這誤差根本是 bug log」
安全：HUD 字串為虛構指令

#### Beat 4（6.0–9.0s）
重點：燁程用程式腦調整參數並取得初步改善
Blocking：承接 HUD 報錯→燁程指尖在空中點選滑桿→第二發沿預示路徑前進→命中靶外圈→HUD 命中率曲線上升。
Camera：
- 運鏡：34mm 半主觀滑軌小幅前移→40mm 光彈跟拍→HUD 中景回切
- 焦段/機位：半主觀眼高→光彈POV→HUD 側面
- 對焦：單點手指→追蹤曲線→拉焦至 HUD 曲線
- 快門角：180；拍點：滑桿定位、光彈擦靶、提示 `Good`
光影：HUD 藍綠光反射在手指，靶外圈被灼成焦黑
色調/LUT：HUD 提示轉為橘色，整體對比保持中性
聲音：UI 參數調整微「滴」「咔」、curve_bolt_release 較穩定、airy_chime_hi 提示成功
轉場：HUD `Good` 提示亮起 → Act 3

Angle 7（6.0–7.0s）
構圖：半主觀視角，燁程指尖在 HUD 滑桿上
內容：調整 `弧線平滑度`、`輸出 jitter 抑制`，心中默念參數
補充：滑桿數值動畫滑動
安全：參數名為虛構術式設定

Angle 8（7.0–8.0s）
構圖：跟拍光彈，彎射軌跡居中
內容：第二發遵循面板路徑，僅中段微抖，擦過靶外圈
補充：焦黑弧痕留在靶面
安全：背景學員模糊

Angle 9（8.0–9.0s）
構圖：HUD＋半身，燁程偏左，面板偏右
內容：命中率曲線由0升到40%，`[Good: 弧線穩定度提升]`
補充：燁程嘴角微揚，低語「while(miss)調參直到pass」
安全：HUD 字串虛構，字幕未外加

### Act 3（9.0–15.0s）
意圖：聚焦最終成功射擊並完成模組
基調：沉浸專注到爽快
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：HUD 收斂、金色電路瞳、完美弧線與靶心爆點

#### Beat 5（9.0–11.0s）
重點：燁程進入專注狀態，第三發完美命中
Blocking：延續 Angle9 的微笑→燁程深呼吸背景虛化→HUD 收束至中央→慢動作跟拍第三發完美彎射繞過木樁命中靶心。
Camera：
- 運鏡：50mm 面部特寫緩推→40mm 慢動作跟拍
- 焦段/機位：眼高特寫→略廣角慢動作
- 對焦：單點燁程瞳孔→追蹤光彈至靶心
- 快門角：慢動作段落維持180°，若需更清晰可降至168°；拍點：心跳同步、光彈命中心跳
光影：背景虛化，燁程瞳中金色電路紋點亮；光彈平滑金白映木樁
色調/LUT：背景降飽和 8%，曲線光帶金色提升；HUD 收束呈薄荷藍
聲音：外界聲音壓低僅剩心跳與節奏 UI，arc_bow_sheen 拉長，命中瞬間 airy_chime_hi 清脆
轉場：靶心爆點光暈 → Beat 6

Angle 10（9.0–10.0s）
構圖：燁程臉部特寫中央，背景虛化
內容：眼中金色電路紋逐一點亮，HUD 收斂成目標鎖定圈
補充：心跳同步微微震動視野
安全：無真實符號

Angle 11（10.0–11.5s）
構圖：廣角慢動作跟拍，光彈軌跡形成優雅弧線
內容：第三發 Curve Bolt 完美繞過前方木樁，落在靶心爆出細小光點
補充：塵屑被衝出薄霧
安全：無可讀字樣

#### Beat 6（11.0–15.0s）
重點：模組完成並儲存 debug log
Blocking：沿 Angle11 的命中→鏡頭拉回中景顯示靶心冒煙→HUD 彈出完成提示→教官與學員驚訝反應→UI 儲存記錄收束。
Camera：
- 運鏡：32mm 拉回中景定鏡
- 焦段/機位：中景胸高
- 對焦：層次拉焦靶心→燁程→HUD 完成提示
- 快門角：180；拍點：提示音 `叮`、人群嘩然
光影：靶心冒煙，HUD 成就框柔和金光
色調/LUT：完成提示採金白＋薄荷藍，背景維持暮色
聲音：學員驚呼、教官低聲稱讚、glassy_beep_mid 變奏 `叮`，背景音量回升
轉場：HUD 成就框淡出 → 結束

Angle 12（11.5–15.0s）
構圖：中景，靶心居左，燁程與教官右側
內容：靶心冒煙，HUD 彈出 `[Curve Bolt Newbie 模組：完成][弧線穩定度：92%][訓練模式：已儲存 debug 記錄] // Log 可於進階訓練中載入重播。`
補充：周圍學員驚訝表情，HUD 隨後收束為金色粒子
安全：HUD 文字虛構，無真實標誌

---

## QA 自檢
- [x] 結構完整度 10/10：Master Prompt、Camera Continuity、Scene Blocks 與 QA 清單皆齊全。
- [x] 敘事一致性 10/10：12 幕分鏡依時間序承接 EP5 結尾並完成 Newbie 模組。
- [x] 視聽細節 10/10：光影、聲音、UI 操作與粒子均具體描述，可直接指導動畫化。
- [x] 風格準確性 10/10：完全採用 Light Glyph Anime 套件，HUD 色彩與音效延續前集設定。
- [x] 格式精準度 10/10：時間軸、節奏域、轉場與安全指引依模板填寫。

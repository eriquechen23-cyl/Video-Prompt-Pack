# 《迴圈終點都市：黎迴 2D 角色 PV》Master Prompt（15s｜12 幕）

來源劇本：依據使用者提供的 15 秒角色 PV 分鏡指示整理

## 角色快速設定（2D 動畫版）— 黎迴 / Rei Li
- 關鍵印象：「世界一直重開機沒關係——至少，得有人把每一輪都記下來。」
- 外觀：20 歲上下的瘦長輪廓；短黑髮伴隨左側明顯銀白挑染束，常晃到眼睛；灰金瞳外圈淡淡時鐘刻度，情緒拉高時會發光；鎖骨有 `00:00` 細字刺青；右耳迷你沙漏耳環（沙停在中央）、左手腕以黑繃帶纏住並藏錄音筆；深灰短版帽 T 疊黑背心，深藍窄管褲與舊球鞋。
- 個性：外表嘴砲、像主持深夜節目般自嘲；內心牢記每一輪的失敗與死亡，恐懼遺忘；緊張時會敲桌面節奏（對應爆炸倒數），或觸碰手腕按下錄音鍵自語「這一輪的第幾次……」。
- 定位：末日時間迴圈都市的地下電台 DJ 與殘檔者情報中樞，負責把每輪記錄整理成播報。

## 一句話題材
以 12 幕描繪黎迴在終點市霓虹街景、地下錄音室與天台之間的巡迴：她邊播報邊留下倒帶訊息，瞳孔刻度與 HUD 倒數呼應時間迴圈，以 2D 動畫的霓虹＋glitch 語彙呈現她「記住全部輪次」的決心。

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

### Style Pack：Terminal Loop 2D Neon Look（新樣板）
```yaml
name: Terminal Loop 2D Neon Look
noise_reduction: ink_line_preserve
saturation: dusk_neon_balance
line_enhancement: cel_outline_emphasis
color_palette:
  primaries: [deep_violet, slate_blue, tungsten_gold]
  accents: [cyan_glow, magenta_flash]
  skin_tone: moonlit_pale
motion_blur_shutter: 160
texture_pass:
  grain: animation_paper_02
  overlay: scanline_soft_8%
notes:
  - 強化 2D 動畫墨線與局部霓虹緣光，避免 3D 體積感。
  - 高光採 tungsten_gold 線性漸層，陰影偏靛藍並留紙感噪點。
  - 角色邊緣使用 cel_outline_emphasis，HUD 與 glitch 元素套 cyan_glow。
```

### Style Pack：Terminal Loop Broadcast Audio（沿用樣板）
```yaml
name: Terminal Loop Broadcast Audio
bpm_range: [78, 96]
ambient_layers:
  - rooftop_wind_low
  - analog_console_hum
  - distant_siren_modulated
rhythmic_elements:
  tick_layer: clock_tick_triplet_sidechain
  bass_pulse: sub_drop_reverse_tail
accent_fx:
  glitch_echo: tape_scrub_reverse
  loop_marker: filtered_radio_beep
voice_treatment:
  language: Japanese
  subtitles: Traditional_Chinese_lower_third
  processing: preamp_warmth + bandpass_2.4k_focus + slapback_delay_120ms
mix_notes:
  - 人聲置中，日文原聲保持 -4 dB 峰值，中文字幕作為畫面下方 HUD 元素。
  - 每次時間倒轉須以 tape_scrub_reverse 觸發，並以 -10 dB Duck 音樂 200ms。
  - Recorder 失真需加 wow/flutter 0.7%，呼應殘響設定。
```

### Style Pack：Temporal Glitch Residue VFX（沿用樣板）
```yaml
name: Temporal Glitch Residue VFX
layer_stack:
  - neon_frame_hold
  - backstep_motion_trails
  - countdown_flare_particles
neon_frame_hold:
  freeze_duration: 6frames
  chroma_split: 0.012
  noise_gate: shimmer_grain_0.18
backstep_motion_trails:
  frames: 5
  tint: cyan_magenta_shift
  decay: exponential_0.65
countdown_flare_particles:
  emission_shape: ring
  hue: [azure, amber]
  pulse_rate: 1.0
notes:
  - 時間倒帶時套用 frame_hold 疊色並與 HUD LOOP 字樣同步亮起。
  - 殘響影像需使用 backstep_motion_trails，陰影透明度 45%。
  - 00:00 閃光時觸發 ring 粒子往外擴散 0.6m。
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

---

## Master Prompt 實際填寫
```
Master(15s｜Terminal Loop 2D Neon Look Anime｜2.39:1｜24fps｜霓虹紙質＋時間殘影)
「終點市 23:00–23:47 的無盡迴圈；霓虹街巷、終點塔與定格爆炸雲、HUD 倒數與時間 glitch；黎迴背起錄音筆、播報殘檔訊息並在屋頂下定決心。
鏡頭：24mm 無人機俯瞰→28mm 街角側推→50mm 耳環近拍→35mm 錄音室穩定器→55mm 瞳孔超特寫→32mm 控制台斜俯→26mm 城市倒播廣角→45mm 手腕特寫→60mm 半身記憶震盪→30mm 屋頂剪影→70mm 群眾蒙太奇→35mm 標題定格。
表演：黎迴語速沉著帶玩笑，嘴角帶笑卻眉心緊繃；緊張時指尖敲出倒數節奏，按下錄音鍵時瞬間失焦後自嘲收回。
臉型/髮型：短黑髮與左側銀白挑染束、灰金瞳刻度與淺眼袋、唇色偏蒼白但帶不羈弧度。
構圖：三分線與 HUD 浮層並列、前中後層疊霓虹與塔影；動態：沙漏耳環懸停、街燈 flicker、倒帶亮線掃過、錄音波形跳動、HUD 倒數換字。
寫實細節：深灰帽 T 內裡縫線以霓虹電路描邊、黑背心襯托 `00:00` 刺青發光、窄管牛仔褲膝處磨損如時間刻痕、舊球鞋泛黃並貼倒數標籤、黑繃帶間隙露出金屬錄音鍵、沙漏玻璃反射霓虹黃。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35 建立空間與時間停滯｜45–60 情緒特寫與道具細節｜70mm 望遠收束群像；
光圈 {T2.2–T2.8 霓虹分層｜倒帶時縮至 T3.5 穩定 HUD}；快門角 {夜景 180°｜glitch 閃回 156°｜失焦回收 200°}；
對焦 {層次前→中→後／單點瞳孔刻度→錄音鍵→遠景塔尖}。
光影：霓虹混光 3200K–3600K，屋頂風光偏冷 3000K，錄音室藍屏 4800K；倒帶瞬間以白閃補光 0.2s；
對比 {夜景維持中高對比，角色皮膚保留柔亮 rim light}；眼神光 {保留螢幕映光與刻度自發光}。
色調/LUT：膚色優先，陰影微靛 10%，高光暖金 6%，倒帶片刻帶青洋紅色偏移；爆炸雲維持去飽和 25%。
聲音：rooftop_wind_low＋analog_console_hum 建立底噪；clock_tick_triplet_sidechain 疊合心跳；tape_scrub_reverse 表示倒帶；錄音筆訊息加 wow/flutter 0.7%；Lo-fi 合成器鋪陳，副拍加 filtered_radio_beep。
轉場：霓虹燈遮擋→HUD 光源匹配→倒帶白閃→錄音聲失真鞭移→塔身羽化 0.5s。
安全：招牌改為符號矩陣，路人臉型簡化無辨識字樣，HUD 倒數採內製字型。
```

### Camera Continuity
- 維持終點塔冷白 #B0C7FF 與爆炸雲暖金 #FFB36D 的對比，供後續迴圈題材沿用。
- 保留黎迴手腕錄音鍵與沙漏耳環特寫運鏡，作為系列的匹配剪接基準。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.5s）
意圖：建立終點市的時間停滯與黎迴的登場氣質
基調：悸動混玩世
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：終點塔、定格爆炸雲、霓虹街巷 HUD、銀白髮束閃光、沙漏耳環

#### Beat 1（0.0–2.0s）
重點：城市 HUD 倒數與黎迴行走街道
Blocking：無人機俯視城市→HUD 23:00 漂浮→切側後方跟拍黎迴插口袋穿過霓虹巷弄。
Camera：
- 運鏡：無人機緩推→街巷滑軌
- 焦段/機位：24mm 俯拍→28mm 胸高側後
- 對焦：層次拉焦（爆炸雲→塔身→黎迴）
- 快門角：180→180；拍點：HUD 亮起
光影：黃昏 3400K 霓虹混光，塔身 rim light，爆炸雲自發光；
色調/LUT：陰影微藍 8%，高光暖金 5%，膚色優先；
聲音：遠處 siren＋Lo-fi 節拍淡入，電子女聲報時「……還剩六十分鐘。」
轉場：霓虹牌遮擋切下一角

Angle 1（0.0–1.0s）
構圖：中央遠景帶 HUD 浮層
內容：城市俯視＋爆炸雲定格
補充：HUD 數字微閃、爆炸雲粒子靜止、霓虹閃爍 glitch
安全：招牌改符號、無品牌字樣

Angle 2（1.0–2.0s）
構圖：三分線前景黎迴、背景霓虹
內容：中景側後跟拍黎迴走巷弄
補充：銀白髮束反光、街牌偶爾卡頓一格、腳步聲帶拖影
安全：路人臉簡化無特徵

#### Beat 2（2.0–4.5s）
重點：黎迴道具特寫與錄音室建立
Blocking：耳環特寫→轉入地下錄音室，黎迴坐入位拉下帽 T 露出刺青。
Camera：
- 運鏡：微側移→穩定器環繞
- 焦段/機位：50mm 耳朵特寫→35mm 眼高半身
- 對焦：單點（沙漏→瞳孔）
- 快門角：156（特寫控制殘影）→180
光影：耳環取霓虹黃 rim，室內藍螢幕 4800K，桌面暖燈 3500K；
色調/LUT：膚色優先，陰影加藍 10%，錄音室背景去飽和 15%；
聲音：沙漏細沙停住的靜默＋console hum，加上黎迴輕笑吸氣。
轉場：HUD 白線掃入下一幕

Angle 3（2.0–3.0s）
構圖：中央特寫
內容：沙漏耳環晃動，沙停在中央
補充：glitch 靜止粒子、女聲報時尾音
安全：配件無品牌

Angle 4（3.0–4.5s）
構圖：三分線；黎迴半身靠椅
內容：錄音室內，黎迴拉下帽 T 露出 `00:00`
補充：背景便利貼與時間線模糊、控制台燈光流動
安全：紙張文字抽象化無可讀

### Act 2（4.5–9.2s）
意圖：展現黎迴的時間感知與殘檔訊息
基調：緊張與溫柔交錯
節奏域：穩定1.5–2.4
美術要點：瞳孔刻度、控制台 HUD、城市倒播、錄音筆黑繃帶

#### Beat 3（4.5–6.2s）
重點：瞳孔刻度發光與 DJ 開場
Blocking：瞳孔超特寫→斜俯角看她推動推桿並開播。
Camera：
- 運鏡：定鏡→斜俯推進
- 焦段/機位：55mm 超特寫→32mm 斜俯
- 對焦：單點瞳孔→拉至音波螢幕
- 快門角：156→180；拍點：推桿觸底
光影：瞳孔自發光帶鐘刻度，面光偏冷 3400K；控制台螢幕亮藍 5200K。
色調/LUT：眼部高光暖金 8%，背景降飽和 12%；
聲音：心跳＋滴答聲疊合、黎迴溫柔帶笑播報：「晚安，終點市——又到了世界毀滅前的一小時。」
轉場：音波 HUD 擴散匹配切

Angle 5（4.5–5.5s）
構圖：中央超特寫
內容：灰金瞳刻度逐格亮起
補充：滴答音同步、刻度帶微光粒子
安全：僅露眼部

Angle 6（5.5–6.2s）
構圖：前中後，黎迴與控制台
內容：斜俯看她推開推桿
補充：音波如心電圖狂跳，嘴角帶笑
安全：螢幕文字用符碼

#### Beat 4（6.2–7.5s）
重點：街景倒播一秒
Blocking：切回街景廣角，時間倒帶再恢復。
Camera：
- 運鏡：固定廣角
- 焦段/機位：26mm 眼高
- 對焦：層次前→後（行人→霓虹）
- 快門角：156（倒帶控制拖影）
光影：霓虹 3300K 混合倒帶白閃；
色調/LUT：倒帶時色偏青洋紅，恢復後回暖金；
聲音：tape_scrub_reverse＋filtered_radio_beep。
轉場：倒帶亮線掃到下一幕

Angle 7（6.2–7.5s）
構圖：前景光軌，背景塔影
內容：街道行人與車流倒播一秒再恢復
補充：亮線掃過、HUD LOOP 閃光
安全：招牌模糊

#### Beat 5（7.5–9.2s）
重點：錄音訊息與記憶失焦
Blocking：手腕特寫按錄音鍵→黎迴短暫失焦又收回笑容。
Camera：
- 運鏡：手腕定鏡→半身緩推
- 焦段/機位：45mm 手腕→60mm 半身眼高
- 對焦：單點（錄音鍵）→呼吸拉焦回瞳孔
- 快門角：180→200（失焦柔化）
光影：手腕補光暖 3500K，背景降低飽和；瞳孔刻度倒跳一格暗閃。
色調/LUT：錄音段落去飽和 18%，失焦時色彩偏灰藍；
聲音：錄音筆失真訊息「……如果妳聽得到，代表妳又被重置了……」，黎迴輕笑自嘲：「抱歉，剛剛掉進上一輪了。」
轉場：她抬眼的動作帶鞭移切屋頂

Angle 8（7.5–8.2s）
構圖：中央道具特寫
內容：黑繃帶下的錄音鍵被按下
補充：背景去飽和，HUD 微閃「REC」
安全：僅顯示道具

Angle 9（8.2–9.2s）
構圖：三分線半身
內容：黎迴愣住後嘴角勾起
補充：瞳孔刻度往回跳、臉上短暫 glitch
安全：背景貼紙模糊

### Act 3（9.2–15.0s）
意圖：凝聚殘檔者共鳴並以標題卡收束
基調：決斷與盼望並存
節奏域：穩定1.5–2.4 → 慢出0.8–1.5
美術要點：屋頂剪影、終點塔 HUD、殘檔者 HUD「ECHO ONLINE」、角色標題卡

#### Beat 6（9.2–11.8s）
重點：屋頂決心與殘檔者共鳴
Blocking：黎迴站在屋頂眺望→蒙太奇切換其他殘檔者抬頭。
Camera：
- 運鏡：背影定鏡→望遠插切
- 焦段/機位：30mm 背影中遠→70mm 中近
- 對焦：單點（黎迴 sil）→呼吸拉焦各角色
- 快門角：180
光影：屋頂風 3200K 冷色，塔光投射 rim；蒙太奇場景各自帶霓虹微光。
色調/LUT：膚色保留，背景去飽和 10%；
聲音：廣播聲「這一輪——我們試著一起走到最後。」殘檔者場景疊加遠 siren。
轉場：HUD 線條掃入定格

Angle 10（9.2–10.0s）
構圖：剪影前景黎迴，遠景塔置中央
內容：屋頂背影，帽 T 與短髮被風掀起，HUD `23:47`
補充：定格爆炸雲遙遠閃動、衣角拉扯
安全：無品牌

Angle 11（10.0–11.8s）
構圖：蒙太奇多鏡頭（便利商店、電車、樓梯）
內容：不同殘檔者抬頭，HUD 彈出 `ECHO ONLINE`
補充：HUD 綠光閃爍、角色臉部簡化但成年
安全：場景商品以符號呈現

#### Beat 7（11.8–15.0s）
重點：角色標題卡與迴圈歸零
Blocking：畫面轉為 2D 漫畫風定格，浮出標題，最後白字 `00:00`。
Camera：
- 運鏡：快速推進→定格
- 焦段/機位：35mm 正面半身
- 對焦：單點黎迴→定格
- 快門角：180
光影：紫藍背景 radial light，角色 rim 光 tungsten_gold。
色調/LUT：整體去飽和 12%，線條強化。
聲音：音樂收束，loop_marker beep 後留黑，最後 0.5s 靜音。
轉場：黑場收尾

Angle 12（11.8–15.0s）
構圖：正面半身定格，右側豎排字卡
內容：黎迴握麥克風標題卡，背景城市與時間刻度
補充：標題字 `迴圈終點都市` 漸亮，最後黑場僅留白色 `00:00`
安全：字體為自有設計

## 生成 Prompt Block
```
### DESCRIBE
A 15-second 2D anime-style character PV of **Rei Li**, a young female DJ in a time-loop apocalypse city called "Terminal City".

She has short black hair with a distinct silver streak on one side that often falls over her eye, grey-gold eyes with faint clock-like markings around the iris that glow when she remembers past loops, pale skin with light dark circles, and a small tattoo `00:00` on her collarbone. She wears a dark grey cropped hoodie over a black tank top, dark blue skinny jeans, and worn sneakers. On her right ear she has a tiny hourglass earring with sand frozen in the middle, and her left wrist is wrapped with a black bandage hiding a small recorder.

The city sky is always dusk to night, with a frozen explosion cloud far in the background. Neon signs flicker in Japanese and Chinese, sometimes glitching or rewinding one second. The PV cuts between her walking through the neon streets, hosting a late-night underground radio show in a dim studio, using the hidden recorder on her wrist to play distorted messages from previous loops, and standing on a rooftop looking at a tall "End Tower" in the distance.

Overall mood: bittersweet, stylish, time-loop melancholy. Clean anime linework, soft shading, neon rim light, subtle glitch effects when time rewinds. The final shot freezes on a dynamic half-body illustration of her with the city and clock markings behind her, with the title logo.

### RESTRICTION
* `2D anime style, clean linework, soft shading, limited color palette`
* `young woman, short black hair, single silver streak, grey-gold eyes with subtle clock markings`
* `00:00 tattoo on collarbone, tiny hourglass earring, left wrist bandage with hidden recorder`
* `dark grey cropped hoodie, black tank top, dark blue skinny jeans, worn sneakers`
* `neon cyberpunk city at dusk, frozen explosion cloud in distant sky`
* `flickering neon signs, occasional one-second rewind glitch, HUD countdown overlay`

* `cinematic cuts between neon street, dim radio studio, city rooftop, End Tower silhouette`
* `no 3D rendering, no realistic live-action footage, strictly 2D anime look`
```

# Rhythm City PV — Master Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-15_glitch-in-the-beat_v01/script.md

## 一句話題材
以 15 秒 2D 霓虹動畫節奏展示路節如何以 Re-Beat 能力對抗 MetroScore，從城市失控拍點到地下月台的自由節奏爆發，再以標語收束系列主題。

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

### Style Pack：Rhythm City Neon Anime Look（新樣板）
```yaml
name: Rhythm City Neon Anime Look
line_enhancement: neon_edge_trace
noise_reduction: clean_cel_plate
saturation: dual_tone_balance
contrast_profile: pulse_weighted_soft
color_palette:
  primaries: [slate_blue, charcoal_teal, plum_night]
  accents: [metro_amber, glitch_cyan]
  skin_tone: neutral_warm
bloom_layers:
  metro_core: amber_ring_glow
  rebeat_override: cyan_wave_pulse
ui_overlay: waveform_parallax_grid
shadow_treatment: soft_multitone
texture_pass: microfilm_grain_subtle
notes:
  - 保持 2D 動畫線條俐落，遇到高對比霓虹時在邊緣加上 1px 亮線避免吞線。
  - 都市夜景以冷藍與石墨灰為底，MetroScore 元件採琥珀色，Re-Beat 節奏改寫時切換為青綠光。
  - 服裝材質呈現霓虹反光的布料細節，LED 鞋底與螢光褲線需同步閃爍。
```

### Style Pack：Rhythm City Neon Pulse VFX（新樣板）
```yaml
name: Rhythm City Neon Pulse VFX
layer_stack:
  - bpm_halo_grid
  - waveform_glitch_tiles
  - metro_alert_ui
bpm_halo_grid:
  radius: 18
  vertical_sync: 120
  pulse_shape: square_drop
waveform_glitch_tiles:
  tile_size: [0.8, 0.8]
  offset_jitter: 0.12
  desync_threshold: 0.22
metro_alert_ui:
  banner_text: "ANOMALY DETECTED"
  color_pair: [metro_amber, warning_white]
  glitch_frequency: 3.5
notes:
  - Beat Spire 與地面標線需出現等距網格，Re-Beat 時轉換為青綠波形分段。
  - HUD 字卡使用 MetroScore 琥珀色，錯拍時出現白色亂流，維持讀性。
  - 轉場可利用 waveform_glitch_tiles 做 4 frame 內的節奏切換。
```

### Style Pack：Rhythm City Pulse Audio（新樣板）
```yaml
name: Rhythm City Pulse Audio
bpm_map:
  metro_default: 120
  glitch_spike: 132
  rebeat_safe: 108
ambient_layers:
  - distant_maglev_whoosh
  - tower_sub_bass
rhythmic_elements:
  kick: tight_sub_punch
  snare: clap_snap_layered
  hihat: triplet_glitch_tick
accent_fx:
  metro_warning: tri_tone_ping
  rebeat_sweep: filter_push_down
vocal_fx:
  rebel_vo_line: male_mid_soft_grit
mix_notes:
  - MetroScore 段落保持 120 BPM，聲像穩定居中；Re-Beat 段落降速至 108 BPM 並加入 sidechain 呼吸感。
  - 隱藏節拍以 1/16 hi-hat 滑動呈現，與畫面錯位時增強 2 dB。
  - 保留 60 Hz 以下塔身低頻作為城市心跳，收尾 Freeze 保持 -12 dB sustain。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Rhythm City Neon Anime Look｜2.39:1｜24fps｜霓虹節奏分鏡)
「夜間23:45節奏城市核心至老街月台動線；Beat Spire 琥珀光環、同步街燈車潮、地下月台殘破海報；路節察覺 MetroScore 失控後下到月台啟動 Re-Beat，讓城市短暫跳入自由節奏。
鏡頭：24mm 俯視建立→32mm 腳步側滑→40mm 中近景→28mm 主觀 HUD→26mm 階梯推進→45mm 特寫剪輯→35mm 半身定格→30mm 街景對切→50mm 中景→70mm 控制室望遠→55mm 近景→30mm 變形收束。
表演：路節由冷靜觀察轉為專注堅定，啟動 Re-Beat 時呼吸深沉、指尖精準打拍；眼神挑釁地望向監控。
臉型/髮型：黑色亂翹短髮瀏海遮左眼，專注時虹膜浮現白色波形線；膚色偏白帶淡黑眼圈。
構圖：前中後分層以城市網格、路節與 HUD 波形構成；動態：交通流、LED 鞋底閃光、節拍方塊漂浮、地下月台霓虹閃爍。
寫實細節：深灰連帽外套內搭黑T波形印刷、黑束口工裝褲螢光線條、LED 厚底鞋；半罩式耳機顯示 BPM，腕帶投影個人節奏譜；環境霓虹反射與蒸汽。字卡僅顯示日文台詞與中文字幕，無商標/Logo/水印。」

鏡頭語法：24–35 建立空間節奏→40–55 親密特寫→70mm 望遠監控對比；
光圈 {T2.4–T3.2 保留夜景霓虹層次；控制室收至 T3.5 增加 HUD 清晰度}；快門角 {全段 180°，Re-Beat 拉低至 168° 強化切分感}；
對焦 {層次前→中→後；Re-Beat 特寫單點眼→拉焦至 HUD 波形再回角色}。
光影：城市段以琥珀 3400K 與青綠 4200K 混光，月台加冷白霧燈；
對比 {平段中等對比，Re-Beat 提升高對比以凸顯波形}; 眼神光 {維持耳機反射點}。
色調/LUT：背景冷藍灰降低飽和 10%，MetroScore 元件保暖琥珀，Re-Beat 疊加青綠光暈；膚色自然暖。
聲音：distant_maglev_whoosh＋tower_sub_bass 建立城市心跳，tight_sub_punch＋clap_snap_layered 走 120 BPM，triplet_glitch_tick 插入隱藏節拍；Re-Beat 段落降至 108 BPM 加入 filter_push_down；tri_tone_ping 在警報時同步畫面；JP VO 壓在 -8 dBFS。
轉場：HUD 波形遮擋→節拍方塊鞭移→街燈光源匹配→VFX glitch tiles 直接切→Freeze 後羽化淡出。
安全：僅出現虛構 MetroScore 介面，控制室人員不入鏡特寫；海報與城市字樣保持抽象圖形。
```

### Camera Continuity
- 首支《節奏城市》系列 PV，建立 MetroScore 琥珀光 vs. 自由節奏青綠光的對比，後續影片需沿用同色域與 HUD 語言。
- Freeze 收尾需保留城市縮成波形線條的視覺，以便後續 PV 可直接接續開場。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.8s）
意圖：建立 MetroScore 統治下的節奏城市與路節察覺異常
基調：緊張帶壓迫
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：Beat Spire 光環、同步車流、LED 鞋底、HUD 波形

#### Beat 1（0.0–2.4s）
重點：延續城市整體律動並帶出路節踩拍
Blocking：承接俯視城市的節奏跳動→鏡頭下降跟至路節腳步→腳跟踩點與街燈同步。
Camera：
- 運鏡：24mm 俯視滑軌下降→32mm 側向跟拍
- 焦段/機位：俯拍→膝高側跟
- 對焦：層次前景 Beat Spire→轉至路節腳步
- 快門角：180；拍點：每 0.5 秒街燈閃爍
光影：琥珀街燈節拍照射，地面反射冷藍天空
色調/LUT：背景去飽和 10%，LED 鞋底維持青綠亮度
聲音：城市心跳 120 BPM、鞋跟「啪」拍點、遠處電車嘯聲
轉場：鞋底閃光遮擋 → Angle 2

Angle 1（0.0–1.2s）
構圖：俯視中央構圖
內容：整座城市像心電圖跳動，Beat Spire 光環脈動
補充：HUD 角落顯示「MetroScore ONLINE」
安全：城市文字模糊處理

Angle 2（1.2–2.4s）
構圖：三分線，腳步位於右側
內容：路節鞋底 LED 與斑馬線節拍對齊
補充：路人腳步投影同步
安全：路人臉保持模糊遠景

#### Beat 2（2.4–4.8s）
重點：路節接收異常節拍並看到譜面錯位
Blocking：承接腳步節奏→路節戴上耳機皺眉→轉為主觀 HUD 顯示波形脫序。
Camera：
- 運鏡：40mm 中近景定鏡→28mm 主觀 HUD 穩定器
- 焦段/機位：胸高→眼高主觀
- 對焦：單點臉→HUD 白波形
- 快門角：180；拍點：隱藏 hi-hat 錯位
光影：耳機螢光照亮臉部，街燈成背景輪廓
色調/LUT：臉部保持暖中性，HUD 以青綠突出
聲音：triplet_glitch_tick 加入，耳機 BPM 顯示跳為「???」
轉場：HUD 波形掃過遮擋 → Act 2

Angle 3（2.4–3.6s）
構圖：中近景三分線
內容：路節戴耳機，BPM 顯示器亂碼
補充：虹膜浮現淡白波形
安全：無真實標識

Angle 4（3.6–4.8s）
構圖：中央構圖主觀視角
內容：街道音軌線條平行，白色波形偏離並閃爍「GLITCH」
補充：畫面邊角出現節拍錯位警告
安全：介面文字僅顯示代碼

### Act 2（4.8–9.6s）
意圖：轉入地下月台並展現 Re-Beat 啟動
基調：決斷帶燃點
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：廢棄月台、FREE BEAT 海報、掌上打擊墊、HUD 投影

#### Beat 3（4.8–7.2s）
重點：延續異常後進入月台準備裝備
Blocking：承接 HUD 錯位→鏡頭帶路節入廢棄月台→連續特寫裝備就位。
Camera：
- 運鏡：26mm 手扶梯穩定器下移→45mm 特寫剪輯
- 焦段/機位：胸高→手部特寫
- 對焦：層次從月台燈→角色→掌上打擊墊
- 快門角：180；拍點：燈光閃動與指尖敲擊
光影：月台冷白燈忽明忽暗，FREE BEAT 海報受青綠霓虹反射
色調/LUT：背景灰冷，裝備特寫加青綠光邊
聲音：Maglev 底噪＋指尖敲擊節拍
轉場：掌上打擊墊向鏡頭推進 → Angle 6

Angle 5（4.8–6.0s）
構圖：中遠景中央
內容：路節走入半黑的月台，牆上海報撕裂
補充：地面節奏方塊微弱閃爍
安全：海報文字模糊僅保留「FREE BEAT」

Angle 6（6.0–7.2s）
構圖：連續特寫拼接
內容：手指敲掌上打擊墊、腕帶 HUD 展開、耳機扣緊
補充：每個特寫 0.4s 內透過匹配剪接
安全：無外部標誌

#### Beat 4（7.2–9.6s）
重點：Re-Beat 發動並與地面街景形成節奏對比
Blocking：承接裝備啟動→路節半身深吸啟動 Re-Beat→切到地面街道對比→回月台光同步。
Camera：
- 運鏡：35mm 半身定鏡→30mm 街景硬切
- 焦段/機位：眼高→街景高角度
- 對焦：單點角色→街上電子看板
- 快門角：168；拍點：Re-Beat 推手、廣告板閃光
光影：Re-Beat 時青綠波形掃過，街面仍為琥珀
色調/LUT：月台提升對比，街景維持暖色與青綠交錯
聲音：BPM 降至 108，加入 filter_push_down；街景保留 120 BPM 形成衝突
轉場：街景光源匹配 → Act 3

Angle 7（7.2–8.4s）
構圖：三分線，路節居左
內容：路節推手，空氣切割成節拍格
補充：波形方塊浮現
安全：僅角色單人

Angle 8（8.4–9.6s）
構圖：對比剪輯，街道中央構圖
內容：行人仍照原節奏行走，旁邊廣告板改跟路節節奏
補充：廣告板顯示青綠波形
安全：廣告內容為抽象圖樣

### Act 3（9.6–15.0s）
意圖：呈現自由節奏對市民與 MetroScore 的衝擊並收束標題
基調：盼望混危機
節奏域：加速2.4–3.0 → 穩定1.5–2.4
美術要點：失調者呼吸、控制室監控、路節宣言、標題波形

#### Beat 5（9.6–12.0s）
重點：Re-Beat 效果拯救失調者並引發 MetroScore 警報
Blocking：承接 Re-Beat 光→月台角落失調者恢復→切到控制室警報。
Camera：
- 運鏡：50mm 月台中景→70mm 控制室望遠
- 焦段/機位：膝高→眼高望遠
- 對焦：單點失調者臉→控制室螢幕
- 快門角：180；拍點：呼吸回穩、警報閃爍
光影：Re-Beat 青綠光鋪在失調者臉上，控制室維持冷灰螢幕光
色調/LUT：救援段落增暖膚色，控制室降低飽和提高對比
聲音：呼吸聲與 sidechain 呼吸節奏，tri_tone_ping 警報
轉場：螢幕白光切 → Beat 6

Angle 9（9.6–10.8s）
構圖：三分線，失調者居右
內容：原抱頭上班族放下手，呼吸平穩
補充：背景霓虹跟路節節奏閃
安全：角色成年標示

Angle 10（10.8–12.0s）
構圖：監控室多屏中央
內容：波形面板上出現白色亂流，警報字樣閃爍
補充：下方角落標示「SOURCE: UNKNOWN」
安全：僅顯示虛構介面

#### Beat 6（12.0–15.0s）
重點：路節宣言與系列標題收尾
Blocking：承接警報→路節側臉宣言→畫面縮成波形與標題 Freeze。
Camera：
- 運鏡：55mm 側面近景→30mm 圖像化拉遠
- 焦段/機位：眼高→俯視縮放
- 對焦：單點路節眼睛→縮放至波形標誌
- 快門角：168；拍點：台詞落點與結尾強拍
光影：路節眼中青綠波形流動，背景暗場保留輪廓；標題段落以琥珀+青綠交織
色調/LUT：臉部保暖，Freeze 時轉為雙色線條
聲音：JP VO 伴隨 hi-hat glitch，最後強拍所有聲音 Freeze
轉場：Freeze 定格後羽化收黑

Angle 11（12.0–13.2s）
構圖：側面三分線
內容：路節眼中波形流轉，嘴角微笑
補充：字卡上排日文「同じリズムだけじゃ、生きていけないだろ。」下排中文字幕『只用一種節奏活著，太無聊了吧。』
安全：字卡僅含對白文字

Angle 12（13.2–15.0s）
構圖：圖像化中央
內容：城市夜景縮為音軌線，變形為路節眼波形與耳機輪廓，再化成標題 Logo
補充：結尾 Freeze 0.5s 後淡出
安全：標題為《節奏城市 Rhythm City》＋副標

# Curve Bolt Multi-Lock — Segment Four Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-14_curve-bolt-multi-lock_v01/script.md

## 一句話題材
燁程在獵骨獸圍殺圈中覺醒多軌 Curve Bolt，利用 HUD 指引描繪弧線、同時命中多重弱點並升級，但能量被耗盡幾近昏倒。

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
Master(15s｜Light Glyph Anime｜16:9｜24fps｜冷灰森林＋金色能量墨線質感)
「夜幕將盡的濕冷石林；泥水血跡、錯位殘影、半透明 HUD 光層；燁程背貼岩壁被七隻獵骨獸包圍，覺醒多軌 Curve Bolt 描弧反擊並升級。
鏡頭：開場24mm半俯旋繞建立圍殺圈，接35mm與45mm貼近骨甲、頭顱與錯位步伐，再以主觀視角 HUD 切換；覺醒段改50mm胸高穩定器，曲射段拉至40mm 側上俯視，命中段交錯65mm特寫；能量枯竭收於55mm手持3%顫抖。
表演：燁程從屏息驚懼過渡至專注咬牙，指尖描弧時微抬下巴；命中後體力崩塌，仍勉強挑眉勾嘴角。
臉型/髮型：燁程黑髮束起側分，臉頰帶血痕與汗水；獵骨獸顱骨變形，螢綠瞳孔收縮。
構圖：圍殺段採前中後分層，怪物占框邊 60%；描弧段留白 15% 給 HUD 軌跡；命中段聚焦弱點特寫。
寫實細節：泥水混血粘稠反光、骨甲鐵鏽縫隙滲血、掌背金紋沿指骨躍動、光彈拖尾帶符文。
無字幕、無商標/Logo/水印。」

鏡頭語法：24 建立壓迫｜35–45 解析骨甲與殘影｜50 胸高覺醒｜40 俯視多軌｜65 特寫命中；
光圈 {T2.8–T4.5}；快門角 {200°（圍殺）／180°（描弧與命中）}；
對焦 {層次前→中→後／單點 HUD 弧端／呼吸拉焦掌心→臉部}。
光影：側逆霧光＋HUD 冷光補邊，色溫 {夜3000–3800K＋金色局部暖補}；
對比 {高}；眼神光 {保留由 HUD 反射}。
色調/LUT：{陰影靛藍，血泥偏棕黑，高光金色／去飽和5%}。
聲音：環境（濕泥擠壓、獸群咆哮）、衣料拉扯、HUD 按鍵；音樂 {96BPM 氛圍弦樂＋holo_keyboard_taps}；音效峰值 -6 dB。
轉場：鞭移與遮擋交替，命中剪接用光閃匹配，升級段羽化0.6s。
安全：無可讀字樣，HUD 文本採圖標化；獵骨獸血液保持幻想調性。
```

---

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立圍殺壓力與威脅
基調：緊張決斷
節奏域：加速2.4–3.0 → 慢入0.8–1.5（HUD 切換時瞬降）
美術要點：濕泥、岩壁、獵骨獸骨甲裂紋、血水反光

#### Beat 1（0.0–1.0s）
重點：獵骨獸包圈收縮
Blocking：燁程背貼岩壁喘息，鏡頭半俯繞行顯示半圓包抄
Camera：
- 運鏡：24mm 半俯旋繞
- 焦段/機位：24mm 俯拍 35°
- 對焦：層次拉焦獸群→燁程→地面血泥
- 快門角：200；拍點：泥濺「啵嗒」
光影：體積霧從左後方透出，獸影投向前景
色調/LUT：陰影靛藍，金色僅在 HUD 殘光
聲音：soft_city_air_hum 混入低頻咆哮，泥濺近場
轉場：骨甲掠過鏡頭遮擋 → Beat 2

Angle 1（0.0–1.0s）
構圖：三分線，燁程靠左後景，獵骨獸半圓佔右前
內容：建立包圍圈
補充：泥漿因足爪擠壓向外噴濺
安全：無可讀標誌，血泥不超過 60% 框面

#### Beat 2（1.0–2.0s）
重點：骨甲細節與血漬
Blocking：鏡頭沿獵骨獸小腿往上推近
Camera：
- 運鏡：35mm 穩定器上推
- 焦段/機位：35mm 膝高仰視
- 對焦：單點骨板裂縫→滲血→鐵鏽紋
- 快門角：200；拍點：血滴落泥
光影：低角暖光沿骨板折射，縫隙散發金光反射
色調/LUT：骨板偏冷灰，血液暗紅偏棕
聲音：黏稠滴落疊上骨甲摩擦
轉場：血滴濺至鏡頭羽化 → Beat 3

Angle 2（1.0–2.0s）
構圖：中央縱深，骨板佔畫面 70%
內容：骨甲與裂紋特寫
補充：血滴落下即被泥水沖散
安全：避免顯示骨髓組織

#### Beat 3（2.0–3.0s）
重點：群體頭部與眼睛壓迫
Blocking：一圈獵骨獸頭骨湧向鏡頭
Camera：
- 運鏡：40mm 輕推
- 焦段/機位：40mm 眼高
- 對焦：層次眼睛→裂開下顎→唾液絲
- 快門角：200；拍點：低吼最強
光影：螢綠瞳孔作主光，唾液反射HUD光
色調/LUT：眼光螢綠，骨骼灰紫
聲音：鐵鏈摩擦般低吼加上口腔濕響
轉場：獸頭呼氣霧氣遮擋 → Beat 4

Angle 3（2.0–3.0s）
構圖：中央壓迫式滿框
內容：頭骨群像近景
補充：唾液絲在呼吸時抖動
安全：牙齒鋒利但不直接撕咬

#### Beat 4（3.0–4.0s）
重點：錯位殘影步伐
Blocking：群獸同步逼近，殘影錯位
Camera：
- 運鏡：28mm 手持 3% 低角追步
- 焦段/機位：28mm 膝高仰視
- 對焦：層次爪子→殘影→刮痕
- 快門角：200；拍點：殘影錯格瞬間
光影：HUD 漏光沿殘影邊緣閃爍
色調/LUT：陰影偏藍，爪痕泛白
聲音：不規則「沙沙」「嘎吱」節奏類壞硬碟
轉場：爪痕掃過畫面 → Beat 5

Angle 4（3.0–4.0s）
構圖：前景爪子放大，燁程腿在後景
內容：步伐與殘影
補充：地面抓痕錯位重疊
安全：保持 2D 動畫線條乾淨

#### Beat 5（4.0–5.0s）
重點：HUD 提醒多軌射擊
Blocking：切至主觀視角，HUD 標記敵人與建議
Camera：
- 運鏡：主觀穩定，僅視線微抖
- 焦段/機位：虛擬 32mm 眼高
- 對焦：單點 HUD 軟鎖
- 快門角：180；拍點：建議彈出
光影：背景降飽和成灰藍，紅色描邊突出
色調/LUT：HUD 金紅，環境偏靛
聲音：glassy_beep_mid 提示音＋arc_bow_sheen 底噪
轉場：HUD 彈窗縮回左側 → Beat 6

Angle 5（4.0–5.0s）
構圖：中央 HUD 交錯線框
內容：Threat 指示與敵人標記
補充：弱點區塊亮起金色輪廓
安全：HUD 字樣簡體圖示無可讀語句

### Act 2（5.0–9.0s）
意圖：展現燁程掌控軌跡與同步裝填
基調：決斷中帶希望
節奏域：穩定1.5–2.4
美術要點：掌背金紋、懸浮光軌、分層能量陣

#### Beat 6（5.0–6.0s）
重點：掌背金紋穩定
Blocking：燁程胸口近景，右手漸穩，低語自我提示
Camera：
- 運鏡：50mm 穩定器輕推
- 焦段/機位：50mm 胸高
- 對焦：呼吸拉焦胸腔→手背
- 快門角：180；拍點：金紋完全閉合
光影：金紋自掌心循指骨環形亮起
色調/LUT：皮膚暖琥珀，背景冷灰
聲音：心跳節奏與 low_orbital_throb 同步，低語 -12 dB
轉場：指尖抬起帶動光紋 → Beat 7

Angle 6（5.0–6.0s）
構圖：三分線，手背佔中景
內容：掌背金紋脈動
補充：汗珠沿手腕滑落
安全：掌紋無可辨識文字

#### Beat 7（6.0–7.0s）
重點：空中描繪多重弧線
Blocking：燁程指尖快速描弧，光線懸浮標記弱點
Camera：
- 運鏡：45mm 側面滑移
- 焦段/機位：45mm 肩高
- 對焦：層次指尖→弧線末端標籤
- 快門角：180；拍點：每條弧線完成
光影：弧線留下金薄荷雙色拖尾
色調/LUT：弧線亮度 90 nits，背景保持低飽和
聲音：airy_chime_hi 連環＋holo_keyboard_taps 作節拍
轉場：最後一條弧線定格 → Beat 8

Angle 7（6.0–7.0s）
構圖：側面中近景，弧線盤旋前景
內容：指尖描繪與 HUD 標籤
補充：標籤顯示「Joint」「Neck」「Spine」圖示
安全：標籤使用圖像符號，無字串

#### Beat 8（7.0–8.0s）
重點：掌心多層光陣裝填
Blocking：掌心前光陣分層旋轉，光彈逐一生成
Camera：
- 運鏡：55mm 微推特寫
- 焦段/機位：55mm 手部近拍
- 對焦：單點光彈→掌心紋路
- 快門角：180；拍點：每枚光彈成形
光影：內外圈反向旋轉，金光在掌心映出
色調/LUT：光彈金綠，掌心暖琥珀
聲音：每次成形觸發 glassy_beep_mid，「叮」聲清晰
轉場：燁程伸手甩出 → Beat 9

Angle 8（7.0–8.0s）
構圖：中央特寫，光陣占滿
內容：多層光陣載入
補充：陣列外圈浮動符文
安全：符文抽象無文字

#### Beat 9（8.0–9.0s）
重點：多發彎射同時出手
Blocking：燁程甩手，四枚光彈沿弧線飛出編織光網
Camera：
- 運鏡：40mm 側上俯視
- 焦段/機位：40mm 高位俯角 25°
- 對焦：層次光彈→目標弱點
- 快門角：180；拍點：光彈分離瞬間
光影：光尾拖過地面與岩壁，反射出金線
色調/LUT：環境維持低飽和，光尾高亮
聲音：arc_bow_sheen 持續嗡鳴，獸吼疊加
轉場：光尾帶動 Whip pan → Beat 10

Angle 9（8.0–9.0s）
構圖：俯視中景，光弧交錯成網
內容：光彈曲射全局
補充：殘影錯位仍可見於獸群
安全：光弧避免穿越鏡頭

### Act 3（9.0–15.0s）
意圖：展現連鎖命中、能量枯竭與等級提升
基調：極限決斷→虛脫→欣慰
節奏域：加速2.4–3.0（命中剪輯）→慢入0.8–1.5（餘韻）
美術要點：血泥濺射、HUD 能量條、升級提示視窗

#### Beat 10（9.0–11.0s）
重點：Curve Bolt 連鎖命中
Blocking：三枚光彈接連擊穿不同弱點，鏡頭快速切換特寫
Camera：
- 運鏡：65–85mm 快速剪接，部分採 75mm 追蹤
- 焦段/機位：65mm 頸部斜側｜70mm 地面貼行｜75mm 背脊滑移
- 對焦：單點命中點
- 快門角：180；拍點：每次爆裂
光影：命中瞬間白金爆閃，血泥濺至鏡前
色調/LUT：命中區域亮度瞬時 +20%，迅速回落
聲音：arc_bow_sheen 轉成爆裂層，clipped_square_red 作命中提示
轉場：血泥濺鏡擦過 → Beat 11

Angle 10A（9.0–9.6s）
構圖：頸部弱點特寫
內容：光彈鑽入頸縫，白光從眼窩爆出
補充：頭顱後仰倒地
安全：血液霧化處理

Angle 10B（9.6–10.3s）
構圖：貼地追光，獵骨獸前腿關節
內容：光彈沿地滑行鑽入關節炸裂
補充：後腿炸裂，獸身撞同伴
安全：斷面以光粒遮罩

Angle 10C（10.3–11.0s）
構圖：背脊縫隙俯視
內容：光彈沿背脊掀飛骨片於胸腔爆開
補充：泥水碎骨濺向鏡頭，玻璃 HUD 擋住
安全：濺射停於 HUD 層

#### Beat 11（11.0–13.0s）
重點：能量枯竭與虛脫
Blocking：燁程雙膝一軟半跪，能量條急速降至 0%，掌心光紋閃爍
Camera：
- 運鏡：55mm 手持 3%
- 焦段/機位：55mm 胸高
- 對焦：呼吸拉焦掌心→臉部→HUD 能量條
- 快門角：180；拍點：條件轉紅
光影：掌心光紋像故障閃爍，環境亮度降低
色調/LUT：整體轉為冷灰，僅警告紅高飽和
聲音：音場抽空僅留高頻耳鳴＋低頻心跳
轉場：耳鳴化為升級提示音 → Beat 12

Angle 11（11.0–13.0s）
構圖：半身三分線，掌心在前景
內容：燁程半跪能量條歸零
補充：HUD 顯示 Energy 12%→3%→0%，WARNING 閃爍
安全：HUD 文字採簡短英文縮寫

#### Beat 12（13.0–15.0s）
重點：Level Up 覺醒提示
Blocking：視角失焦邊緣變暗，系統視窗彈出 Level Up，金紋加深，燁程露出疲憊笑
Camera：
- 運鏡：主觀視角緩慢晃動→回燁程面部
- 焦段/機位：虛擬 32mm 主觀＋60mm 臉部近景
- 對焦：單點 HUD 視窗→燁程眼神
- 快門角：180；拍點：等級 2 提示亮起
光影：中央視窗亮金，邊緣暗角收束
色調/LUT：HUD 金綠漸層，皮膚暖光回復
聲音：升級提示和聲上揚，耳鳴轉成柔和持音，燁程低語
轉場：定格在燁程堅定眼神 → 黑場

Angle 12A（13.0–14.0s）
構圖：主觀 HUD 置中
內容：`LEVEL UP` `等級 1 → 等級 2` 視窗
補充：右手皮下金線增厚貼骨節
安全：視窗字體大寫英文，中文採系統字

Angle 12B（14.0–15.0s）
構圖：臉部近景，三分線靠右
內容：燁程滿頭汗、血痕，露出疲憊笑
補充：背景獸屍與泥水模糊
安全：面部傷口僅表層擦傷

---

## 聲音層與事件對應
- 環境層：soft_city_air_hum＋森林夜風，Beat 1–4 提升 -10 dB 至 -7 dB；Beat 11 起急速淡出。
- 獸群層：低頻咆哮與骨甲摩擦交替，Beat 10 切為多點爆裂同步 sidechain。
- 魔力層：low_orbital_throb 自 Beat 6 開始與心跳同步，Beat 11 下降 12 dB。
- HUD/UI 層：glassy_beep_mid（提示）、clipped_square_red（警告）、airy_chime_hi（弧線完成），須控於 -14 dB。
- 事件音效時間碼：
  - 1.4s 骨甲摩擦「咔咔」對應殘影錯位。
  - 4.5s 建議彈窗觸發 glassy_beep_mid。
  - 7.6s 每枚光彈裝填叮聲記錄並貼上符號。 
  - 8.2s 曲射啟動 arc_bow_sheen 漸強。
  - 9.2s／9.8s／10.6s 三段命中分別觸發爆裂層並加入命中 UI ping。
  - 12.2s Energy 0% 時觸發 clipped_square_red → 連續 3 次閃爍。
  - 13.4s Level Up 彈窗播放 airy_chime_hi 疊和聲上揚。
- 音樂：96 BPM crystalline_aether_pad 與 holo_keyboard_taps 節奏；Beat 10 提升 2 dB，Beat 11 急降至 -18 dB 保留耳鳴。

## QA Checklist（拍前勾選）
- [ ] 確認 24/35/45/50/65mm 焦段與主觀視角切換時無視差突兀。
- [ ] HUD 文本維持矢量清晰度，警告紅色不溢出線條。
- [ ] 光彈亮度峰值 ≤ 110 nits，命中爆閃時使用 2 frame 自動曝光補償。
- [ ] 血泥濺射以粒子＋HUD 層遮罩處理，避免寫實組織。
- [ ] 音效峰值 -6 dB，整體混音 -14 LUFS，耳鳴頻率控制於 6 kHz。
- [ ] 種子、HUD 動畫緩動、曲射 spline 設定記錄於製片表。

## 交付備註
- 交付格式：16:9｜1920×1080｜24fps｜ProRes 4444 + 分離立體聲 48kHz。
- 請提供 HUD 層與光彈軌跡為可分離 EXR AOV 以利後期校調。
- 能量條與 Level Up 視窗須輸出含透明 Alpha 的額外 pass，方便 UI 版本迭代。
- 建議保留命中段 raw 無 HUD 版本 1 份，以便音效延伸。

# 曲線光彈二次鎖殺 — Master Prompt（15s｜12 幕）

## 一句話題材
燁程背靠岩壁被新一波獵骨獸逼近，掃描骨甲弱點後重構曲線射擊路徑，發出第二發 Curve Bolt 穿入關節連鎖擊倒敵群，同時驚險躲過骨片反撲。

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
Master(15s｜Light Glyph Anime Glyph-Combat｜16:9｜24fps｜霧濕冷藍＋骨甲鐵鏽對比質感)
「夜半濕霧林地岩壁死角；泥漿噴濺、骨甲殘骸、浮動 HUD 鎖定框；燁程喘息背貼岩壁掃描獵骨獸弱點，重塑第二發 Curve Bolt 以弧線穿刺後腿關節。
鏡頭：手持 28mm 近距貼牆→32mm 俯視殘屍→40mm 微移特寫→35mm 頭部歪斜近景→30mm 中景半圓包圍→45mm HUD 疊加視角→55mm 右手特寫→28mm 掌心低角→
60mm 追蹤彎射→70mm 長焦爆裂→48mm 慢動作掠過→52mm 胸近景定格。
表演：燁程肩膀抖動、呼吸急促；掃描時雙眼來回跳動，嘴角緊繃；施法時指尖顫抖，命中後驚嚇反射閃避骨片，最後帶著害怕又振奮的目光自語。
臉型/髮型：黑色半長亂髮被霧水貼額，臉頰帶泥痕與汗水；瞳孔略偏琥珀色。
構圖：前段以三分線壓迫讓怪物從側後逼近；HUD 視角採中央對齊凸顯紅色弱點標記；曲線射擊段讓弧線跨畫面右下至左上；動態：霧雨、泥濺、骨甲碰撞殘影、
掌心光紋逐節點亮、遠林綠眼浮現。
寫實細節：泥水沿岩壁滴落形成細流；倒地獵骨獸骨板外翻鋸齒染鐵鏽橘；關節縫露出暗紅肌肉帶濕亮；HUD 紅圈套住肩頸內腿縫隙；骨片擦過臉頰留細淺血線。
無字幕、無商標/Logo/水印。」

鏡頭語法：28–35 建立壓迫→45–60 HUD 與施法→60–70 長焦爆裂→52 收束；
光圈 {T2.5–T3.2} 保持角色突出，HUD 段收至 {T4} 兼顧浮層；爆裂瞬間降至 {T2.0} 拉出光暈；快門角 {165°} 壓迫段帶殘影，HUD 段收至 {150°}，爆裂後慢動作放寬至 {180°}。
對焦 {層次前→中→後} 從前景泥濺掃至怪物群，再切至單點鎖定 HUD 標記與掌心，光彈飛行採呼吸拉焦追蹤關節爆點。
光影：森林冷藍霧光＋掌心金光雙主光；獵骨獸骨甲反射金綠邊緣；爆裂時白光吞沒畫面並在泥水中折射；色溫 夜 3400K 基底，Curve Bolt 核心升至 5200K。
對比 {中高}，眼神光 {由掌心與 HUD 反射補光}。
色調/LUT：背景霧藍與石灰，骨甲偏灰白帶鐵鏽橘，肌肉暗紅；金色弧線配薄荷藍邊緣；去飽和 5%。
聲音：環境含 soft_city_air_hum 降頻變成低沉風鳴，混入泥水刮擦與骨甲撞擊「咚」聲；HUD 彈出加 airy_chime_hi、glassy_beep_mid；詠唱為低聲咒語混 crystalline_aether_pad；
Curve Bolt 放出伴 arc_bow_sheen 與 low_orbital_throb；骨碎時加入金屬裂聲與泥濺低頻；骨片掠過帶鋒利破風；尾段喘息混遠處新綠眼低吼迴響。
轉場：怪物逼近以泥濺遮擋→俯視殘屍用骨片掠過擦拭→頭部特寫以黏液滴落聲匹配切→半圓包圍時利用殘影錯頻交疊→HUD 上線以光掃羽化→光彈尾跡做動態 wipe→
骨碎後以泥浪遮擋→慢動作骨片掠過採呼吸切→最後以視線停格淡出。
安全：HUD 文字採抽象符號無可讀語；血液以暗紅光膜處理無內臟細節。
```

---

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：放大獵骨獸壓迫與危機未解除
基調：緊張、窒息
節奏域：加速2.4–3.0 → 穩定1.5–2.4
美術要點：濕泥、岩壁、骨甲獵骨獸、鐵鏽色血水

#### Beat 1（0.0–2.4s）
重點：燁程仍被圍困，倒地獵骨獸暴露可怖細節
Blocking：燁程背靠岩壁喘息→鏡頭拉後露出更多獵骨獸→視線落向腳邊倒地屍體
Camera：
- 運鏡：手持貼牆緩慢後退
- 焦段/機位：28mm 胸高近距→32mm 俯視
- 對焦：單點鎖燁程臉→下拉屍體
- 快門角：165；拍點：泥水被爪刮起、視線滑向屍體
光影：冷霧漫射主體＋掌心微光反射臉側
色調/LUT：霧藍背景、骨板灰白、泥水泛鐵銹橘
聲音：濕泥刮擦、喘息、遠處低吼
轉場：屍體骨板邊緣擦過鏡頭做遮擋 → Angle 2

Angle 1（0.0–1.2s）
構圖：燁程右側三分線，左後方怪物殘影逼近
內容：燁程手仍伸出半空，背貼岩壁急喘
補充：泥水被怪物爪拍出小浪，空氣有霧粒漂浮
安全：服飾無 Logo，血液抽象化

Angle 2（1.2–2.4s）
構圖：俯視倒地獵骨獸居中，骨板向外翻
內容：骨板鋸齒交錯包覆，全身沾泥混血
補充：縫隙露出暗紅肌肉，濕泥帶金屬反光
安全：肌肉呈符碼紋理無寫實內臟

#### Beat 2（2.4–5.0s）
重點：展示獵骨獸異形構造與群體壓迫
Blocking：鏡頭掃過前肢與頭部→拉回圍攻隊形→殘影錯頻逼近
Camera：
- 運鏡：滑軌側移搭配手持細抖
- 焦段/機位：40mm 近特寫→35mm 中景
- 對焦：單點交替鎖定爪尖、眼睛、燁程
- 快門角：160；拍點：倒鉤顫抖、眼球螢光
光影：月光逆邊勾骨板，掌心金光補側臉
色調/LUT：骨甲灰白帶鏽橘，眼球螢綠外溢
聲音：倒鉤刮地刺耳「沙」、骨甲碰撞「咚」、錯頻殘影低頻脈衝
轉場：殘影拖尾作鞭移 → Act 2

Angle 3（2.4–3.6s）
構圖：前肢佔畫面左側，倒鉤插泥
內容：關節反向彎折，倒鉤微顫
補充：泥面被劃出同心圓水紋伴刺耳聲效
安全：倒鉤無斷肢血肉細節

Angle 4（3.6–4.4s）
構圖：怪物頭部近景佔右側，燁程模糊在左後
內容：一側眼窩深陷，另一眼螢綠鼓出，口角鋸齒牙外露
補充：黑色黏液滴落地面伴「嗒」聲
安全：黏液無生物性內臟質感

Angle 5（4.4–5.0s）
構圖：中景半圓包圍，燁程中心偏後
內容：三四隻獵骨獸錯頻殘影合圍
補充：骨甲碰撞出節奏錯亂的「咚、咚」迴音
安全：殘影抽象化無多頭重影

### Act 2（5.0–9.0s）
意圖：展現 HUD 分析與 Curve Bolt 路徑構築
基調：緊張中精準冷靜
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：HUD 線框、紅色弱點標記、掌心淡金光紋

#### Beat 3（5.0–7.2s）
重點：HUD 視角掃描出骨甲縫隙弱點
Blocking：視角切入 HUD 疊加→標記關節弱點→燁程視線追隨標籤
Camera：
- 運鏡：穩定器微推
- 焦段/機位：45mm UI 疊視→50mm 半身
- 對焦：單點鎖 HUD 線框→拉回燁程眼神
- 快門角：150；拍點：紅圈亮起、提示文字跳出
光影：HUD 金青描邊發光，背景壓暗
色調/LUT：整體偏冷，紅色警示圈高飽和
聲音：airy_chime_hi 隨標記出現，holo_keyboard_taps 點亮節點
轉場：HUD 框線掃過畫面 → Angle 7

Angle 6（5.0–6.0s）
構圖：主觀視角 HUD 佔全畫面，怪物骨甲線框突出
內容：肩關節、頸側、腿內側標紅圈，提示浮現「裝甲縫隙/結構弱點/建議攻擊路徑」符號體
補充：背景實景降飽和，僅骨甲描邊清晰
安全：文字以符號矩陣呈現

Angle 7（6.0–7.2s）
構圖：燁程右手特寫在左下，HUD 懸浮於右上
內容：淡金光紋沿指骨穩定亮起，燁程在空中勾勒弧線
補充：指尖拉出的光線留下一條細弧形路徑
安全：手背紋路無可讀字

#### Beat 4（7.2–9.0s）
重點：第二發 Curve Bolt 藉預設軌跡飛行
Blocking：掌心光陣轉動→光彈沿弧線貼牆飛行→繞過骨甲接近後腿關節
Camera：
- 運鏡：低角推進追光
- 焦段/機位：28mm 掌心→60mm 尾隨→70mm 長焦關節
- 對焦：單點掌心→呼吸拉焦追光彈→鎖定關節
- 快門角：155；拍點：光陣完成、光彈擦過岩壁
光影：光彈拖出薄金弧線照亮岩壁邊緣
色調/LUT：金色核心搭薄荷藍羽化，背景維持霧藍
聲音：arc_bow_sheen 與 low_orbital_throb 疊加，岩壁擦過帶「滋」聲
轉場：尾跡做光亮 wipe → Act 3

Angle 8（7.2–8.4s）
構圖：掌心位於左下三分線，光陣旋轉在前
內容：掌心小型光陣轉速加快，燁程念咒
補充：光陣符紋穩定發光並投射在臉側
安全：咒語僅口型無字幕

Angle 9（8.4–9.0s）
構圖：鏡頭貼著光彈背後，弧線沿岩壁向右
內容：光彈緊貼先前畫出的軌跡，擦過骨板邊緣
補充：岩壁冒出被灼的細霧，「滋」聲伴火花
安全：無血液噴濺

### Act 3（9.0–15.0s）
意圖：展現命中、連鎖撞擊與燁程驚險餘生
基調：決斷、餘悸
節奏域：穩定1.5–2.4 → 慢入0.8–1.5
美術要點：白光爆裂、泥浪、骨片掠過、遠處綠眼

#### Beat 5（9.0–12.0s）
重點：光彈鑽入後腿關節引發連鎖摔落
Blocking：光彈折向後腿→關節白光爆裂→領頭怪撞倒同伴跌入泥水
Camera：
- 運鏡：長焦橫移配拉焦
- 焦段/機位：70mm 側面→55mm 跟跌落
- 對焦：鎖定關節爆點→拉向倒地兩獸
- 快門角：150；拍點：白光炸裂、泥浪濺起
光影：白光填滿關節，泥浪反射金粉
色調/LUT：爆點純白夾青綠，泥水深褐帶金粒
聲音：骨裂清脆、悶響撞擊、泥水拍擊
轉場：泥浪遮擋 → Beat 6

Angle 10（9.0–10.8s）
構圖：光彈於畫面左側折入關節，右側是骨甲
內容：白光填滿關節，骨片與焦黑肉屑被炸出
補充：粒子在空中化為金粉消散
安全：焦肉以炭化粒子呈現無血腥

Angle 11（10.8–12.0s）
構圖：長焦壓縮，領頭怪倒向同伴
內容：後腿癱軟整隻側翻，撞倒旁邊獵骨獸一同跌進泥水
補充：泥浪與血水混成暗色霧花
安全：血水顏色偏暗紅能量流

#### Beat 6（12.0–15.0s）
重點：骨片掠臉的驚險與燁程對規律的領悟
Blocking：骨片飛向燁程→他側頭閃避臉頰被劃傷→後撤半步看著發光右手→遠處再次亮起綠眼
Camera：
- 運鏡：慢動作推進→穩定器微退
- 焦段/機位：48mm 慢動作→52mm 胸近景
- 對焦：鎖定骨片→切回燁程眼神與手掌
- 快門角：180；拍點：骨片擦過、呢喃台詞
光影：掌心餘光閃爍，遠林綠眼點狀亮起
色調/LUT：回到冷藍基底，臉頰血痕為暖紅
聲音：骨片破風、高頻擦過；燁程喘息與低語「……只要抓到規律，就打得動你們。」；遠處獸吼低迴
轉場：最後停格在眼神 → 結束

Angle 12（12.0–15.0s）
構圖：慢動作特寫骨片從左向右掠過→切至胸近景
內容：骨片擦過臉側劃出淺血痕，燁程蹬牆拉開半步盯著仍發光的手
補充：血滴沿臉線滑落，後景樹林浮現更多狹長綠眼
安全：血痕淺薄無滴落，遠處眼光抽象化

---

## 音訊層級與節奏指引
- 98BPM 混合絃樂與電子節奏，前段以 soft_city_air_hum 降頻營造壓迫脈衝，加入低頻呼吸樣本與骨甲金屬敲擊節奏作鋪陳。
- HUD 段將 airy_chime_hi 與 glassy_beep_mid 作為標記提示，配合 holo_keyboard_taps 點亮每個弱點圈；燁程詠唱採低聲層疊 crystalline_aether_pad 粒子音。
- Curve Bolt 飛行疊 arc_bow_sheen 與 low_orbital_throb，擦過岩壁加細微「滋」字樣高頻；爆裂瞬間加入 white flash hit 與金屬碎裂脆響，泥浪使用低頻衝擊加短暫尾音。
- 骨片掠過時強化高頻破風與血滴聲降混，尾段保留喘息與遠方綠眼低吼，音樂降至 60% 音量突出燁程呢喃。

## 交付備註
- 影格速率 24fps，手持抖動控制在 2% 以維持臨場壓迫但不影響 HUD 閱讀。
- HUD 與提示文字採符號矩陣輸出，禁用可讀語言；血液以能量霧化處理避免寫實血腥。
- Curve Bolt 顏色遵循 style pack：金色核心＋薄荷藍邊緣，骨片高光帶青綠反射以呼應 HUD。

## QA 自檢
- [x] 結構完整：Master、Scene Blocks、音訊、交付、QA 全數就位。
- [x] 敘事一致：時間軸對應十二幕描述，Curve Bolt 第二發軌跡與連鎖反應一致。
- [x] 視聽細節：鏡頭、光影、聲效、VFX 均具體可操作。
- [x] 風格準確：引用 Light Glyph Anime 系列樣板並維持 2D Anime 質感。
- [x] 格式精準：時間標記、幕次層級、標點符合專案規範。
- [x] 安全檢核：移除可讀字樣、血腥弱化、遵循 QA Checklist。

# Light Glyph Anime Intro — Master Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-14_light-glyph-anime-intro_v01/script.md

## 一句話題材
清晨霧環城的護盾裂縫引來骨骸獸，燁龍在高塔邊緣以基底詠唱語施放〈能量彎射〉縫合破口，肩頭米漿輸送星火，共同宣告光迴路術師的正式登場。

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
Master(15s｜Light Glyph Anime｜2.39:1｜24fps｜晨霧光程式質感)
「清晨霧環城高塔邊；冷灰石欄、淡金護盾膜、霧中骨骸獸火花；燁龍啟動透明魔導環以基底語敲出〈能量彎射〉縫合裂縫，米漿跳上肩輸送星火。
鏡頭：開場25mm 滑軌俯瞰霧城→推至塔邊升高，過程以穩定器穿霧，塔頂段落改用32mm 繞肩，施法時 55mm 微推鎖定掌心光軌，命中瞬間 75mm 壓縮遠景。
表演：燁龍由冷靜觀察轉為專注詠唱，口型穩定、眼神鎖定裂縫；米漿慵懶降落後以尾巴星火貼近光晶，心電語氣帶調侃。
臉型/髮型：燁龍黑色短髮微亂、眉上瀏海；米漿圓臉霧霾藍毛、右耳白毛尖。
構圖：三分線置燁龍偏左，護盾裂縫與骨骸獸佔右後景層，留白 15% 讓 HUD 浮層；動態：晨霧流、護盾脈動、手指光軌、星火粒子。
寫實細節：外套內襯銀線沿呼吸脈動、領口符文呼吸亮滅、靴底踏欄拖出淡藍殘影、HUD 玻璃層顯 BaseChant v1.0、骨骸獸骨片崩解成光粉。
無字幕、無商標/Logo/水印。」

鏡頭語法：25 建立空間｜32 塔頂互動｜55 詠唱親密｜75 壓縮遠景；
光圈 {T2.8–T4}；快門角 {165° 施法光束維持清晰，護盾震動段降至150°}；
對焦 {層次前→中→後／單點掌心 HUD／呼吸拉焦裂縫與骨骸獸}。
光影：晨霧散射＋護盾側逆光，魔導環投射薄荷藍補光；色溫 {晨光5200K 混護盾金光4200K}；
對比 {柔中帶高}；眼神光 {保留於光晶反射}。
色調/LUT：陰影霧藍、石材冷灰，膚色暖琥珀、光束金白強調；去飽和 4%。
聲音：soft_city_air_hum 與 crystalline_aether_pad 打底，遠鐘聲 -10 dB，holo_keyboard_taps 對拍手勢，燁龍詠唱男中音 -14 dBFS，curve_bolt_release 與 light_code_dissolve 對齊命中；音樂維持 100BPM 氛圍絃樂輕推。
轉場：霧氣遮擋匹配 → 護盾閃光鞭移 → HUD 字串滑入 → 光束羽化掃過。
安全：無可讀字樣，HUD 以抽象符號顯示；遠景群眾僅霧中剪影。
```

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立霧環城清晨危機與護盾異常
基調：緊張盼望
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：環狀城市霧層、淡金護盾、灰石城牆、骨骸獸剪影

#### Beat 1（0.0–2.2s）
重點：護盾受損、骨骸獸摩擦
Blocking：城市俯視→護盾一角暗下→骨骸獸刮結界
Camera：
- 運鏡：25mm 滑軌俯視推進
- 焦段/機位：25mm 高角往下
- 對焦：層次拉焦護盾→獸爪→火花
- 快門角：165；拍點：火花噴散
光影：晨霧漫射＋護盾金光閃爍
色調/LUT：陰影霧藍、護盾金白加飽和 6%
聲音：soft_city_air_hum、護盾嗡鳴、吱啦刮擦、遠鐘聲
轉場：火花羽化 → Angle 2

Angle 1（0.0–1.1s）
構圖：中央廣角俯視
內容：霧環城全景與護盾暗斑
補充：霧層以 background_mist_scroll 流動
安全：去除文字與旗幟

Angle 2（1.1–2.2s）
構圖：三分線，護盾裂縫偏右
內容：骨骸獸貼附護盾刮擦
補充：light_dust 粒子往下落
安全：骨骸獸細節無過度血腥

#### Beat 2（2.2–5.0s）
重點：守衛呼喊與鏡頭穿霧
Blocking：守衛在霧中示警→鏡頭推升穿過霧層指向高塔
Camera：
- 運鏡：穩定器垂直上升帶側移
- 焦段/機位：28mm 眼高→抬升至半空
- 對焦：呼吸拉焦守衛→霧→塔頂剪影
- 快門角：165；拍點：守衛揮手
光影：霧內散射，遠方高塔沐晨光
色調/LUT：霧灰降低飽和，護盾邊緣金光點亮
聲音：守衛呼喊 -8 dB、風聲帶水氣、鐘聲回音
轉場：霧遮擋 → Act 2

Angle 3（2.2–3.6s）
構圖：三分線，守衛剪影偏左
內容：守衛揮手大喊
補充：霧粒飄動、HUD 警示符號短暫閃爍
安全：HUD 文字改抽象幾何

Angle 4（3.6–5.0s）
構圖：中央仰視，塔尖漸顯
內容：鏡頭穿霧上升看到塔頂輪廓
補充：parallax_glass_hud 淡入指向塔頂
安全：無額外標語

### Act 2（5.0–10.0s）
意圖：建立燁龍專注啟動基底語的流程
基調：冷靜決斷
節奏域：穩定1.5–2.4
美術要點：深藍連帽外套、透明魔導環、BaseChant HUD、晨風

#### Beat 3（5.0–6.6s）
重點：塔頂待命姿態
Blocking：燁龍背對坐在石欄，魔導環浮起等待
Camera：
- 運鏡：32mm 穩定器半圓繞後
- 焦段/機位：32mm 胸高偏後
- 對焦：單點胸前光晶
- 快門角：165；拍點：HUD 亮起
光影：護盾金光反射臉側，晨光背光
色調/LUT：外套深藍保持低飽和、光晶暖白提升
聲音：crystalline_aether_pad、soft_city_air_hum 混合，Ambient 鐘聲遠化
轉場：HUD 畫面滑入 → Beat 4

Angle 5（5.0–6.6s）
構圖：三分線背對，光晶居畫面右上
內容：燁龍坐姿等待，魔導環顯 BaseChant v1.0
補充：HUD_edge_trace 沿外套線條脈動
安全：HUD 文本僅英文模板

#### Beat 4（6.6–8.2s）
重點：啟動基底語輸入
Blocking：燁龍抬眼→手指敲空氣→HUD 顯示語句
Camera：
- 運鏡：55mm 微推貼近面部與手
- 焦段/機位：55mm 眼高
- 對焦：呼吸拉焦眼睛→手勢→HUD 字串
- 快門角：165；拍點：每句詠唱落點
光影：眼睛金線亮起，HUD 薄荷藍補光
色調/LUT：膚色暖琥珀，HUD 金藍對比
聲音：holo_keyboard_taps、glassy_beep_mid 配語句
轉場：語句完成時 HUD 擴散 → Beat 5

Angle 6（6.6–7.4s）
構圖：過肩中近景
內容：燁龍手指在空中敲擊，語法條顯示 `let element = LIGHT;`
補充：glyph_refresh_rate 14 的更新節奏可見
安全：語法僅英文

Angle 7（7.4–8.2s）
構圖：特寫眼睛
內容：虹膜金線啟動
補充：emissive_gold_script 在瞳孔跳動
安全：無

#### Beat 5（8.2–10.0s）
重點：站立預備施法
Blocking：燁龍站起踩上石欄，靴底留殘影
Camera：
- 運鏡：40mm 低角上推
- 焦段/機位：40mm 膝高仰視
- 對焦：單點靴底→手掌
- 快門角：165；拍點：靴底著欄
光影：石欄反射淡金光，領口符文呼吸亮
色調/LUT：石材冷灰，光晶暖白增加
聲音：低頻 rumble 漸升、靴底衝擊聲、airy_chime_hi 在符文亮起時響
轉場：靴底光痕拖尾 → Act 3

Angle 8（8.2–10.0s）
構圖：中央仰視中景
內容：燁龍站立準備施法，靴底淡藍殘影
補充：light_dust 隨風散
安全：無

### Act 3（10.0–15.0s）
意圖：呈現施法命中與角色互動收束
基調：決斷盼望
節奏域：穩定1.5–2.4 → 慢入0.8–1.5
美術要點：彎曲光束、護盾裂縫縫合、骨骸獸解體、米漿星火

#### Beat 6（10.0–12.0s）
重點：光束成形與飛行
Blocking：燁龍掌心拉出光線，弧線越過城牆
Camera：
- 運鏡：55mm 微推後側移 15°
- 焦段/機位：55mm 眼高
- 對焦：層次拉焦手掌→光束→裂縫
- 快門角：150；拍點：光束彎折
光影：光束金白強亮，霧中反射薄荷藍
色調/LUT：光束高光飽和 8%，背景霧藍低飽和
聲音：curve_bolt_release、低頻削弱環境聲
轉場：光束帶出鞭移 → Beat 7

Angle 9（10.0–11.0s）
構圖：三分線過肩
內容：掌心拉出光束起始
補充：spell_vector_trail 帶符文流
安全：無

Angle 10（11.0–12.0s）
構圖：壓縮遠景
內容：光束弧線穿越護盾裂縫
補充：背景骨骸獸被紅框標記
安全：HUD 紅框為抽象幾何

#### Beat 7（12.0–13.2s）
重點：命中縫合護盾
Blocking：光束鑽入骨骸獸→護盾縫合→獸體崩解
Camera：
- 運鏡：75mm 壓縮定格微震
- 焦段/機位：75mm 目標側視
- 對焦：單點裂縫→護盾恢復
- 快門角：150；拍點：護盾閉合
光影：護盾金光從暗處重新鋪滿
色調/LUT：護盾金白亮度提升，骨骸獸化為淡灰光粉
聲音：light_code_dissolve、護盾嗡鳴恢復，環境音回歸
轉場：護盾光波擴散 → Beat 8

Angle 11（12.0–13.2s）
構圖：中央特寫護盾
內容：骨骸獸解體為光粉
補充：light_code_dissolve 粒子向下飄
安全：無

#### Beat 8（13.2–15.0s）
重點：米漿登場輸送能量並收束遠眺
Blocking：米漿跳至肩膀輸送星火→燁龍吐槽後與貓一同望向恢復的護盾，心語落下
Camera：
- 運鏡：50mm 起手稍微拉近後轉 32mm 緩慢拉遠
- 焦段/機位：50mm 眼高啟動→過渡至32mm 背視
- 對焦：呼吸拉焦米漿→光晶→遠方地平線
- 快門角：165；拍點：星火傳輸與內心台詞落點
光影：星火薄荷藍照亮臉側，護盾柔和金光作背光
色調/LUT：毛色霧藍保持柔和，星火偏薄荷、高塔霧灰降飽和，遠天空淡金過門
聲音：purr_riser_glow 疊慵懶 VO，燁龍吐槽 -12 dBFS，內心台詞 -14 dBFS，ambient bed 漸弱留鐘聲尾音
轉場：光晶閃光羽化 → 黑

Angle 12（13.2–15.0s）
構圖：過肩中近景起始→緩慢拉遠背視
內容：米漿落肩輸能、HUD 顯示 Runtime Success，燁龍帶笑吐槽後與她望向恢復完整的護盾
補充：星火粒子旋入光晶後化為 glow_dust_overlay，遠方護盾脈動穩定
安全：HUD 文字抽象化、無額外標語

## Audio Notes（整體）
- 音樂以 100BPM 氛圍絃樂為基底，使用 soft_city_air_hum 與 crystalline_aether_pad 疊層，骨骸獸段落降低中頻留出刮擦聲。
- VO：燁龍詠唱採清晰男中音 -14 dBFS，米漿心電語音 -16 dBFS 帶 0.6s 混響並疊高頻靜電於情緒變化。
- SFX 觸發表：吱啦刮擦（0.6s）、compile_ping（6.9/7.6/8.1s）、靴底衝擊（8.6s）、curve_bolt_release（10.4s）、light_code_dissolve（12.3s）、purr_riser_glow（13.4s）。
- 動態：Limiter 設 -1 dBTP，整體 Loudness -14 LUFS，對話峰值維持 -6 dB，HUD 與鍵擊 -12 dB 以下。

## VFX Notes（整體）
- 背景霧使用 background_mist_scroll 緩速滾動，護盾震動套用 hud_symbol_plane 微幅抖動，裂縫周圍加入 crimson_error 閃爍作為故障提示。
- 光束採 spell_vector_trail，color_mix 以 auric_gold 為核心，薄荷藍作軌跡邊光；符文沿 taper 0.42 跑動並在命中時觸發 light_code_dissolve。
- 米漿星火充能啟動 cat_starflare 0.41，粒子往胸口光晶旋入形成柔和渦流，HUD 彈窗顯示 Runtime Success 以 panel_opacity 0.65 呈現。
- 护盾縫合時啟動 glow_dust_overlay，波紋沿護盾面擴散 0.6s 後收斂，骨骸獸殘骸轉為細粉飄落並融入霧層。

## QA Checklist（自評 10/10）
- [x] 情緒→運鏡：霧城緊張→塔頂冷靜→施法決斷節奏清楚。
- [x] 膚色維持 55–65 IRE，護盾與光束亮度控制避免過曝。
- [x] 轉場完成：霧遮擋、護盾閃光鞭移、HUD 滑入、光束羽化。
- [x] LUT 與光比記錄：陰影霧藍、光束金白、外套銀線脈動同步。
- [x] Audio hook 對齊：鍵擊、詠唱、光束命中、星火輸送皆有標記。
- [x] VFX 設定引用 Light Glyph Anime 預設，HUD 延遲與粒子流向明確。
- [x] 安全檢查：無品牌、無可讀文件、群眾僅霧中剪影。
- [x] 生成參數：2.39:1｜24fps｜15s 與 100BPM 氛圍音樂設定一致。
- [x] 角色造型：燁龍服裝、米漿星紋與星火細節遵循世界觀。
- [x] 文件結構：已內嵌核心模板與 Style Pack，全檔案命名符合規範。

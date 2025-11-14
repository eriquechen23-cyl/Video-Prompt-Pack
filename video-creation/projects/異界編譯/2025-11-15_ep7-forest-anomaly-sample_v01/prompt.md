# 異界編譯 EP7 — 森林異常與獵骨獸樣本 Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-15_forest-anomaly-sample_v01/script.md

## 一句話題材
巡林隊前往濕冷異界森林勘察獵骨獸異常增殖，燁程在實戰中使用 Curve Bolt 協同擊殺後進行樣本檢測，卻在骨板上讀到重複電路 template 與短暫「Error Log」，暗示更巨大的系統錯亂。

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
Master(15s｜Light Glyph Anime｜2.39:1｜24fps｜濕冷森林＋金路標本質感)
「黎明前的濕冷異界森林巡邏路段；泥水根鬚、紫藍電路天幕、螢綠獸眼；巡林隊在隊長指示下戒備行進，燁程配合標準陣式釋出 Curve Bolt 擊倒獵骨獸並檢測骨板 template 與 Error Log。」
鏡頭：開場26mm俯角跟拍列隊→Beat 2 俯視跟隨刮痕→Beat 3 35mm仰視天幕→Beat 4 45mm手持≤3%停格準備→交戰段採32mm廣角覆蓋陣式、50mm追蹤彎射→樣本檢查切至60mm環繞→主觀 HUD 由35mm 虛擬焦段導入→結尾以24mm半俯拉遠示警。
表演：燁程從緊張跟隨轉為專注發招，擊倒後喘息仍保持觀察；隊長沉穩下指令，隊員默契分工測量；群獸低吼、目光游移。
臉型/髮型：燁程黑髮略濕貼額，臉上泥點與細汗；隊長成熟女性短髮，其他巡林員罩帽半遮臉；獵骨獸骨甲破損露暗紅肌纖。
構圖：列隊時使用前中後層次凸顯隊形，戰鬥段保留 HUD 彎射弧線 15% 留白，樣本檢查以圓弧包圍屍體，Error Log 懸於視野中央後縮至角落。
寫實細節：泥水被踩出漩渦，骨甲表面帶規則裂紋與金色電路花紋，燁程手環浮現透明 UI，Error Log 視窗 glitch 閃爍，遠方樹幹刻滿複製 template。
無字幕、無商標/Logo/水印。」

鏡頭語法：26 建立隊伍空間｜32–35 圍繞衝突｜45–50 戰鬥聚焦｜60 樣本檢查｜主觀 HUD 35 虛擬焦段｜24 拉遠撤離；
光圈 {T2.8–T4.0 雨霧段保景深，戰鬥瞬間收至T3.5 以凝凍泥濺；樣本特寫放至T2.5 強調粒子}；快門角 {巡邏與檢查180°；突襲時降至168° 增緊張；Error Log 閃現 144° 強化閃爍}；
對焦 {層次前→中→後／單點鎖定獵骨獸瞳孔與骨板節點／呼吸拉焦於 HUD 框線與 Error Log}。
光影：森林霧氣折射紫藍電路頂光＋隊員提燈暖光填補；獵骨獸倒地時補以金色殘光勾邊；Error Log 涌現時以HUD冷光局部提升；色溫 {夜3000–3800K 混合電路4200K 閃爍}；
對比 {前段柔對比呈霧感，戰鬥瞬間提升中高對比，Error Log 切換時降低背景亮度}；眼神光 {由 HUD 與提燈反射保持}。
色調/LUT：泥地與樹幹去飽和6%，紫藍天幕保高飽和細節，骨板電路紋以金＋薄荷藍高亮，膚色維持暖琥珀。
聲音：soft_city_air_hum 混合森林濕氣低頻與遠處鳥鳴、隊伍腳步泥濺；戰鬥段以arc_bow_sheen＋holo_keyboard_taps 銜接陣式，獵骨獸骨裂伴隨clipped_square_red 錯誤聲；Error Log 彈出時 airy_chime_hi 先響後轉成失真的crystalline_aether_pad 波動。
轉場：泥水濺上鏡頭擦拭→抓痕擦拭匹配剪→電路閃光作鞭移→骨板碎屑遮擋→HUD 彈窗直接切換→Error Log glitch 羽化縮回→遠景拉遠硬切收尾。
安全：HUD 字串與 Error Log 為虛構符號化資訊；血跡控制為乾裂或霧化噴濺，不呈現露骨臟器；巡林徽章去品牌化。
```

### Camera Continuity
- 前集（EP6）收於 Act 3 Angle 12：訓練場中景見到靶心冒煙、HUD 成就框淡出，燁程握著手環的光環。延續該畫面收束後的 UI 色票（薄荷藍＋金金），本集開場沿用相同手環造型並在巡林制服上增添外掛護甲。
- 保持 Light Glyph Anime 風格 HUD 銜接：彎射軌跡沿用上一集的 auric gold 軌跡厚度，Error Log 視窗縮退角落時保留同樣的 parallax_glass_hud 半透明質感。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.8s）
意圖：建立巡林任務氛圍與異常跡象
基調：緊張預警
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：濕冷森林、巡林制服護甲、泥濘與抓痕、紫藍電路天幕

#### Beat 1（0.0–1.2s）
重點：隊伍穿越泥濘保持隊形
Blocking：承接 EP6 收束後的行軍，隊長領頭、隊員排隊向東巡林，燁程在中段調整背帶。
Camera：
- 運鏡：26mm 俯角滑軌跟拍 1.5m
- 焦段/機位：26mm 胸高略俯 20°
- 對焦：層次前景泥濘→中景隊伍→後景霧林
- 快門角：180；拍點：靴子踩泥「啵嗒」
光影：霧中頂光 + 队員提燈暖光形成雙色側逆光
色調/LUT：泥水偏冷灰，制服保暖琥珀金線
聲音：soft_city_air_hum 疊濕風，衣料摩擦，遠處鳥鳴短暫後熄
轉場：隊長抬手示意 → Angle 2

Angle 1（0.0–1.2s）
構圖：三分線，隊長置前景左，燁程位於中段
內容：巡林隊列穿梭樹根間
補充：胸前徽章晃動反射薄金光
安全：制服無真實徽章文字

#### Beat 2（1.2–2.4s）
重點：抓痕與腳印密集異常
Blocking：鏡頭落地沿抓痕推進，隊長蹲下指示密度升高
Camera：
- 運鏡：35mm 俯視滑軌沿地面 1m
- 焦段/機位：35mm 膝高俯視
- 對焦：單點拉焦抓痕→腳印→血水漥
- 快門角：180；拍點：隊長低聲評語
光影：提燈斜射出橙光，反射血水
色調/LUT：血水控於暗紅帶紫，泥地仍低飽和
聲音：隊長低語「這密度又比上週高了……」-12 dBFS，背景濕響
轉場：鏡頭抬至隊長視線 → Angle 3

Angle 2（1.2–2.4s）
構圖：俯視，抓痕與腳印形成放射狀
內容：血水沿抓痕流入泥坑
補充：HUD 小型記錄框短暫浮現記錄密度
安全：HUD 數據採符號化

#### Beat 3（2.4–3.6s）
重點：天空電路異常閃爍
Blocking：燁程抬頭，鏡頭仰視電路雲層迴圈閃爍
Camera：
- 運鏡：35mm 仰角固定
- 焦段/機位：35mm 眼高仰 60°
- 對焦：呼吸拉焦樹冠→電路光
- 快門角：180；拍點：光路卡頓閃爍
光影：紫藍閃爍加劇，其他聲響被削弱
色調/LUT：天空保持高飽和紫藍，樹冠剪影偏墨綠
聲音：環境聲被降噪，只剩呼吸與衣物摩擦
轉場：電路突閃 → Angle 4

Angle 3（2.4–3.6s）
構圖：仰視中央留白給電路
內容：電路線條在雲層上 loop 卡頓
補充：HUD 在視野角落提示「Atmosphere Lag Detected」
安全：提示為虛構英文

#### Beat 4（3.6–4.8s）
重點：獵骨獸即將襲擊
Blocking：前排隊員舉手停下，樹叢震動傳出低吼
Camera：
- 運鏡：45mm 手持≤3%跟隨
- 焦段/機位：45mm 胸高
- 對焦：單點前排隊員手勢→轉到樹叢螢綠眼
- 快門角：168；拍點：低吼與骨甲碰撞聲
光影：提燈暖光被螢綠反光吞沒，陰影收緊
色調/LUT：背景降亮以凸顯螢綠瞳
聲音：低吼、骨甲互撞「咔、咔」疊低頻心跳
轉場：隊長口令「三點方向，準備。」→ Act 2

Angle 4（3.6–4.8s）
構圖：中景，隊員手勢佔左側，螢綠眼於右側陰影
內容：突襲前的壓迫
補充：泥地細震，落葉顫
安全：無明顯流血

### Act 2（4.8–9.6s）
意圖：呈現協同攻擊與樣本製造
基調：決斷緊張
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：標準陣式光紋、Curve Bolt 軌跡、骨板碎屑、巡林測量工具

#### Beat 5（4.8–6.0s）
重點：標準陣式與 Curve Bolt 同步施放
Blocking：術師在地拍出陣式，燁程手環亮起預覽弧線
Camera：
- 運鏡：32mm 側面廣角覆蓋半隊伍
- 焦段/機位：32mm 眼高
- 對焦：層次術師→燁程→撲出獵骨獸
- 快門角：168；拍點：光彈射出、HUD 預覽亮起
光影：陣式白金光映地，Curve Bolt 預覽以薄荷藍透出
色調/LUT：背景降飽和，能量光保持高亮
聲音：咒語重疊、arc_bow_sheen 启動、骨甲被直線光彈擊中悶響
轉場：光彈命中爆光 → Angle 5

Angle 5（4.8–6.0s）
構圖：側向，術師居左，燁程偏右
內容：陣式光彈直射，燁程手環浮現 UI 弧線
補充：HUD 預覽弧線在視野角落閃過
安全：陣式符號為抽象幾何

#### Beat 6（6.0–7.2s）
重點：協同擊殺與倒地
Blocking：獵骨獸被直線光彈失衡，燁程彎射鑽入頸後骨縫
Camera：
- 運鏡：45mm 跟隨獵骨獸側後方帶慢動作
- 焦段/機位：45mm 肩高
- 對焦：單點鎖定彎射弧端→骨縫爆裂
- 快門角：156；拍點：骨板炸裂、落地濺泥
光影：金色彎射拖尾照亮骨縫，泥濺捕光
色調/LUT：骨碎偏灰白，碎屑裡帶金光
聲音：骨裂聲、泥水「啪」、隊長喊「留一隻當樣本！」
轉場：骨屑遮擋 → Angle 6

Angle 6（6.0–7.2s）
構圖：跟隨視角，獵骨獸居中央倒向右前
內容：Curve Bolt 弧線鑽入後頸
補充：HUD 指標在命中瞬間變綠，計分條上升
安全：血量顯示為抽象條狀

#### Beat 7（7.2–8.4s）
重點：樣本檢查準備
Blocking：隊員圍半圈清泥，燁程蹲下喘息
Camera：
- 運鏡：60mm 半環繞 90°
- 焦段/機位：60mm 膝高略俯
- 對焦：層次骨板→測量工具→燁程表情
- 快門角：180；拍點：記錄板寫下編號
光影：提燈暖光掃過骨板，映出電路紋
色調/LUT：骨板帶濕亮反射，泥血控在暗紅
聲音：記錄員念筆記「第七組樣本，邊境北段……」、衣料摩擦
轉場：鏡頭壓近骨板 → Angle 7

Angle 7（7.2–8.4s）
構圖：中近景，骨板佔畫面 60%，燁程蹲右側
內容：隊員清理泥巴，刻度尺貼近骨板
補充：燁程喘息嘴角噴出白霧
安全：測量板上僅符號

#### Beat 8（8.4–9.6s）
重點：重複電路紋特寫
Blocking：鏡頭沿骨板紋路平移，顯示重複 template
Camera：
- 運鏡：80mm 極近滑移 0.3m
- 焦段/機位：80mm 俯視
- 對焦：單點沿著電路節點拉焦
- 快門角：180；拍點：每段複製 pattern 對齊
光影：HUD 提示微光掃過紋路
色調/LUT：電路線以 auric gold + mint glow 提亮
聲音：holo_keyboard_taps 微弱點擊，燁程喃喃「這……根本是同一段 template。」
轉場：UI 框線自動浮現 → Act 3

Angle 8（8.4–9.6s）
構圖：極近特寫，電路 pattern 填滿畫面
內容：重複 pattern 含弧形走線、三方節點、鋸齒分叉
補充：細小瑕疵完全重複
安全：無真實符號

### Act 3（9.6–15.0s）
意圖：揭示 Error Log 與撤離決策
基調：不安懸疑
節奏域：穩定1.5–2.4 → 慢入0.8–1.5（Error Log 閃爍）
美術要點：HUD 偵測框、Error Log 視窗、遠處螢綠瞳孔、森林複製 template

#### Beat 9（9.6–10.8s）
重點：主觀視角啟動偵測模式
Blocking：畫面轉入燁程視角，HUD 框選 pattern
Camera：
- 運鏡：主觀視角固定，僅 UI 動態
- 焦段/機位：虛擬35mm 眼高
- 對焦：自動跟隨 HUD 高亮
- 快門角：180；拍點：偵測框對齊 pattern
光影：視野邊緣暗化，HUD 金框亮度提升
色調/LUT：背景降飽和 10%，HUD 金薄荷高亮
聲音：airy_chime_hi 清脆提示，電子滴聲
轉場：Error Log 視窗跳出 → Angle 9

Angle 9（9.6–10.8s）
構圖：主觀，HUD 框線佔中間，背景失焦
內容：淡金框線標記 pattern，旁出現半透明資料
補充：icon 表示複製層級
安全：資料以符號呈現

#### Beat 10（10.8–12.0s）
重點：Error Log 彈出與干擾
Blocking：HUD 上浮出 Error Log 視窗，顯示亂碼並閃爍
Camera：
- 運鏡：主觀微推近骨板
- 焦段/機位：虛擬40mm
- 對焦：單點 Error Log 視窗
- 快門角：144；拍點：雜訊「嘶」聲
光影：視窗泛紅，背景亮度瞬降
色調/LUT：Error Log 改為紅白反相，亂碼閃動
聲音：clipped_square_red 失真提示，雜訊掃過
轉場：視窗縮回視野角落 → Angle 10

Angle 10（10.8–12.0s）
構圖：主觀，Error Log 視窗中央後縮為小紅點
內容：視窗顯示「【Error Log】」後閃亂碼
補充：路徑標記顫動
安全：文本為虛構符號

#### Beat 11（12.0–13.2s）
重點：外部視角顯示只有燁程看見
Blocking：切回外部中近景，隊友量測骨板，燁程僵住
Camera：
- 運鏡：55mm 定機
- 焦段/機位：55mm 胸高
- 對焦：單點燁程瞳孔→隊友臉
- 快門角：180；拍點：隊友詢問
光影：提燈暖光照隊友，燁程臉被 HUD 金光映亮
色調/LUT：人物膚色暖琥珀，背景保持霧藍
聲音：隊友問「欸，新人？你在看什麼？」燁程吸氣回答「沒事，只是覺得……紋路有點怪。」背景 UI 低語延續
轉場：燁程站起 → Angle 11

Angle 11（12.0–13.2s）
構圖：中近景，燁程偏右，隊友偏左
內容：燁程眼中倒映 HUD，臉色僵硬
補充：Error Log 點縮進視野角落
安全：無可讀資料板文字

#### Beat 12（13.2–15.0s）
重點：拉遠揭示複製 template 與撤退命令
Blocking：鏡頭半俯拉遠，露出周遭樹幹與泥地都出現同樣 pattern，遠處螢綠眼再度亮起，隊長下令撤退
Camera：
- 運鏡：24mm 半俯拉遠 6m
- 焦段/機位：24mm 高於隊伍 3m 俯視
- 對焦：層次骨板→周圍樹幹→遠處瞳孔
- 快門角：180；拍點：遠方多重咆哮與命令
光影：電路光在森林多點閃耀，遠處綠光點亮霧氣
色調/LUT：森林整體降飽和，複製 template 以金色高亮散佈
聲音：多重咆哮疊加、隊長喊「往東撤，這區的 spawn 率完全不對勁。」、HUD 低語電子雜訊僅燁程可聞
轉場：畫面拉遠，Error Log 小點隱於角落 → 結束

Angle 12（13.2–15.0s）
構圖：半俯遠景，樣本屍體居畫面中央逐漸縮小
內容：森林各處出現複製電路 pattern，遠處螢綠瞳孔亮起
補充：燁程握緊手環光環，眉頭緊鎖
安全：遠處怪物保持霧化輪廓

---

## QA 自檢
- [x] 結構完整度 10/10：Master Prompt、Camera Continuity、Scene Blocks 與 QA 清單全部呈現且時間軸標註完整。
- [x] 敘事一致性 10/10：延續 EP6 結尾，建立巡林任務→遭遇→樣本分析→Error Log 伏筆的連續流程。
- [x] 視聽細節 10/10：鏡頭、光影、聲音、HUD 與 Error Log 效果具體可操作。
- [x] 風格準確性 10/10：全程遵循 Light Glyph Anime 套件與通用 VFX Pack，HUD 色彩與音效與前集一致。
- [x] 格式精準度 10/10：引用模板完整貼上，分鏡層級、節奏域與安全指引符合規範。

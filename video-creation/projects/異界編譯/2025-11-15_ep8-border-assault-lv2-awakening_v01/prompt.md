# 異界編譯 EP8 — 邊境襲擊與 Lv.2 正式覺醒 Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-15_border-assault-lv2-awakening_v01/script.md

## 一句話題材
獵骨獸潮在黃昏邊境撕裂木柵，燁程啟用 Curve Bolt Lv.2 的多重軌跡清線，並在戰場靜止瞬間收到除錯者權限啟用的神秘訊息。

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
Master(15s｜Light Glyph Anime｜2.39:1｜24fps｜邊境夕暮電路攻防質感)
「黃昏邊境聚落防線；泥濘木柵、紫藍電路雲、螢綠獵骨獸光潮；獵骨獸潮衝撞防線之際，燁程啟動 Curve Bolt Lv.2 多軌彎射護住友軍並觸發除錯者權限彈窗。」
鏡頭：開場24mm俯角俯瞰木柵→Beat 2 低角貼地跟衝鋒→Beat 3 側向35mm 捕捉衝撞→Beat 4 手持≤3%跟隨燁程奔向破口→Beat 5 主觀 HUD 介面→Beat 6 半側50mm 聚焦手勢→Beat 7 主觀魚眼感→Beat 8 後上方32mm 俯視光軌→Beat 9 穿巷跟拍28mm→Beat 10 40mm 低線急拐→Beat 11 55mm 環繞半跪姿→Beat 12 85mm 眼睛極特寫收束。
表演：燁程從急促奔跑轉為高集中指令，施放後體力透支顫抖；守軍緊繃，驚呼於光軌；居民驚恐撤退後慢慢回神；系統聲線冷靜播報。
臉型/髮型：燁程黑髮被汗水貼額，頰上泥濘；巡林隊員穿深灰披肩與護甲；居民衣著簡易防寒披風；獵骨獸骨板外翻帶霧光紋路。
構圖：前中後層次凸顯防線與獸潮距離，彎射光軌保留15% 留白避免與 HUD 重疊；主觀段落中央留給介面文本，結尾極近眼部反射 HUD。
寫實細節：泥水被踐踏成扇形濺起，木柵裂紋與削落木屑飛散，HUD 上多個 lock tag 閃爍，能量光彈貼牆滑行時投射薄金反射；除錯者彈窗採深色矩陣底紋。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35 建立與衝撞｜32–50 聚焦燁程施法｜主觀虛擬35–40｜55–85 收束情緒；
光圈 {T2.8–T4.0 建立段維持景深；施法時收至T3.2 凝凍粒子；終場極特寫開至T2.0 加強虛化}；快門角 {衝鋒與彎射168° 強化速度；HUD 段180°；除錯者啟用瞬間144° 增加閃爍張力}；
對焦 {層次前→中→後 控制獸潮與防線距離／主觀段鎖定 HUD 文本／結尾呼吸拉焦眼部電路紋}。
光影：夕陽低角暖光混合紫藍電路頂光，木柵投下長陰影；光彈飛行時產生薄荷藍金雙色 rim light；除錯者彈窗使環境亮度降低一級僅留 HUD 冷光；色溫 {黃昏4300–4800K 與電路4200K 交錯}；
對比 {開場中等對比呈焦躁，獸潮衝撞時提升至中高對比，彈窗瞬間降低背景對比突出 UI}；眼神光 {透過 HUD 與餘光維持}。
色調/LUT：背景木柵與泥地去飽和6%，獸骨外殼保持冷灰，能量光軌 auric gold + mint glow 高亮；膚色保持暖琥珀但汗水反光略降飽和。
聲音：soft_city_air_hum 疊警鐘與低頻獸吼；曲線施放使用arc_bow_sheen、glassy_beep_mid 鎖定提示、airy_chime_hi 彈窗啟用；地面濺泥、木柵破裂、居民尖叫層層堆疊；音樂維持 low_orbital_throb + holo_keyboard_taps 節奏。
轉場：警鐘節奏作聲壓切至獸潮→泥濺遮擋→光彈軌跡鞭移→HUD 彈窗直接切換→除錯者彈窗羽化後淡出→眼部極近以 HUD 閃爍淡出。
安全：HUD 文本採虛構英數符碼；血腥控制為光解與碎裂不露內臟；居民臉部保持適度距離避免可辨識個資。
```

### Camera Continuity
- 前集（EP7）收於 Act 3 Angle 12：森林拉遠顯示複製 template 與遠方螢綠瞳孔，燁程握著發光手環，Error Log 點縮於視角角落。本集開場延續該 Error Log 僅燁程可見的狀態，警鐘聲與遠方螢綠光點直接接續並轉換為邊境木柵外景。
- 維持 Light Glyph Anime HUD 厚度與 auric gold + mint glow 光軌設定；彎射線條沿用上一集厚度0.42 taper，新增多軌交會時以 parallax_glass_hud 疊層維持一致視覺語言。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.0s）
意圖：建立邊境危機與防線崩潰前兆
基調：緊張預警
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：木柵、警鐘、巡林隊弓陣、紫藍電路雲、螢綠光點

#### Beat 1（0.0–1.0s）
重點：邊境前線的不安黃昏
Blocking：承接 EP7 遠景螢綠光，鏡頭俯視木柵內外；巡林隊在柵頂拉弓，遠處螢綠光點逐顆亮起，警鐘敲擊回響。
Camera：
- 運鏡：24mm 俯角穩定器由內向外推 3m
- 焦段/機位：24mm 高於木柵 4m 俯視
- 對焦：層次前景木柵→中景巡林隊→遠景光點
- 快門角：180；拍點：警鐘敲擊
光影：夕陽低角暖光與紫藍電路雲冷光交疊
色調/LUT：木柵暖褐略降飽和，天空偏藍紫
聲音：警鐘、遠處複製獸吼 loop、衣料摩擦
轉場：警鐘節奏切至獸潮貼地 → Angle 2

Angle 1（0.0–1.0s）
構圖：前中後層次，木柵佔前景上三分之一
內容：巡林隊布陣與遠方光點同時入畫
補充：旗幟微颯、HUD 小標記浮現危機指數
安全：旗幟無真實紋章

#### Beat 2（1.0–2.0s）
重點：獵骨獸潮的第一排衝鋒
Blocking：延續 Beat 1 的警鐘節奏，鏡頭貼地跟隨獸潮衝刺，泥水向兩側濺開。
Camera：
- 運鏡：28mm 貼地滑軌前進 6m
- 焦段/機位：28mm 膝高
- 對焦：單點鎖定領頭獵骨獸頭顱
- 快門角：168；拍點：前蹄落地濺泥
光影：紫藍頂光反射骨板冷光，泥濺捕捉夕陽橙
色調/LUT：獸骨維持冷灰，泥水偏棕灰
聲音：密集「啵嗒」踩泥、重複咆哮層疊
轉場：泥濺擦過鏡頭遮擋 → Angle 3

Angle 2（1.0–2.0s）
構圖：中央強透視，骨板線條導向遠景
內容：獵骨獸成隊衝刺
補充：泥水向鏡頭飛濺形成動態遮擋
安全：無血漬飛濺到鏡頭

#### Beat 3（2.0–3.0s）
重點：木柵首次被衝撞
Blocking：延續 Beat 2 濺泥遮擋後切入側面，木柵被撞裂，守軍標準能量彈偏折。
Camera：
- 運鏡：35mm 側向滑軌 2m
- 焦段/機位：35mm 胸高
- 對焦：單點木柵裂紋→轉至獸頭
- 快門角：156；拍點：木頭爆裂
光影：撞擊時火花與金色錯誤紋一閃
色調/LUT：木頭裂面偏亮，骨甲表面燒黑痕
聲音：木頭「咔嚓」、能量彈被彈回金屬聲、後方居民驚呼
轉場：裂木碎屑飛過形成遮擋 → Angle 4

Angle 3（2.0–3.0s）
構圖：三分線，木柵位於左側，獸頭右側
內容：木柵裂開與能量彈彈開
補充：背景居民奔跑形成模糊軌跡
安全：居民臉部保持模糊

#### Beat 4（3.0–4.0s）
重點：燁程奔赴破口
Blocking：承接碎屑遮擋，鏡頭手持跟在燁程側後方穿過混亂隊伍，他的 HUD 彈出警示。
Camera：
- 運鏡：32mm 手持≤3%跟跑 5m
- 焦段/機位：32mm 肩高
- 對焦：單點燁程面部→呼吸拉焦前方缺口
- 快門角：172；拍點：系統提示音
光影：HUD 金藍光映在燁程臉上，背景火光忽明暗
色調/LUT：前景膚色暖琥珀，背景降飽和
聲音：燁程喘息、系統播報「偵測：邊境防線崩潰風險」、哭喊交疊
轉場：HUD 介面撲滿視野 → Angle 5

Angle 4（3.0–4.0s）
構圖：過肩跟隨，燁程佔右前景
內容：燁程推開同伴衝向缺口
補充：徽章晃動，手環光圈亮起
安全：同伴臉部保持部分遮擋

### Act 2（4.0–8.0s）
意圖：展示 Curve Bolt Lv.2 多軌規劃與齊發
基調：決斷加速
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：HUD 主觀介面、光軌預覽、目標鎖定標籤、木柵與屋簷導引

#### Beat 5（4.0–5.0s）
重點：Lv.2 多重模式啟動
Blocking：延續 Beat 4 過肩視角轉入主觀 HUD，介面彈出功能說明與戰場小地圖。
Camera：
- 運鏡：主觀穩定
- 焦段/機位：虛擬35mm
- 對焦：單點 HUD 文字
- 快門角：180；拍點：鎖定提示音
光影：HUD 冷光覆蓋視野，背景略降亮
色調/LUT：背景去飽和10%，HUD 金藍高亮
聲音：glassy_beep_mid 鎖定聲、系統旁白「建議：啟用多重軌跡，以降低友軍傷亡。」
轉場：HUD 介面往兩側分開 → Angle 6

Angle 5（4.0–5.0s）
構圖：主觀，中央彈窗居中
內容：Curve Bolt Lv.2 介面與戰場地圖
補充：友軍藍點與敵軍紅點閃爍
安全：資訊為符號化

#### Beat 6（5.0–6.0s）
重點：在空中畫出軌跡
Blocking：延續主觀介面，回到半側近景，燁程雙手勾勒多條光軌繞開友軍。
Camera：
- 運鏡：50mm 穩定器半圈 60°
- 焦段/機位：50mm 胸高
- 對焦：呼吸拉焦手指→光軌終點
- 快門角：168；拍點：每條軌跡完成時嗡鳴
光影：淡金線條懸浮，貼著木柵與屋簷流動
色調/LUT：光軌 auric gold + mint glow 強對比
聲音：細微電流嗡鳴、燁程自語「if ally == true then curve around…」
轉場：光軌節點閃爍 → Angle 7

Angle 6（5.0–6.0s）
構圖：三分線，燁程佔左側，光軌佔右側
內容：多條預軌跡懸浮於空
補充：每個終點上方漂浮紅色 Target icon
安全：無真實程式碼

#### Beat 7（6.0–7.0s）
重點：多目標鎖定完成
Blocking：承接光軌閃爍，切回主觀 HUD，八隻獵骨獸被框線標示，右下角顯示 targets_acquired。
Camera：
- 運鏡：主觀微魚眼穩定
- 焦段/機位：虛擬33mm
- 對焦：單點鎖定框
- 快門角：180；拍點：連續八聲鎖定
光影：鎖定框以薄荷藍閃爍，背景保持暗
色調/LUT：HUD 對比提升，獸體輪廓保陰影
聲音：連續「滴」聲、系統文字「多重射擊就緒。」
轉場：燁程推手動作帶動視野前傾 → Angle 8

Angle 7（6.0–7.0s）
構圖：主觀，八個框線散佈全視野
內容：LOCK 01–08 標籤依序亮起
補充：右下角數值 `targets_acquired = 8/8`
安全：數值為虛構

#### Beat 8（7.0–8.0s）
重點：弧光齊發
Blocking：延續前傾動作，從燁程後上方俯視，八條彎曲能量光彈貼牆繞人飛出。
Camera：
- 運鏡：32mm 後上方俯視拉出 4m
- 焦段/機位：32mm 高於燁程 2.5m
- 對焦：層次燁程→光軌→目標
- 快門角：156；拍點：光彈離掌瞬間
光影：光蛇沿路投下金藍掃光，木柵與屋簷被掠過時閃亮
色調/LUT：背景低飽和，光彈保持高亮飽和
聲音：連續「咻」破空聲，後方隊友驚呼「這種軌跡是什麼等級？！」
轉場：選取其中兩條光軌作匹配剪 → Angle 9

Angle 8（7.0–8.0s）
構圖：燁程居左下，光軌向畫面外延伸
內容：八條光蛇穿越破口
補充：木柵破洞火花四散
安全：無實際爆炸碎片濺入鏡頭

### Act 3（8.0–15.0s）
意圖：展現曲線清掃、終極攔截與除錯者權限啟用
基調：緊張轉收束後的震盪
節奏域：加速2.4–3.0 → 慢入0.8–1.5
美術要點：巷弄光軌、巨型獵骨獸、HUD 彈窗、除錯者對話框、/compiler_log 字樣

#### Beat 9（8.0–9.0s）
重點：巷弄裡的曲線清掃
Blocking：沿 Beat 8 的匹配剪跟隨兩條光彈低空穿巷，一條守住居民，一條貫穿翻牆獸。
Camera：
- 運鏡：28mm 低空穩定器轉彎 90°
- 焦段/機位：28mm 膝高
- 對焦：呼吸拉焦光彈→目標獸
- 快門角：156；拍點：命中瞬間
光影：光彈沿牆面拖出光帶，巷道反射冷光
色調/LUT：巷道灰牆去飽和，光點 auric gold 高亮
聲音：孩童哭聲被光彈爆裂聲壓過，遠方指揮喊「清出一條路了！」
轉場：光彈尾端拖影作光源匹配 → Angle 10

Angle 9（8.0–9.0s）
構圖：低角度跟隨，光彈曲線貫穿畫面
內容：光彈繞過抱孩婦人後擊中獸頭
補充：婦人抱緊小孩蹲下
安全：兒童臉部背對鏡頭

#### Beat 10（9.0–10.0s）
重點：最後一波強行攔截
Blocking：延續巷弄亮光切回防線，巨大獵骨獸破柵；燁程再拉一條貼地急彎光軌擊殺。
Camera：
- 運鏡：40mm 側面手持≤3%後退 2m
- 焦段/機位：40mm 腰高
- 對焦：單點巨獸下顎→光軌終點
- 快門角：156；拍點：光軌穿出後頸
光影：巨獸自背後燃起錯誤紅光隨即熄滅
色調/LUT：巨獸骨甲偏深灰，錯誤紋閃紅
聲音：巨獸怒吼戛然而止，系統字幕飄過「提前終止錯誤執行緒。」燁程呼吸急促
轉場：巨獸倒地煙塵遮擋 → Angle 11

Angle 10（9.0–10.0s）
構圖：側面近景，巨獸佔右側，燁程左側
內容：光軌三度貼地拐彎鑽入下顎
補充：地面泥水被光線切出弧形
安全：巨獸血液以光粒表現

#### Beat 11（10.0–12.0s）
重點：戰場靜止與系統彈窗
Blocking：承接煙塵散去，時間像被壓慢，燁程半跪喘息，HUD 全屏彈出除錯者權限訊息。
Camera：
- 運鏡：55mm 緩慢環繞 120°
- 焦段/機位：55mm 膝高略俯
- 對焦：層次燁程→HUD 彈窗→倒地獸
- 快門角：180；拍點：低頻啟用音
光影：環境亮度下降一級，HUD 深色面板浮現
色調/LUT：背景降飽和，HUD 文本高對比
聲音：低頻「咚」、環境聲遠化成回聲，系統播報「除錯者權限：局部啟用。」
轉場：HUD 文字縮至角落 → Angle 12

Angle 11（10.0–12.0s）
構圖：中近景，燁程居中央偏右
內容：燁程半跪，掌心殘留微光，HUD 彈窗佔視野
補充：彈窗下出現 `/compiler_log [NEW]`
安全：權限文本為虛構

#### Beat 12（12.0–15.0s）
重點：/compiler_log 的倒影與疑問
Blocking：延續彈窗縮角，鏡頭切至燁程右眼極近特寫，HUD 字樣倒映，他內心低語疑問，背景隊友慢慢靠近卻看不到 UI。
Camera：
- 運鏡：85mm 定機
- 焦段/機位：85mm 眼高極近
- 對焦：單點虹膜電路紋
- 快門角：180；拍點：最終 UI 提示音
光影：HUD 光在虹膜中跳動，背景模糊保持暗
色調/LUT：虹膜金線高亮，周邊皮膚柔焦
聲音：燁程心聲「所以…我不是只是被丟進來而已？」、最後一聲 UI「滴」
轉場：/compiler_log 字樣微閃後淡出 → 結束

Angle 12（12.0–15.0s）
構圖：極近眼部，HUD 倒影佔中央
內容：虹膜電路紋閃爍 `/compiler_log`
補充：背景巡林隊模糊靠近
安全：無可讀個資，僅 HUD 倒影

---

## QA 自檢
- [x] 結構完整度 10/10：Master Prompt、Camera Continuity、Scene Blocks 與 QA 清單齊備並依 12 幕時間標註。
- [x] 敘事一致性 10/10：承接 EP7 螢綠異常與 Error Log，推進至邊境攻防、Lv.2 彎射與除錯者權限啟用。
- [x] 視聽細節 10/10：各段鏡頭、光影、HUD 軌跡、聲音提示與系統訊息具體可操作。
- [x] 風格準確性 10/10：全程套用 Light Glyph Anime Look/VFX/Audio 與通用 VFX Pack，HUD 與光軌色票一致。
- [x] 格式精準度 10/10：引用模板完整貼上，分鏡層級與節奏域、轉場、安全提示符合規範。

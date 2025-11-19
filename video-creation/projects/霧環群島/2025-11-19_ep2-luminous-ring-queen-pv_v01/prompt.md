# 霧環群島 EP2 — 夕輝聖環女王・艾爾薇恩 登場 PV Prompt（15s｜12 幕）

來源設定：黃昏光明試煉 BOSS「夕輝聖環女王・艾爾薇恩」12 幕 15 秒登場 PV 指南。

## 一句話題材
燃光草原被鎖進永恆黃昏，挑戰者踏入聖環石圈，迎來夕輝聖環女王・艾爾薇恩的審視：草尖點亮、權杖落地、光環庇護與黃昏誓約交錯，最終以「光只照出真相」的宣告開啟試煉。

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
### Style Pack：Twilight Luminous Sanctum Look（新樣板）
```yaml
name: Twilight Luminous Sanctum Look
color_palette:
  primaries: [sunset_amber, warm_ivory, meadow_green]
  accents: [soft_celadon, pearlescent_gold, dawn_blush]
lighting:
  key: horizon_band_softbox (4300–4700K)
  fill: grass_bounce_warm_green (4800K diffused)
  rim: halo_arc_backlight (5200K narrow)
exposure: slightly_over_by_0.4_stop
contrast_profile: gentle_S_curve_with_preserved_highlights
skin_render: sun-kissed_ivory_with_gold_specular
materials:
  armor: satin_ivory_plate + etched_celtic_knots emitting micro light
  fabrics: translucent_orange_voile with woven gold filaments
  stone: weathered_granite with embedded rune glow
lens_treatment:
  bloom: 0.28 focused on halos
  chromatic_aberration: none, prioritize clarity
  lens_flare: tangential_half-halo triggered by bright rim light
notes:
  - 確保草尖光點帶有細微粒子漂浮，像被加持。
  - 任何陰影保持柔和，禁止冷色陰影；夜色不得壓暗至失去暖度。
  - 背景雲層需留粉紫漸層並與光弧呼應。
```

### Style Pack：Twilight Luminous Sanctum VFX（新樣板）
```yaml
name: Twilight Luminous Sanctum VFX
niagara_presets:
  - dusk_ring_expand (radial light disc with rune crawl + grass emissive trigger)
  - spear_of_setting_sun (angled volumetric shafts with particle sparks)
  - dawn_ember_pickup (collectible firefly orbs + ribbon trails)
unity_vfx_graph:
  - Sanctum.Halo.ArcOpen.vfx
  - Grasslight.StepGlow.vfx
  - Sunstone.Split.Orbits.vfx
particle_behavior:
  ember_speed: 0.8 m/s drift, accel toward player grab
  halo_segments: 7 nested arcs, each offset 12°
  rune_glow_decay: 1.6s exponential falloff
shader_controls:
  fresnel_color: fff6d2 core, cca971 rim
  dissolve_mask: gradient_from_ground_up 0.35 bias
bloom_profile:
  idle: 0.18
  oath_callout: 0.34 sustained 0.5s
  title_flash: 0.42 then decay to 0.1 in 0.8s
sync_hooks:
  staff_impact: link sub-bass hit + radial ring expand
  oath_voice_line: trigger halo segments rotate + rune glyph emission
  logo_flash: daybreak_whiteout with golden sigil trails
notes:
  - 白色鳥群僅作遠景粒子路徑，不可遮擋角色臉。
  - 地面光點需跟隨腳步生成並於 3s 內散為浮光。
```

### Style Pack：Twilight Luminous Sanctum Audio（新樣板）
```yaml
name: Twilight Luminous Sanctum Audio
bed_layers:
  - warm_dusk_wind (stereo, low rustle)
  - luminous_grass_chime (granular bell tones)
  - distant_choir_pad (female alto cluster, vowel "ah")
accent_fx:
  - sunstone_pulse (sub shimmer + crystalline ping)
  - halo_bloom_whoosh (band-limited sweep)
  - spear_rain_shower (angled droplets + airy hits)
  - dawn_ember_pick (soft finger harp pluck)
voiceover:
  language: zh-TW
  tone: calm_firm_goddess
  treatment: light_echo_220ms + high_shelf_-1dB_above_6k
mix_notes:
  - Pad 以 -12 dBFS 鋪底，風與草聲 -16 dBFS；spear_rain 提升至 -8 dBFS 對應光矛。
  - 台詞必須清楚可懂，且與 halo_bloom_whoosh 做 ducking 3 dB，保持權威感。
  - 結尾 Logo 僅留合唱長音與日石爆鳴殘響 0.7s，Fade 至 -24 dBFS。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Twilight Luminous Sanctum Look｜16:9｜24fps｜柔暖夕照聖環質感)
「永恆黃昏的《燃光草原》聖環石圈；風拂草尖光粒、立石符文、遠空白羽鳥；夕輝聖環女王・艾爾薇恩自光弧內現身，落杖展開庇護、審視來者並宣布黃昏誓約。」
鏡頭：Act1 24mm 高空俯瞰→28mm 草尖滑行→35mm 逆光剪影→50mm 頭冠特寫；Act2 40mm 低角權杖→24mm 拉遠光域→70mm 眼睛微推→32mm 俯視畫圈→30mm 仰視光矛；Act3 28mm 主觀踏入→60mm 正面宣告→45mm 日石爆光推近 Logo。
表演：艾爾薇恩整體沉穩，語氣如祝禱；落杖時肩膀穩定、眼神微冷；台詞「黃昏，從不撒謊」「說吧，你來這裡……求的是光，還是勝利？」「光不會替你作答，只會照出你真正的樣子。」需分段清晰。
臉型/髮型：柔和橢圓臉、金琥珀雙眼、淡金蜜棕長髮及腰，頭戴開口聖環與乳白石，髮絲被風輕拂。
構圖：多用中央對稱與弧形領線；草原、石圈、光環提供前中後景；留白 15% 供光粒漂浮；遠景鳥群為頂層動態。
寫實細節：象牙白軟甲＋淡金胸甲刻細緻結繩；半透明淡橙披風織入金線、邊緣持續掉落火花；夕光權杖白木包金，日石懸浮；地面足跡變光點再散。
無字幕、無商標/Logo/水印。

鏡頭語法：24–35mm 建立環境、40–60mm 人物互動、70mm 眼神壓迫；
光圈 {Act1 T4.0 保景深、Act2 T3.2 強調權杖與眼神、Act3 T2.8 收斂背景}；快門角 {常規 180°、權杖落地 144°、光矛降落 200°}；
對焦 {高空段層次前→中→後，人物段單點眼睛與日石，主觀段呼吸拉焦足跡→艾爾薇恩臉}。
光影：主光為低角夕陽 4500K，草地提供暖綠反光，背後半開光弧做 rim；夜霧避免冷色。
色調/LUT：去飽和 5%，高光偏金白，陰影帶粉橘，草地保留少量草綠；光矛段加入粉紫雲彩以強化神性。
聲音：warm_dusk_wind + luminous_grass_chime 打底，sunstone_pulse、halo_bloom_whoosh、spear_rain_shower 與動作同步；台詞保持前景；合唱 pad 於 Logo 收束。
轉場：光粒遮擋→草尖匹配→白鳥掠過 wipe→光環擴散鞭移→槍雨閃白→日石爆光羽化入 Title。
安全：整段僅顯示祝福儀式，無血腥；白鳥不可誤認為真實物種標記；未顯示可讀語言符石。
```

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.5s）
意圖：建立燃光草原與黃昏審視氛圍
基調：溫柔敬畏
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：高地草原、立石聖環、光粒草尖、逆光披風

#### Beat 1（0.0–1.0s）
重點：黃昏高地全景
Blocking：高空俯視推進，太陽壓在地平線，石圈居中央。
Camera：
- 運鏡：24mm 空拍滑入
- 焦段/機位：24mm 俯角 70°、高度 120m
- 對焦：層次拉焦雲帶→石圈
- 快門角：180；拍點：第一聲 Pad
光影：夕陽逆光＋雲緣體積光
色調/LUT：金橘漸層＋粉紫陰影
聲音：低沉合唱 Pad、風掃麥浪
轉場：雲影掠過遮擋 → Angle 1

Angle 1（0.0–1.0s）
構圖：中央石圈，遠山與太陽成水平線
內容：草原被光帶切開、立石排出聖環
補充：空中白羽鳥群遠距滑過
安全：無可讀符文

#### Beat 2（1.0–2.0s）
重點：草尖光點與符文石特寫
Blocking：鏡頭貼地沿草尖滑行，掠過刻紋石面。
Camera：
- 運鏡：28mm 低角滑軌
- 焦段/機位：28mm 地面 0.15m，俯角 15°
- 對焦：層次光點→符文
- 快門角：180；拍點：光點脈衝
光影：草尖受點狀高光
色調/LUT：暖金草色＋淡綠符光
聲音：風鈴粒子＋輕微電流
轉場：符文亮度溢出 → Angle 2

Angle 2（1.0–2.0s）
構圖：前景草尖、右側立石半入
內容：每根草尖頂有光粒跳動
補充：符文沿石縫蔓延
安全：符文無可讀語言

#### Beat 3（2.0–3.0s）
重點：艾爾薇恩背光剪影
Blocking：鏡頭拉至中景，女王背對夕陽站在石圈中心。
Camera：
- 運鏡：35mm 穩定器滑入
- 焦段/機位：35mm 胸高、逆光
- 對焦：單點人物輪廓
- 快門角：180；拍點：合唱升高
光影：強逆光剪影＋披風透明發光
色調/LUT：暗剪影對比暖天空
聲音：低鼓輕敲
轉場：披風甩動遮擋 → Angle 3

Angle 3（2.0–3.0s）
構圖：人物中央，披風往右延伸
內容：長髮、披風、權杖剪影
補充：地面足跡化作光點
安全：僅剪影

#### Beat 4（3.0–4.5s）
重點：聖環頭飾亮起與首句台詞
Blocking：靠近頭部，乳白石逐顆亮，艾爾薇恩低語「黃昏，從不撒謊。」
Camera：
- 運鏡：50mm 微推
- 焦段/機位：50mm 肩高
- 對焦：單點頭飾
- 快門角：180；拍點：每顆石亮
光影：柔光打臉，背後光弧 rim
色調/LUT：肌膚暖白＋金光點
聲音：三聲細高光點音效＋呢喃
轉場：頭飾最後一顆石爆出光線 → Angle 4

Angle 4（3.0–4.5s）
構圖：臉偏左三分線，頭飾佔上框
內容：乳白石逐顆點亮、眼神溫柔
補充：髮絲被風揚起
安全：無其他角色

### Act 2（4.5–9.5s）
意圖：展開庇護權杖、光環、審視與招式預告
基調：聖潔試煉
節奏域：穩定1.5–2.4
美術要點：夕光權杖、光環擴散、草地點亮、光矛預警

#### Beat 5（4.5–5.5s）
重點：權杖落地與光環爆發
Blocking：她將權杖垂直插地，日石脈動炸出金橘波。
Camera：
- 運鏡：40mm 低角仰視
- 焦段/機位：40mm 膝高仰 20°
- 對焦：單點權杖
- 快門角：144；拍點：權杖撞地
光影：地面光波擴散
色調/LUT：暖金中心向外淡
聲音：低頻轟鳴＋sunstone_pulse
轉場：光波沿地推進 → Angle 5

Angle 5（4.5–5.5s）
構圖：權杖置中，地面光環自腳下擴張
內容：日石分裂出細小光環
補充：塵土被光吹開
安全：無爆炸碎片

#### Beat 6（5.5–6.5s）
重點：燃光草原聖域全景
Blocking：拉遠繞拍半圈，草尖集體點亮，鳥群掠空。
Camera：
- 運鏡：24mm 繞拍
- 焦段/機位：24mm 胸高
- 對焦：層次人物→草地
- 快門角：180；拍點：合唱增強
光影：光環照亮半透明霧
色調/LUT：金白草海＋粉紫天空
聲音：合唱開聲＋halo_bloom_whoosh
轉場：鳥群擦鏡 → Angle 6

Angle 6（5.5–6.5s）
構圖：人物居中，草地成光面
內容：遠空白鳥、石圈符文同時亮起
補充：披風邊緣火花持續飄散
安全：鳥為抽象粒子

#### Beat 7（6.5–7.5s）
重點：夕光審視目光與提問
Blocking：艾爾薇恩抬頭直視鏡頭，問「說吧，你來這裡……求的是光，還是勝利？」
Camera：
- 運鏡：70mm 緩推
- 焦段/機位：70mm 眼高
- 對焦：單點眼睛
- 快門角：180；拍點：語句停頓
光影：眼內金琥珀旋光
色調/LUT：背景柔焦暖金
聲音：合唱壓低，只留心跳與台詞
轉場：眼中光粒外放 → Angle 7

Angle 7（6.5–7.5s）
構圖：極近眼部，倒映玩家輪廓
內容：金琥珀虹膜內漂浮淡綠光粒
補充：睫毛與光粒同步閃耀
安全：無血腥

#### Beat 8（7.5–8.5s）
重點：聖環庇護陣形成
Blocking：她以杖尖畫圈，完整光陣亮起，環內柔光、環外陰影。
Camera：
- 運鏡：32mm 俯視旋轉
- 焦段/機位：32mm 3m 高俯視
- 對焦：層次杖尖→環線
- 快門角：180；拍點：符文鎖定
光影：地面符文逐一點亮
色調/LUT：環內暖、環外偏紫
聲音：符文敲擊＋halo_bloom
轉場：光陣邊緣成鞭移 → Angle 8

Angle 8（7.5–8.5s）
構圖：正俯視圓形陣，人物置中央
內容：環內護盾流動，環外光柱預示
補充：符文如小法陣旋轉
安全：無可讀文字

#### Beat 9（8.5–9.5s）
重點：燃光槍雨預兆
Blocking：她舉杖，天空光線被拉成斜角光矛，地面顯示落點。
Camera：
- 運鏡：30mm 仰角上搖
- 焦段/機位：30mm 胸高仰 35°
- 對焦：層次人物→天空光矛
- 快門角：200；拍點：光矛聚能
光影：雲層被拉成橘金線
色調/LUT：暖金雲＋粉紫陰影
聲音：嗡鳴聚能＋spear_rain_shower
轉場：光矛光條掃過匹配 → Angle 9

Angle 9（8.5–9.5s）
構圖：女王位於下方三分線，天空佔 2/3
內容：光矛陣列在雲層凝聚
補充：地面出現細長預示光點
安全：光矛僅能量體

### Act 3（9.5–15.0s）
意圖：玩家踏入試煉、誓約台詞、Logo 收束
基調：莊嚴試煉
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：主觀足跡光點、正面宣告、日石光爆 Title Card

#### Beat 10（9.5–10.5s）
重點：玩家踏入石圈
Blocking：主觀鏡頭穿過草地與光環，足跡變光點。
Camera：
- 運鏡：28mm 主觀往前
- 焦段/機位：28mm 眼高
- 對焦：呼吸拉焦草尖→足跡→女王
- 快門角：180；拍點：腳步聲
光影：足跡光點維持 2s 後散
色調/LUT：前景光點亮、背景柔暖
聲音：草地沙沙＋心跳增強
轉場：足跡光點升空 → Angle 10

Angle 10（9.5–10.5s）
構圖：第一人稱，手伸向光環邊界
內容：跨越聖環瞬間，地面光紋浮現
補充：UI 式紋路一閃即逝
安全：無 HUD 文字

#### Beat 11（10.5–12.5s）
重點：試煉宣告與主台詞
Blocking：切回正面中景，披風飄揚，她宣告「光不會替你作答，只會照出你真正的樣子。」
Camera：
- 運鏡：60mm 穩定器平推
- 焦段/機位：60mm 胸高
- 對焦：單點臉→日石
- 快門角：180；拍點：台詞落點
光影：夕陽從肩後透出，披風半透明
色調/LUT：象牙白甲＋暖金 rim
聲音：台詞前景、合唱與風收束
轉場：日石亮度飆升白閃 → Angle 11

Angle 11（10.5–12.5s）
構圖：人物中央，披風弧形佔後景
內容：光粒繞著她旋轉，權杖立地
補充：字幕僅內部記錄不入畫
安全：無其他角色

#### Beat 12（12.5–15.0s）
重點：Logo 收束與祝福標語
Blocking：快速推近日石→白閃→Logo，「黃昏，只為誠實之人開啟。」浮現。
Camera：
- 運鏡：45mm 推近日石→白閃轉平面卡
- 焦段/機位：45mm 胸高
- 對焦：單點日石
- 快門角：200；拍點：光波爆發
光影：日石爆出環狀光波吞沒畫面
色調/LUT：金白爆光後轉象牙白字卡
聲音：sunstone_pulse + choir 長音，殘響 0.7s
轉場：白閃羽化 → Angle 12

Angle 12（12.5–15.0s）
構圖：中央 Logo，「夕輝聖環女王・艾爾薇恩」中英雙語（自有字體）
內容：背景殘留光弧與粒子飄落
補充：標語「黃昏，只為誠實之人開啟。」置底
安全：僅使用原創字體與語句

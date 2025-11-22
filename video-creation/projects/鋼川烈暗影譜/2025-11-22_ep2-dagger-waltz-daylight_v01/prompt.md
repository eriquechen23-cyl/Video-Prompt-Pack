# 鋼川烈暗影譜 EP2 — 白日匕首圓舞曲：瞬移刺客 vs 巨型異獸 PV Prompt（15s｜12 幕｜9:16）

來源劇本：user 提供「白天版＋瞬移匕首＋匕首圓舞曲」文案

## Required Input Fields（拍前必填）
- project_name：鋼川烈暗影譜
- series_name/arc：黑塔城陽炎篇
- episode_index：2
- slug：dagger-waltz-daylight_v01
- target_platform：短影音（TikTok/YouTube Shorts/IG Reels 同步）
- duration_sec：15（預設）
- style_primary：Anime Fantasy Look + Zenith Noon Real Look（本檔 Default ON）
- style_secondary：Manga Impact Frame（Angle 8/12 強制啟用）
- worldstate_ref：正午廢墟廣場，巨型異獸破土而出，胸口紅光脈動
- goal：2D 日系動漫風格 + 漫畫衝擊格，展示匕首瞬移圓舞曲擊破巨獸

## Project Info（UTC+8 日期規則）
- Project 路徑：video-creation/projects/鋼川烈暗影譜/2025-11-22_ep2-dagger-waltz-daylight_v01
- 拍攝日期標記：2025-11-22（UTC+8）
- 畫幅：9:16 直式，構圖預留字幕下緣 12% 安全框
- 時長與節奏：15 秒（12 幕×1.2s），Act 切分：Act1 0–4.8s｜Act2 4.8–10.8s｜Act3 10.8–15.0s
- 角色狀態：鋼川烈（短髮，黑銀外套＋冷白刀光，低重心瞬移步）；巨型異獸（漆黑厚皮、骨刺、胸口紅色核心脈動，粗糙皮膚在陽光下刺眼）
- 持續要素：白日刺眼高光、灰白粉塵、速度線粒子、紅光能量霧、漫畫擬聲字在擊破瞬間

## Technical Specs（統一拍攝參數）
- Aspect Ratio：9:16｜解析度：1080×1920｜FPS：24（若需慢動建議拍 48 匯出 24）
- Shutter：180°（Angle 8 黑白衝擊改為 144°，保線稿）
- Lens Set：24mm/32mm 建立空間與巨獸尺度；50mm/65mm 角色瞬移貼身；85mm/135mm 壓縮碎片與漫畫格掉落
- Camera Motion：滑軌 + 側移 + 少量繞拍；手持 ≤3%；鞭移或遮擋轉場僅用於速度感銜接
- DOF：近景 f/2.0–2.8；廣角環境 f/4–5.6，保持眼部與刀尖清晰；熱浪造成邊緣微折射，不套柔焦
- Grain：輕膠片顆粒 6–8%，避免破圖；Chromatic Aberration：≤0.02 保線條銳利
- Color Pipeline：linear → log → filmic LUT（陰影微藍、陽光高光暖白 5400K）→ 最終對比 +6%；白日壓高光但保留皮膚細節
- Delivery：Rec.709；-14 LUFS；-1 dBTP；固定種子記錄；連戲與時序一致

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
```
Master({時長}s｜{風格}｜{畫幅}｜{fps}｜{質感})
「{時間/地點}；{環境元素1/2/3}；{主體＆動作一句話}。
鏡頭：{滑軌/側向/繞拍/手持≤3%/穩定器}。
表演：{情緒/肢體/視線}。
臉型/髮型：{依上傳五官特徵}。
構圖：{三分線/中央/前中後/留白10–20%}；動態：{風/水/人群/道具}。
寫實細節：{服裝/材質/肌理/光影過門；PBR 粗糙度0.15–0.45/金屬度/法線或置換；微刮痕/汗液/指紋；重力/慣性/布料彈性/流體折射}。
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
物理/質感：{重力/慣性/碰撞/布料彈性/流體黏度；PBR 粗糙度/金屬度/法線或置換；膚質分層/油光控制；景深/畸變/顆粒顆度}
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

### 交付參數預設（`_core/delivery_presets.md`）
```
畫幅：{16:9｜9:16｜1:1}
解析度：{1920×1080｜1080×1920｜2048×2048}
幀率：{24/30/48/60}（如需輕慢動：拍 48–60，輸出 24）
防抖：{開/關}；運動模糊：開；顆粒：微膠片
色彩：Rec.709（交付版）／LOG（調色版）
聲音：立體聲 48kHz；-14 LUFS（YouTube），-1 dBTP
種子：{固定/隨機（記錄）}；連戲：開；時序一致：開
```

### QA Checklist（`_core/qa_checklist.md`）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 物理寫實：重力/慣性/布料或流體反應與光學行為已寫入 Master 與各 Beat/Angle；PBR 粗糙度/金屬度、膚質分層與高級質感來源（光比/紋理/顆粒）明確。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

## _stylepacks
### Style Pack：Anime Fantasy Look（預設開啟，Applicable for 空間建立與角色特寫）
- Applicable for：全段鏡頭；特別用於廢墟遠景與角色近景
- Do NOT mix with：seraphic_realism（避免過度柔光）；urban_switch_fx
- Default：ON
- Visual traits：clean_edges、強線稿、pastel_magenta/teal/warm_gold 調色、膚色保護
- Audio traits：依主配樂維持空氣感，減少重低頻，保留腳步聲與砂塵顆粒聲
- YAML 原文：
```yaml
name: Anime Fantasy Look
noise_reduction: clean_edges
saturation: vivid_controlled_skin
line_enhancement: strong_outline
color_palette:
  primaries: [pastel_magenta, teal, warm_gold]
  skin_tone: protected
motion_blur_shutter: 150
notes:
  - 邊緣俐落，維持動畫質感
  - 色彩飽和但控制膚色
  - 建議搭配 24–35mm 誇張空間感
```

### Style Pack：Zenith Noon Real Look（適用正午過曝高光，與匕首光反射）
- Applicable for：白日廢墟、陽光直射、熱浪折射、巨獸粗糙皮膚高光
- Do NOT mix with：seraphic_realism（避免過度柔霧）；moonlit_wolf_meme
- Default：ON（與 Anime Fantasy Look 共存，控制肌理）
- Visual traits：刻意過曝白日，硬質高光與沙紋陰影，熱浪邊緣抖動
- Audio traits：環境帶熱氣嗡鳴、微金屬共振，避免厚重混響
- YAML 原文：
```yaml
name: Zenith Noon Real Look
lut: Zenith-Overexpose-HDR
saturation_adjust: -0.03  # 去飽和 3%
contrast: high_linear
highlight_rolloff: hard_clip_with_bloom
shadow_floor: lifted_sand  # 影子被抹平
white_point: 1.05  # 刻意過曝
texture: tempered_glass_scale
specular_detail: molten_gold_edges
heat_warp_pass: micro_ripple_sheet
notes:
  - 強化正午過曝質感，暗部保留極少量沙紋，不產生藍色陰影。
  - 鱗片表面需呈現多層玻璃反射並含熾橙內發光。
  - 景深受熱浪影響需保持邊緣抖動，勿套柔焦濾鏡。
```

### Style Pack：Zenith Noon Real Audio（配合白日環境與能量噴散）
- Applicable for：全段日光場景，特別是紅光爆炸與熱浪穿行
- Do NOT mix with：frost_gambler（溫差矛盾）
- Default：ON
- Audio traits：
```yaml
name: Zenith Noon Real Audio
core_layers:
  - baked_desert_wind
  - heat_buzz_harmonics
  - distant_metal_creak
  - granular_sandfall
impact_events:
  - cue: solar_pressure_drop
    sfx: subsonic_column_crush
    level_db: -4
    width: 140
  - cue: gnomon_lock
    sfx: glass_ring_sweep
    level_db: -7
    width: 120
  - cue: thermal_wing_cut
    sfx: vacuum_slice_thump
    level_db: -6
    width: 150
  - cue: helio_dive
    sfx: hypersonic_descend_roar
    level_db: -2
    width: 160
voiceover:
  language: ja-JP  # 用日文配音交付，口條簡潔低沉
  tone: solemn_genderless
  treatment: band_limit_mid_high
mix_notes:
  - 風聲需維持 -18 dBFS 底噪並含金屬共振尾音，對應封印結構。
  - 光柱與日晷事件必須 sidechain 風聲 3 dB，凸顯衝擊。
  - 結尾旁白僅 0.7s，定位中央，殘響 0.3s 後歸於靜音。
```

### Style Pack：Zenith Noon Real VFX（熱浪折射與紅光爆裂）
- Applicable for：正午陽光、熱浪扭曲、紅光能量噴散、地面折射
- Do NOT mix with：frost_gambler、seraphic_realism
- Default：ON（與 Manga Impact Frame 在指定角度交替）
- Visual traits：地面熱浪扭曲、折射閃爍、紅光體積粒子
- YAML 原文：
```yaml
name: Zenith Noon Real VFX
heat_haze_layers:
  - id: zenith_ground_glimmer
    distortion: 0.42
    speed: 1.6
  - id: apex_sky_veil
    distortion: 0.28
    speed: 0.9
solar_column_profile:
  core_color: fff8cf
  rim_color: ffad45
  falloff: exponential_hard
  particles: silica_dust_updraft
wing_trail_shader:
  refractive_index: 1.23
  thickness_cm: 65
  ember_specks: 0.18
sundial_cage_geometry:
  slices: 24
  rotation_speed_rps: 0.85
  cut_beam_width_cm: 8
reflection_cache:
  afterglare_delay_s: 2.2
  intensity_scale: 1.35
notes:
  - 光柱與光籠採體積陰影貼圖而非 2D billboard，以利真實折射。
  - 翅膀熱浪需在遠景造成背景折射，並帶動砂塵短暫懸浮。
  - 尾巴日晷展開時，光條必須對應地面刻度動畫並可作為腳本判定區域。
```

### Style Pack：Manga Impact Frame（黑白衝擊格與碎片漫畫化）
- Applicable for：Angle 8 漫畫黑白擊破，Angle 12 碎片漫畫格化
- Do NOT mix with：real_cinema、seraphic_realism（避免寫實膚質過細）
- Default：ON 於指定鏡頭
- Visual traits：
  - 黑白高對比，粗速度線背景；眼睛與匕首保留局部色彩
  - 巨大擬聲字「ガキィン!!」，2px 外描邊；碎片漫畫格化掉落
- Audio traits：
  - 鋼鳴瞬間高頻 4–6kHz 拉升；BGM 抽空 0.2s 後回流
  - 紙張撕裂 Foley 疊加碎片落地，立體聲左右掃
- Notes：黑白段落降低 Bloom，線稿銳利；回色 6 帧漸入

### Style Pack：Dagger Teleport Waltz（新樣板，用於瞬移殘影與匕首軌跡）
- Applicable for：烈瞬移軌跡、刀光弧線、速度線粒子
- Do NOT mix with：storm_boss_lockon（避免過度電光）；real_cinema
- Default：ON
- Visual traits：
  - 匕首軌跡以銀白長曝光線條呈現，殘影透明度 35%，尾端帶粒子火花
  - 瞬移點閃爍白光 + 空氣折射圈，PBR 金屬反射跟隨殘影
  - 瞬移時地面與角色腳下翻湧「暗影噴濺」特效，呈現低飽和墨黑裂隙與陰影拉扯，與正午高光形成對比
- Audio traits：
  - 瞬移時短促「啪」聲搭配微弱空氣抽空；刀光拖尾帶 2kHz 亮鋒音
  - 軌跡節奏與 BPM 同步 1.1x，結尾加 sidechain 壓制環境風 2 dB
- Notes：保持重力向下的布料拉扯與粉塵噴起，避免無重力飄浮

## Master Prompt（含 Brand/Physics/PBR/Camera Continuity）
- Brand Bible：鋼川烈＝暗鋼外套 + 琥珀眼高光 + 瞬移裂環步；語氣冷冽短句，偶帶日文擬聲；場景偏灰白石塊與強烈陽光，高光硬邊，速度線粒子協同。
- Worldstate：正午（5400–5600K）廢墟廣場，裂開石板、倒塌石柱，灰白粉塵飄浮；巨型異獸漆黑粗糙皮膚，骨刺鋸齒狀，胸口紅光核心以 80 bpm 率脈動。
- Camera Continuity：開場 24–28mm 略低角遠景強光；Act1 繞拍建立尺度；Act2 50–65mm 跟隨瞬移圓舞曲；Act3 85–135mm 壓縮碎片與漫畫格；全段 180° 快門，Angle 8 調 144°，Angle 12 可 180° 搭漫畫格掉落。
- Physics & PBR：布料受重力 9.8 m/s² 下垂，瞬移滑步時產生後向拖拽；匕首金屬度 0.9 粗糙度 0.12 帶指紋；異獸皮膚粗糙度 0.6、法線凸起，骨刺金屬度 0.35；紅光能量霧有體積散射，噴散遵循拋物線；粉塵因踩踏形成湧升 2 m/s 再落下；瞬移閃光在空氣中產生折射圈並拖出低飽和暗影噴濺，與正午高光交疊形成對比陰影。 
- Optics：硬質頂光 + 反射亮斑；刀刃鏡面反射環境；景深鎖定眼睛與刀尖，背景粉塵輕散焦；速度線與刀光使用向量運動模糊；熱浪造成邊緣折射。
- Master Prompt：
  - Master(15s｜2D anime daylight dagger teleport + manga impact｜9:16｜24fps｜sharp linework + noon glare)
  - 「正午廢墟廣場；裂石、倒柱、熱浪粉塵；瞬移刺客鋼川烈用雙匕首圍繞巨型異獸跳出圓舞曲，敲裂胸口紅光並以漫畫衝擊格擊破。」
  - 鏡頭：低角遠景→近距繞拍→衝擊特寫；表演：冷靜計算→高速流暢→落地收刀；構圖：三分線＋前中後層次，保留陽光高光與粉塵遮擋。
  - 寫實細節：外套布料法線 4K，肩口磨痕；匕首磨砂握柄粗糙度 0.4；異獸皮膚裂縫滲紅光，體積霧受陽光散射；粉塵在強光中形成瑞利散射光束；速度線粒子與火花按慣性衰減。

## Platform Layer
- Hook A（故事向 0–1s）：黑影炸開巨獸躍出，日光刺眼 + 地面崩裂音
- Hook B（衝擊向 0–1s）：Angle 8 黑白漫畫衝擊格 + 「ガキィン!!」居中霸屏
- Caption 建議：短版「白日匕首瞬移圓舞曲」；長版「鋼川烈：陽光下的瞬移匕首擊破巨獸核心」
- First-shot visual hook：正午硬光下裂開地面，黑影鼓起爆開
- Thumbnail：烈背對陽光側臉，匕首反光，身後巨獸胸口紅光爆裂，碎片漫畫格化下落
- Hashtags：#Anime #Dagger #Teleport #Waltz #BossFight #MangaImpact #Daylight
- CTA：末尾定格「Watch the full waltz」文字供剪輯（畫面內不顯示）

## Negative Instructions
- 禁用真實商標、名人肖像、宗教政治符號
- 禁用過曝飽和失真、廉價濾鏡、魚眼過度畸變、超過 5% 手持晃動
- 畫面尺度：PG-13；無血腥破皮，破壞以能量與碎片呈現
- 不使用寫實照片貼圖；避免無重力飄浮；粉塵需受重力回落

## Act/Beat/Angle（12 幕 × 1.2s，含 Physics/PBR/光學）
### Act 1（0.0–4.8s）｜白日壓迫與刺客起手 — 基調：緊張，節奏域 1.5–2.0s，意圖建立場域與對位
- 美術要點：白日硬光，裂開石板、倒塌石柱，灰白粉塵；烈外套黑銀、匕首冷白反光；異獸皮膚粗糙黑褐，骨刺鋸齒。

#### Beat 1（0.0–1.2s）
- 重述狀態機：場景空景，地面裂縫鼓起黑影。
- 重點：巨型異獸破土出場。
- Blocking：黑影鼓起→炸開→巨獸四肢撐地站起。
- Camera：24mm 略低角遠景，滑軌後退 1.5m；對焦層次黑影→巨獸上半身；快門 180°。
- Lighting：硬質正午頂光 5400K，高對比，石縫內暗部抬升；粉塵折射光斑。
- Materials & Physics：地面石板粗糙度 0.55；爆開碎石依重力抛物線飛散；巨獸皮膚粗糙度 0.6 帶骨刺法線；紅光核心透過薄皮散射。
- Emotion & Performance：巨獸甩落瓦礫，四肢撐地沉重。
- Audio & Transition：熱風底噪 + 石板崩裂低頻；轉場直接切 Beat2。
- Angle（建立環境）：
  - Camera：遠景三分線，巨獸偏中央上方；鏡頭緩慢後退穩定器。
  - Lighting：頂光硬邊，地面高光刺眼；粉塵透光。
  - Materials & Physics：碎石撞地產生粉塵柱，受重力下落；骨刺金屬度 0.35。
  - Emotion & Performance：巨獸昂首咆哮，胸口紅光跳動。
  - Audio & Transition：爆裂音佔 -6 dB 峰值，風聲持續；切入 Beat2。

#### Beat 2（1.2–2.4s）
- 重述狀態機：巨獸已立於中央，粉塵尚未落定。
- 重點：烈在光影交界準備出手。
- Blocking：烈半蹲陰影邊緣，匕首轉動。
- Camera：50mm 中近景側背，胸高，滑軌微推 0.6m；對焦刀柄→眼睛；快門 180°。
- Lighting：背光陽光形成 rim 光，反射在刀身；陰影區色溫 5200K，對比高。
- Materials & Physics：外套布料粗糙度 0.28 帶塵；汗珠微光；匕首金屬度 0.9；粉塵漂浮慣性 1.5 m/s。
- Emotion & Performance：烈抬眼鎖定胸口紅光，呼吸穩定。
- Audio & Transition：衣料摩擦、刀旋轉金屬聲，風聲持續；鞭移遮擋轉 Beat3。
- Angle（角色起手）：
  - Camera：三分線右側放烈，左側留巨獸模糊；穩定器。
  - Lighting：側逆光勾勒輪廓，刀身冷白反光。
  - Materials & Physics：髮絲被風 2 m/s 吹動；匕首鋒面指紋細節可見。
  - Emotion & Performance：眼神冷冽，嘴角緊繃。
  - Audio & Transition：刀旋轉輕響對應畫面 12 帧；遮擋切入下鏡。

#### Beat 3（2.4–3.6s）
- 重述狀態機：烈已鎖定目標，準備第一次瞬移。
- 重點：第一次丟匕首示範瞬移。
- Blocking：烈前踏一步，甩匕首到巨獸腳邊，瞬移到匕首旁滑步。
- Camera：28mm 低機位貼地跟拍，側向滑軌 4m；對焦跟刀；快門 180°。
- Lighting：陽光在刀弧上形成鏡面閃光；地面反光強烈。
- Materials & Physics：刀弧空氣摩擦形成細微光尾；瞬移閃光折射粉塵並拖出低飽和暗影霧絲貼地滑行；鞋底摩擦石板留下刮痕。
- Emotion & Performance：烈神情專注，動作利落。
- Audio & Transition：匕首破風聲 + 瞬移「啪」聲；直接切 Beat4。
- Angle（瞬移示範）：
  - Camera：低角中央構圖，刀弧佔前景；手持 0%。
  - Lighting：頂光 + 匕首高光閃爍；粉塵在刀弧旁被光切割。
  - Materials & Physics：瞬移閃光拉出折射圈與墨黑暗影噴濺，粉塵被推開 0.3m；滑步摩擦帶粉塵波。
  - Emotion & Performance：烈身形低矮貼地滑行。
  - Audio & Transition：瞬移聲短促，落點帶砂石碎響；切入 Beat4。

#### Beat 4（3.6–4.8s）
- 重述狀態機：烈已示範瞬移，巨獸開始反擊。
- 重點：巨爪橫掃，烈瞬移貼身閃避。
- Blocking：巨獸抬爪橫掃；烈丟第二把匕首到爪外側並瞬移滑過。
- Camera：32mm 略仰角中景，滑軌側移 3m；對焦跟烈；快門 180°。
- Lighting：爪影遮光形成強烈光影對比；刀光在爪下反射。
- Materials & Physics：骨刺金屬度 0.35 帶磨損；爪掃起粉塵；烈滑過皮膚留白痕，摩擦產生熱；瞬移時地面陰影向外撕裂形成暗影波紋。
- Emotion & Performance：烈冷靜貼身，身體緊繃。
- Audio & Transition：巨爪風切 + 刀刮皮膚聲；遮擋切至 Act2。
- Angle（閃避瞬間）：
  - Camera：中景三分線，烈在右下躲避；鏡頭輕跟。
  - Lighting：爪子遮光形成動態陰影，刀光冷白突出。
  - Materials & Physics：滑步拖出粉塵帶，瞬移殘留暗影晕在地面翻湧；匕首與皮膚接觸產生微火花。
  - Emotion & Performance：烈眼神仍鎖定胸口。
  - Audio & Transition：爪風低頻掃過左→右；鞭移進入 Act2。

### Act 2（4.8–10.8s）｜匕首圓舞曲 — 基調：決斷，節奏域 2.2–2.6s，意圖環繞與弱點累擊
- 美術要點：環繞粉塵軌跡形成弧形刮痕；紅光在裂紋透出；陽光反射刀光。

#### Beat 5（4.8–6.0s）
- 重述狀態機：烈已閃過爪擊，站位在巨獸側面。
- 重點：匕首圓舞曲起始，烈繞圈瞬移。
- Blocking：烈連續丟匕首至不同位置並瞬移，畫出大圓。
- Camera：俯視 24mm，微旋轉繞拍；對焦跟烈；快門 180°。
- Lighting：頂光形成烈與巨獸的強影；粉塵陰影呈弧。
- Materials & Physics：每次瞬移粉塵被推成波並夾帶暗影霧絲留下腳印狀殘影；地面刮痕粗糙度 0.5；刀光留銀線殘影 35% 透明。
- Emotion & Performance：烈動作如舞步，呼吸短促。
- Audio & Transition：節奏感配樂 + 刀風；光源匹配轉 Beat6。
- Angle（圓舞曲軌跡）：
  - Camera：俯拍中央構圖，烈為圓心動態軌跡。
  - Lighting：硬光讓軌跡影子清晰。
  - Materials & Physics：粉塵被拖成弧形，重力下落形成薄霧；瞬移圈折射光閃並伴墨黑暗影卷起再消散。
  - Emotion & Performance：烈流暢旋轉，身形連續。
  - Audio & Transition：每落點伴「啪」聲定位；直接切 Beat6。

#### Beat 6（6.0–7.2s）
- 重述狀態機：巨獸胸口已多次受擊，裂紋初現。
- 重點：弱點特寫，紅光滲出。
- Blocking：烈瞬移到裂紋旁，刀尖懸停。
- Camera：65mm 特寫，胸高側面；對焦刀尖；快門 180°。
- Lighting：陽光打在刀尖與汗水上形成高光；紅光透散。
- Materials & Physics：皮膚裂縫邊緣粗糙度 0.65；紅光體積散射；刀尖金屬反射環境。
- Emotion & Performance：烈屏息，肌肉緊繃。
- Audio & Transition：心跳低鼓 + 細微能量嗡鳴；直接切 Beat7。
- Angle（弱點貼近）：
  - Camera：特寫中央，刀尖與裂縫同焦；穩定器。
  - Lighting：高對比，高光在刀與汗珠閃亮。
  - Materials & Physics：紅光霧受氣流震動 0.2cm；皮膚微顫；刀尖有指紋。
  - Emotion & Performance：烈眼神微眯，嘴角緊。
  - Audio & Transition：心跳同步畫面縮放；切入 Beat7。

#### Beat 7（7.2–8.4s）
- 重述狀態機：裂縫明顯，烈準備收束節奏。
- 重點：蓄力前一刻，圓舞曲節奏收束。
- Blocking：烈接住回旋匕首，瞬移到胸口正前方，空中旋身。
- Camera：50mm 中近景，略仰角；對焦眼→刀；快門 180°。
- Lighting：頂光 + 胸口紅光作底光；背光 rim 勾邊。
- Materials & Physics：烈在空中旋轉時衣襬因慣性上揚；匕首殘影拖尾；瞬移剛結束的暗影霧仍在腳下翻湧；紅光照亮面部下緣。
- Emotion & Performance：表情決斷，肌肉緊繃準備突刺。
- Audio & Transition：音樂降噪 0.3s 製造真空；直接切 Beat8。
- Angle（蓄力姿態）：
  - Camera：三分線左側烈居中偏上；穩定器微推。
  - Lighting：紅光從下照，陽光 rim；高對比。
  - Materials & Physics：衣襬布料粗糙度 0.3，因旋轉呈弧形拉伸；瞬移暗影在地面留下暈痕，粉塵被旋轉氣流帶起。
  - Emotion & Performance：眼神鎖定裂縫，呼吸短促。
  - Audio & Transition：音樂頻寬收窄；硬切到 Beat8 黑白。

#### Beat 8（8.4–9.6s）
- 重述狀態機：烈已到位準備擊破。
- 重點：漫畫感擊破黑白衝擊格。
- Blocking：烈半空旋轉一圈，雙匕首交叉刺入裂縫，畫面切黑白擬聲字爆出。
- Camera：極近景衝擊，75mm；快門 144°；視角隨刺擊前移 0.5m。
- Lighting：黑白高對比，速度線背景；刀與眼保留色彩。
- Materials & Physics：刀尖刺入皮膚，碎片炸開，紅光以黑白噴散；速度線描繪慣性。
- Emotion & Performance：烈怒喝，肌肉爆發。
- Audio & Transition：BGM 抽空 0.2s，鋼鳴「ガキィン!!」；漸進回色至 Beat9。
- Angle（漫畫衝擊格）：
  - Camera：中央構圖，刀交叉占據畫面；速度線輻射。
  - Lighting：黑白硬光，無灰階；匕首保留冷白色，眼保琥珀。
  - Materials & Physics：皮膚碎片以漫畫線條飛散；擬聲字 2px 外描邊。
  - Emotion & Performance：烈眉頭緊鎖，牙關咬緊。
  - Audio & Transition：擬聲字伴金屬破音，6 帧後色彩回流；切 Beat9。

#### Beat 9（9.6–10.8s）
- 重述狀態機：裂縫已開，紅光噴散。
- 重點：色彩回來，紅色能量噴散；烈翻身離開。
- Blocking：烈後空翻沿紅光邊緣滑開；紅光霧噴出。
- Camera：中景側面 35mm，跟拍烈後翻；快門 180°。
- Lighting：陽光硬光 + 紅光強背光；粉塵透射形成光柱。
- Materials & Physics：紅光體積霧速度 4 m/s 向外；碎皮粗糙度 0.6 翻出；烈翻身衣襬受慣性飄動再回落。
- Emotion & Performance：烈面色冷靜收刀。
- Audio & Transition：紅光爆炸低頻 + 空氣抽空；光源匹配轉 Act3。
- Angle（能量噴散）：
  - Camera：三分線，烈在右側翻身；紅光佔左側。
  - Lighting：紅光強背光造成剪影，陽光填補高光。
  - Materials & Physics：碎片以抛物線落下，受重力明顯；熱浪折射背景。
  - Emotion & Performance：烈動作流暢，落地前收腿。
  - Audio & Transition：爆炸聲後留低頻尾音；切入 Act3。

### Act 3（10.8–15.0s）｜收束與落幕 — 基調：收束，節奏域 1.8–2.2s，意圖展示安全撤離與巨獸崩塌
- 美術要點：石柱倒塌處安全位，紅光漸弱；碎片漫畫格化落下；白日粉塵成霧牆。

#### Beat 10（10.8–12.0s）
- 重述狀態機：紅光爆炸後烈仍在半空。
- 重點：最後一投，瞬移到安全位置。
- Blocking：烈丟最後匕首至遠處倒柱裂縫，瞬移跪地緩衝。
- Camera：斜俯視 28mm 跟匕首飛行；對焦刀身→落點；快門 180°。
- Lighting：陽光在刀身形成長形高光；背景紅光餘暈。
- Materials & Physics：匕首旋轉帶金屬高光；瞬移閃光推開粉塵並在落點投下暗影裂縫效果；落地膝蓋摩擦石板，粉塵揚起 0.3m。
- Emotion & Performance：烈落地穩定吐氣。
- Audio & Transition：匕首破風 + 瞬移啪聲；遮擋切 Beat11。
- Angle（最後瞬移）：
  - Camera：跟拍刀身，三分線左上落點；鏡頭稍微鞭移。
  - Lighting：硬光沿刀脊流動；落點處陰影降低對比。
  - Materials & Physics：粉塵被瞬移氣壓與暗影衝擊波向外推；匕首刺入裂縫，石屑飛濺。
  - Emotion & Performance：烈落地單膝緩衝，呼氣白霧微可見。
  - Audio & Transition：刀刺入聲清脆；遮擋切 Beat11。

#### Beat 11（12.0–13.2s）
- 重述狀態機：烈已站在安全位置，巨獸胸口裂開。
- 重點：巨獸搖晃崩塌。
- Blocking：巨獸胸口紅光亂閃，裂痕蔓延，全身倒向一側。
- Camera：中遠景 35mm 背對烈，穩定器後退 1m；快門 180°。
- Lighting：硬光在碎片上形成亮斑；粉塵霧牆反射陽光。
- Materials & Physics：裂痕沿骨刺擴散，碎片受重力慢動作落下；體積霧厚度 8%。
- Emotion & Performance：烈背對鏡頭站穩，呼吸回復平緩。
- Audio & Transition：巨獸倒地低頻震動 + 粉塵聲；直接切 Beat12。
- Angle（崩塌遠景）：
  - Camera：三分線，烈前景偏右；巨獸佔後景左側倒下。
  - Lighting：陽光在粉塵中產生光柱；紅光漸弱。
  - Materials & Physics：碎片拋物線下降，空氣阻力令旋轉；粉塵受重力回落。
  - Emotion & Performance：烈不回頭僅微動肩膀。
  - Audio & Transition：倒塌聲佔低頻，尾音漸弱；切入 Beat12。

#### Beat 12（13.2–15.0s）
- 重述狀態機：巨獸已倒地，碎片落下。
- 重點：碎片如漫畫格落下，烈定格。
- Blocking：碎片漫畫格化飄落，烈站中央收刀，畫面定格。
- Camera：中景側面→緩慢拉遠仰角；85mm→135mm 拉；快門 180°。
- Lighting：背光陽光形成輪廓光；粉塵光霧包圍。
- Materials & Physics：碎片邊緣以漫畫邊框呈現，內部 halftone dots；碎片重力下落，少量受風偏移；匕首金屬反光淡入。
- Emotion & Performance：烈沉靜，雙匕首自然下垂；最後 0.3s 定格側臉。
- Audio & Transition：BGM 最後重擊→收掉，只留風聲與碎片落地；Freeze frame 收尾。
- Angle（定格）：
  - Camera：拉遠至廣角，烈居中央，碎片自上落。
  - Lighting：輪廓光勾邊，粉塵霧柔化背景；漫畫格碎片部分高光。
  - Materials & Physics：碎片帶 halftone dots 粒徑 1px；顆粒控制 8%；景深輕微。
  - Emotion & Performance：烈表情平靜，汗水沿頰流下。
  - Audio & Transition：風聲與碎片紙張撕裂 Foley；最後 Freeze Frame 0.3s。

## Technical Specs（重申生成設定）
- 9:16｜1080×1920｜24fps｜180°；Angle 8 144°
- Lens：24/28/35/50/65/85/135mm 視段落；運鏡滑軌 + 繞拍 + 少量鞭移
- DOF：眼睛/刀尖優先；顆粒 6–8%；CA ≤0.02；log→filmic LUT
- 音訊：-14 LUFS；-1 dBTP；立體聲 48kHz；環境風 + 熱嗡鳴 + 刀鳴

## Assumptions
- 角色造型依 EP1 模板（黑銀外套、琥珀眼）延續，未提供其他更動。
- 異獸為單一個體，胸口紅光為唯一弱點，無其他外掛裝備。
- 配樂以節奏輕推鼓點為主，無人聲歌唱。

## Changelog vs Previous Episode
- 場景由夜間改為正午硬光；引入熱浪折射與過曝質感。
- 技能展示由「裂環步法」改為「匕首瞬移圓舞曲」，新增瞬移殘影與匕首軌跡。
- 漫畫衝擊格保留，但紅光噴散改為白日強光。

## Next Episode / Spin-off Ideas
- 下一集：巨獸核心碎片被回收，引出新的機械熔合怪在夕陽環境；烈需要空中瞬移。
- 下一集：烈與同伴合作，瞬移匕首與遠程狙擊聯動，夜晚雨中戰。
- 番外：日常短片「烈的匕首保養」，展示 PBR 紋理與光學細節。

## Negative Instructions（重申）
- 無品牌、無可讀文件、無政治宗教符號；PG-13 無血腥。
- 避免過曝完全洗白；控制手持晃動 ≤5%；不使用過度魚眼。

## AGENT Self-Check
- 結構：Master/Act/Beat/Angle/timecode 12×1.2s 均已列，Platform/Negative/Assumptions/Changelog 完整。
- Physics & PBR：每幕寫明重力、慣性、粉塵/紅光流體行為、刀金屬度/粗糙度、皮膚法線、光學折射/反射。
- Stylepacks：Anime Fantasy Look + Zenith Noon Real Look/Audio/VFX + Manga Impact Frame + Dagger Teleport Waltz，標註 Applicable/Do NOT mix/default。
- Continuity：銜接 EP1 角色造型與匕首設定，場景改為正午並於 Changelog 註記；Platform Hook/Thumbnail 已更新。
- QA Checklist：需於生成前再次逐項自評 10/10（未勾選欄位待執行）。

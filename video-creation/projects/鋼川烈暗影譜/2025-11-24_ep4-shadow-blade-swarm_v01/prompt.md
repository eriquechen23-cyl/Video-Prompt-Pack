# 鋼川烈暗影譜 EP4 — 暗影飛刃 vs 影域小怪群 PV Prompt（15s｜12 幕｜9:16）

來源劇本：使用者提供之《暗影飛刃・鋼川烈 vs 影域小怪群》文本（含世界觀、角色動作、12 幕分鏡節奏）

## Required Input Fields（拍前必填）
- project_name：鋼川烈暗影譜
- series_name/arc：鋼脈都市下層影域防衛戰
- episode_index：4
- slug：shadow-blade-swarm_v01
- target_platform：短影音（TikTok/YouTube Shorts/IG Reels 同步）
- duration_sec：15（12 幕 × 約 1.0–1.5s；總長 15s）
- style_primary：Anime Fantasy Look + Urban Switch FX（本檔 Default ON）
- style_secondary：Manga Impact Frame：Shadow Scatter（Angle 10–12 指定啟用）
- worldstate_ref：鋼脈都市下層濕冷巷道，霓虹破碎映水，影域小怪從裂縫湧出
- goal：2D 日系戰鬥番 PV，暗影瞬移 + 飛刀標記連段，終極圓形爆裂斬收束

## Project Info（UTC+8 日期規則）
- Project 路徑：video-creation/projects/鋼川烈暗影譜/2025-11-24_ep4-shadow-blade-swarm_v01
- 拍攝日期標記：2025-11-24（UTC+8）
- 畫幅：9:16 直式，構圖預留字幕下緣 12% 安全框
- 時長與節奏：15 秒（12 幕分別為 1.0/1.0/1.2/1.3/1.2/1.3/1.5/1.2/1.3/1.5/1.3/1.2s）；Act 切分：Act1 0–4.5s｜Act2 4.5–11.0s｜Act3 11.0–15.0s
- 角色狀態：鋼川烈（短髮肌肉青年，黑紅戰鬥服緊貼肌群，暗紅能量紋沿鎖骨→手臂，可驅動飛刀與瞬移）；影域小怪（黑霧與骨刺拼湊，小於成人，眼窩暗黃光點，動作似犬＋昆蟲）
- 持續要素：破碎霓虹反射、積水地面水花、白霧混黑影流動、飛刀暗紅能量紋、瞬移黑紅殘影、日文短喝

## Technical Specs（統一拍攝參數）
- Aspect Ratio：9:16｜解析度：1080×1920｜FPS：24（如需慢動建議拍 48 匯出 24）
- Shutter：180°（漫畫衝擊段落 144° 保線）；手持 ≤3%
- Lens Set：24/32mm 建立巷道窄深；50/65mm 角色近身瞬移；85–120mm 壓縮飛刀陣
- Camera Motion：滑軌 + 側移 + 局部手持 3% 內；瞬移用鞭移或遮擋剪接
- DOF：近景 f/2.0–2.8（手與飛刀清楚）；中景 f/4–5.6；景深注意霓虹散焦光斑
- Grain：輕膠片顆粒 8%，避免破圖；Chromatic Aberration：≤0.02 保線稿；Dispersion 控制防霓虹邊色散
- Color Pipeline：linear → log → filmic LUT（陰影青藍、霓虹品紅/電藍，紅色能量保持暖）→ 最終對比 +5%；膚色保護
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
基調：{療癒/悸/孤獨/決斷/緊張/盼望}
節奏域：{慢入0.8–1.5｜穩定1.5–2.4｜加速2.4–3.0}s
美術要點：{環境/道具/服裝/妝髮}

Beat {k}（{t0–t1}s）
重點：{情節/行為/情緒變化}
Blocking：{入畫/停位/互動/道具接觸}
Camera：
- 運鏡：{滑軌/側移/繞拍/手持≤3%/穩定器}
- 焦段/機位：{24–35/50–75/100–135mm｜眼高/高/膝高/俯拍}
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
### Style Pack：Anime Fantasy Look（預設開啟，Applicable for 霓虹巷道與角色特寫）
- Applicable for：全段鏡頭；特別用於巷道霓虹與烈的暗紅紋路近景
- Do NOT mix with：seraphic_realism（避免過度柔光）；zenith_noon_realism（避免日照感）
- Default：ON
- Visual traits：clean_edges、強線稿、pastel_magenta/teal/warm_gold 調色、膚色保護
- Audio traits：空氣感留存，保持環境滴水與白霧流動聲，低頻適度
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
  - 邊緣俐落維持動畫質感
  - 色彩飽和但控制膚色
  - 搭配巷道霓虹保持光斑清晰
```

### Style Pack：Urban Switch FX（預設開啟，對瞬移殘影與飛刀軌跡使用）
- Applicable for：瞬移殘影、飛刀軌跡、巷道霓虹閃爍；Act2–Act3 所有打擊角度
- Do NOT mix with：seraphic_realism（避免過度柔霧）；moonlit_wolf_meme（避免表情誇張）
- Default：ON
- Visual traits：motion_defined 線條，charcoal/neon_lime/crimson/steel_blue/tungsten_warm 配色，拖影與能量邊緣 Fresnel 勾光，水面反射帶微波紋
- Audio traits：Transient 加強打擊與瞬移「嗡」聲，低頻抑制避免霧噪，保留滴水和霓虹嗡鳴
- YAML 原文：
```yaml
name: Urban Switch FX Look
noise_reduction: balanced_motion
saturation: neutral_skin_pop
line_enhancement: motion_defined
color_palette:
  primaries: [charcoal, neon_lime, crimson]
  accents: [steel_blue, tungsten_warm]
  skin_tone: preserved
motion_blur_shutter: 170
exposure_bias: +0.2
notes:
  - 夜間城市對比，皮膚自然略暖
  - 動作拖影需兼顧飛刀殘影
  - 水面反射保留波紋與霓虹拉絲
  - 多機位方便匹配遮擋瞬移
```

### Style Pack：Manga Impact Frame：Shadow Scatter（新樣板）
- Applicable for：Angle10–Angle12 終極圓形爆裂斬與殘響，提供漫畫化衝擊格
- Do NOT mix with：real_cinema、seraphic_realism（避免過寫實皮膚）
- Default：ON 於指定鏡頭
- Visual traits：
  - 黑白高對比背景＋粗速度線，角色與飛刀光保持全彩；黑霧碎片保留深灰描邊
  - 彩色日文 SFX「斬」「爆」帶 3px 外描邊與 halftone dots（粒徑 0.8–1.0px）；紅黑爆圈帶放射線條
  - 分格 3–4 格，主格彩色、側格黑白線稿，底格呈現落塵與倒影
- Audio traits：
  - 衝擊瞬間音樂抽空 0.2–0.25s，僅留低頻「ドン」後回流
  - 加入紙張撕裂 + 金屬切削 Foley 疊加，SFX 位置對應畫面文字
- Notes：切換黑白時降低 Bloom，保留線稿銳度；回彩漸進 6–8 帧

## Master Prompt（含 Brand/Physics/PBR/Camera Continuity）
- Brand Bible：鋼川烈＝黑紅戰鬥服、暗紅能量飛刀、瞬移殘影、短髮側削、實戰肌肉；語氣短促日語；場景色調冷霓虹 + 暖紅能量。
- Worldstate：鋼脈都市下層巷道，寬 2.8–3.4 m，牆面鏽蝕金屬＋濕漆霓虹招牌；積水深 1–2 cm 形成鏡面；排氣管吐白霧密度 0.08，風速 1.5 m/s；黑霧沿地流動 0.6 m/s，影域裂縫在地面/牆面。
- Camera Continuity：
  - Act1：24–32mm 俯拍/側推建立環境 → 32–40mm 手部特寫 → 32mm 背影 + 35mm 巷道長焦遠端。
  - Act2：35–50mm 跟隨飛刀，瞬移用鞭移或遮擋；局部 55–65mm 中近景重擊。
  - Act3：65–120mm 聚刀陣與終極爆裂，漫畫格段落快門 144°，其餘 180°。
- Physics & PBR：
  - 地面積水折射率 1.33、粗糙度 0.22；水花粒徑 1–4 mm，重力 9.8 m/s²，落地形成圓環波 0.5 m。
  - 飛刀金屬粗糙度 0.18、金屬度 0.85，紅色能量紋 emissive 1.6 cd/m²，旋轉角速度 ~18 rev/s；瞬移殘影粒子 0.4–0.8 mm，拖影長度 0.8–1.2 m。
  - 戰鬥服彈性纖維粗糙度 0.32、縫線可見；汗膜油光 0.04；鞋底橡膠摩擦係數 0.82 在濕地輕微滑移；踢擊時足背肌肉張力明顯，褲褶延遲 0.1s。
  - 影域小怪：黑霧密度 0.1，骨刺粗糙度 0.45 金屬度 0.25；移動如四足與昆蟲混合，重心低，爬行速度 3–4 m/s；被斬後解散成 0.2–0.5 mm 黑灰粒。
- Optics：霓虹混光 3500–5200K 交錯，主光偏冷 4800K，紅色能量提供暖對比；積水與金屬鏡面有鏡面/粗糙反射，鏡面帶菲涅耳；體積霧受飛刀衝擊帶出流線；景深保持烈眼睛與飛刀清晰。
- Master Prompt：
  - Master(15s｜2D anime neon assassin｜9:16｜24fps｜sharp linework + manga impact)
  - 「鋼脈都市下層濕冷巷道；破碎霓虹、積水反射、白霧與黑影流動；鋼川烈以暗紅飛刀標記瞬移，近身斬擊影域小怪群，終極圓形爆裂斬清場。」
  - 鏡頭：滑軌+側移+鞭移瞬移，手持 ≤3%；表演：冷靜→高速連打→收束；構圖三分線，留白 10–15% 給霓虹與霧。
  - 寫實細節：濕牆 4K 法線，鏽蝕置換；飛刀刮痕與指紋；黑霧折射少，吸收係數 0.2；水花重力與黏度；霓虹眩光控制。

## Platform Layer
- Hook A（故事向 0–1s）：俯瞰霓虹霧巷與低沉怪嘶吼，壓迫氛圍
- Hook B（衝擊向 0–1s）：第一把飛刀慢動作釘入怪群「啷」響
- Caption 建議：短版「暗影飛刃清場」；長版「鋼川烈：巷道瞬移飛刀陣」
- First-shot visual hook：俯視霓虹與積水倒影，遠方黑霧蠢動
- Thumbnail：烈站巷中央，飛刀懸浮紅紋亮，四周黑霧小怪包圍
- Hashtags：#Anime #Action #ShadowBlade #Neon #MangaImpact #9x16
- CTA：末尾定格紅光與飛刀碎片，可加「再看一次瞬移連段」剪輯指示（不入畫）

## Negative Instructions
- 禁用真實商標、名人肖像、宗教政治符號
- 禁用過曝、廉價濾鏡、魚眼過度畸變、手持晃動 >5%
- 畫面尺度：PG-13；破壞以黑霧碎解與光爆呈現，避免血腥
- 不使用寫實照片貼圖；不混用超寫實皮膚細節

## Act/Beat/Angle（12 幕 × 15s，含 Physics/PBR/光學）
### Act 1（0.0–4.5s）｜巷道壓迫與準備 — 基調：緊張、潛伏，節奏域 1.0–1.3s
- 美術要點：霓虹碎光、積水倒影、白霧與黑影流，烈黑紅戰服預亮。

#### Beat 1（0.0–1.0s）
- 重述狀態機：環境建立，怪聲遠處。
- 重點：俯視鋼脈都市下層巷道。
- Blocking：高空俯拍緩降，巷道霓虹映水，遠處黑霧蠢動。
- Camera：24mm 高空俯拍，滑軌下移 2m；對焦層次遠→近；快門 180°。
- Lighting：霓虹紅藍混光 3800–5200K；對比中高；眼神光不需。
- Materials & Physics：積水粗糙度 0.22 形成鏡面，水面微波幅度 3–5 mm；白霧密度 0.08；滴水頻率 1/1.5s；地面金屬板粗糙度 0.35。
- Emotion & Performance：無角色，營造空洞壓迫。
- Audio & Transition：環境空洞、金屬滴水；遠處低吼；直接切 Beat2。
- Angle：中央構圖巷道為主，前中後霧層次；安全：無可讀字。

#### Beat 2（1.0–2.0s）
- 重述狀態機：烈即將出場。
- 重點：鋼川烈走出巷口，戰服微亮。
- Blocking：烈從暗處走向巷中央，靴子踩水花。
- Camera：32mm 側拍中景，輕推 1m；手持 2%；對焦臉與胸；快門 180°。
- Lighting：側逆霓虹，冷藍主光 4800K，紅紋低亮；對比中；眼神光微弱。
- Materials & Physics：戰服布料粗糙度 0.32、縫線可見；積水被踩水花粒徑 2–4 mm，拋角 35°；紅紋 emissive 0.8，呼吸式閃爍每 0.6s。
- Emotion & Performance：烈冷靜、呼吸穩定，肩線緊繃。
- Audio & Transition：水花、靴底摩擦；環境低頻；光源匹配切 Beat3。
- Angle：三分線左 1/3 烈，右側霓虹倒影；安全：去Logo。

#### Beat 3（2.0–3.2s）
- 重述狀態機：烈站定，準備武器。
- 重點：手部特寫飛刀分裂。
- Blocking：烈抬右手，飛刀在指間旋轉並分裂。
- Camera：40mm 手部特寫，背景自動壓暗；對焦刀背；快門 180°。
- Lighting：刀面高光＋紅紋；背景霓虹壓暗；對比高。
- Materials & Physics：飛刀金屬度 0.85、粗糙度 0.18；能量紋發光 pulsate 6 Hz；旋轉角速度 18 rev/s；指節汗膜 0.05，微油光；霧氣受刀風扭曲。
- Emotion & Performance：烈低聲日語呢喃 1–2 字，眼神平穩。
- Audio & Transition：清脆金屬聲＋低沉呢喃；鞭移到背影 Beat4。
- Angle：中央構圖刀，留白 10%；補充淡紅霧；安全：無可讀字。

#### Beat 4（3.2–4.5s）
- 重述狀態機：武器就緒，怪群出現。
- 重點：背影前景烈，中遠景小怪湧出。
- Blocking：烈背對鏡頭，前方排水溝與牆縫冒黑霧小怪爬出。
- Camera：32mm 背影中景，微晃 3%；對焦層次怪群；快門 180°。
- Lighting：霓虹反射在黑霧；暗黃眼點成片亮起；對比高。
- Materials & Physics：黑霧密度 0.1 流速 0.6 m/s；骨刺粗糙度 0.45 金屬度 0.25；地面震動幅度 2–3 mm；水波擴散半徑 0.4 m。
- Emotion & Performance：烈背影穩，肩微抬暗示準備。
- Audio & Transition：低吼＋霧聲，鏡頭微震；直接切 Act2。
- Angle：烈佔畫面 30%，怪群鋪滿前方；補充霧層；安全：無文字。

### Act 2（4.5–11.0s）｜飛刀標記與瞬移連擊 — 基調：加速、壓制，節奏域 1.2–1.5s
- 美術要點：飛刀殘影、紅黑光軌、霧中黑影、打擊能量弧。

#### Beat 5（4.5–5.7s）
- 重述狀態機：第一刀甩出。
- 重點：飛刀慢動作特寫釘入怪群。
- Blocking：烈甩出第一把飛刀，鏡頭隨刀飛行釘入中央。
- Camera：35mm 追刀鏡頭，滑軌向前 3m；快門 180°；對焦隨刀。
- Lighting：刀身反射烈眼神，紅黑殘影拖長；霓虹反射拉絲。
- Materials & Physics：刀速 25 m/s；殘影粒子 0.4–0.8 mm；撞擊時骨刺碎裂粒徑 1–3 mm；水霧被撕開形成 V 形。
- Emotion & Performance：烈眼神鎖定，動作乾淨。
- Audio & Transition：金屬「啷」、風切聲；直接切 Beat6。
- Angle：刀佔畫面中心，背景拉動模糊；安全：無可讀字。

#### Beat 6（5.7–7.0s）
- 重述狀態機：飛刀落點，烈準備瞬移。
- 重點：瞬移出現近身斬擊第一次。
- Blocking：飛刀落點周圍小怪抬頭，烈殘影「啪」出現，一拳半月斬擊。
- Camera：45mm 腰部中近景，手持 3%；快門 180°；對焦烈拳。
- Lighting：紅能量沿手臂爆衝；黑霧被紅光照亮；對比高。
- Materials & Physics：拳弧能量密度 1.2 cd/m²；黑霧被掀開 6 m/s；碎片遵循重力；衣料彈性回彈 0.12s；拳風使霧形成扇形。
- Emotion & Performance：烈低喝，肌肉全力收縮。
- Audio & Transition：短促日文喝聲＋打擊音；遮擋切 Beat7。
- Angle：烈略居左，扇形斬擊掃右側；補充紅黑殘影；安全：無文字。

#### Beat 7（7.0–8.5s）
- 重述狀態機：飛刀標記遍布巷道。
- 重點：連續瞬移＋群體壓制（多紅點）。
- Blocking：斜俯視巷道，紅點飛刀標記多處，烈高速瞬移於紅點間踢擊/肘擊/雙刀斬。
- Camera：28mm 斜俯視，滑軌升降 1m；快門 180°；對焦層次跟隨烈殘影。
- Lighting：紅點標記在黑霧中閃；霓虹與紅光交錯；對比中高。
- Materials & Physics：每次瞬移拖影長 1 m；踢擊碎霧粒 0.2–0.5 mm；肘擊骨刺彈飛 8–10 m/s；鞋底摩擦 0.82，地面水花被捲起形成線條。
- Emotion & Performance：烈表情冷靜，節奏準確。
- Audio & Transition：重節拍配合瞬移節奏；鞭移轉 Beat8。
- Angle：多重殘影形成對角線；安全：無可讀字。

#### Beat 8（8.5–9.7s）
- 重述狀態機：近身踢擊突出力量。
- 重點：低機位貼地，烈一腳側踢碎怪。
- Blocking：烈瞬移到鏡頭前，一腳側踢，小怪碎成黑霧向鏡頭撲。
- Camera：30mm 低機位貼地，跟蹤 1m；快門 180°；對焦腳背。
- Lighting：腿部能量亮到極致；霧被踢向鏡頭遮擋；對比高。
- Materials & Physics：腿部肌肉緊繃，布料拉伸，褲褶延遲 0.1s；黑霧粒子加速度 12 m/s²；水花被踢起 0.6 m；鞋底粗糙度 0.3。
- Emotion & Performance：烈短喝，表情集中。
- Audio & Transition：踢擊衝擊＋霧撲面聲；遮擋切 Beat9。
- Angle：腳背佔前景，霧向鏡頭撲；安全：去Logo。

#### Beat 9（9.7–11.0s）
- 重述狀態機：小怪剩餘，需準備 AOE。
- 重點：聚集飛刀，形成圓圈。
- Blocking：烈單膝半蹲，雙手揚起，散落飛刀被紅能量牽引漂浮成大圈。
- Camera：55mm 中遠景，環繞 120°；快門 180°；對焦飛刀陣。
- Lighting：紅紋同時亮至刺眼，霧被吸附向圓心；對比高。
- Materials & Physics：飛刀漂浮高度 0.8–1.5 m；旋轉角速度 12 rev/s；黑霧被吸附流速 2 m/s；能量線粒徑 0.5 mm；地面水被吸形成向心波。
- Emotion & Performance：烈沉著吸氣，肩膀微抖蓄力。
- Audio & Transition：飛刀嗡鳴、能量吸附聲；鏡頭繞一圈後切 Act3。
- Angle：圓形刀陣佔畫面中間，小怪在外圍；安全：無文字。

### Act 3（11.0–15.0s）｜終極圓形爆裂斬與殘響 — 基調：決斷、收束，節奏域 1.2–1.5s
- 美術要點：飛刀陣、漫畫衝擊格、紅黑衝擊波、落塵與霓虹倒影。

#### Beat 10（11.0–12.5s）
- 重述狀態機：刀陣形成，烈準備終擊。
- 重點：瞬移到圓心，交叉蓄力。
- Blocking：畫面一黑一紅閃，烈出現在圓心，雙臂交叉於胸前蓄能。
- Camera：65mm 全景→中近景，定點微推 1m；快門 144° 漫畫線條清楚；對焦烈臉與手臂。
- Lighting：刀陣紅光圍繞，背景黑白速度線瞬間出現；對比極高。
- Materials & Physics：能量集中在前臂，粗糙度 0.2；汗膜油光 0.04；黑霧在外圍被壓縮形成環狀；飛刀停頓 0.1s 再爆射。
- Emotion & Performance：烈短促日文喝聲，眼神犀利。
- Audio & Transition：音樂抽空 0.2s 後回流；金屬共振；漫畫「斬」SFX；直接切 Beat11。
- Angle：中央烈，刀陣圍繞；補充漫畫放射線；安全：文字僅 SFX。

#### Beat 11（12.5–13.8s）
- 重述狀態機：能量即將釋放。
- 重點：爆裂斬掃空，小怪被抹除。
- Blocking：烈張開雙臂，飛刀向外爆射形成圓形衝擊波，畫面短暫漫畫格。
- Camera：
  - 初段 0.3s：50mm 俯視俯拍，衝擊波擴張；
  - 中段 0.7s：漫畫分格 3–4 格，主格彩色展示衝擊波，側格黑白線稿小怪解散；
  - 收尾 0.3s：回彩跟進衝擊波掃過後景。
  - 快門：漫畫段落 144°，其他 180°。
- Lighting：黑紅能量爆開，霓虹被覆蓋成紅色；回彩後恢復霓虹；對比高。
- Materials & Physics：衝擊波速度 18 m/s 半徑 3–4 m；小怪解散成 0.2–0.5 mm 黑灰粒，遵循重力落下；飛刀碎片帶熾紅邊，粗糙度 0.4；地面水被吹起形成噴環。
- Emotion & Performance：烈怒吼無聲，姿態穩定。
- Audio & Transition：低頻「ドン」+ 撕裂聲；音樂回流；鞭移到 Beat12。
- Angle：主格彩色，側格黑白，底格落塵；安全：僅 SFX 字。

#### Beat 12（13.8–15.0s）
- 重述狀態機：怪群已清空，殘響收尾。
- 重點：爆炸後殘響與收尾特寫。
- Blocking：黑霧被風捲走，飛刀碎片化光點；烈站巷中央略喘，紅紋收斂，轉身走向深處。
- Camera：
  - 開頭 0.6s：慢鏡中遠景，霧向後退；
  - 收尾 0.6s：側後近景烈上半身，轉身離開；鏡頭拉遠定格於地面殘缺飛刀倒影。
  - 快門 180°。
- Lighting：霓虹重新映水，紅光漸弱；灰塵在光束中漂浮；對比回中。
- Materials & Physics：光點粒徑 0.3–0.6 mm 慢速 0.4 m/s 上飄；紅紋亮度衰減 1.6→0.3 cd/m²；汗霧呼氣在冷空氣形成霧 0.8s；水面倒影拉絲。
- Emotion & Performance：烈呼吸穩定，眼神帶戰意光；轉身果斷。
- Audio & Transition：回到滴水與遠警笛；畫面淡出；收束。
- Angle：前中後層：霧/烈/巷深；最後定格飛刀倒影；安全：無可讀字。

## Platform Slices / Caption 對應
- 短版截取：0.0–2.0s 建立霓虹壓迫 + 3.2–4.5s 小怪湧出，字幕「下層影域開啟」「獵手登場」
- 衝擊版截取：11.0–13.8s 終極爆裂斬漫畫格，字幕「斬・爆」
- 長版保留全程，字幕與 Hook 對應：HookA 0–1s 霓虹俯瞰、HookB 4.5–5.7s 第一刀釘入

## Assumptions
- 巷道寬度與積水深度如上；無其他角色介入；無 UI。
- 飛刀能量色維持紅黑，不加入其他色以避免風格衝突。
- 日語短喝僅作聲音，不上螢幕字幕。

## Negative Instructions 自動檢核清單
- ☐ 無品牌 Logo 或真實商標
- ☐ 無可讀文件、看板、宗教或政治符號
- ☐ 手持晃動 ≤5%，無魚眼畸變
- ☐ 無血腥破皮，破壞以黑霧解散與能量爆呈現
- ☐ 字幕僅漫畫擬聲字，無額外 UI

## AGENT Self-Check
- 結構：已依 Master/Act/Beat/Angle/timecode 12 幕撰寫，含 Platform Layer、Assumptions、Platform Slices。
- Physics & PBR：每 Beat 標註重力、慣性、粒徑、折射、布料摩擦；Master 提供光學與材質參數。
- Stylepacks：Anime Fantasy Look + Urban Switch FX 預設開啟，Angle10–12 啟用 Manga Impact Frame：Shadow Scatter；無衝突風格。
- Continuity：延續鋼川烈黑紅戰服與飛刀設定；場景移至鋼脈都市下層巷道；記錄霓虹反射與飛刀碎片光點為持續要素。
- QA：已附 QA Checklist；交付前需確認 LUT、種子、音畫同步、無侵權元素。

## Camera Continuity Notes（跨鏡延續）
- Act1 結束機位：32mm 背影微晃，Act2 開頭接追刀 35mm 需保持運動方向一致並以霓虹光源匹配。
- Act2 Beat7 多瞬移使用同一對角線運動，遮擋點選用黑霧與霓虹招牌；Beat8 低機位需記錄高度 15 cm 以便後續重現。
- Act3 漫畫格段落使用快門 144°、飽和度下降 10%，回彩時需平滑過渡至 180° 正常參數。

## Persistent Elements（跨集保留）
- 角色：鋼川烈黑紅戰服、暗紅飛刀紋路、瞬移殘影樣式；能量色紅黑固定。
- 場景：下層巷道霓虹破碎光、積水鏡面、白霧與黑影流動；地面刮痕與飛刀碎片光點在下一集需保留或說明清理。
- 道具與特效：飛刀殘影、紅黑衝擊波、漫畫擬聲字風格（斬/爆），體積霧扭曲；滴水頻率與霓虹閃爍保持一致。
- 音樂動機：空洞環境 + 低頻節奏，瞬移伴隨「嗡」；終擊時音樂抽空後回流的處理需維持系列一致。

## Changelog vs Previous Episode
- 新增場景：從冰霜廣場轉至鋼脈都市下層巷道，加入霓虹與積水倒影設定。
- 角色武裝：回到飛刀瞬移戰鬥，強化能量紋對飛刀的連結，新增圓形刀陣終擊。
- 風格調整：維持 Anime Fantasy + Urban Switch FX，新增 Manga Impact Frame：Shadow Scatter 專供終擊漫畫格，擬聲字改為「斬」「爆」。
- 持續要素更新：記錄地面水花與飛刀碎片光點，需於後續集數保留；霧流方向 1.5 m/s 需保持。

## Micro-action Timeline 補充
- Beat6 半月斬擊（T0–T1.3s）：
  - T0：烈從殘影中出現，左腳踏地產生水波；
  - T0+0.4：腰轉帶拳，紅能量沿手臂向外 12 m/s；
  - T0+0.9：拳弧掃過小怪，黑霧被扯成細絲；
  - T1.3：烈收拳轉身準備下一跳，霧回填形成渦流。
- Beat7 多點瞬移（T0–T1.5s）：
  - T0：第一個紅點閃亮，烈瞬移出現空中踢擊；
  - T0+0.5：第二個紅點牆邊肘擊，牆面水滴被震散；
  - T0+1.0：落地雙刀交叉斬，地面水花形成 X 形；
  - T1.5：殘影收束，紅點短暫閃爍後熄滅。
- Beat11 爆裂斬（T0–T1.5s）：
  - T0：雙臂張開，飛刀同步爆射；
  - T0+0.3：漫畫主格出現，衝擊波邊緣帶放射線；
  - T0+0.9：側格顯示小怪霧化，黑灰粒向外拋 15 m/s；
  - T1.5：回彩，全景霧被掃清僅留紅光塵。

## Platform Layer 追加切片策略
- Shorts 版本：剪入 Beat5 慢動飛刀 + Beat8 低機位踢碎，字幕「一刀開局」「貼面碎影」。
- Reels 版本：保留 Beat7 瞬移連打連段，左右聲道配合紅點位置；字幕逐段標記「踢」「肘」「斬」。
- 長版 YouTube：完整 15s，描述欄附色溫/LUT/種子方便複製；終擊漫畫格保留高解析。

## Execution Notes
- 求解建議：黑霧使用 VDB + velocity field，骨刺 RBD；飛刀殘影可用 Houdini Trails + Sprite Sheet；瞬移用鞭移 + 光源遮擋。
- 渲染：保持 log，霓虹避免飽和剪裁；紅黑能量 Bloom 控制不過曝；水面使用 Screen Space Reflection 加微波法線。
- Denoise 限制：漫畫段落關閉時域降噪保持線稿；霧量大段落降低 denoise 以保體積層次。
- 相機校正：24–32mm 時作 5% barrel 校正避免巷道畸變；長焦聚刀陣需記錄焦距與 DOF 以便連戲。
- 音畫同步：瞬移「嗡」聲觸發紅點亮度，門檻 -12 dB，attack 25ms，release 180ms；衝擊波用 envelope 控制 Bloom。
- 安全：檢查無多餘文字、無未授權素材；漫畫 SFX 為唯一文字。

## Next Episode / Spin-off Ideas
- 主線延伸 1：影域裂縫暫時封閉但留下紅黑殘光，可作為下一集追查源頭的線索，可能引出更大型影獸。
- 主線延伸 2：巷道戰後霓虹系統受能量衝擊閃爍，可讓烈追蹤能源供應管線，導向地鐵層的伏擊戰。
- 番外/日常短片：烈在裝備間維護飛刀，測試能量紋與瞬移同步，展示細膩控制與品牌語氣的冷靜旁白。

## SORA Prompt Compiler 提醒
- 完成 `prompt.md` 後需以 SORA PROMPT COMPILER 轉為 `sora.md` JSON，僅保留渲染必要資訊（meta/style/global_prompt/negative/shots）。
- `shots` 需對應 12 幕 S01–S12，時間以 15s ÷ 12 平均換算，保持英文 3–5 句描述運鏡/光影/材質/情緒/聲音。
- 禁止將 `_core`/`_stylepacks` 全文或平台層文字帶入 `sora.md`，僅保留必要禁用項與場景要點。

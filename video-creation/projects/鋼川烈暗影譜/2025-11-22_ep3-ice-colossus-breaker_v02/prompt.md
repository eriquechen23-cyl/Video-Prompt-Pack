# 鋼川烈暗影譜 EP3 — 爆紋鬥拳 vs 巨人冰石像 PV Prompt（15s｜12 幕｜9:16）

來源劇本：使用者提供之《爆紋鬥拳・鋼川烈 vs 巨人冰石像》完整影片 PROMPT v2（已含世界觀＋角色外觀＋爆紋鬥拳特效＋12 幕分鏡）

## Required Input Fields（拍前必填）
- project_name：鋼川烈暗影譜
- series_name/arc：鋼脈都市邊境冰戰篇
- episode_index：3
- slug：ice-colossus-breaker_v02
- target_platform：短影音（TikTok/YouTube Shorts/IG Reels 同步）
- duration_sec：15（預設 12 幕 × 1.2s）
- style_primary：Anime Fantasy Look + Urban Switch FX（本檔 Default ON）
- style_secondary：Manga Impact Frame：Ice Rupture（Angle 12 強制啟用）
- worldstate_ref：鋼脈都市邊緣冷卻塔廣場被霜凍封鎖，巨人冰石像甦醒
- goal：2D 日系戰鬥番 PV，冰霜對比爆紋拳，結尾漫畫分格頭頂爆破

## Project Info（UTC+8 日期規則）
- Project 路徑：video-creation/projects/鋼川烈暗影譜/2025-11-22_ep3-ice-colossus-breaker_v02
- 拍攝日期標記：2025-11-22（UTC+8）
- 畫幅：9:16 直式，構圖預留字幕下緣 12% 安全框
- 時長與節奏：15 秒（12 幕×1.2s），Act 切分：Act1 0–4.8s｜Act2 4.8–10.8s｜Act3 10.8–15.0s
- 角色狀態：鋼川烈（短髮肌肉青年，黑紅戰鬥服，手臂爆紋暗紅待啟；爆紋蓄力會亮到紅橘並噴微爆粒子）；巨人冰石像（樓層高，石砌肌肉覆冰層，裂縫藍白能量脈動，關節厚冰）
- 持續要素：冰霜粒子飄落、紅橘爆紋光、冷霧白氣、碎冰破片的高亮反光、微震動視覺、漫畫擬聲字「ドガァァン!!」於 Angle 12

## Technical Specs（統一拍攝參數）
- Aspect Ratio：9:16｜解析度：1080×1920｜FPS：24（若需慢動建議拍 48 匯出 24）
- Shutter：180°（Angle 12 漫畫衝擊改為 144° 線條更銳）
- Lens Set：24mm/32mm 建立巨人量感；50mm/65mm 近距爆紋；85–135mm 壓縮碎片鏈
- Camera Motion：滑軌＋側移＋有限手持 ≤3%；高速繞拍時保持主體清晰，配合遮擋或鞭移轉場
- DOF：近景 f/2.0–2.8（拳頭與眼睛清楚）；遠景 f/4–5.6；保持巨人巨大感與前景冰屑層次
- Grain：輕膠片顆粒 8%，避免破圖；Chromatic Aberration：≤0.02 以保線稿；Dispersion 控制防止冰屑邊彩
- Color Pipeline：linear → log → filmic LUT（陰影冷藍、冰層偏青，高光暖橘來自爆紋）→ 最終對比 +6%；膚色保護
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
### Style Pack：Anime Fantasy Look（預設開啟，Applicable for 空間建立與角色特寫）
- Applicable for：全段鏡頭；特別用於冰霜廣場遠景與烈的爆紋近景
- Do NOT mix with：seraphic_realism（避免過度柔光）；urban_switch_fx（若需乾淨線稿時關閉疊加）
- Default：ON
- Visual traits：clean_edges、強線稿、pastel_magenta/teal/warm_gold 調色、膚色保護
- Audio traits：依主配樂維持空氣感，減少重低頻，保留冰裂聲與拳擊衝擊
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

### Style Pack：Urban Switch FX（預設開啟，對爆紋與冰霜衝擊使用）
- Applicable for：爆紋衝擊、冰屑爆破、速度線層；Act2–Act3 所有打擊角度
- Do NOT mix with：seraphic_realism（避免過度柔霧）；zenith_noon_realism（避免偏日間曬感）
- Default：ON
- Visual traits：motion_defined 線條，charcoal/neon_lime/crimson/steel_blue/tungsten_warm 調和，動作拖影兼顧服裝殘影，Fresnel rim light 在冰層邊緣
- Audio traits：配合爆紋衝擊同步的 transient 放大；冰裂高頻清晰；低頻抑制避免混濁
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
  - 保留夜間城市對比，皮膚自然略暖
  - 動作拖影需兼顧服裝切換殘影
  - 配合雨霧與火星可用 Fresnel rim light
  - 建議同場景多機位以利無縫隱剪
```

### Style Pack：Manga Impact Frame：Ice Rupture（新樣板）
- Applicable for：Angle 12 漫畫黑白擊破，頭頂垂直爆破分格
- Do NOT mix with：real_cinema、seraphic_realism（避免過度寫實膚質）
- Default：ON 於指定鏡頭
- Visual traits：
  - 黑白高對比背景＋粗速度線，角色與爆紋光保持全彩；碎冰邊緣保留淡藍描邊
  - 巨大彩色日文 SFX「ドガァァン!!」帶 3px 外描邊與 halftone dots（粒徑 0.8–1.2px）
  - 漫畫格 3–4 格分布，主格彩色，側格黑白線稿，底部長條顯示坑洞與煙霧
- Audio traits：
  - 衝擊瞬間音樂抽空 0.25s，僅留低頻「ドン」後回流
  - 碎冰加入紙張撕裂 Foley 疊加，立體聲掃掠；SFX 音量 +3 dB 對應文字位置
- Notes：切換至黑白時降低 Bloom，保留線稿銳度；回流時漸進上色 6 帧

## Master Prompt（含 Brand/Physics/PBR/Camera Continuity）
- Brand Bible：鋼川烈＝黑紅戰鬥服、紅橘爆紋拳、短髮側削、實戰肌肉、冷靜集中；語氣硬派短句，中日混用（「爆、穿」等）；場景色調冷藍冰霜 + 暖橘爆光。
- Worldstate：鋼脈都市邊緣冷卻塔廣場，地面覆冰厚度 3–6 cm，鋼梁與廢墟結霜；體積霧 8% 隨風 2 m/s 飄移；巨人冰石像如樓高，石肌金屬混合，冰層粗糙度 0.3，裂縫藍白能量跳動。
- Camera Continuity：開場 24–28mm 高空俯瞰，Act1 維持 28–32mm 建立巨感；Act2 35–50mm 繞腿與胸口；Act3 65–135mm 於蓄能與終擊壓縮；全段 180° 快門，Angle 12 144°。
- Physics & PBR：
  - 冰屑粒徑 2–12 mm，密度 0.9 g/cm³，碎裂時遵循重力 9.8 m/s²，空氣阻力使橢圓抛物線下降；石塊質量 30–80 kg，落地再碎成二次粒子。
  - 爆紋光源為紅橘炙熱，PBR 粗糙度 0.2、金屬度 0.1，拳頭皮膚 SSS 明顯，汗膜反射 0.05；冰層折射 1.31，內部藍白體積散射，邊緣 Fresnel 高亮。
  - 布料：上衣彈性纖維粗糙度 0.35，縫線可見；戰鬥鞋橡膠底摩擦係數 0.85 在冰面仍略滑；滑行留下刮痕深 2–4 mm；氣浪扭曲用 heat haze。
- Optics：側逆光勾邊，冷藍主光 5200K，爆紋暖光 5000–6000K 提供色溫對比；景深保持烈雙眼與拳頭清晰；速度線向量模糊；冰層鏡面反射含粗糙法線，輕微色散 0.02 限制。
- Master Prompt：
  - Master(15s｜2D anime ice vs explosive fist｜9:16｜24fps｜sharp linework + manga impact)
  - 「霜凍冷卻塔廣場；冰封地面、破碎鋼梁、巨人冰石像甦醒；鋼川烈以紅橘爆紋鬥拳沿腿拆解，躍頂雙拳貫穿頭頂引爆整具巨人，末段漫畫分格。」
  - 鏡頭：滑軌+側移+繞拍，手持 ≤3%；表演：專注→爆發→收束吐白霧；構圖三分線，巨人保持量感，留白 10–15%。
  - 寫實細節：冰霜貼圖 4K 法線，裂紋置換；拳套磨損邊緣；爆紋粒子大小 0.5–1.5 mm；冰屑折射反光；環境霧受拳風扭曲。

## Platform Layer
- Hook A（故事向 0–1s）：高空俯瞰冰封廣場與巨人甦醒，冰霜粒子飄落
- Hook B（衝擊向 0–1s）：Angle 4 第一記爆紋膝擊，紅橘衝擊環擊碎冰層
- Caption 建議：短版「爆紋鬥拳 vs 冰石巨像」；長版「鋼川烈：從膝到頭的貫穿爆破」
- First-shot visual hook：冰封廣場俯瞰與巨人石冰肌理，藍白能量脈動
- Thumbnail：烈躍於巨人頭頂上方蓄力，紅橘能量尾跡繞塔，巨人眼窩藍光
- Hashtags：#Anime #Action #Explosion #Ice #MangaImpact #9x16
- CTA：末尾定格烈吐白霧，畫面可加「再看一次爆破」剪輯指示（不入畫）

## Negative Instructions
- 禁用真實商標、名人肖像、宗教政治符號
- 禁用過曝、廉價濾鏡、魚眼過度畸變、超過 5% 手持晃動
- 畫面尺度：PG-13；破壞以碎冰/光爆呈現，避免血腥
- 不使用寫實照片貼圖；不混用超寫實皮膚細節

## Act/Beat/Angle（12 幕 × 1.2s，含 Physics/PBR/光學）
### Act 1（0.0–4.8s）｜冰鎮壓迫與起手 — 基調：緊張、寒冷對比，節奏域 1.5–2.0s，建立巨感與主角準備
- 美術要點：結霜廣場、破碎鋼梁、冷卻塔剪影、冰層反光、烈黑紅戰服、巨人石冰肌理藍白脈動。

#### Beat 1（0.0–1.2s）
- 重述狀態機：初始空場，建立環境與巨人靜止。
- 重點：高空俯瞰冰鎮廣場與巨人冰石像。
- Blocking：巨人站中央靜止，周遭霜面裂痕；鏡頭向下推。
- Camera：24mm 高空俯拍，滑軌垂直緩降 2m；對焦層次由遠塔→巨人→地表裂紋；快門 180°。
- Lighting：冷藍主光 5200K 從天頂，地面反光偏青；對比中高；眼神光不需。
- Materials & Physics：冰面粗糙度 0.35、金屬度 0，薄霧散射 8%；冰霜粒子飄落速度 0.4 m/s 受風 2 m/s 飄偏；巨人石肌粗糙度 0.5 帶冰晶法線。
- Emotion & Performance：壓迫寂靜，巨人尚未動，靠藍白脈動暗示生命。
- Audio & Transition：風聲輕、冰霜摩擦聲；音樂低頻墊入；直接切 Beat2。
- Angle：中央構圖巨人占畫面 40%，前中後層塔/巨人/地裂；補充細霧漂浮；安全：無可讀字。

#### Beat 2（1.2–2.4s）
- 重述狀態機：巨人靜止即將甦醒。
- 重點：巨人頭部轉動，肩膀冰層裂開。
- Blocking：巨人上半身仰角中近景，頭部微轉，肩冰裂。
- Camera：32mm 膝高仰拍，手持 2% 微震；對焦在眼窩→肩裂；快門 180°；呼吸拉焦。
- Lighting：冷主光 5000K，裂縫藍白自發光；對比高，邊緣冰反射。
- Materials & Physics：冰層厚 4 cm、粗糙度 0.3；裂紋延伸伴隨冰屑噴射速度 3–4 m/s；石肌金屬度 0.2 帶磨痕；體積霧因裂開被震動。
- Emotion & Performance：巨人甦醒壓迫，鏡頭微震加重量感。
- Audio & Transition：冰裂聲、低頻隆隆，金屬摩擦；鞭移遮擋轉 Beat3。
- Angle：巨人頭與肩佔畫面 60%，仰角強調體量；補充藍白脈動；安全：無可讀符號。

#### Beat 3（2.4–3.6s）
- 重述狀態機：巨人甦醒，烈準備進場。
- 重點：鋼川烈登場，爆紋預亮。
- Blocking：烈低角推近三分之二身，身體前傾握拳，站在畫面右側。
- Camera：28mm 低機位側前推 1m；對焦單點在拳頭→眼睛；快門 180°。
- Lighting：側逆光冷藍 5200K，自上方；爆紋初亮紅橘 5200–5500K；對比中，眼神光微弱。
- Materials & Physics：戰服布料粗糙度 0.32、有縫線；爆紋紋路置換微凸，亮時金屬度 0.1；腳邊冰裂紋深 1–2 mm，冰屑因腳壓跳起 0.3 m。
- Emotion & Performance：烈專注、呼吸收束，手指微震。
- Audio & Transition：拳緊握布料摩擦、爆紋火花細聲；光源匹配切 Beat4。
- Angle：三分線，烈在右 1/3，左側遠景巨人腿模糊；補充冰霧飄；安全：去Logo。

#### Beat 4（3.6–4.8s）
- 重述狀態機：烈已蓄勢，準備首擊。
- 重點：低位衝刺與膝關節爆破（第一記爆紋）。
- Blocking：烈從右側貼地滑入，繞過巨人腳掌，轉腰抬拳擊膝。
- Camera：35mm 低角貼地跟拍，滑軌側移 3m，手持 ≤2%；對焦隨拳；快門 180°。
- Lighting：冷主光 + 爆紋暖光瞬間提升；膝部冰層反射橘光；對比提高。
- Materials & Physics：拳套皮革粗糙度 0.25；膝冰層折射 1.31、粗糙度 0.28；衝擊環衝量推開冰屑 6–8 m/s；碎冰遵循重力落下，部分因爆風向外拋。
- Emotion & Performance：烈咬牙重擊，身體低重心旋腰。
- Audio & Transition：爆紋衝擊「ドン」低頻 + 冰碎高頻；震波使畫面微震 1–2px；直接切 Act2。
- Angle：膝關節近景，構圖中央；前景冰屑飛向鏡頭；安全：無可讀字。

### Act 2（4.8–10.8s）｜拆解腿部到胸口 — 基調：加速、攻守交替，節奏域 2.4–3.0s
- 美術要點：冰屑鏈、紅橘爆紋鏈、冰震波、能量核心藍白光。

#### Beat 5（4.8–6.0s）
- 重述狀態機：膝已爆裂，腿部裂縫形成踏點。
- 重點：烈沿腿爆紋連打往上拆解。
- Blocking：烈踩裂縫往上跑，每一步打出拳；鏡頭環繞腿部。
- Camera：32mm 繞拍 220° 高速，保持烈與裂縫居中；對焦層次拉焦腳→拳；快門 180°。
- Lighting：冷主光 + 爆紋暖光沿腿向上，對比高；體積霧被衝擊切開。
- Materials & Physics：每拳向內塌陷再爆開，冰層粗糙度 0.3；爆紋粒子 0.5–1.5 mm，速度 10 m/s；掉落碎石質量 5–10 kg 再撞地二次碎裂。
- Emotion & Performance：烈節奏穩定、每拳吐氣，肌肉緊繃。
- Audio & Transition：連打節奏與音樂鼓點同步；鞭移遮擋轉 Beat6。
- Angle：腿部占滿畫面，烈與爆紋鏈形成對角線；補充碎冰尾煙；安全：去可讀字。

#### Beat 6（6.0–7.2s）
- 重述狀態機：腿部嚴重破壞，巨人反擊準備踏地。
- 重點：巨人暴走，冰震波反擊。
- Blocking：巨人抬另一腿重踏地面，烈被震退滑行。
- Camera：35mm 中遠側視，固定位置觀察衝擊；對焦鎖在踏點→烈；快門 180°。
- Lighting：踏點藍白光爆，高對比；爆紋護拳未啟；環境霧被震波推開。
- Materials & Physics：踏擊點產生冰刺高度 1–1.5 m；震波速度 20 m/s 沿地面傳播；烈滑行摩擦係數 0.85，冰屑刮痕深 3 mm；碎冰拋角 35°。
- Emotion & Performance：烈被迫後退，眉頭緊鎖仍保持重心。
- Audio & Transition：低頻重踏、冰刺爆破、震波嗡鳴；匹配剪接轉 Beat7 以震波前緣作遮擋。
- Angle：巨人與烈同框，震波向鏡頭推；補充冰霜煙塵；安全：無可讀字。

#### Beat 7（7.2–8.4s）
- 重述狀態機：震波抵達，烈需要防禦。
- 重點：爆紋護拳抵消衝擊。
- Blocking：烈雙臂交叉胸前，腳步穩；護盾亮起。
- Camera：50mm 中近景正面；微推 0.6m；對焦臉與手臂；快門 180°。
- Lighting：爆紋全亮紅橘，震波藍白撞擊；對比極高；眼神光保留。
- Materials & Physics：爆紋護盾表面粗糙度 0.18、金屬度 0.12，形成透明氣壓球；冰屑被彈飛速度 8–12 m/s；慢動作 0.7x 0.4s 突顯碰撞；碎冰撞盾有彈性係數 0.25。
- Emotion & Performance：烈咬牙、肌肉繃緊，重心下沉。
- Audio & Transition：護盾炸裂混色聲；音樂暫降後回復；直接切 Beat8。
- Angle：烈中心構圖，護盾衝擊波佔前景；補充空氣扭曲；安全：去Logo。

#### Beat 8（8.4–9.6s）
- 重述狀態機：震波被抵消，巨人胸口待攻。
- 重點：烈躍上胸口，打開能量核心。
- Blocking：烈踩碎冰踏點跳上胸口，重拳砸下。
- Camera：40mm 後仰跟拍跳躍，鏡頭隨烈上升 3m；對焦單點在拳頭；快門 180°。
- Lighting：胸口爆光藍白，爆紋紅橘包圍；光比高；體積霧被拳風推散。
- Materials & Physics：胸冰層厚 5 cm 粗糙度 0.28；能量核心自發光 6500K；碎冰以 12–15 m/s 向外噴；拳頭摩擦冰面產生熱霧；石塊內部顯示熔岩狀光流。
- Emotion & Performance：烈呼氣重擊，眼神鎖定核心。
- Audio & Transition：冰爆＋能量嗡鳴；拉鏡至落地 Beat9；可用遮擋轉場。
- Angle：從烈背後仰視，胸口裂開中心；補充粒子噴射；安全：無可讀字。

### Act 3（10.8–15.0s）｜蓄能到終擊漫畫格 — 基調：決斷、高潮收束，節奏域 2.4–3.0s
- 美術要點：爆紋蓄能光軌、紅橘回收、子彈時間扭曲、漫畫黑白格。

#### Beat 9（9.6–10.8s）
- 重述狀態機：胸口已裂，烈落回地面。
- 重點：落地滑行，能量回收到雙拳。
- Blocking：烈落地向後滑，右腳穩住，雙拳收腰蓄力。
- Camera：45mm 斜俯視跟拍滑行 2m；對焦拳頭；快門 180°。
- Lighting：地面光軌紅橘向上回收，環境冷藍；對比高。
- Materials & Physics：滑行刮痕深 2–3 mm，冰屑被融成水霧再蒸；光軌回收速度 6 m/s 沿腿到手臂；鞋底橡膠摩擦產熱煙。
- Emotion & Performance：烈沉穩吸氣，肩膀起伏，眼神鎖巨人。
- Audio & Transition：滑行摩擦、能量吸入聲；直接切 Beat10。
- Angle：烈位於右下，光軌導向拳頭；補充地面反光；安全：去Logo。

#### Beat 10（10.8–12.0s）
- 重述狀態機：能量集中，需特寫蓄能。
- 重點：爆紋蓄能特寫（肌肉與紋路）。
- Blocking：手臂與拳頭特寫，背景虛化。
- Camera：75mm 近距特寫，單點對焦拳背與青筋；快門 180°；微移 0.2m。
- Lighting：紅橘爆紋漸亮，周圍冷藍邊光；熱浪扭曲使背景散焦波動。
- Materials & Physics：膚質 SSS 層顯汗膜，油光 0.05；爆紋流動速度每 0.2s 一段；拳頭氣壓球透明度 0.2；旋轉碎冰粒子數 400–600，速度 3 m/s。
- Emotion & Performance：烈深呼吸，青筋浮起，指節微顫。
- Audio & Transition：心跳低鼓、氣流吸入；鞭移上推至 Beat11。
- Angle：中央構圖拳頭，留白 10%；補充熱氣波紋；安全：無可讀字。

#### Beat 11（12.0–13.2s）
- 重述狀態機：拳頭蓄滿能量，準備跳頂。
- 重點：躍上頭頂，自上而下俯衝準備。
- Blocking：烈沿冰柱與裂縫跳升，停於巨人頭頂上方合拳，前傾待砸。
- Camera：
  - 前半：35mm 側後方跟拍衝刺上升 4m；
  - 後半：65mm 快速上升至巨人頭頂俯視，烈跳向鏡頭；對焦隨烈。
- Lighting：紅橘尾跡清晰；背景慢動子彈時間；冷藍主光保留輪廓。
- Materials & Physics：能量尾跡持續 0.6s，粒子速度 8–10 m/s；氣壓球在拳外形成透明殼折射冰屑；碎冰滑過氣壓表面受摩擦融化。
- Emotion & Performance：烈眼神鎖頂點，短暫停頓後俯衝。
- Audio & Transition：音樂抽空 0.15s 營造子彈時間；呼嘯風聲；直接切 Beat12。
- Angle：俯視構圖，巨人頭頂為背景，烈衝向鏡頭；補充尾跡弧線；安全：無可讀字。

#### Beat 12（13.2–15.0s）
- 重述狀態機：烈已在頭頂上方蓄滿力道。
- 重點：漫畫感終極爆破，從頭頂貫穿全身。
- Blocking：雙拳垂直砸頂，垂直爆炸鏈；漫畫分格呈現。
- Camera：
  - 命中瞬間 0.2s：俯視正上方 50mm，定格衝擊；
  - 中段 0.7s：切漫畫分格 3–4 格，主格斜側上方；
  - 收尾 0.2–0.3s：回到全彩，拉近烈側臉特寫。
  - 快門：命中 144° 保線；其餘 180°。
- Lighting：爆紋極亮紅橘 6000K，貫穿沿節點噴光；背景黑白線稿時抑制 Bloom；回彩恢復對比。
- Materials & Physics：爆破沿脖、胸、腹、膝噴碎冰速度 15–20 m/s；坑洞深至地面 1.5–2 m；漫畫格碎冰邊緣 halftone；烈拳頭冒煙，護腕燒焦粗糙度 0.4。
- Emotion & Performance：烈怒吼無聲，落地半跪，吐白霧後眼神穩定。
- Audio & Transition：低頻「ドン」→音樂抽空→回流；SFX「ドガァァン!!」疊加；結尾淡出。
- Angle：
  - 主格彩色：烈拳嵌頂，爆紋鏈垂直；
  - 側格黑白：頭部炸裂、軀幹裂開；
  - 底格：坑洞與半跪烈背對鏡頭，全彩；
  - 回彩特寫：烈側臉 75mm，爆紋熄滅冒煙；留白 10%。
- 安全：漫畫擬聲字為唯一文字；無商標。

## Platform Slices / Caption 對應
- 短版截取：0.0–2.4s（巨人甦醒）＋3.6–4.8s（首擊），字幕「冰封巨像醒了」「爆紋鬥拳先手」
- 衝擊版截取：12.0–15.0s 終擊漫畫格，字幕「ドガァァン!! 貫穿」
- 長版保留全程，字幕與 Hook 對應：HookA 0–1s「冰鎮廣場甦醒」、HookB 3.6–4.8s「首擊爆破」

## Assumptions
- 巨人冰石像尺寸約 6–7 層樓高；冰層厚度設定已如上。
- 爆紋顏色固定紅橘，不加入其他色系避免風格衝突。
- 無其他角色或 UI 介面；聲音僅環境與音樂，不含對話。

## Negative Instructions 自動檢核清單
- ☐ 無品牌 Logo 或真實商標
- ☐ 無可讀文件、看板、宗教或政治符號
- ☐ 手持晃動 ≤5%，無魚眼畸變
- ☐ 無血腥破皮，破壞以碎冰與光爆呈現
- ☐ 字幕僅漫畫擬聲字，無額外 UI

## AGENT Self-Check
- 結構：已依 Master/Act/Beat/Angle/timecode 12 幕撰寫，含 Platform Layer、Assumptions、Platform Slices。
- Physics & PBR：每 Beat 標註重力、慣性、冰屑粒徑、爆紋 PBR、布料摩擦、折射；Master 提供整體光學與材質參數。
- Stylepacks：Anime Fantasy Look + Urban Switch FX 預設開啟，Angle 12 啟用 Manga Impact Frame：Ice Rupture；未混用衝突風格。
- Continuity：延續鋼川烈黑紅戰服與爆紋設定；新場景為鋼脈都市冷卻塔廣場；無前集未解元素。
- QA：已附 QA Checklist；需交付前逐項確認 LUT、種子、音畫同步、無侵權元素。

## Camera Continuity Notes（跨鏡延續）
- Act1 結束機位：35mm 貼地膝高，運鏡向左；Act2 開頭承接同向滑軌，維持運動方向一致。
- Act2 Beat6 震波畫面使用固定側視，下一鏡 Beat7 需以震波前緣遮擋作匹配剪接，保持視角高度一致避免跳接。
- Act3 蓄能特寫（Beat10）需記錄焦距 75mm、光圈 f/2.0、快門 180°，便於回到 Beat11 65mm 俯視時做柔和遮擋轉場。

## Persistent Elements（跨集保留）
- 角色：鋼川烈黑紅戰服、爆紋圖騰、短髮與琥珀眼；爆紋顏色紅橘固定。
- 場景：冷卻塔剪影、結霜鋼梁、冰霧 8% 體積；地面刮痕與坑洞需在後續集數保留或合理修復。
- 道具與特效：爆紋衝擊環、紅橘能量光軌、漫畫擬聲字風格；冰屑粒徑 2–12 mm，速度分佈需一致。
- 音樂動機：低頻重鼓 + 高頻冰裂，終擊時音樂抽空再回流的處理需保持系列一致性。

## Changelog vs Previous Episode
- 新增場景：由黑塔城轉至鋼脈都市冷卻塔冰霜廣場，增加藍白體積霧與冰面反射設定。
- 角色武裝：雙匕首場景改為空手爆紋鬥拳，增加手臂爆紋 PBR 參數與氣壓球特效。
- 風格調整：維持 Anime Fantasy Look，但加入 Urban Switch FX 以強化冰霜爆破拖影；漫畫格樣式改為彩色主格 + 黑白側格，擬聲字改「ドガァァン!!」。
- 持續要素更新：新增冰面刮痕與頭頂坑洞需在下一集持續存在或以鏡頭解釋修復。

## Micro-action Timeline 補充
- Beat4 膝擊（T0–T1.2s）：
  - T0：烈右腳貼地滑入，左腳外旋提供反作用力；
  - T0+0.4：腰部扭轉帶動肩膀，拳頭沿斜上軌道；
  - T0+0.8：拳面接觸冰層 0.05s 後爆紋觸發，衝擊環半徑 0.6m；
  - T1.1：碎冰向外飄，烈重心壓低準備下一步。
- Beat7 抵擋（T0–T1.2s）：
  - T0：震波前緣觸及護盾，表面張力波紋 0.2m；
  - T0+0.5：護盾紅橘與震波藍白混色產生扭曲，烈腳跟下滑 5 cm；
  - T0+0.9：慢動作展開，冰屑在護盾表面滑動留下熔化軌跡；
  - T1.2：護盾壓回震波，烈抬頭準備反攻。
- Beat12 終擊（T0–T1.8s）：
  - T0：雙拳命中頭頂，形成高亮光點；
  - T0+0.2：轉入漫畫分格，主格顯示爆紋鏈沿軀幹下貫；
  - T0+0.9：側格展示頭部大塊碎冰飛散，碎片邊緣帶藍光；
  - T1.4：底格顯示坑洞白霧，烈半跪冒煙；
  - T1.8：畫面回彩，鏡頭推近烈側臉定格。

## Next Episode / Spin-off Ideas
- 主線延伸 1：巨人冰石像破碎後留下藍白核心碎片，下一集可作為新的能源爭奪，引入其他武裝團隊。
- 主線延伸 2：冷卻塔區域因爆破造成能量失衡，觸發更大範圍的霜暴，鋼川烈需尋找封印方法。
- 番外/日常短片：烈在訓練場測試爆紋控制，使用冰塊靶做微爆練習，展示細膩控制力。

## Platform Layer 追加切片策略
- Shorts 版本：重點剪入 Beat4 首擊 + Beat12 終擊，節奏卡在 120 BPM，字幕只顯示擬聲字與短句「一拳碎冰」。
- Reels 版本：保留 Act2 Beat5 連打環繞，搭配左右聲道冰屑掃掠，字幕逐拳標記「1」「2」「3」。
- 長版 YouTube：完整 15s，於描述欄附上色溫、LUT 名稱與錄製種子以便複製。

## Execution Notes
- 求解建議：冰屑與爆紋衝擊可分兩層模擬（RBD for stone + particle ice dust），再於合成用 Depth Fade 過門。
- 渲染：保持 log 輸出，避免高光剪裁；冰屑需啟用次表面散射輕量版以保藍白透感。
- Denoise 限制：終擊漫畫格段落關閉時域降噪，保留線稿銳度；其餘段落可使用輕度 denoise 0.3。
- 相機校正：避免廣角畸變拉伸巨人比例，24–28mm 時需做 5% barrel 校正；長焦段確保景深不過淺。
- 音畫同步：爆紋觸發使用 envelope follower 控制 Bloom 強度，門檻 -12 dB，攻擊 30ms，釋放 180ms。
- 安全：持續檢查無多餘文字、無未授權素材，字幕僅在 Angle12 內嵌擬聲字。

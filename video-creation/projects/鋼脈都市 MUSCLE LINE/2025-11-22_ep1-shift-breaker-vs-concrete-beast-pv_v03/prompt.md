# 《劍盾變形・充能巨斧師・朝倉蓮 vs 巨獸》Master Prompt（15s｜12 幕｜9:16｜2D 日系動漫＋高對比黑黃鋼筋質感｜正午鋼脈廢墟）

來源劇本：使用者提供的 12 幕分鏡，聚焦鋼脈都市邊緣廢棄高架工地，朝倉蓮以僅能從劍盾形態變形一次為充能巨斧的《Shift Breaker》對抗拖著鋼筋混凝土殘骸的巨獸，強調單次變形節奏與核心斬擊。影片維持 15 秒直式 PV，包含漫畫格瞬切與無 UI 影像，僅最後出現標題卡。

## Input Fields（需完整填寫並覆核）
- project_name：鋼脈都市 MUSCLE LINE
- series_name/arc：變形巨斧師支線
- episode_index：1
- slug：shift-breaker-vs-concrete-beast-pv_v02
- target_platform：vertical social (9:16)／YouTube Shorts／TikTok
- duration_sec：15
- style_primary：Anime Fantasy Look
- style_secondary：Urban Switch FX Look＋Light Glyph Anime Look（疊加黃黑能量脈衝）
- worldstate_ref：鋼脈都市訓練場破壞 Stage 1→3（巨獸核心暴露）
- goal：以高對比黑黃能量與寫實 PBR 材質展現劍盾→充能巨斧的唯一變形，擊穿紅色核心並留下可信的破壞與灰塵動態

## 世界與角色速記
- 場景：鋼脈都市邊緣廢棄高架與工地，斷裂鋼筋裸露，碎石與柏油粉塵被風吹起；地表乾裂，局部積灰。光源主來自正午偏右上 50° 太陽（5400–5600K），補光為遠處警示燈黃光（3400K），逆光在混凝土塵霧中形成體積光柱。
- 朝倉蓮：短髮、肩寬肌肉纏緊，外套甩開露出緊身戰鬥背心。膚質 base/SSS/specular 分層，汗膜薄。武器《Shift Breaker》劍盾形態金屬度 0.62、粗糙度 0.28，邊角有磨痕與油漬；護手齒輪帶指紋、刮痕，唯一變形時節點亮黃白光並折疊為巨斧。
- 巨獸：由鋼筋、混凝土與拆卸梁柱組成，四肢踏地粉碎柏油；身體內有紅色不規則核心脈動。混凝土粗糙度 0.72、金屬度 0.08，鋼筋金屬度 0.88、粗糙度 0.36。尾巴帶鐵骨與瓦礫，揮動產生碎石彈射與灰塵波。
- 光影與質感：主光位固定右上 50°，陰影方向一致；日光白與黑黃能量閃光製造高對比。景深適中（T2.2–T4），24–35mm 誇張視角為主，局部 50–75mm 特寫。運動模糊遵循 180° 快門，漫畫格時暫停景深與模糊後回復。
- 武器變形物理：唯一一次變形從劍盾折疊為充能巨斧，遵循齒輪與滑軌運動，伴隨機械噴汽；變形動能轉換為光脈衝沿斧柄流動，粒子遵守慣性與空氣阻力。碰撞時金屬反彈、碎石飛散符合動量守恆。

## Continuity Layer
- 軸線鎖定：鏡頭多保持在蓮右後 120° 弧線，巨獸朝畫面左方推進，避免左右互換；漫畫格特效後恢復同軸。
- 光源連貫：正午主光來自右上 50°，黃光 rim 勾邊；紅色核心光溢出胸腔裂縫但不改變主光方向。
- 鏡頭距離曲線：Act I–II 使用 24–35mm 建立空間與劍盾防禦；Act III 過渡到 35–50mm 聚焦變形與充能；Act IV 收束用 50–75mm 核心擊殺與特寫。
- 狀態時間線：巨獸破壞 Stage 1（完整外殼，0–6s）→ Stage 2（尾擊後裂紋與塵霧，6–10s）→ Stage 3（核心受擊爆裂，10–13.2s）→ Stage 4（崩塌，13.2–15s）。蓮蓄壓亮度 40%（啟動）、70%（變形完成）、100%（核心斬擊）、50%（收束）。
- Camera Continuity：前一鏡面假定從訓練場建立鏡收束；本段延續同一 LUT 與黑黃能量配色，保持鏡頭滑移方向由右向左或由下向上，不跨軸。

## Technical Specs
- Aspect Ratio：9:16 直幅；解析度：1080×1920；FPS：24（必要慢動作用 48 拍攝、24 輸出）；快門角：180° 基準；鏡頭：24/35/50/75mm（24–35 建立空間、50–75 特寫核心）。
- 動態：穩定器＋短距滑軌；手持不超過 3%；運動模糊遵循 180°，漫畫格時暫停模糊並增線稿。景深：中等，對焦眼→武器→核心層次拉焦。
- 顆粒與色彩流程：Log 拍攝→ filmic LUT（黑黃高對比）→ 最終對比；微膠片顆粒，避免重影；HDR 安全，峰值 < 120 nits 在 UI 缺席下控制核心爆光。
- 壓縮保留策略：強邊緣線稿、減少高頻噪點，灰塵粒子在 12–24px 內模糊避免抖動；字幕僅最後標題卡白底黑字保留清晰度。

## 一句話題材
朝倉蓮在鋼脈都市廢墟訓練場以劍盾擋下巨獸鐵骨尾擊，唯一變形為充能巨斧後躍斬紅色核心，斧光把正午塵霧切成黑黃裂線後扛斧離場。

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
物理/質感：{重力/慣性/碰撞/布料彈性/流體黏度；PBR 粗糙度/金屬度/法線或置換；質分層/油光控制；景深/畸變/顆粒顆度}
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
☐ 物理寫實：重力/慣性/布料或流體反應與光學行為已寫入 Master 與各 Beat/Angle；PBR 粗糙度/金屬度、膚質分層與高級質感來源（光比/紋理/顆粒）明確。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

### Style Pack：Anime Fantasy Look（`_stylepacks/anime_fantasy/look.yml`）
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
Applicable for：2D 動漫線條強化、需要黑黃高對比光軌時可混用；Do NOT mix with：過度寫實膚色 LUT；Default ON/OFF：ON；Visual traits：粗線條、柔和塗色、金色光暈；Audio traits：節奏輕推、避開人聲。

### Style Pack：Urban Switch FX Look（`_stylepacks/urban_switch_fx/look.yml`）
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
Applicable for：近未來都市與武器切換殘影；Do NOT mix with：低對比柔焦人像風；Default ON/OFF：ON；Visual traits：黑灰底＋螢光綠/黃點綴，運動模糊帶拖尾；Audio traits：偏工業節奏與金屬撞擊。

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
Applicable for：光軌、HUD、能量脈衝；Do NOT mix with：過飽和暖調童話風；Default ON/OFF：OFF（特效段落開啟）；Visual traits：金色與薄荷光軌、乾淨線稿；Audio traits：高頻電子提示音。

### Style Pack：Shift Breaker Industrial Audio（新增樣板）
Applicable for：巨斧變形、工業訓練場；Do NOT mix with：抒情鋼琴、童話鐘聲；Default ON/OFF：ON；Visual/Audio traits：
- Visual：不新增額外 LUT，搭配金屬火花與蒸汽，保持黑黃警示配色。
- Audio：齒輪「咔嗒」分層、氣壓釋放「嘶」、金屬滑軌摩擦低頻；心跳樣低鼓點對應節點亮起。

## Master Prompt（套用模板後填寫）
Master(15s｜2D 日系動漫＋黑黃工地高對比＋HUD 光軌點綴｜9:16｜24fps｜金屬與混凝土 PBR＋漫畫線稿瞬切)
「正午｜鋼脈都市廢棄高架訓練場；斷骨狀高架、灰塵、紅色核心脈動巨獸；朝倉蓮以劍盾形態迎擊尾擊，啟動唯一變形轉為充能巨斧，跳斬巨獸胸口核心後扛斧收場。
鏡頭：滑軌＋側向跟隨＋短暫慢動作，穩定器為主，手持僅受擊時 3% 內；
表演：蓄力呼吸穩定，爆發時肩臀同步，視線鎖定核心或來襲尾巴；
臉型/髮型：短髮、下頜線清晰；
構圖：三分線＋前中後；灰塵、能量碎屑動態；留白 12–18%；
寫實細節：戰鬥背心布料粗糙度 0.34、金屬扣件金屬度 0.58；膚質 base 反射受汗膜，SSS 透紅；《Shift Breaker》金屬刷痕、油漬，粗糙度 0.28；變形時齒輪噴汽遵循壓力釋放，粒子受重力下墜；混凝土塵霧散射正午光形成體積霧；重擊時碎石拋物線落地，摩擦在地面留白粉尾。
無字幕、無商標/Logo/水印；僅末尾標題卡。」

鏡頭語法：24–35mm 空間誇張｜35–50mm 衝突｜50–75mm 核心刺擊；光圈 T2.2–T4；快門角 180°（慢動作 200°）；對焦層次拉焦核心→角色。
光影：側逆正午光＋工地警示黃光；色溫主 5400–5600K 副 3400K；對比高；眼神光保留。
色調/LUT：膚色優先，陰影微藍灰，高光暖黃，去飽和 4%。
聲音：環境風與塵，金屬撞擊與齒輪聲；音樂工業節奏＋低鼓心跳；峰值對應尾擊、防禦、核心斬擊。
轉場：直接切＋遮擋（碎石/塵霧）＋速度線遮擋；羽化 0.6s。
安全：無品牌，連戲與時序一致。

## 交付設定
- 畫幅：9:16；解析度：1080×1920；幀率 24fps；防抖：開；運動模糊：開；顆粒：微膠片。
- 種子：固定記錄；連戲：開；時序一致：開；色彩：Rec.709 交付，另備 LOG。

## Platform Layer
- Hook A（故事向 0–1s）：巨獸拖鋼筋逼近，紅光脈動；鏡頭俯視推入，字幕建議「這裡是訓練場，不歡迎迷路怪物」淡入 0.6s。
- Hook B（衝擊向 0–1s）：直接播 Beat 10 漫畫格黑黃斧光爆裂，音效提前 0.2s 預告；字幕建議「斧光切開核心」。
- First-shot visual hook：灰塵逆光剪影＋紅色裂縫光線。
- Caption 建議：短版 15 字內「Shift Breaker 核心破壞」；長版 30 字內「蓮以劍盾→充能巨斧，一擊劈開核心」。
- 縮圖構圖：Beat 9 踏碎起跳前的斧刃蓄光對準紅核，黑黃對比，標題置右下；保留留白給平台 UI。
- Hashtag：#ShiftBreaker #鋼脈都市 #AnimePV #形態切換 #黑黃能量
- CTA：結尾標題卡右下小字「Follow for more builds」，使用矢量體無品牌。

## Negative Instructions
- 禁用真實商標、宗教與政治符號；
- 不出現血腥內臟、過度寫實骨折；
- 避免過曝白片或極端魚眼畸變；
- 不插入任何介面 UI（除結尾標題卡），不加入可讀文件；
- 避免卡通化極簡線稿，保持 PBR 金屬與混凝土細節。

## Changelog vs Previous Episode
- 版本更新：改為 15 秒｜12 幕結構，對應使用者提供的新版分鏡。
- 武器限制：移除戰鎚與破甲槍階段，僅保留劍盾→充能巨斧的唯一變形。
- 光線調整：由夕光改為正午高對比，體積霧與灰塵色溫同步更新。

## Assumptions
- 上一集未交付，假定本集作為首支訓練場對戰 PV。
- 巨獸為無智慧訓練目標，不需複雜表情，僅核心脈動。
- 蓮的服裝維持前期標準（背心＋工裝褲），若後續更改需於系列模板更新。

## 分鏡（15s｜12 幕｜Act→Beat→Angle；每 Beat 約 1.25s，含運鏡、光影、聲音、物理/PBR、轉場）

Act 1（0.0–3.75s）
意圖：建立場景與威脅；基調：壓迫＋準備；節奏域：慢入 1.25s×3；美術要點：廢棄高架、巨獸紅核、蓮背影與劍盾輪廓。

Beat 1（0.0–1.25s） 鋼脈廢墟俯視（延續前置場景，軸線同，Stage=1）
- Camera：俯視 24mm，滑軌推進；層次拉焦煙塵→巨獸核心；快門角 180°；
- Lighting：正午主光 5500K 俯照，紅核內光滲出裂縫；體積霧在高架骨間折射；
- Materials & Physics：混凝土粗糙 0.72，鋼筋反射 0.36；塵埃因巨獸步伐震動上揚 1.2m；地面裂縫因重量微塌；
- Emotion & Performance：巨獸無表情但咆哮，呼吸帶震動；
- Audio & Transition：低頻踩踏＋鋼筋拖曳聲；工業脈衝鼓點淡入；直接切入 Beat2。
Angle A｜構圖：高空三分線，巨獸置中心偏左；內容：廢棄高架如斷肋；補充：紅光脈動映亮塵霧邊緣；安全：無可讀字。

Beat 2（1.25–2.5s） 朝倉蓮背影登場（承接 Beat1 塵霧，軸線固定，蓄壓亮度 40%）
- Camera：中遠景 28mm，從足下碎石推升到肩與劍盾；手持 3% 微晃；
- Lighting：側光正午勾勒背肌，警示燈黃光點在劍盾柄；
- Materials & Physics：碎石因他腳步滑落，摩擦聲；劍盾金屬刷痕可見；熱浪扭曲背景建築；
- Emotion & Performance：蓮深呼吸，肩膀收緊；視線向遠處巨獸；
- Audio & Transition：呼吸聲＋鞋底磨砂；機械預充電嗡鳴；塵霧遮擋轉 Beat3。
Angle A｜構圖：背影居中偏右；內容：劍盾輪廓清晰；補充：遠處巨獸模糊搖晃；安全：無文字。

Beat 3（2.5–3.75s） 巨獸尾巴砸下，劍盾格擋（Stage1 尾擊，蓮亮度 50%）
- Camera：低角 24mm，側向跟拍尾巴橫掃；碰撞瞬間短暫慢動作，快門角 200°；
- Lighting：主光從右上落下，衝擊揚起灰塵形成白霧圈；
- Materials & Physics：劍盾粗糙 0.3、金屬度 0.62；尾巴瓦礫撞擊產生碎石拋物線，灰塵震波擴散；肌肉收縮可見纖維；
- Emotion & Performance：蓮重心下沉，牙關緊咬；
- Audio & Transition：衝擊「ドン」低頻＋金屬摩擦；慢動作後回復正常速度；碎石遮擋切 Beat4。
Angle A｜構圖：劍盾占右側三分線，尾巴從左上掃入；補充：畫面邊緣微畸變；安全：無字。

Act 2（3.75–7.5s）
意圖：穩住衝擊、拉開距離、準備變形；基調：決斷；節奏域：穩定 1.25s×3；美術要點：肌肉張力、護手裂紋、節點點亮。

Beat 4（3.75–5.0s） 肌肉與護手特寫穩住衝擊（蓄壓 55%）
- Camera：超近景 50mm，微左右抖動；
- Lighting：主光形成高對比，護手邊緣反射細火花；
- Materials & Physics：護手指紋與汗跡可見，盾面細裂紋但仍撐住；汗珠受震動甩落遵循重力；
- Emotion & Performance：前臂青筋浮起，眼神堅定；
- Audio & Transition：金屬緊繃聲＋低頻嗡鳴；鞭移對位 Beat5。
Angle A｜構圖：前臂對角線貫穿畫面；補充：塵霧在背景漂浮；安全：無字。

Beat 5（5.0–6.25s） 拉開距離準備反擊（蓄壓 60%）
- Camera：中景 35mm 側視，平移跟拍滑步退後；
- Lighting：正午光穿過塵霧形成光柱；
- Materials & Physics：鞋底踩碎碎石，粉塵被滑動拖出線條；劍盾立在身前，金屬邊角鏽蝕反光；
- Emotion & Performance：蓮呼吸節奏穩定，身體微側呈防守反擊姿勢；
- Audio & Transition：碎石摩擦＋低鼓點；直接切 Beat6。
Angle A｜構圖：蓮左肩朝向鏡頭，前中後景分明；補充：遠處巨獸步伐震動地面；安全：無字。

Beat 6（6.25–7.5s） 變形啟動節點點亮（蓄壓 70%）
- Camera：近距劍柄 50mm 繞拍 180°；對焦節點；快門角 200° 強調速度；
- Lighting：節點自發黃白光，與正午光混合；微火花；
- Materials & Physics：齒輪轉動帶油漬反光；氣壓釋放白霧向後噴，受重力下墜；盾面折疊預備；
- Emotion & Performance：蓮拇指按下啟動，手腕穩定；
- Audio & Transition：齒輪「咔嗒」分層＋氣體「嘶」；光源匹配切 Beat7。
Angle A｜構圖：劍柄對角線佔畫面；內容：黃白節點亮起順序；補充：蒸汽冷凝在金屬；安全：無字。

Act 3（7.5–11.25s）
意圖：展開唯一變形、充能、跳躍攻擊；基調：爆發；節奏域：加速 1.25s×3；美術要點：盾面折疊、巨斧充能紋路、跳躍弧線。

Beat 7（7.5–8.75s） 劍盾→充能巨斧變形完成（蓄壓 80→90%）
- Camera：中近景 35mm，跟隨武器甩動弧線，關鍵瞬間慢動作；
- Lighting：斧刃輪廓流動黑黃能量線，金屬高光受正午直射；
- Materials & Physics：盾面向後折疊滑到另一側形成雙面斧，刀身粗化延伸；滑軌齒輪鎖定時有火花；
- Emotion & Performance：蓮肩膀帶動甩動，眼神切到巨獸核心；
- Audio & Transition：金屬折疊聲＋能量嗡鳴提升；直接切 Beat8。
Angle A｜構圖：斧刃佔右側，能量線弧形包圍；補充：背景塵霧被甩開；安全：無字。

Beat 8（8.75–10.0s） 壓低重心蓄力（蓄壓 90%）
- Camera：中近景 35mm 前側，輕微推近斧頭；
- Lighting：斧刃紋路由暗轉亮，地面被能量烤得微紅；
- Materials & Physics：碎石微微浮起再落下，遵循重力；能量流在斧刃形成穩定脈動；
- Emotion & Performance：蓮眉頭緊鎖，呼吸短促，雙手握斧柄；
- Audio & Transition：斧刃低沉嗡鳴＋心跳鼓點；直接切 Beat9。
Angle A｜構圖：斧頭貼近地面，蓮目光對準巨獸；補充：塵埃繞著斧刃旋起；安全：無字。

Beat 9（10.0–11.25s） 踏碎地面起跳衝向核心（巨獸 Stage2→3，蓄壓 100%）
- Camera：中遠景 28mm 低角，從腳踏裂地抬升跟隨跳躍；形成強烈透視；
- Lighting：日光直射，身後拖出黑黃能量尾跡；
- Materials & Physics：地面龜裂碎石向外射，跳躍弧線遵循重力，衣料受風飄動；
- Emotion & Performance：表情決斷，咬牙；
- Audio & Transition：空氣撕裂音＋鼓點加速；直接切漫畫格 Beat10。
Angle A｜構圖：斧尖對準核心，背景斜線高架；補充：灰塵被氣流推開；安全：無字。

Act 4（11.25–15.0s）
意圖：命中核心、崩塌、收束與標題卡；基調：沉著；節奏域：穩定 1.25s×3；美術要點：漫畫格衝擊、塵埃落定、斧回肩。

Beat 10（11.25–12.5s） 漫畫格衝擊定格（巨獸 Stage3 爆閃）
- Camera：全畫面漫畫格化，近乎定格；
- Lighting：黑白線稿，黑黃斧光十字爆裂與紅核仍保留彩色；
- Materials & Physics：核心破裂，能量裂縫撕開輪廓；線稿速度線粗黑；顆粒控制保持乾淨；
- Emotion & Performance：瞬間爆發，蓮肌肉線條漫畫化加粗；
- Audio & Transition：衝擊聲與低頻共振，同步心跳；震動線條抖動 1s；鞭移回實拍 Beat11。
Angle A｜構圖：斧光十字置中央，巨獸輪廓撕裂；補充：背景簡化成城市剪影；安全：無 Logo。

Beat 11（12.5–13.75s） 巨獸崩塌、蓮落地收勢（巨獸 Stage4，蓄壓降至 60%）
- Camera：遠景 35mm 從巨獸崩落推到蓮側身中景；
- Lighting：塵霧中光束穿透，斧上的光紋逐漸變暗；
- Materials & Physics：巨獸胸口爆出光柱後崩塌成瓦礫，碎塊落地彈跳；蓮落地滑步，鞋底與碎石摩擦留粉痕；
- Emotion & Performance：蓮吐氣，姿態穩；
- Audio & Transition：瓦礫落下揚起灰塵，光柱淡出；直接切 Beat12。
Angle A｜構圖：蓮側身剪影在前景，崩塌在遠景左；補充：灰塵粒子落在鏡頭形成前景散焦；安全：無字。

Beat 12（13.75–15.0s） 上半身特寫與標題卡（蓄壓 50%）
- Camera：胸部以上特寫 75mm，緩慢推近；
- Lighting：陽光染黃背景，巨斧餘光微亮；眼神光保留；
- Materials & Physics：汗膜薄亮，皮膚粗糙 0.38；斧節點餘光脈動；背景光軌為先前斧光殘痕；
- Emotion & Performance：蓮把巨斧扛回肩上，微微側頭看向城市；
- Audio & Transition：環境風收束，低鼓心跳淡出；標題卡右下淡入 0.3s「劍盾変形・充能巨斧師・朝倉蓮」；羽化結束。
Angle A｜構圖：臉與斧柄佔右側，留白給標題；補充：背景城市剪影微糊；安全：標題卡無商標。

## 音樂與音效分層（對應 Style Pack）
- 背景：工地風聲＋低頻工業脈衝鼓（-12 dBFS）；
- 變形：齒輪「咔嗒」與氣壓釋放疊加；節點亮起配合高頻金屬叮聲；
- 衝擊：尾擊、防禦、核心斬擊各有低頻撞擊層，Limiter -1 dBTP；核心爆閃加入脈衝波；
- 收束：塵埃落下微顆粒聲，心跳節奏淡出，標題卡無語音。

## VFX 與物理特化
- 變形光軌：使用 Light Glyph Anime 金色 HUD 線條，沿斧柄自下而上流動；Fresnel 邊緣光強度與蓄壓比例同步。
- 碎石與塵霧：Houdini flipbook 破碎貼圖 8×8，噴射角度依撞擊法線；Depth Fade 保證與地面融合。
- 核心爆閃：SDF Dissolve 由中心向外 0.4s，bloom 0.82 峰值後降至 0.3；爆閃後殘留紅光雲氣隨重力下墜。
- 粒子物理：灰塵受風向右後方 5°，重力加速度 9.8m/s²；金屬碎片有旋轉慣性。

## Platform & Delivery Cross-Check
- 確認交付版無 UI，標題卡文字輪廓清晰；
- Shorts/TikTok 壓縮前預加銳利與降噪，邊緣線條保留；
- 預留 10% 安全區避免平台 UI 遮蔽核心鏡頭。

## Next Episode / Spin-off Ideas
- 主線延伸：巨獸核心碎片成為武器「核心過載」模式的起點。
- 主線延伸：訓練場升級夜間雨戰，加入電弧與多目標演練。
- 番外：蓮示範《Shift Breaker》唯一變形的保養流程特寫。

## Persistent Elements（跨集維護）
- 角色外觀：蓮短髮、背心黑灰配黃線，工裝褲護板磨痕維持；汗膜亮度 ≤0.12。
- 武器狀態：劍盾護手刮痕與左上裂紋固定（金屬度0.62/粗糙0.28）；巨斧外緣磨損15%、能量紋路90 BPM，變形後不可回切。
- 場景破壞：高架斷點與前景放射裂縫固定；粉塵雲 Beat1–5 持續、Beat11 沉降；核心爆閃紅霧停留2.2s（#ff3b3b，≤120 nits）。
- 音樂動機：低鼓心跳 80 BPM → 變形 96 BPM → 擊殺 72 BPM 持續沿用。
- UI/字幕：僅尾標題卡白字黑邊 80% 黑底無襯線，其餘段落禁字幕。

## Camera & Lighting Continuity Table
- Act 1：24–28mm 俯/膝高滑軌，主光5500K右上50°、陰影向左下；拉焦煙塵→巨獸→蓮背影（0.4s）。
- Act 2：35mm 胸高平移微抖 2–3%；主光不變，護手火花補光；對焦前臂→護手→盾裂紋，景深0.8m。
- Act 3：35–40mm 胸/眼高跟甩斧；日光＋能量自發光5200K；對焦節點→斧刃→眼神，慢動作鎖斧刃。
- Act 4：50–75mm 定格後推近；核心爆閃後光位回主光；對焦核心碎裂→崩塌→蓮臉並保留眼神光。

# 《變形巨斧師・朝倉蓮 vs 巨獸》Master Prompt（15s｜11 幕｜9:16｜2D 日系動漫＋高對比黑黃鋼筋質感｜廢棄高架訓練場）

來源劇本：使用者提供的 11 幕分鏡，聚焦鋼脈都市邊緣廢棄高架工地，朝倉蓮以可切換盾斧/戰鎚/破甲槍形態的《Shift Breaker》對抗拖著鋼筋混凝土殘骸的巨獸，強調變形節奏與核心斬擊。影片維持 15 秒直式 PV，包含漫畫格瞬切與無 UI 影像，僅最後出現標題卡。

## Input Fields（需完整填寫並覆核）
- project_name：鋼脈都市 MUSCLE LINE
- series_name/arc：變形巨斧師支線
- episode_index：1
- slug：shift-breaker-vs-concrete-beast-pv_v01
- target_platform：vertical social (9:16)／YouTube Shorts／TikTok
- duration_sec：15
- style_primary：Anime Fantasy Look
- style_secondary：Urban Switch FX Look＋Light Glyph Anime Look（疊加黃黑能量脈衝）
- worldstate_ref：鋼脈都市訓練場破壞 Stage 1→2（巨獸核心暴露）
- goal：以高對比黑黃能量與寫實 PBR 材質展現武器變形，擊穿紅色核心並留下可信的破壞與灰塵動態

## 世界與角色速記
- 場景：鋼脈都市邊緣廢棄高架與工地，斷裂鋼筋裸露，碎石與柏油粉塵被風吹起；地表乾裂，局部積灰。光源主來自斜側夕光（4300–4600K），補光為遠處鈉燈（3200K）與機械警示燈黃光，逆光在混凝土塵霧中形成體積光柱。
- 朝倉蓮：短髮、肩寬肌肉纏緊，外套甩開露出緊身戰鬥背心。膚質 base/SSS/specular 分層，汗膜薄。武器《Shift Breaker》金屬度 0.62、粗糙度 0.28，邊角有磨痕與油漬；關節齒輪帶指紋、刮痕，變形時節點亮黃白光。
- 巨獸：由鋼筋、混凝土與拆卸梁柱組成，四肢踏地粉碎柏油；身體內有紅色不規則核心脈動。混凝土粗糙度 0.72、金屬度 0.08，鋼筋金屬度 0.88、粗糙度 0.36。尾巴帶鐵骨與瓦礫，揮動產生碎石彈射與灰塵波。
- 光影與質感：主光位固定右上 45°，陰影方向一致；夕光暖、背景冷灰，黑黃能量閃光製造高對比。景深適中（T2.2–T4），24–35mm 誇張視角為主，局部 50–75mm 特寫。運動模糊遵循 180° 快門，漫畫格時暫停景深與模糊後回復。
- 武器變形物理：變形過程遵循齒輪與滑軌運動，伴隨機械噴汽；變形動能轉換為光脈衝沿斧柄流動，粒子遵守慣性與空氣阻力。碰撞時金屬反彈、碎石飛散符合動量守恆。

## Continuity Layer
- 軸線鎖定：鏡頭多保持在蓮右後 120° 弧線，巨獸朝畫面左方推進，避免左右互換；漫畫格特效後恢復同軸。
- 光源連貫：夕光主光來自右上 45°，黃光 rim 勾邊；紅色核心光溢出胸腔裂縫但不改變主光方向。
- 鏡頭距離曲線：Act I–II 使用 24–35mm 建立空間與武器變形；Act III–IV 過渡到 35–50mm 聚焦衝突與核心刺擊；Act V 收束用 50–75mm 近景與特寫。
- 狀態時間線：巨獸破壞 Stage 1（完整外殼，0–6.5s）→ Stage 2（腿部崩裂露紅光，6.5–10.4s）→ Stage 3（核心受擊爆裂，10.4–13.5s）→ Stage 4（崩塌，13.5–15s）。蓮蓄壓亮度 40%（啟動）、70%（戰鎚橫掃）、90%（破甲刺擊）、40%（收束）。
- Camera Continuity：前一鏡面假定從訓練場建立鏡收束；本段延續同一 LUT 與黑黃能量配色，保持鏡頭滑移方向由右向左或由下向上，不跨軸。

## Technical Specs
- Aspect Ratio：9:16 直幅；解析度：1080×1920；FPS：24（必要慢動作用 48 拍攝、24 輸出）；快門角：180° 基準；鏡頭：24/35/50/75mm（24–35 建立空間、50–75 特寫核心）。
- 動態：穩定器＋短距滑軌；手持不超過 3%；運動模糊遵循 180°，漫畫格時暫停模糊並增線稿。景深：中等，對焦眼→武器→核心層次拉焦。
- 顆粒與色彩流程：Log 拍攝→ filmic LUT（黑黃高對比）→ 最終對比；微膠片顆粒，避免重影；HDR 安全，峰值 < 120 nits 在 UI 缺席下控制核心爆光。
- 壓縮保留策略：強邊緣線稿、減少高頻噪點，灰塵粒子在 12–24px 內模糊避免抖動；字幕僅最後標題卡白底黑字保留清晰度。

## 一句話題材
朝倉蓮在鋼脈都市廢墟訓練場啟動變形巨斧《Shift Breaker》，以盾斧擋下巨獸鐵骨尾擊，再切換戰鎚與破甲槍刺入紅色核心，斧光把夕色天空切成黑黃裂線後扛斧離場。

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
「黃昏｜鋼脈都市廢棄高架訓練場；斷骨狀高架、灰塵、紅色核心脈動巨獸；朝倉蓮以變形巨斧從盾→鎚→破甲槍，擊穿巨獸胸口核心後扛斧收場。
鏡頭：滑軌＋側向跟隨＋短暫慢動作，穩定器為主，手持僅受擊時 3% 內；
表演：蓄力呼吸穩定，爆發時肩臀同步，視線鎖定核心或來襲尾巴；
臉型/髮型：短髮、下頜線清晰；
構圖：三分線＋前中後；灰塵、能量碎屑動態；留白 12–18%；
寫實細節：戰鬥背心布料粗糙度 0.34、金屬扣件金屬度 0.58；膚質 base 反射受汗膜，SSS 透紅；《Shift Breaker》金屬刷痕、油漬，粗糙度 0.28；變形時齒輪噴汽遵循壓力釋放，粒子受重力下墜；混凝土塵霧散射夕光形成體積霧；重擊時碎石拋物線落地，摩擦在地面留白粉尾。
無字幕、無商標/Logo/水印；僅末尾標題卡。」

鏡頭語法：24–35mm 空間誇張｜35–50mm 衝突｜50–75mm 核心刺擊；光圈 T2.2–T4；快門角 180°（慢動作 200°）；對焦層次拉焦核心→角色。
光影：側逆夕光＋工地警示黃光；色溫主 4300–4600K 副 3200K；對比高；眼神光保留。
色調/LUT：膚色優先，陰影微藍灰，高光暖黃，去飽和 4%。
聲音：環境風與塵，金屬撞擊與齒輪聲；音樂工業節奏＋低鼓心跳；峰值對應尾擊、防禦、核心刺擊。
轉場：直接切＋遮擋（碎石/塵霧）＋速度線遮擋；羽化 0.6s。
安全：無品牌，連戲與時序一致。

## 交付設定
- 畫幅：9:16；解析度：1080×1920；幀率 24fps；防抖：開；運動模糊：開；顆粒：微膠片。
- 種子：固定記錄；連戲：開；時序一致：開；色彩：Rec.709 交付，另備 LOG。

## Platform Layer
- Hook A（故事向 0–1s）：巨獸拖鋼筋逼近，紅光脈動；鏡頭俯視推入，字幕建議「這裡是訓練場，不歡迎迷路怪物」淡入 0.6s。
- Hook B（衝擊向 0–1s）：直接播 Beat 9 漫畫格黑黃斧光爆裂，音效提前 0.2s 預告；字幕建議「斧光切開天空」
- First-shot visual hook：灰塵逆光剪影＋紅色裂縫光線。
- Caption 建議：短版 15 字內「Shift Breaker 核心破壞」；長版 30 字內「蓮的變形巨斧訓練日，巨獸核心被一擊切開」。
- 縮圖構圖：Beat 8 跳刺前的斧槍對準紅光，黑黃對比，標題置右下；保留留白給平台 UI。
- Hashtag：#ShiftBreaker #鋼脈都市 #AnimePV #形態切換 #黑黃能量
- CTA：結尾標題卡右下小字「Follow for more builds」，使用矢量體無品牌。

## Negative Instructions
- 禁用真實商標、宗教與政治符號；
- 不出現血腥內臟、過度寫實骨折；
- 避免過曝白片或極端魚眼畸變；
- 不插入任何介面 UI（除結尾標題卡），不加入可讀文件；
- 避免卡通化極簡線稿，保持 PBR 金屬與混凝土細節。

## Changelog vs Previous Episode
- 初次登場《Shift Breaker》完整三段變形；
- 新增巨獸紅色核心 Stage 條列，供後續集數延續；
- 場景破壞狀態設為訓練場 Stage 2（高架殘肋＋碎石雲），後續需維持瓦礫分佈與紅光殘留。

## Assumptions
- 上一集未交付，假定本集作為首支訓練場對戰 PV；
- 巨獸為無智慧訓練目標，不需複雜表情；
- 蓮的服裝維持前期標準（背心＋工裝褲），若後續更改需於系列模板更新。

## 分鏡（15s｜11 幕｜Act→Beat→Angle；每 Beat 約 1.3s，含運鏡、光影、聲音、物理/PBR、轉場）

Act 1（0.0–3.9s）
意圖：建立場景與威脅；基調：壓迫＋準備；節奏域：慢入 1.3s×3；美術要點：廢棄高架、巨獸紅核、蓮背影與折疊巨斧。

Beat 1（0.0–1.3s） 巨獸逼近的鋼脈廢墟（延續前置場景，軸線同，Stage=1）
- Camera：俯視 24mm，滑軌推進；層次拉焦煙塵→巨獸核心；快門角 180°；
- Lighting：逆光夕色 4400K，紅核內光滲出裂縫；體積霧在高架骨間折射；
- Materials & Physics：混凝土粗糙 0.72，鋼筋反射 0.36；塵埃因巨獸步伐震動上揚 1.2m；地面裂縫因重量微塌；
- Emotion & Performance：巨獸無表情但咆哮，呼吸帶震動；
- Audio & Transition：低頻踩踏＋鋼筋拖曳聲；工業脈衝鼓點淡入；直接切入 Beat2。
Angle A｜構圖：高空三分線，巨獸置中心偏左；內容：廢棄高架如斷肋；補充：紅光脈動映亮塵霧邊緣；安全：無可讀字。

Beat 2（1.3–2.6s） 朝倉蓮登場背影（承接 Beat1 塵霧，軸線固定，蓄壓亮度 40%）
- Camera：中遠景 28mm，從足下碎石推升到肩與斧柄；手持 3% 微晃；
- Lighting：側光夕陽勾勒背肌，警示燈黃光點在斧柄；
- Materials & Physics：碎石因他腳步滑落，摩擦聲；斧柄金屬刷痕可見；熱浪扭曲背景建築；
- Emotion & Performance：蓮深呼吸，肩膀收緊；視線向遠處巨獸；
- Audio & Transition：呼吸聲＋鞋底磨砂；機械預充電嗡鳴；塵霧遮擋轉 Beat3。
Angle A｜構圖：背影居中偏右；內容：折疊巨斧輪廓清晰；補充：遠處巨獸模糊搖晃；安全：無文字。

Beat 3（2.6–3.9s） 變形啟動節點點亮（承接蓄壓 40%→60%）
- Camera：近距斧柄 50mm 繞拍 180°；對焦節點；快門角 200° 強調速度；
- Lighting：節點自發黃白光，與夕光混合；微火花；
- Materials & Physics：齒輪轉動帶油漬反光；氣壓釋放白霧向後噴，受重力下墜；刃片解鎖如花瓣折射光；
- Emotion & Performance：蓮手腕穩定，拇指按下啟動；
- Audio & Transition：齒輪「咔嗒」分層＋氣體「嘶」；鞭移對位 Beat4；
Angle A｜構圖：斧柄對角線佔畫面；內容：黃白節點亮起順序；補充：蒸汽冷凝在金屬；安全：無字。

Act 2（3.9–7.8s）
意圖：防禦與反擊準備；基調：決斷；節奏域：穩定 1.3s×3；美術要點：斧盾、防禦衝擊、戰鎚蓄力。

Beat 4（3.9–5.2s） 尾巴重擊 vs 斧盾防禦（延續軸線，巨獸 Stage1 尾擊，蓮亮度 60%）
- Camera：低角 24mm，側向跟拍尾巴橫掃；慢動作 0.5s 內，快門角 200°；
- Lighting：逆光 rim 勾邊，塵霧被衝擊形成白霧圈；
- Materials & Physics：斧盾厚重粗糙 0.3，金屬度 0.62；尾巴瓦礫撞擊產生碎石拋物線，灰塵震波擴散；肌肉收縮可見纖維；
- Emotion & Performance：蓮重心下沉，牙關緊咬；
- Audio & Transition：衝擊「ドン」低頻＋金屬摩擦；慢動作後回復正常速度；碎石遮擋切 Beat5。
Angle A｜構圖：斧盾占右側三分線，尾巴從左上掃入；補充：畫面邊緣魚眼微扭曲；安全：無字。

Beat 5（5.2–6.5s） 變形切換為長柄戰鎚（蓄壓 70%）
- Camera：中近景 35mm 側面，跟隨身體扭轉；對焦鎚頭形成弧線；
- Lighting：夕光勾輪廓，節點黃光沿縫隙爬行；
- Materials & Physics：刃片折疊，鎚頭伸出帶側刺；能量沿金屬表面流動如脈搏；摩擦火花極短；
- Emotion & Performance：蓮腰部扭力蓄勢，眼神轉向巨獸腿；
- Audio & Transition：齒輪加速聲＋能量嗡鳴提升；光源匹配切 Beat6。
Angle A｜構圖：動線弧形包圍鎚頭；補充：身體肌肉張力清晰；安全：無字。

Beat 6（6.5–7.8s） 橫掃巨獸腿部崩裂（巨獸 Stage2 觸發）
- Camera：低角 28mm 貼鎚頭運動，運動模糊弧線；
- Lighting：撞擊火花加黃光，背景夕光逆光；
- Materials & Physics：混凝土外殼炸開，鋼筋折斷彈跳；紅光組織閃爍，碎石與金屬碎片拋射遵循動量；
- Emotion & Performance：蓮怒喝，肩背肌群顫動；
- Audio & Transition：碎裂聲＋金屬撕裂，漫畫線條「ガキィ」音效化；短暫停頓後抖動；光源匹配切 Beat7。
Angle A｜構圖：鎚頭橫掃佔畫面前景，腿部裂開在中景；補充：背景速度線幾格；安全：無字。

Act 3（7.8–11.8s）
意圖：武器升級與核心突刺；基調：爆發；節奏域：加速 1.3s×3；美術要點：破甲斧槍、跳躍刺擊、漫畫格爆閃。

Beat 7（7.8–9.1s） 上挑變形為破甲斧槍（蓄壓 80→90%）
- Camera：中近景 35mm，慢動作 0.5s 捕捉刃片旋轉；
- Lighting：刀片形成圓形光軌，黃白光圈如魔法陣；
- Materials & Physics：鎚頭分裂成多片刀刃繞柄旋轉，磁扣鎖定；能量重新分配沿柄流動；
- Emotion & Performance：蓮深吸，眼神鎖定核心；
- Audio & Transition：旋轉風切＋節點「咔嗒」；慢動作後加速前衝；直接切 Beat8。
Angle A｜構圖：斧柄斜向右上，光環圍繞；補充：背景塵霧被旋風帶開；安全：無字。

Beat 8（9.1–10.4s） 跳躍直刺胸口核心（軸線維持，巨獸 Stage2→3）
- Camera：遠中景 28mm 低角，向上跟隨跳躍；切至核心特寫 75mm；
- Lighting：核心紅光暴走，對比黃斧光；空氣速度線拉出黑黃交錯；
- Materials & Physics：地面因踩踏碎裂，碎石向外射；跳躍弧線遵循重力；斧尖刺入時紅光過曝；
- Emotion & Performance：表情決斷，咬牙；
- Audio & Transition：空氣撕裂音＋鼓點加速；核心附近脈動「ドク」；直接切漫畫格 Beat9。
Angle A｜構圖：斧尖對準核心，透視高架斜線；補充：背景崩塌梁柱；安全：無字。

Beat 9（10.4–11.8s） 漫畫格衝擊定格（巨獸 Stage3 爆閃）
- Camera：全畫面漫畫格化，近乎定格；
- Lighting：黑白線稿，黑黃斧光十字爆裂為唯一色彩；
- Materials & Physics：核心破裂，能量裂縫撕開輪廓；線稿速度線粗黑；顆粒控制保持乾淨；
- Emotion & Performance：瞬間爆發，蓮肌肉線條漫畫化加粗；
- Audio & Transition：衝擊聲與低頻共振，同步心跳；震動線條抖動 1s；鞭移回實拍 Beat10。
Angle A｜構圖：斧光十字置中央，巨獸輪廓撕裂；補充：背景簡化成城市剪影；安全：無 Logo。

Act 4（11.8–15.0s）
意圖：收束與標題卡；基調：沉著；節奏域：穩定 1.3s×2；美術要點：塵埃落定、斧回肩、特寫與標題。

Beat 10（11.8–13.5s） 塵埃落定巨斧回肩（巨獸 Stage4 崩塌，蓮亮度降回 40%）
- Camera：中景 35mm 從遠處崩塌推到蓮側身；
- Lighting：灰塵中光束穿透，金屬餘溫微光；
- Materials & Physics：巨獸身體崩落形成塵幕，碎塊落地彈跳；斧柄收回重斧形態，關節卡榫合攏；
- Emotion & Performance：蓮吐氣放鬆，嘴角微揚；
- Audio & Transition：塵埃落下聲＋金屬折疊「咔」；直接切 Beat11。
Angle A｜構圖：蓮側身剪影在前景，崩塌在遠景左；補充：灰塵粒子落在鏡頭形成前景散焦；安全：無字。

Beat 11（13.5–15.0s） 上半身特寫與標題卡（收束，亮度常亮 40%）
- Camera：胸部以上特寫 75mm，輕微推近；
- Lighting：夕光染黃背景，斧節點微亮；眼神光保留；
- Materials & Physics：汗膜薄亮，皮膚粗糙 0.38；斧節點餘光脈動；背景光軌為先前斧光殘痕；
- Emotion & Performance：蓮稍低頭，嘴角可靠笑；視線瞄向城市；
- Audio & Transition：環境風收束，低鼓心跳淡出；標題卡右下淡入 0.3s「変形巨斧師・朝倉蓮」；羽化結束。
Angle A｜構圖：臉與斧柄佔右側，留白給標題；補充：背景城市剪影微糊；安全：標題卡無商標。

## 音樂與音效分層（對應 Style Pack）
- 背景：工地風聲＋低頻工業脈衝鼓（-12 dBFS）；
- 變形：齒輪「咔嗒」與氣壓釋放疊加；節點亮起配合高頻金屬叮聲；
- 衝擊：尾擊、防禦、鎚擊、刺擊各有低頻撞擊層，Limiter -1 dBTP；核心爆閃加入脈衝波；
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
- 主線延伸：巨獸核心爆裂後留下紅色碎片，下一集展示蓮將碎片裝回武器做「核心過載」模式。
- 主線延伸：訓練場升級為夜間雨戰，加入電弧元素與多目標演練。
- 番外短片：蓮教學《Shift Breaker》三段變形的保養流程，工具細節特寫。

## AGENT Self-Check
- 結構：Master、Continuity Layer、Technical Specs、Platform Layer、Negative Instructions、Changelog、Assumptions、Act→Beat→Angle（11 幕，含 timecode）、音樂/VFX、Next Episode 全數齊備。
- Physics & PBR：每幕寫明重力、慣性、碎石拋物線、PBR 粗糙度/金屬度、光學（體積霧、bloom、折射）與高級質感來源（夕光對比、膠片顆粒）。
- Stylepacks：Anime Fantasy Look＋Urban Switch FX Look＋Light Glyph Anime Look 全文貼上，新增 Shift Breaker Industrial Audio 樣板並標註適用/禁混；未混用衝突 LUT。
- Continuity：軸線、光位、鏡頭距離曲線與巨獸破壞 Stage、蓮蓄壓亮度分段已列；漫畫格後回到同軸。
- QA Checklist：遵循 _core 條目，交付設定與安全規範確認；未插入品牌或 UI；標題卡單純字樣。
- 不足揭露：缺乏上一集實際影像參考，假設為首支 PV；若後續有角色造型改動需更新 _core 模板。

## Persistent Elements Checklist
- 角色：朝倉蓮保持短髮、背心＋工裝褲、黑黃護腕；若後續受傷需在世界模板標註傷口位置與包紮材質。
- 武器：Shift Breaker 默認三段形態（盾斧、戰鎚、破甲槍），節點黃白光；劃痕與油漬需在後續集數保持一致，磨損增加時記錄時間戳。
- 場景：廢棄高架斷肋、塵霧密度中等、地表裂紋布局；巨獸殘骸留下紅光碎片與鋼筋柱，為下一集基礎。
- 色彩：黑灰基調＋黃光警示＋紅核對比；漫畫格時維持同 LUT 黑白線稿。
- 音樂動機：工業低鼓心跳與齒輪節奏為系列主題音；變形提示音一致保留。

## Camera & Lighting Reference Table
- 24mm：Beat1 俯視建立；特徵為誇張透視、體積光條紋。
- 28mm：Beat2–6 滑移與低角跟拍；注意畸變校正保持直線高架。
- 35mm：Beat5–8 變形與跳刺；略壓縮背景維持角色比例。
- 50–75mm：Beat9 漫畫格後的核心特寫與 Beat11 特寫；淺景深強調臉部與斧節點。
- 主光 4300–4600K，副光 3200K；反光板不使用，改以塵霧散射填充；陰影方向統一左下。

## Color Pipeline & Grain Control
- 拍攝 Log，轉換至 filmic LUT（黑黃對比強化），Gamma 2.2；
- Highlight roll-off 以保留核心爆閃細節，避免裁剪；
- Grain：0.15 強度，膠片顆粒分佈均勻，避免在紅核區塊形成彩噪；
- Chromatic aberration：極輕微於畫面邊緣 <0.2%，漫畫格階段關閉。

## Audio Routing & Loudness Plan
- 主 Bus：環境＋音樂 -14 LUFS；
- SFX Bus：變形與衝擊 -8 至 -3 dB 峰值，Limiter -1 dBTP；
- Sidechain：衝擊觸發壓縮音樂 3 dB，避免掩蔽；
- Foley：鞋底摩擦、碎石落地、布料摩擦各自獨立軌，方便後期微調；
- Reverb：訓練場開放空間混響 0.7s，漫畫格瞬間關閉混響營造乾聲。

## Editing & Transition Notes
- 鞭移與碎石遮擋需保持方向一致（右→左或上→下）避免跳軸；
- 漫畫格切入與退出需使用 2 帧白閃以銜接動畫工具；
- Beat4 慢動作長度控制 0.5s，其餘回到 24fps 正速；
- 標題卡淡入 0.3s，停留 0.7s，結尾保留 0.2s 黑場給平台緩衝。

## Alternate Hook Cut（僅供剪輯用，保留原時間線）
- Version A：Beat9 漫畫格開場 → Beat1 俯視 → 其餘照常，總長仍 15s；
- Version B：Beat3 變形特寫開場 → Beat4 防禦 → Beat8 刺擊 → Beat11 標題，穿插 0.2s 白閃保持節奏。

## Safety & Compliance
- 無未成年出現，肌肉暴露維持 PG-13，無血跡；
- 全程無讀得出的品牌或標誌，工地警示牌只用抽象圖形；
- 不使用宗教或軍事徽章；
- 背景群眾不存在，避免隱私問題；
- 標題卡字體使用通用無襯線，無商標化。

## Caption & Localization Hints
- 日文版：hook 字樣可用「訓練場に迷い込むな」；
- 中文版：主標題「變形巨斧師・朝倉蓮」；
- 英文版：備用字幕「Shift Breaker: Core Drill」；
- 所有字幕保持白字黑描邊 2px，安全框內 90% 區域。

## LUT / VFX Toggle Map per Beat
- Beat1–2：Anime Fantasy Look ON，Light Glyph OFF，Urban Switch ON。
- Beat3–5：Anime Fantasy＋Urban Switch ON，Light Glyph 部分開啟於節點；
- Beat6：三者全開，光軌強度 0.7；
- Beat7–8：Light Glyph ON（光環），其餘保持；
- Beat9：切入漫畫格，全部 LUT 暫停，線稿化；
- Beat10–11：恢復 Anime Fantasy＋Urban Switch，Light Glyph 僅保留餘光。

## QA Reminders by Beat
- Beat1：霧密度與逆光對比檢查，避免核心過曝；
- Beat4：慢動作顆粒保持一致，不放大噪點；
- Beat6：碎石遮擋轉場時確認遮罩邊緣無鋸齒；
- Beat8：刺擊時景深跟焦準確，核心與斧尖同步清晰；
- Beat9：漫畫格線條粗細一致，黑黃對比不失真；
- Beat11：標題卡字距檢查，餘光不要蓋住文字。

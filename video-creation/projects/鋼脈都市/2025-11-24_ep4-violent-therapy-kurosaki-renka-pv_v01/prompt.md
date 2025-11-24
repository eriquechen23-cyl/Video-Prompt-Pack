# 《鋼脈都市｜暴力治療・黑粉戀花 PV》— Master Prompt（15s｜12 幕）

專案欄位：
- project_name：鋼脈都市
- series_name/arc：鋼脈都市・黑粉地下診所篇
- episode_index：4
- slug：violent-therapy-kurosaki-renka-pv_v01
- target_platform：短影音（9:16，YouTube Shorts / TikTok）
- duration_sec：15（依專案規範預設 15s，12 幕 × 1.25s）
- style_primary：Urban Switch FX Look（黑粉霓虹醫療質感＋動態殘影）
- style_secondary：Sci-Fi Realism Look（鋼脈都市夜景金屬與霓虹折射平衡）
- worldstate_ref：鋼脈都市夜間，高架橋陰影下 2 層地下診所，室內啞光黑牆與螢光粉線條；戶外戰場在高架橋支撐柱旁的空地，霓虹與雨霧混光，幫派與怪物交戰。
- goal：製作 15 秒 12 幕 PV，呈現黑崎戀花準備針筒、衝入戰場暴力治療隊友、對壞人施放戀愛麻醉，再回到診所幫「在意的人」包紮；需含日文旁白（第三人稱 N1–N5）與角色台詞 R1–R6，並完整標註物理與 PBR 細節供動畫工具解析。
- date_tz_utc8：2025-11-24（UTC+8）
- target_platform_hook：Hook A 故事向（地下診所亮燈→針筒準備→衝向戰場），Hook B 衝擊向（暴力治療 buff 爆發→戀愛麻醉粉霧封鎖）
- platform_slice_strategy：長版完整 15s；短版優先截取 0–3s（診所亮燈與針筒準備）、7–12s（暴力治療＋戀愛麻醉）並附對應字幕行

來源劇本：使用者提供《暴力治療・黑粉戀花》PV 敘述、日文旁白 N1–N5 與角色台詞 R1–R6

## 一句話題材
鋼脈都市的夜裡，害羞卻暴力的黑崎戀花在黑粉霓虹地下診所準備巨型針筒，衝入高架橋下的混戰為隊友注入粉色能量並制裁濫用醫療的幫派，最後帶著臉紅的溫柔在診所替「特別在意的人」包紮。

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
```
# Global Master Prompt Template

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

```

### Audio Pack 指引（`_core/audio_pack.md`）
```
# Audio Pack 指引

```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
人聲：避免加入一般人聲（對話、歌唱等），僅可使用詠唱或咒語式聲線作為氛圍點綴
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```

```

### VFX 通用 Pack（`_core/vfx_pack.md`）
```
# VFX 通用 Pack

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

```

### 交付參數預設（`_core/delivery_presets.md`）
```
# 交付參數預設

```
畫幅：{16:9｜9:16｜1:1}
解析度：{1920×1080｜1080×1920｜2048×2048}
幀率：{24/30/48/60}（如需輕慢動：拍 48–60，輸出 24）
防抖：{開/關}；運動模糊：開；顆粒：微膠片
色彩：Rec.709（交付版）／LOG（調色版）
聲音：立體聲 48kHz；-14 LUFS（YouTube），-1 dBTP
種子：{固定/隨機（記錄）}；連戲：開；時序一致：開
```

```

### QA Checklist（`_core/qa_checklist.md`）
```
# QA Checklist（拍前 30 秒）

```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 物理寫實：重力/慣性/布料或流體反應與光學行為已寫入 Master 與各 Beat/Angle；PBR 粗糙度/金屬度、膚質分層與高級質感來源（光比/紋理/顆粒）明確。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

```

### Scene Block Template（`_core/scene_block.md`）
```
# Scene Block Template

## Continuity Layer（連貫性強化規則｜撰寫於 Master 前）
- 先在 Master 前建立「Continuity Layer」，明示軸線、主光、鏡頭距離與角色狀態時間線，後續各 Beat 以「延續」語氣引用，避免鏡頭沙拉。
- 軸線鎖定：標註主角/BOSS 左右位置與鏡頭主要站位（例：「蓮右側，蛇左側，鏡頭多在蓮右後 120° 弧線」），禁止跨軸造成左右互換。
- 鏡頭距離曲線：15s 影片每 Act 僅用 1–2 個焦段族群（Act I 24–35mm｜Act II 35–50mm｜Act III 50–75mm）；三秒內避免廣角與長焦來回跳。
- 光源連貫：固定主光方向（例：太陽在右上 45°），保持陰影方向一致；僅在漫畫格或特效片段可暫時風格化，完成後回復原光位。
- 狀態時間線：BOSS 需列出每 4–5 秒的破壞 Stage（完整→裂紋→崩解）並在 Beat 內直接引用 Stage 名稱；主角則以蓄壓/傷勢/裝備亮度等分段標註當前階段（例：「蓄壓 70%、護膝警示一次」）。
- Hook 政策：Baseline Master Prompt 保持線性；如需 Hook 版（先擊殺再倒帶等），請獨立撰寫段落或檔案 `hook_cut_prompt`，不得混寫於 baseline 時間線。
- Beat 撰寫：每 Beat 開頭先重述與上一 Beat 的軸線/光位/距離/Stage 關係，再寫本幕唯一改動重點；仍須完整填 Camera、Lighting、Materials & Physics、Emotion & Performance、Audio & Transition，不得以「同前鏡」代稱。

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

```

### Style: Urban Switch FX Look（`_stylepacks/urban_switch_fx/look.yml`）
```
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

### Style: Sci-Fi Realism Look（`_stylepacks/sci_fi_realism/look.yml`）
```
name: Sci-Fi Realism Look
lut: Neutral+BlueShadows
contrast: medium_high
highlight_control: neon_balance
reflection_priority: metal_glass
color_temperature_range: [3600, 4200]
bloom:
  base: 0.2
  peak: 0.6
notes:
  - 允許霓虹混光，保留暗部細節
  - 金屬與玻璃反射優先處理
  - 夜景需維持主體分離

```

## Technical Specs
- 畫幅：9:16 直式｜解析度 1080×1920｜幀率 24fps（拍 48fps 輸出 24 保留粉霧與霓虹殘影）
- 快門角：室內準備段 180°；戰場暴力治療段 200° 拉長粉色殘影；診所收尾 172° 強調細節
- 鏡頭組：Act I 24–32mm 建立診所與外部街景，Act II 35–55mm 追拍衝刺與注射，Act III 55–75mm 收束特寫；保持 180° 軸線左側視角
- 景深：室內 1.0m，戰場 1.4m，收尾 1.8m；焦外加入 0.3% 粉色散景光斑
- 顆粒：Filmic grain 8–10%；色彩流程：Log → Neutral+BlueShadows LUT → final contrast（粉霓虹保留）
- 光學畸變：微桶形 0.6%，Chromatic aberration 粉邊限制 0.35px
- 切片輸出策略：0–3s Hook A；7–12s Hook B；字幕對應日文旁白與角色台詞
- 配音：旁白 N1–N5 偏冷靜熱血男聲；戀花台詞 R1–R6 為年輕女聲帶害羞顫音；錄製 -16 LUFS，VO 與 SFX 分離輸出

## Master Prompt（內含 Brand Layer / Worldstate Snapshot / Constraint List / Execution Note）
- Brand Layer：黑粉地下診所 Brand Bible——主色啞光黑 #0b0b0f、螢光粉 #ff4fa7、點綴心形霓虹 #ff7ac3；服裝為貼身戰鬥衣（粗糙度0.34、金屬度0.22），肩腰有粉色發光紋路，巨型針筒透明槍管折射率 1.48。口頭禪：「打一針就會好很多。」
- Worldstate Snapshot：夜晚 22:10，高架橋下陰影區 12m 高，霓虹與救護燈光交錯；診所室內 18°C，牆面啞光黑粗糙度0.42，粉色 LED 線條亮度 160 nits；戰場地面濕滑薄水膜 0.15mm，空氣霧化粒徑 20–40μm。
- Constraint List：
  1. 軸線固定在戀花左前 120°，戰場時保持鏡頭在她左側 1.5–2m。
  2. 螢光粉能量亮度上限 210 nits，避免過曝；黑色區域最低 8 IRE 保留細節。
  3. 醫療場景 PG-13：針筒注射無血液濺射，以粉色能量與光脈衝呈現。
  4. PBR：診所金屬器械粗糙度0.28、金屬度0.9；PVC 醫療包粗糙度0.25；戰場柏油粗糙度0.58、金屬度0.04；體積霧吸收係數 0.27。
- Execution Note：採 camera projection 固定診所牆面光紋；粉霧使用 VDB 200³，吸收 0.24，散射 0.55；螢光液體 Flip 90k 粒子烘焙為 12×12 spritesheet；注射瞬間採用 bloom 0.6 但控高光。
- Camera Continuity：Act I 室內以 28mm 滑軌→Act II 戰場 40–50mm 跟拍→Act III 65–75mm 靜態收束；主光室內粉燈左上 45°、戰場路燈右上 30° 持續。

## Platform Layer
- Hook A（故事向）：0–3s 診所鐵門被推開、粉色心形霓虹亮起、戀花綁馬尾準備針筒；字幕「鋼脈都市の夜、誰も知らない診療所にネオンが灯る。」
- Hook B（迷因/衝擊）：7–12s 戰場暴力治療與戀愛麻醉粉霧封鎖；字幕「打一針就會好很多。……たぶん♡」
- Caption 建議：繁中＋日文「黑粉醫療」「暴力治療」「戀愛麻醉」；Hashtag：#鋼脈都市 #黑崎戀花 #暴力治療
- CTA：結尾 0.5s 疊字「フォローで次の治療へ」；縮圖構圖：戀花背槍針筒、腰腹螢光紋路與心形霓虹同框，留 15% 上方空白
- 切片策略：VO 軌道分開；保留粉霧粒子層與霓虹 specular；字幕語系日文＋繁中

## Negative Instructions（含自動檢核清單）
- 禁用：真實商標、醫療機構標誌、宗教/政治符號、血腥穿刺畫面、魚眼與過曝濾鏡。
- 語言環境：全程繁中＋日文，無英文 UI。
- 侵權檢核：角色、診所、幫派設計皆為原創，不引用已知 IP；字幕大小 8% 畫幅以下。
- 自動檢核：
  1. 可讀字樣：僅 LOGO「黑粉地下診所 KUROSAKI CLINIC」，其他標示模糊。
  2. 商標：醫療器械與路牌無真實品牌。
  3. 宗教政治符號：無。
  4. 風格衝突：僅開啟 Urban Switch FX + Sci-Fi Realism，禁用其他 LUT。
  5. 字幕語系：繁中＋日文，VO 對應。
  6. 配音語系：旁白與台詞均日文，無英文旁白。

## Assumptions
1. 戰場幫派與怪物造型為黑鐵與霧組合，無血液（理由：PG-13 與原文「鋼筋與混凝土飛散」）。
2. 戀花針筒能量為心形脈衝粉色光，不產生針孔血跡（理由：避免血腥並符合品牌調性）。
3. 診所外無民眾圍觀，只有隊友與幫派衝突（理由：確保運鏡與安全）。

## Act / Beat / Angle（12 幕 × 約1.25s，含 micro-actions 與物理/光學細節）

### Act I（0.0–5.0s） 地下診所準備｜基調：冷靜→點火｜節奏域：慢入0.9→穩定1.6s｜美術要點：啞光黑牆、粉色心形霓虹、巨型針筒透明折射

#### Beat 1（0.0–1.2s）
重點：外景建立鋼脈都市夜色與診所位置。軸線初始 24mm。
Blocking：高架橋下霓虹像心電圖閃爍，鏡頭沿破裂鋼筋滑入鐵門。
Camera：滑軌前推，24mm 腰高，對焦鐵門鏽跡→心形霓虹，快門角180。
Lighting：路燈 3400K 作主光，霓虹 3800–4200K 閃爍；對比 1.6：1，鐵門邊緣粉色反光。
Materials & Physics：鐵門粗糙度0.6、金屬度0.7，雨滴 0.4mm 隨重力 9.8m/s² 落下；霓虹玻璃折射 1.5。體積霧吸收 0.25。
Emotion & Performance：無角色，營造秘密入口感。
Audio & Transition：遠處警笛 -16 dB；霓虹嗡鳴 -18 dB；推鏡過鐵門遮擋切入 Beat2。
Angle：前中後層次，鐵門佔前景，霓虹心形在中景閃爍。

#### Beat 2（1.2–2.5s）
重點：診所內部黑粉光淹沒，戀花身影進入。軸線 28mm。
Blocking：鐵門被推開，粉色霧氣洩出，戀花背影走入，背上巨型針筒可見。
Camera：跟隨滑移 28mm，肩高，對焦針筒透明槍管，快門角180。
Lighting：心形霓虹 3600K 作主光，粉色 LED 160 nits 沿牆流動；對比 1.8：1。
Materials & Physics：牆面啞光黑粗糙度0.42；粉霧粒徑 18μm，散射 0.52；針筒玻璃折射 1.48，內有粉色液體粘度 1.5 Pa·s 慢速旋轉。
Emotion & Performance：戀花的步伐穩，微帶緊張。
Audio & Transition：鐵門金屬摩擦 -12 dB；腳步踩在橡膠地墊 -16 dB；硬切 Beat3。
Angle：中央構圖，粉霧自門縫向鏡頭前擴散 0.6m。

#### Beat 3（2.5–3.8s）
重點：戀花綁起粉色馬尾，展示腰腹線與發光紋路。軸線 32mm。
Blocking：戀花抬手將長直粉髮束起，服裝肩線與側腰紋路亮起。
Camera：側移 32mm 胸高，呼吸拉焦臉→手→腰線，快門角180。
Lighting：粉色心形霓虹作補光，背後黑牆吸光；對比 2.0：1。
Materials & Physics：戰鬥衣粗糙度0.34，膠條金屬度0.22；發光紋路亮度 180 nits 沿法線凹槽流動；汗膜 0.03mm 在鎖骨形成 specular。
Emotion & Performance：害羞笑、嘴角微抿，眼神專注鏡中倒影。
Audio & Transition：髮束摩擦聲 -18 dB；皮筋彈響 -14 dB；鞭移到 Beat4。
Angle：三分構圖，腰線佔右下；光紋沿肩膀流到腰際形成 S 線。

#### Beat 4（3.8–5.0s）
重點：戀花檢查巨型針筒並聽到前線呼叫，台詞 R1。軸線 32–35mm。
Blocking：指尖滑過透明槍管，粉色液體旋轉浮出心形氣泡；耳機傳來呼叫，戀花側耳聽。
Camera：微俯 35mm 桌面高度，對焦槍管心形氣泡，快門角180。
Lighting：桌面上方 3500K 柔光，粉液自發光 170 nits；對比 1.9：1。
Materials & Physics：液體折射率1.48、粘度 1.5 Pa·s；氣泡直徑 6mm 浮升速度 0.02m/s；金屬活塞粗糙度0.3、金屬度0.9；橡膠手套粗糙度0.28。
Emotion & Performance：戀花輕紅臉，說台詞「じっとしててね、すぐに楽にしてあげるから♡ ……ちょっとだけ、痛いかもだけど。」
Audio & Transition：VO 女聲 -11 dB；耳機呼叫聲帶雜訊 -16 dB；硬切入 Act II。
Angle：中央構圖特寫槍管與手套，補充：粉光在手背形成柔和反射。

### Act II（5.0–10.0s） 戰場暴力治療｜基調：爆發與律動｜節奏域：穩定1.7→加速2.6s｜美術要點：黑粉霓虹紋路、粉色能量脈衝、心形粉霧

#### Beat 5（5.0–6.3s）
重點：戀花背著針筒衝出診所，踏入高架橋陰影戰場。軸線 35mm。
Blocking：戀花拉上醫療包，跨過破碎混凝土跑向呼叫源。
Camera：Steadicam 跟拍 35mm 腰高，對焦背部針筒與臀腿線條，快門角200。
Lighting：路燈 3300K 斜射形成 rim；遠霓虹 4000K 填光；對比 2.0：1。
Materials & Physics：柏油粗糙度0.58、金屬度0.04，薄水膜 0.15mm；鞋底摩擦係數0.62，火星粒徑 0.4mm；針筒背帶尼龍置換 0.3mm 隨跑動 0.2s 延遲。
Emotion & Performance：表情切換到專注，呼吸加快。
Audio & Transition：腳步+金屬碰撞 -10 dB；心跳低頻 70 BPM 淡入；鞭移到 Beat6。
Angle：低角度跟隨，粉色紋路在跑動時沿脊線亮起。

#### Beat 6（6.3–7.5s）
重點：戰場混戰，黑粉紋路從心口亮到指尖。軸線 40mm。
Blocking：戀花滑入倒下隊友旁，左手托背，右手針筒伸長「咔」聲。
Camera：手持≤3% 40mm 胸高，呼吸拉焦臉→針筒→隊友肩，快門角200。
Lighting：高架下路燈 3200K 主光，粉能量作副光 190 nits；對比 2.1：1。
Materials & Physics：針筒金屬度0.9、粗糙度0.28；伸長機構阻尼 0.4，聲響對應；隊友護甲粗糙度0.45；粉能量沿皮膚法線移動 0.2s 延遲。
Emotion & Performance：戀花咬唇，眼神專業但緊張。
Audio & Transition：針筒「咔」聲 -8 dB；旁白 N3「彼女の注射は、ときに優しく、ときにあまりにも暴力的だ。」-10 dB；硬切 Beat7。
Angle：過肩構圖，針筒從前景刺入隊友肩後，粉光拖尾 0.6m。

#### Beat 7（7.5–8.8s）
重點：暴力治療注入，隊友 buff 爆發，台詞 R2。軸線 45mm。
Blocking：針筒刺入肩後，粉色能量像心跳脈衝擴散全身，隊友肌肉瞬間鼓起站起。
Camera：中近 45mm 胸高，快門角200 捕捉脈衝殘影；呼吸拉焦粉光→隊友臉。
Lighting：粉脈衝 200 nits 為主光；周圍霓虹提供 0.2 fill；對比 2.3：1。
Materials & Physics：能量脈衝速度 8m/s，沿血管路徑形成粒子流；汗珠 0.8mm 被震散；肌肉膨脹帶動衣料拉伸 10%，粗糙度變 0.37。
Emotion & Performance：戀花小聲鼓勵，隊友睜眼怒吼，台詞 R2「ほら、まだ戦えるでしょ？ 無茶するなら……ちゃんと最後まで、面倒見させて。」
Audio & Transition：VO 女聲 -10 dB；隊友低吼 -9 dB；鼓點加強；鞭移 Beat8。
Angle：中央構圖，針筒與隊友肩佔前景，粉光形成心跳波紋。

#### Beat 8（8.8–10.0s）
重點：面對幫派頭目，戀花準備《戀愛麻醉》粉霧。軸線 50mm。
Blocking：戀花抬眼看向頭目，將針筒插地，粉霧沿地面快速蔓延。
Camera：穩定器微低 50mm，對焦針筒插地瞬間，快門角200。
Lighting：粉霧自發光 180 nits；路燈形成逆光；對比 2.2：1。
Materials & Physics：粉霧粒徑 12–20μm，擴散速度 6m/s；地面粗糙度0.58；粉霧受風 2m/s 向左飄；菲涅耳反射在霧邊形成粉色 halo。
Emotion & Performance：戀花保持害羞笑但語氣冷，台詞 R3「医療を悪用する人は、ほんとに嫌い。安心して、ちゃんと効く麻酔だから……二度と、同じことはできないよ？」
Audio & Transition：VO -10 dB；粉霧噴出聲 -9 dB；旁白 N4「医療を踏みにじる者には——容赦のない、恋愛麻酔。」-11 dB；硬切 Act III。
Angle：俯視 20°，粉霧形成心形鎖鏈圖案。

### Act III（10.0–15.0s） 心跳過載與診所收束｜基調：爆發→溫柔｜節奏域：加速2.5→收束1.4s｜美術要點：粉色脈衝、診療床光暈、LOGO 收尾

#### Beat 9（10.0–11.3s）
重點：戀花啟動《心拍過載》，心口紋路亮到指尖，台詞 R4。軸線 50–55mm。
Blocking：戀花深呼吸，按壓胸前紋路，粉光脈衝隨心跳加速。
Camera：肩側 55mm，單點對焦胸口與手指，快門角172 凍結紋路細節。
Lighting：粉光 200 nits 成主光，環境霓虹降到 0.4 fill；對比 2.1：1。
Materials & Physics：心跳 120→160 BPM，胸前皮膚汗膜 0.04mm；紋路自發光沿法線凸起 0.3mm；衣料彈性 12% 被撐開。
Emotion & Performance：眉頭皺，語氣堅定，台詞 R4「心臓、フル稼働……これ以上は、ほんとはやりたくないんだけど。みんなを守るためなら……いいよね、少しくらい無茶しても。」
Audio & Transition：VO -10 dB；心跳低頻同步；鏡頭鞭移到 Beat10。
Angle：中央構圖，手指按壓胸口紋路，粉光沿手臂跑向指尖。

#### Beat 10（11.3–12.5s）
重點：戰場收束，敵人被粉霧束縛四肢發軟。軸線 55–60mm。
Blocking：幫派頭目動作像被心形鎖鏈綁住，跪倒；背景怪物停滯。
Camera：長焦 60mm 壓縮，胸高，快門角180；拉焦敵人→戀花。
Lighting：粉霧作主光 170 nits；路燈形成冷 rim；對比 2.0：1。
Materials & Physics：粉霧黏度 0.9，附著在衣物粗糙度0.5；束縛能量像鏈條厚度 2cm；粒子衰減 0.6s。
Emotion & Performance：戀花冷靜注視，表情回到醫者權威。
Audio & Transition：粉霧鎖鏈聲 -12 dB；旁白 N2/N4 淡入重申醫療制裁；硬切 Beat11。
Angle：過肩構圖，戀花肩膀前景，敵人模糊跪地。

#### Beat 11（12.5–13.8s）
重點：回到診所，戀花為「特別在意的人」包紮，台詞 R5。軸線 65mm。
Blocking：戀花坐在診療床旁，替對方肩膀纏繃帶，雙手細膩拉緊。
Camera：75mm 近景，對焦手與繃帶，快門角172；微微下搖呈現表情。
Lighting：上方柔粉燈 3300K 主光，桌邊醫療燈 3600K 填；對比 1.6：1。
Materials & Physics：繃帶棉纖維粗糙度0.55；皮膚粗糙度0.35，汗膜 0.02mm；醫療包 PVC 粗糙度0.25；彈性拉伸 8%。
Emotion & Performance：戀花臉紅碎念，台詞 R5「もう……次に無茶したら、本気で縫い付けて、ベッドから離さないからね？」
Audio & Transition：VO 女聲 -11 dB；繃帶摩擦 -16 dB；旁白 N5「暴力的な治療と、不器用な優しさ。それが、鋼脈都市の黒粉メディック——黒崎恋花。」-10 dB；鞭移 Beat12。
Angle：三分構圖，手與繃帶在前景，戀花臉紅佔中景。

#### Beat 12（13.8–15.0s）
重點：收尾 LOGO 與 Catchphrase R6。軸線 70–75mm。
Blocking：鏡頭從戀花腰腹紋路移到背後巨型針筒，LOGO 亮起。
Camera：穩定器後撤 75mm，胸高，對焦 LOGO；快門角172。
Lighting：粉色腰腹紋路 170 nits；背後心形霓虹 180 nits；對比 1.5：1 保留細節。
Materials & Physics：腰腹紋路沿皮膚 0.3mm 凸起；針筒玻璃折射 1.48，內液體慢速旋轉；LOGO 亮度 160 nits。
Emotion & Performance：戀花低聲 R6「一本打てば、すぐに楽になるよ。ね？ 私、ちゃんと優しくしてるから……たぶんね♡」
Audio & Transition：VO -10 dB；背景音樂淡出；LOGO「黑粉地下診所 KUROSAKI CLINIC」與副標「打一針就會好很多。」顯示後黑場。
Angle：中央構圖，LOGO 占中景，針筒與腰腹紋路形成視覺導線。

## Platform Layer（字幕/Caption/Hook 重申）
- 字幕時間軸：
  - 0.2s：旁白 N1「鋼脈都市の夜。壊れた高架の下、誰も知らない診療所に、ひとつのネオンが灯る。」
  - 3.9s：R1「じっとしててね、すぐに楽にしてあげるから♡ ……ちょっとだけ、痛いかもだけど。」
  - 7.7s：R2「ほら、まだ戦えるでしょ？」
  - 8.9s：R3「医療を悪用する人は、ほんとに嫌い。」
  - 10.4s：R4「心臓、フル稼働……」
  - 12.9s：R5「もう……次に無茶したら」
  - 14.2s：R6「一本打てば、すぐに楽になるよ。」
- Hook 切點：0–3s、7–12s；縮圖色彩建議：黑粉對比＋心形霓虹。
- Caption 切片：短版 A（0–3s）診所亮燈；短版 B（7–12s）暴力治療與粉霧鎖鏈。

## Physics & PBR Layer（跨幕統一參數）
- 重力：9.8m/s²；粉霧粒徑 12–20μm，霧散阻尼 0.14；液體粘度 1.5 Pa·s；氣泡浮升 0.02m/s。
- 布料：戰鬥衣彈性 12%，摩擦係數 0.4，法線貼圖 1K，置換 0.2mm；腰腹紋路光暈半徑 0.6cm。
- 金屬：針筒金屬度0.9、粗糙度0.28；診所器械鋼材粗糙度0.3；高架鋼筋磨損 20%。
- 路面：柏油粗糙度0.58、金屬度0.04，水膜折射 1.33；刮痕深度 1–2mm；摩擦火花粒徑 0.3–0.5mm。
- 光學：室內粉光色溫 3400–3600K；室外路燈 3200–3400K；霓虹 3800–4200K；Bloom 控制 0.32；Chromatic aberration 0.35px。

## Stylepacks Do/Don't 引用
- Urban Switch FX Look — Do：保持 motion_defined 線條、粉霓虹殘影；Don't：不要過度 motion blur 造成粉紋糊掉。
- Sci-Fi Realism Look — Do：金屬與玻璃反射優先，霓虹平衡；Don't：避免霓虹過曝或皮膚失真。

## Platform Layer（切片輸出策略）
- 長版：完整 15s，附日文旁白與角色台詞字幕。
- 短版 A：0–3s 診所亮燈與針筒準備；字幕 N1+R1。
- 短版 B：7–12s 暴力治療＋戀愛麻醉；字幕 R2/R3/N4。

## Self-Check
- 結構：Master/Act/Beat/Angle/timecode 齊全，12 幕對齊 15s。
- Physics & PBR：各 Beat 標明重力、霧粒徑、粗糙度/金屬度、折射與光學；跨幕統一層列出液體與粉霧參數。
- Stylepacks：Urban Switch FX + Sci-Fi Realism 開啟，Do/Don't 已引用，無其他 LUT。
- Continuity：軸線左前 120° 貫穿；光源路燈/粉光持續；診所→戰場→診所轉場以遮擋與粉霧銜接。
- Negative Instructions：禁用血腥/商標/宗教政治符號，字幕語系受控。
- Platform/Caption：Hook、字幕時間軸、切片策略完整。
- 生成設定：Technical Specs 與交付預設符合；QA Checklist 原文已貼入。
- 潛在不足：未提供角色正面參考，需要製作時補充臉部貼圖 ID；戰場怪物粒子需渲染測試以確保粒徑不遮擋主體。
- 自評：品質清單 10/10，準備交付。

## AGENT Self-Check
1. 結構完整度：Master Prompt、Technical Specs、Platform Layer、Negative Instructions、Act/Beat/Angle 均完整，時間軸 12 幕標明 15s。
2. 敘事一致性：診所準備→戰場暴力治療→戀愛麻醉→診所溫柔收束，符合黑粉醫療主題，旁白與台詞對應畫面。
3. 視聽細節：每 Beat 含運鏡、光影、聲音、轉場與 micro-actions（馬尾束起、針筒伸長、粉霧鎖鏈）。
4. 風格準確性：stylepacks 原文完整貼上，色調黑粉與霓虹符合設定。
5. 格式精準度：標題、欄位、命名含日期/集數/slug，遵守專案規範。
6. 物理質感：提供重力、摩擦、粒徑、折射、粗糙度與粘度等量化數據；高級質感來源（粉光/bloom/金屬反射）嵌入。
7. 量化標記：時間碼、亮度 nits、速度 m/s、粒徑 μm、對比比值均標註，避免模糊詞彙。
8. 可交付性：Platform 切片、字幕時間軸、交付規格與 QA Checklist 具備，VO/SFX 分軌策略清楚。
9. Stylepacks 使用：Urban Switch FX（ON）、Sci-Fi Realism（ON），其他 OFF；Do/Don't 已遵守。
10. Continuity：軸線、光源、顆粒與 LUT 延續；LOGO 收尾對應品牌層，粉霧與心形符號在前後呼應。

## Additional Continuity Log
- 粉霧顆粒在 Beat8–10 有殘留，後續若續集需接戰場，請保持霧濃度 0.12 以銜接。
- LOGO 字體與顏色固定：粉色 #ff7ac3，字厚 3mm 內發光；後續集數沿用。
- 鏡頭高度表：Act I 腰高 1.0–1.2m；Act II 胸高 1.3–1.4m；Act III 近景 1.2–1.4m，避免偏差導致軸線錯位。
- 光比一致性：Act I–II 維持 1.8–2.3：1，Act III 降到 1.5–1.6：1；粉光亮度上限 210 nits。
- 角色姿態曲線：跑步步頻 2.6 步/s，注射瞬間肩肘角度 65–85°，綁繃帶時手腕微彎 12°；心拍過載時胸口起伏振幅 6mm。
- HUD/字幕安全框：上下各留 10% 安全區，LOGO 占中下 20%，字幕置於下方安全區內。

## Execution Notes Extended
- VDB 與 Flip 粒子：粉霧使用 VDB 200³，霧粒徑 12–20μm；液體 Flip 90k 粒子，烘焙為 12×12 spritesheet，Alpha 外擴 1px 防縫。
- Camera Projection：診所牆面與心形霓虹投影固定，避免運鏡造成紋路飄移；戰場遠處霓虹同用投影保持一致。
- Motion Blur Policy：戰場使用 200° 快門保留粉霧尾，診所收尾降到 172° 確保 LOGO 清晰；Motion blur 確認不吞線。
- Color Pipeline：Log → Neutral+BlueShadows LUT →對比 +0.1 gamma→papergrain 10%；粉霧層去飽和 3%。
- Audio Sync：針筒伸長（Beat6）、脈衝爆發（Beat7）、粉霧鎖鏈（Beat8–10）設 transient marker 對應 Bloom 與攝影機微震 0.4px；Limiter -1 dBTP。
- Safety：移除可讀文字，字幕只用自家 LOGO；粉霧與霓虹亮度控制 <210 nits。

## Alt Hooks & Captions（備用）
- Hook C：Beat9 心拍過載胸口特寫，字幕「暴力的治療，也有溫柔的心跳。」
- Caption 備用文案：
  - 「粉色注射，秒上戰場。」
  - 「醫療也是武器。」
  - 「戀愛麻醉，讓壞人腿軟。」
- 縮圖備用：針筒插地形成粉霧心形鎖鏈，戀花背影居中。

## Persistent Elements for Next Episode
- 心形霓虹與 LOGO 色票固定；診所牆面刮痕與桌面器械擺位保持，以利續集連戲。
- 針筒內藥液顏色與氣泡設定沿用；腰腹紋路亮度標準維持 170–180 nits。
- 特別在意的患者包紮位置與繃帶走向記錄，下集可延續康復狀態。

## Extended Micro-actions & Timing Map
- T0–0.3s（Beat1）：鏡頭從 0.4m 滑升到 1.4m；雨滴落地濺起 0.6mm 水珠；霓虹閃爍頻率 1.2Hz。
- T0.3–0.6s（Beat2）：鐵門開啟角度 0→45°，粉霧流速 1.2m/s；針筒背帶微晃 0.1m。
- T0.6–1.0s（Beat3）：馬尾束緊時間 0.22s，髮絲 0.2s 延遲落下；腰紋光線沿法線凹槽 0.18s 逐段點亮。
- T1.0–1.2s（Beat4）：氣泡浮升 0.02m/s，手指接觸玻璃 0.12s 形成指紋痕跡；耳機呼叫在 T1.1s 響起。
- T1.2–2.0s（Beat5）：步頻 2.6 步/s；背帶震幅 6mm；水膜因跑動濺起 0.5m 粉色反光水花。
- T2.0–2.5s（Beat6）：針筒伸長 0.35m 用時 0.16s；隊友肩部肌肉收縮 0.2s；粉紋沿臂 0.25s 跑完。
- T2.5–3.3s（Beat7）：脈衝間隔 0.15s，一共 4 拍；肌肉膨脹使衣料拉伸 10%，回彈 0.3s。
- T3.3–4.0s（Beat8）：粉霧擴散半徑 1.2m，用時 0.6s；鏈條圖案在 T3.7s 形成；敵人膝蓋彎曲 35°。
- T4.0–5.0s（Beat9）：心跳 120→160 BPM 在 0.8s 內提升；粉光沿指尖 0.12s；胸腔起伏 6mm。
- T5.0–5.8s（Beat10）：粉霧束縛衰減 0.6s；敵人跌倒速度 1.1m/s；背景粒子停滯後 0.3s 再散。
- T5.8–6.6s（Beat11）：繃帶拉伸 8% 用時 0.4s；戀花手腕微彎 12°；患者呼吸起伏 4mm。
- T6.6–7.2s（Beat12）：鏡頭後撤 2.0m/s；針筒內液體旋轉 0.3 Hz；LOGO 漸亮 0.4s。

## Platform Slice Mapping（字幕對應時間碼補充）
- 0.0–0.8s：外景鋪陳，無字幕；適合做無聲 B-roll。
- 1.0–3.0s：R1 準備針筒；粉霓虹佔滿畫面。
- 7.0–9.0s：暴力治療＋粉霧鎖鏈字幕；可裁成衝擊向短版。
- 12.5–15.0s：診所溫柔收束＋LOGO；適合作結 CTA。

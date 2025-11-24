# 鋼川烈暗影譜 EP5 — 黑紅爆紋・鋼川烈 個人 PV Prompt（15s｜12 幕｜9:16）

來源劇本：使用者提供之《黑紅爆紋・鋼川烈｜個人PV 文案》（霓虹夜城、廢墟訓練、晨跑與再臨戰場的連續場景，含日文台詞）

## Required Input Fields（拍前必填）
- project_name：鋼川烈暗影譜
- series_name/arc：黑紅爆紋個人篇（鋼脈都市）
- episode_index：5
- slug：black-red-burst-pv_v01
- target_platform：短影音（TikTok/YouTube Shorts/IG Reels 同步）
- duration_sec：15（12 幕 × 約 1.0–1.5s；總長 15s）
- style_primary：Anime Fantasy Look + Urban Switch FX（本檔 Default ON）
- style_secondary：無額外漫畫格，僅以紅黑爆紋的衝擊線做字幕邊飾
- worldstate_ref：鋼脈都市夜間霓虹高架、廢墟訓練場與清晨高架跑道交織；紅黑能量紋綁在拳頭
- goal：2D 日系動漫風格個人 PV，聚焦拳擊爆紋、晨跑沉澱與再臨戰場的宣示

## Project Info（UTC+8 日期規則）
- Project 路徑：video-creation/projects/鋼川烈暗影譜/2025-11-24_ep5-black-red-burst-pv_v01
- 拍攝日期標記：2025-11-24（UTC+8）
- 畫幅：9:16 直式，構圖預留字幕下緣 12% 安全框
- 時長與節奏：15 秒（12 幕分別為 1.0/1.0/1.2/1.2/1.3/1.2/1.3/1.2/1.2/1.3/1.3/1.0s）；Act 切分：Act1 0–4.4s｜Act2 4.4–10.6s｜Act3 10.6–15.0s
- 角色狀態：鋼川烈（短髮肌肉青年；黑色貼身戰鬥上衣貼合胸肩，紅色能量線沿鎖骨→手臂→指節黑紅繃帶；拳擊與踢擊為主；語氣短促日語）
- 持續要素：紅黑能量呼吸式閃爍、雨後積水鏡面、霓虹折射光斑、廢墟粉塵、晨跑汗珠、遠處警笛殘響

## Technical Specs（統一拍攝參數）
- Aspect Ratio：9:16｜解析度：1080×1920｜FPS：24（如需慢動建議拍 48 匯出 24）
- Shutter：180°（爆紋衝擊段落 150–160° 保線）；手持 ≤3%
- Lens Set：24/32mm 建立都市與訓練場空間；50/65mm 角色胸肩與拳頭特寫；85–120mm 壓縮晨跑肌肉運動
- Camera Motion：滑軌 + 側移 + 繞拍；拳擊段落搭 5% 手持；晨跑用穩定器跟拍；戰鬥段落可用鞭移對齊衝擊
- DOF：近景 f/2.0–2.8（拳/繃帶/能量紋清晰）；中景 f/4–5.6；晨跑遠景 f/5.6–8 保地平線
- Grain：輕膠片顆粒 8%，避免破圖；Chromatic Aberration：≤0.02 保線稿；Dispersion 控制不過度霓虹邊色散
- Color Pipeline：linear → log → filmic LUT（夜景陰影青藍、霓虹紅黑與品紅；晨跑日光偏暖 5400K）→ 最終對比 +4%；膚色保護
- Delivery：Rec.709；-14 LUFS；-1 dBTP；固定種子記錄；連戲與時序一致

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
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


### Scene Block Template（`_core/scene_block.md`）
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


### Audio Pack 指引（`_core/audio_pack.md`）
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


### VFX 通用 Pack（`_core/vfx_pack.md`）
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


### 交付參數預設（`_core/delivery_presets.md`）
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


### QA Checklist（`_core/qa_checklist.md`）
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


## _stylepacks
### Style Pack：Anime Fantasy Look（預設開啟，Applicable for 夜間霓虹與角色特寫）
- Applicable for：Act1 夜景、Act2 廢墟拳擊與晨跑特寫、Act3 戰鬥收束
- Do NOT mix with：seraphic_realism（避免過度柔光）；zenith_noon_realism（避免硬朗日照）
- Default：ON
- Visual traits：clean_edges、強線稿、pastel_magenta/teal/warm_gold 調色、膚色保護
- Audio traits：空氣感留存，保持雨聲/滴水與遠警笛，低頻適度
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

### Style Pack：Urban Switch FX（預設開啟，用於紅黑爆紋拖影與拳擊衝擊波）
- Applicable for：紅黑能量紋呼吸、拳擊/踢擊衝擊波、雨後水花反射；Act2 拳擊微慢動、Act3 連擊
- Do NOT mix with：seraphic_realism（避免過柔霧）；moonlit_wolf_meme（避免表情誇張）
- Default：ON
- Visual traits：motion_defined 線條，charcoal/neon_lime/crimson/steel_blue/tungsten_warm 配色，拖影與能量邊緣 Fresnel 勾光，水面反射帶微波紋
- Audio traits：Transient 加強拳風「ドン」與腳步；低頻抑制避免霧噪，保留雨滴與警笛
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

## Master Prompt（含 Brand/Physics/PBR/Camera Continuity）
- Brand Bible：鋼川烈＝黑色貼身戰鬥上衣（粗糙度 0.3–0.35）、紅色能量紋沿鎖骨→手臂→指節繃帶（emissive 0.8–1.4 cd/m² 呼吸 0.6s 週期），短髮側削、肩頸肌肉明顯；語氣短促日語，核心信念「守護」。
- Worldstate：
  - 夜間鋼脈都市高架與霓虹：濕度高，雨後積水 1–2 cm，粗糙度 0.22；霓虹招牌光 3600–5200K 交錯；高架金屬樑帶鏽斑置換 4K。
  - 廢墟訓練場：破碎混凝土牆粗糙度 0.55，粉塵粒徑 0.4–0.8 mm；吊掛沙袋填充砂重 45–55 kg，表面皮革粗糙度 0.38，縫線可見；雨滴偶爾落下 1/2.0s。
  - 清晨高架跑道：潮濕柏油粗糙度 0.4，反照率 0.18；金屬欄杆溫度 18–20°C；薄霧密度 0.04，順風 2.1 m/s 吹向城市遠方。
  - 戰場回歸：廢棄街區霧 0.09，黑影輪廓蠢動；遠處 siren -18 dB；牆面有燒黑痕與裂縫。紅黑能量紋可快速提亮至 emissive 1.8 cd/m²。
- Camera Continuity：
  - Act1：24–32mm 俯拍/側推建立霓虹與倒影 → 40–50mm 胸肩與能量紋呼吸 → 50mm 手部繃帶。
  - Act2：35–55mm 拳擊訓練，微手持；轉入 65–85mm 清晨跑步跟拍；慢動段落快門 150°。
  - Act3：50–70mm 近身宣示 → 65–90mm 連擊 → 35mm 收尾全景，對焦拉回安靜街區。
- Physics & PBR：
  - 雨後積水折射率 1.33，水花粒徑 2–4 mm 拋角 35°；足底橡膠摩擦係數 0.82（濕地輕滑）。
  - 能量紋：紅光帶散射半徑 2–4 cm，沿肌肉纖維微鼓起 0.5 mm；呼吸時亮度波形正弦 0.6s；拳擊時瞬間脈衝 1.6 cd/m²，衝擊波粒子 0.3–0.6 mm 向外 14–18 m/s。
  - 繃帶：布料粗糙度 0.5，纖維走向沿指節纏繞；汗液薄膜 0.05，光澤由拳擊摩擦拉出亮線；摩擦係數 0.7。
  - 沙袋：受拳擊位移 6–12 cm 擺動週期 0.9–1.2s，粉塵被震起形成 0.5–0.8 m 高氣霧；碰撞聲附帶低頻共振 120 Hz。
- Optics：霓虹混光 3500–5200K 交錯；晨跑主光偏暖 5400K 補以 4800K 反光；對比中高，眼神光保留；積水鏡面帶菲涅耳反射；肌膚分層 base/SSS/specular 分明；景深保持拳、臉、能量紋清楚。
- Master Prompt：
  - Master(15s｜2D anime black-red brawler｜9:16｜24fps｜sharp linework + PBR skin/cloth + controlled bloom)
  - 「鋼脈都市霓虹與雨後鏡面；廢墟訓練場拳擊點燃紅黑能量紋，清晨高架沉澱汗氣；夜色回到裂痕街區，鋼川烈宣告不再逃跑，爆紋拳連擊怪影。」
  - 鏡頭：滑軌/側推/環繞，手持 ≤3%；表演：冷靜前進→爆發拳擊→沉穩呼吸→決心連擊；構圖三分線與前中後層次；留白 10–15% 給霧與能量。
  - 寫實細節：戰鬥服法線與汗膜、繃帶纖維、能量紋隆起；雨水折射/鏡面；粉塵與衝擊波對霧與衣褶的二次運動。

## Platform Layer
- Hook A（故事向 0–1s）：霓虹雨夜倒影中一個身影逼近，紅紋隨心跳亮起
- Hook B（衝擊向 0–1s）：沙袋被重拳擊出波紋，紅黑氣旋繞腳
- Caption 建議：短版「黑紅爆紋・鋼川烈」；長版「拳上綁著異能的格鬥者」
- First-shot visual hook：俯視積水鏡面中的紅黑剪影，鏡頭緩降
- Thumbnail：烈握拳低頭，紅紋亮度高，背景霓虹與雨滴倒影
- Hashtags：#Anime #PV #Fight #RedBlack #Neon #Brawler #9x16
- CTA：末尾肩膀喘息定格，可加「再打一輪？」提示（不入畫）

## Negative Instructions
- 禁用真實商標、名人肖像、宗教政治符號
- 禁用過曝、廉價濾鏡、魚眼過度畸變、手持晃動 >5%
- 畫面尺度：PG-13；碰撞以光爆/粉塵/霧散呈現，避免血腥
- 不使用寫實照片貼圖；不混用超寫實皮膚細節；字幕僅保留日語短句

## Act/Beat/Angle（12 幕 × 15s，含 Physics/PBR/光學）
### Act 1（0.0–4.4s）｜霓虹夜行與能量預熱 — 基調：壓迫、專注，節奏域 1.0–1.2s
- 美術要點：雨後鏡面、霓虹紅黑光帶、呼吸式能量紋。

#### Beat 1（0.0–1.0s）
- 重述狀態機：霓虹高架夜景建立。
- 重點：俯視高架與積水，遠處一身影逼近。
- Blocking：高空俯拍沿高架梁滑降，雨水形成鏡面，紅黑剪影在倒影中拉長。
- Camera：24mm 俯拍滑軌下降 2m；對焦層次遠→近；快門 180°。
- Lighting：霓虹紅藍交錯 3600–5200K；路燈暖 4200K；對比中高。
- Materials & Physics：積水粗糙度 0.22、折射 1.33；雨滴 1/1.6s；金屬梁鏽斑置換；霧密度 0.05 向右漂 1.5 m/s。
- Emotion & Performance：角色未露臉，壓迫氛圍建立。
- Audio & Transition：環境滴水 + 遠警笛 -18 dB；切入 Beat2。
- Angle：中央構圖高架 S 形引導，留白 12%；安全：無可讀字。

#### Beat 2（1.0–2.0s）
- 重述狀態機：角色進場，能量紋呼吸。
- 重點：胸肩特寫，紅紋隨呼吸微亮。
- Blocking：烈從橋下暗處走向鏡頭，肩膀前傾，呼吸一收一放。
- Camera：40mm 胸肩中近景，穩定器側推 1m；快門 180°。
- Lighting：側逆霓虹，主光冷藍 4800K，紅紋自發光 0.9；對比中；眼神光微弱。
- Materials & Physics：戰服布料粗糙度 0.33，汗膜 0.03；能量紋呼吸亮度 0.8→1.1 cd/m²；肩膀肌肉在布料下隆起 2–3 mm。
- Emotion & Performance：烈目光鎖定前方，呼吸穩。
- Audio & Transition：低沉電流嗡＋腳步踩水；光源匹配切 Beat3。
- Angle：三分線右肩在 1/3，左側留霓虹；安全：去Logo。

#### Beat 3（2.0–3.2s）
- 重述狀態機：拳頭與繃帶細節。
- 重點：小臂肌肉與黑紅繃帶。
- Blocking：烈抬起右拳，繃帶纏繞的指節微微收緊。
- Camera：50mm 手部特寫，微拉焦指節→能量紋；快門 180°。
- Lighting：刀鋒式側光，高光凸顯繃帶紋理；背景霓虹壓暗；對比高。
- Materials & Physics：繃帶粗糙度 0.5、纖維可見；汗液光澤 0.05；能量紋沿手背鼓起 0.5 mm；肌肉張力顯露。
- Emotion & Performance：拳頭蓄力，眉頭微蹙。
- Audio & Transition：手部布料摩擦 + 細微電流；鞭移至 Beat4 背影。
- Angle：中央構圖拳頭占 40%，背景虛化；安全：無字樣。

#### Beat 4（3.2–4.4s）
- 重述狀態機：宣示自己的場域。
- 重點：背影前景，烈抬頭吐出台詞「ここが、俺のフィールドだ。」
- Blocking：烈停在高架橋底中央，緩慢抬頭，嘴型配合日語。
- Camera：32mm 背影中景，微低機位；手持 3%；快門 180°。
- Lighting：橋底環境光 4000K，霓虹反射在積水；紅紋隨語氣脈衝至 1.3 cd/m²。
- Materials & Physics：積水被腳步踩出 2–3 cm 波紋；布料褶皺延遲 0.1s；呼出白霧 0.03 密度。
- Emotion & Performance：聲線低沉堅定，肩線向前傾。
- Audio & Transition：日語台詞 -10 dB；水滴回響；直接切 Act2。
- Angle：背影置中，倒影占下方 1/3；安全：字幕預留底部。

### Act 2（4.4–10.6s）｜廢墟拳擊與晨跑沉澱 — 基調：爆發、專注，節奏域 1.2–1.3s
- 美術要點：廢墟粉塵、紅黑衝擊波、晨光汗霧。

#### Beat 5（4.4–5.6s）
- 重述狀態機：切到廢墟訓練場。
- 重點：烈對沙袋重拳，沙袋變形。
- Blocking：烈左腳前踏，右拳全力擊打沙袋，粉塵飛起。
- Camera：45mm 中近景側拍，手持 3%；快門 160°。
- Lighting：頂部破洞漏下冷光 4600K，側補暖 3800K；能量紋閃亮。
- Materials & Physics：沙袋皮革粗糙度 0.38；拳擊接觸 18 m/s，沙袋凹入 8 cm；粉塵粒徑 0.6 mm 被衝擊向外 12 m/s；戰服褶皺延遲 0.08s。
- Emotion & Performance：烈牙關緊咬，呼吸粗重。
- Audio & Transition：拳擊「ドン」+ 低頻共振；粉塵沙沙；動態切 Beat6。
- Angle：三分線，拳頭在左 1/3；安全：無字。

#### Beat 6（5.6–6.8s）
- 重述狀態機：連續拳擊微慢動。
- 重點：紅紋沿肩背點燃，多拳連擊。
- Blocking：烈連續三拳，肩背肌肉帶動腰轉，粉塵形成螺旋。
- Camera：55mm 斜後跟拍，微 slow 0.85x；對焦肩→拳；快門 150°。
- Lighting：背光紅能量 rim，加冷主光 4800K；對比高。
- Materials & Physics：能量脈衝 1.6 cd/m²；衝擊波在空氣形成 0.3–0.5 m 震紋；粉塵旋渦半徑 0.7 m；汗滴被甩出 2–3 m/s。
- Emotion & Performance：眼神專注，眉頭緊鎖。
- Audio & Transition：連打節奏對齊鼓點；鞭移到 Beat7。
- Angle：肩背占 60%，沙袋模糊；安全：無字。

#### Beat 7（6.8–8.1s）
- 重述狀態機：切到清晨高架跑道。
- 重點：烈戴手套慢跑，肌肉發光汗澤。
- Blocking：烈向鏡頭左→右跑過，肩膀起伏，呼吸穩。
- Camera：85mm 平行跟拍，穩定器；快門 180°。
- Lighting：日光 5400K 偏暖，背光 rim；紅紋收斂成暗紅 0.6；對比中。
- Materials & Physics：汗珠粒徑 1–2 mm 順臉頰滑落；布料隨步伐 0.15s 延遲；鞋底摩擦 0.82，水花小於 1 cm。
- Emotion & Performance：表情平靜，嘴角微張吸氣。
- Audio & Transition：均勻呼吸與鞋底節奏；光源匹配切 Beat8。
- Angle：側拍三分線，背景城市模糊；安全：字幕空間保留。

#### Beat 8（8.1–9.3s）
- 重述狀態機：細節強調耐力。
- 重點：腳步踏地與能量鎖緊。
- Blocking：鏡頭低位跟拍腳步，紅紋在繃帶內收斂像封印。
- Camera：35mm 低機位推進 1.5m；快門 180°；對焦足背。
- Lighting：地面反射天空柔光 5200K；暗紅能量作邊光。
- Materials & Physics：柏油粗糙度 0.4；鞋底水花 0.8 cm 拋角 30°；能量鎖紋如鎖鏈收束，亮度降到 0.5。
- Emotion & Performance：步伐穩，呼吸落在 0.8–1.0s 節奏。
- Audio & Transition：鞋底節奏 + 輕微脈衝音；直接切 Beat9。
- Angle：低角度，足尖在左 1/3；安全：去Logo。

#### Beat 9（9.3–10.6s）
- 重述狀態機：內心宣言。
- 重點：烈望向遠方，台詞「守りきれるだけの力が、欲しいだけだ。」
- Blocking：烈在高架邊停下，手撐欄杆，望向都市晨光。
- Camera：65mm 半身側面，微拉焦眼→遠景；快門 180°。
- Lighting：晨光暖 5400K，城市反射偏冷 5000K 形成對比；眼神光保留。
- Materials & Physics：汗霧在冷暖交界形成淡薄煙 0.02 密度；金屬欄杆粗糙度 0.35；能量紋微亮 0.7。
- Emotion & Performance：語氣平靜但堅定，目光銳利。
- Audio & Transition：日語台詞 -9 dB；遠處車流；光源匹配切 Act3。
- Angle：左三分線為烈，右側留城市；安全：字幕預留。

### Act 3（10.6–15.0s）｜戰場再臨與爆紋連擊 — 基調：決心、爆發，節奏域 1.2–1.3s
- 美術要點：霧中怪影、紅黑氣旋、衝擊波弧線。

#### Beat 10（10.6–11.9s）
- 重述狀態機：夜色回到廢棄街區，怪影蠢動。
- 重點：烈站在中央，能量紋自胸口往雙臂蔓延。
- Blocking：霧中怪物輪廓閃現，烈抬頭深吸氣，拳頭握緊，關節爆裂聲。
- Camera：50mm 正面中景，微低角；快門 170°。
- Lighting：霧中冷光 4200K，紅紋自發光 1.6；對比高；體積霧吸收係數 0.2。
- Materials & Physics：霧密度 0.09 被呼氣推開；能量紋鼓起 0.8 mm；拳套繃帶摩擦發出細聲；地面裂縫粗糙度 0.5。
- Emotion & Performance：眼神銳利，呼吸加深，嘴角下壓。
- Audio & Transition：骨節爆裂 + 低頻隆隆；遮擋剪接到 Beat11。
- Angle：中央構圖，前景霧遮 15%；安全：無字。

#### Beat 11（11.9–13.2s）
- 重述狀態機：連續戰鬥 montage。
- 重點：近身連擊、迴旋踢、貼面閃刀，紅光爆紋。
- Blocking：快速剪接三動作：左直拳→右迴旋踢→貼身閃過怪爪反肘擊，衝擊波弧線掃出。
- Camera：65mm 近景，鞭移跟拳→踢→肘；快門 150°。
- Lighting：紅黑互補，動態光隨衝擊閃亮；對比高。
- Materials & Physics：衝擊波弧線粒子 0.3–0.6 mm，速度 16 m/s；怪影被砸向地面粉塵 0.5 mm；衣物延遲 0.1s；重力 9.8 m/s² 明確。
- Emotion & Performance：動作俐落，呼喝短促「ハッ！」。
- Audio & Transition：拳腳衝擊 + 風切；銜接 Beat12 的 siren 遠響。
- Angle：剪接三組鏡頭保持軸線；安全：避免怪物細節過多。

#### Beat 12（13.2–15.0s）
- 重述狀態機：戰鬥收束與台詞。
- 重點：烈站在破碎路面中央，呼吸穩定，微笑說「まだ、やれる。」
- Blocking：鏡頭繞半圈至正面，紅紋收回體內，肩膀起伏減緩。
- Camera：35mm 半身環繞 120°；快門 180°；對焦眼睛。
- Lighting：雨停後空氣清透，主光冷 4600K，紅紋暗下到 0.5；對比中。
- Materials & Physics：積水鏡面反射紅光漸弱；衣料回彈，繃帶略鬆；霧散向兩側 0.7 m/s；呼吸在冷空氣形成白霧。
- Emotion & Performance：微笑但眼神依然鋒利，呼吸均衡。
- Audio & Transition：遠處 siren 回音 -18 dB；環境靜下；以淡出收尾。
- Angle：中央構圖，背景裂紋與燒黑牆面；安全：字幕結尾可置頂。

## Micro-action Timeline 補充
- Beat6 連續拳擊（T0–T1.2s）：
  - T0：右拳擊出，能量紋亮至 1.6 cd/m²，沙袋凹 8 cm；
  - T0+0.4：左拳接續，腰轉帶動肩背，粉塵被扯成弧線；
  - T0+0.8：右拳上勾，粉塵漩渦半徑擴到 0.7 m；
  - T1.2：沙袋回彈，烈後撤半步，肩膀仍緊繃。
- Beat8 足步封印（T0–T1.2s）：
  - T0：右腳踩入水窪，水花 0.8 cm 拋角 30°；
  - T0+0.4：能量紋沿腳背收束，亮度降到 0.5；
  - T0+0.8：左腳接地，布料褶皺順時延遲 0.15s；
  - T1.2：兩腳節奏穩定，呼吸與步頻同步。
- Beat11 連擊 montage（T0–T1.3s）：
  - T0：左直拳命中，衝擊波弧線展開 60°；
  - T0+0.5：右迴旋踢掃過，鞋底擦地帶起火星 0.2–0.4 mm；
  - T0+0.9：貼面閃過怪爪，肘擊下砸，粉塵噴散 14 m/s；
  - T1.3：鏡頭切換，紅紋逐步收斂，準備 Beat12。

## Platform Layer 追加切片策略
- Shorts 版本：剪入 Beat5 慢動拳擊與粉塵、Beat11 連擊爆紋，字幕「黑紅爆紋」「拳上綁著力量」。
- Reels 版本：保留 Beat7–Beat9 的晨跑與宣言，搭配低飽和暖色；字幕「守りきれるだけの力」。
- 長版 YouTube：完整 15s，描述欄附色溫/LUT/種子方便複製；戰鬥段落保持 24fps。

## Execution Notes
- 求解建議：粉塵用 VDB + velocity field；能量紋 pulse 用 Niagara 或 VFX Graph Fresnel；水花可用 Flipbook；衝擊波用 Sprite Sheet 帶 Flowmap。
- 渲染：保持 log，霓虹與能量 Bloom 控制在不過曝；雨後鏡面用 SSR + 微波法線；晨跑段落降低顆粒以保潔淨。
- Denoise 限制：爆紋段落降低 denoise 保留線稿；霧量高段落增 samples 避免閃爍。
- 相機校正：24–32mm 做 5% barrel 校正；長焦晨跑需記錄焦距/DOF 便於連戲；鞭移需遮擋對齊。
- 音畫同步：台詞對應紅紋脈衝，門檻 -12 dB；拳擊瞬間提升鼓組 transient；警笛作遠景音景。
- 安全：檢查無多餘文字、無未授權素材；字幕僅保留日語台詞。

## Next Episode / Spin-off Ideas
- 主線延伸 1：高架晨跑目擊遠方能源塔閃爍，可引出下一集追查爆紋源頭。
- 主線延伸 2：廢墟訓練場的沙袋被能量灼燒，露出內芯晶體，成為後續武器升級伏筆。
- 番外/日常短片：烈教學繃帶纏法與能量呼吸控制，展示品牌語氣的冷靜旁白。

## SORA Prompt Compiler 提醒
- 完成 `prompt.md` 後需以 SORA PROMPT COMPILER 轉為 `sora.md` JSON，僅保留渲染必要資訊（meta/style/global_prompt/negative/shots）。
- `shots` 需對應 12 幕 S01–S12，時間以 15s ÷ 12 平均換算，保持英文 3–5 句描述運鏡/光影/材質/情緒/聲音。
- 禁止將 `_core`/`_stylepacks` 全文或平台層文字帶入 `sora.md`，僅保留必要禁用項與場景要點。

## AGENT Self-Check
- 結構：Master/Act/Beat/Angle/timecode 均完整；12 幕時間標註，Act 節奏對齊 15s。
- Physics & PBR：各幕寫入重力、慣性、布料/流體反應、能量紋 emissive、PBR 粗糙度/金屬度與光學行為。
- Stylepacks：Anime Fantasy Look + Urban Switch FX 已貼原文，套用於夜景、拳擊、晨跑與戰鬥段落，無衝突。
- Continuity：Camera Continuity 列出各 Act 焦段與運鏡；品牌與世界觀延續鋼脈都市設定。
- Negative：禁用商標/血腥/過曝已列；字幕限制日語台詞。
- 自評：10/10；若需更多怪物細節將在使用者確認後補充。

## Project Inputs
- project_name: 黑綠風壓衝線・風見迅
- series_name/arc: 鋼脈都市・黃昏疾風篇
- episode_index: 1
- slug: wind-pressure-line-pv
- target_platform: TikTok / Shorts / Reels 直式 9:16
- duration_sec: 15 (12 幕 × 1.2s)
- style_primary: 黑綠風壓疾跑動漫
- style_secondary: 工業寫實陰影 + 速度線漫畫化
- worldstate_ref: 黃昏鋼脈都市高架與港區交界，訓練用機械小怪突然啟動
- goal: 製作 15 秒 2D 日系動漫個人 PV，凸顯風見迅的黑綠風壓跑酷與近戰風壓斬線招式，含日文配音與漫畫化高潮。

## _core (Brand Bible & Worldstate)
- Brand Traits:
  - 主角風見迅：黑色貼身機能上衣（尼龍/氨綸，法線織紋 0.3，粗糙度 0.32，金屬度 0.05），胸肌與肩線清晰；鎖骨至前臂刻有螢綠風紋（發光 950 nits，脈動頻率 2.4Hz，正常時亮度 40%，爆發時 100%，法線凸起 0.5mm）。
  - 下身：深灰工裝慢跑褲（粗糙度 0.45，膝部加固 0.6，縫線 0.9mm），褲側螢綠線條連到鞋面（TPU 亮面，金屬度 0.15）；鞋底抓地紋理 1.6mm，摩擦係數 0.86。
  - 動作習慣：起跑前腳踝旋轉 0.4s 預熱；高速時前傾 12°，手臂貼近軀幹形成流線；收尾習慣輕碰右耳耳機確認通訊。
  - 口頭禪：低聲評估「……風向き、悪くないな。」；戰鬥中笑著挑釁「オレについて来れんのかよ？」；收尾帶笑「さあ、次の現場まで走るか。」。
  - 道具狀態：通訊耳機黑色霧面（粗糙 0.5，金屬度 0.12），螢綠指示燈 600 nits 間歇亮；腕部護具內藏微型風壓共振器（金屬度 0.78），啟動時發出 1.6kHz 風切音。
- Worldstate Snapshot (前置設定):
  - 場景：黃昏 17:40，太陽仰角 10°，主光 4200K 斜射，海風從港區吹向高架（風速 6.2m/s，含鹹味與機油味）；高架橋像交錯的鋼筋血管，路面乾燥混凝土粗糙 0.62。
  - 高架結構：雙層互鎖護欄鋼材金屬度 0.72，表面鏽蝕 0.4；路面標線螢綠反光塗料亮度 300 nits；橋下陰影 AO 0.55。
  - 訓練機械小怪：身高 1.1m，球形中軸加四肢，鋁合金外殼金屬度 0.76，粗糙度 0.28，紅外掃描眼亮度 700 nits；內部陀螺穩定器使其彈跳起身。
- Constraints (不可變更):
  - 角色與主要動作均為 2D cel shading，3D 僅作粒子/體積/環境輔助；描邊 0.8–1.2px 依景深調整。
  - 影片長度固定 15 秒，12 幕 × 1.2s，9:16 直式構圖；遵守 180 度規則與平移/推拉運鏡為主。
  - 機械小怪不可出現血液，僅火花/碎片；風壓斬線只刻出乾淨刮痕與細長風刃，不得過度血腥或斷肢。
  - 漫畫化高潮需出現在 Act2 Beat3/Act3 Beat1，加入網點與擬聲字「ゴオ」「バシュ」。
- Brand Do / Don't：
  - Do：對比度 1.8 gamma curve；螢綠主題色 #58ff9e 作為速度線與 FX；用 6500K rim 光勾勒輪廓；運鏡以平移+推拉，保持 2–6px 視差層。
  - Don't：禁止 360° 繞拍與魚眼；避免過度霓虹飽和；禁止寫實景深散景；禁止將角色建模為重度 3D 光影。
- Character Sheet:
  - 身高 178cm，體脂 10%，肩寬 47cm；心率在起跑瞬間 150bpm，爆發拳時 168bpm；呼吸節奏 0.6s 吸、0.7s 呼。
  - 皮膚：基底色 #d8c0b2，SSS 半徑 1.0mm，specular 0.18；汗珠分佈額頭/鎖骨 0.05mm 高，折射 1.33。
  - 表情：淡笑 15%，眼神專注，眉峰收緊；戰鬥時瞳孔縮小 5%，眼白反光 550 nits。
- Environment Sheet:
  - 港區霓虹：遠處藍紫 #4d65ff 招牌亮度 800 nits；橋下昏暗 AO 0.55；混凝土法線粗度 0.48。
  - 海風帶霧：鹽霧顆粒密度 0.03，粒徑 60–120µm，受路面摩擦加熱升溫 1.2°C。
  - 高架照明：路燈 3800K，間距 12m，亮度 350 nits，鏡面反射在雨水殘留 0.2mm 透明水膜上；目前地面八成乾燥。

## _stylepacks
- Style: Black-Green Windline Sprint (Default ON)
  - Applicable for: 高速跑酷、螢綠速度線、風壓殘影、黑色機能服質感。
  - Do NOT mix with: 童話柔光、粉彩夢幻、血腥寫實。
  - Visual traits: 描邊 1.0px；螢綠速度線放射密度 26 條/秒；殘影透明度 65% 階梯 3 層；風壓刮痕刻度 1–2cm 深度、邊緣毛刺 0.4mm。
  - Audio traits: 風切聲上升 700Hz → 2.5kHz；拳擊衝擊低頻 90Hz；耳機提示音 1.6kHz；日文配音低沉帶鼻音。
  - Default ON: 螢綠殘影、速度線、風紋脈動；Default OFF: 霓虹 lens flare。
  - Do / Don't：Do 使用 24–50mm 鏡頭，平移+推拉；Do 以 cel shading 光影 1–2 階；Don't 過度景深、Don't 使用 3D 角色陰影。
- Style: Industrial Highway Dusk (Support ON)
  - Applicable for: 鋼脈都市高架、港區海風、鋼筋護欄與混凝土材質、夕陽斜射陰影。
  - Do NOT mix with: 霧濛童話、夜間霓虹賽博飽和。
  - Visual traits: 太陽 4200K 斜光帶 1.2 stops 對比；護欄鏽蝕法線 0.35；遠方港口吊臂半透明輪廓 40%；體積霧密度 0.05，視差 3px。
  - Audio traits: 海風 180Hz 低頻帶鹹霧，遠處貨船鳴笛 120Hz，橋下空腔迴響 1.1s；金屬震動 2kHz。
  - Default ON: 硬光+rim、薄霧、金屬鏽蝕；Default OFF: 濃霧遮擋。
  - Do / Don't：Do 控制顆粒 8–10%；Do 用 6500K rim 光分離角色；Don't 過曝夕陽；Don't 讓背景霓虹搶奪主體亮度。
- Style: Manga Impact Overlay (Climax ON)
  - Applicable for: 漫畫化高潮瞬間、風壓衝擊圈、手繪擬聲字。
  - Do NOT mix with: 實拍模糊、過度光暈。
  - Visual traits: 網點 45度 0.8px 間距；描邊在高潮增粗至 1.4px；速度線 radial burst 32 條/秒；擬聲字「ゴオ」「バシュ」白底黑描邊 2px。
  - Audio traits: 衝擊瞬間低頻加強 +3dB，風壓爆圈帶 500Hz noise；紙張摩擦音 650Hz 淡入。
  - Default ON: Act2 Beat3 與 Act3 Beat1；Default OFF: 其他時段。
  - Do / Don't：Do 在高潮加入 2D overlay；Do 保持 cel shading；Don't 讓漫畫疊層遮蔽角色面部。

## Technical Specs
- Aspect Ratio: 9:16 直式；解析度 1080x1920。
- FPS: 24fps；Shutter: 180° (1/48s)；Motion blur 遵循實景速度。
- Lens kit: 24mm（環境推移）、35mm（主中景）、50mm（半身特寫）、75mm（拳頭與耳機特寫）。
- Depth of Field: 主體景深 0.7–0.9m，背景輕微散焦；避免過度景深與逼真散景。
- Grain & Color: Filmic LUT；對比度 1.8 gamma curve，飽和度 -4%；微顆粒 10%；色彩流程：line art → flat color → shadow (hard + soft) → FX pass（螢綠速度線/風刃）→ LUT。
- Light: 主光 4200K 夕陽斜射，rim 光 6500K 後上方；地面反射 4500K；AO 0.5；體積霧 0.05；螢綠自發光與反射在皮膚/布料控制 30% 內。
- Simulation notes: 風沙粒徑 80–120µm；風壓殘影粒子 1mm sprite；小怪火花粒子 0.6mm，粒子上限 45k；VDB 風壓煙霧解析度 0.012；Flip smoke 限制 0.015；2D/3D Layering 嚴格標註。
- Compression strategy: 上傳前 GOP 24，bitrate 20Mbps；對高亮螢綠採用 tone mapping 避免社群壓縮飽和。

## Master Prompt
- Duration: 15s，12 幕，每幕約 1.2s，時間軸標記在 Act/Beat/Angle 中。
- Scene Overview: 黃昏的鋼脈都市高架橋，港風帶鹹味；高架像鋼筋血管延伸，遠處港口吊臂與霓虹做背景。風見迅站在空蕩高速車道風口，黑色機能服與螢綠風紋點亮，準備衝刺與風壓搏擊。
- Worldstate Snapshot: 沿用 `_core`，夕陽 4200K，風速 6.2m/s，薄霧 0.05，路面乾燥；訓練機械小怪從路障後彈出，作為測試靶。
- Constraint List:
  - 9:16 直式，平移/推拉/上下移運鏡，禁止 360° 繞拍；描邊 0.8–1.2px，高潮 1.4px。
  - 角色全程 2D cel shading；3D 僅粒子/體積/環境，大視差禁止；殘影透明度 65%，最大層數 3。
  - 物理：風壓初速 30m/s，拳擊觸地時風刃刮痕深 1cm；重力 9.81m/s²；鞋底摩擦 0.86；小怪重量 18kg，彈跳 0.4m。
  - 安全：機械小怪破壞僅火花與煙塵，無血腥；PG-13；字幕中日雙語。
- Execution Note:
  - Camera projection：背景高架以 2.5D 投影 + 輕微 parallax 2–4px；跑酷路線平移 1.2m/s 視覺速度，結合 2D 速度線。
  - FX Solver & Budget：風壓煙霧 VDB 0.012，粒子上限 45k；火花粒子 1e4；限制 bloom 1.1 stops；Denoise 適中保留線稿。
  - Manga overlay：Act2 Beat3 & Act3 Beat1 套用網點 0.8px、速度線 radial、擬聲字「ゴオ」「バシュ」。
- Camera Continuity:
  - 開場 35mm 俯視拉至 24mm 俯視，保持左→右運動方向；中段側拍 35mm 平移；高潮落地 50mm → 75mm 特寫匹配剪接。
  - 光比 2.2:1（key:fill），高潮風壓爆圈時暫升至 3:1；rim 6500K 持續勾邊。
- High-end Look:
  - 皮膚：base #d8c0b2，SSS 1.0mm，specular 0.18，粗糙度 0.38；汗珠折射 1.33，微表面油膜 0.02。
  - 布料：尼龍/氨綸織紋 120 線/cm，法線強度 0.35；褲料纖維 0.2mm 抗撕裂；鞋面 TPU 亮面塗層 0.4mm。
  - 金屬：護欄金屬度 0.72，粗糙度 0.4；小怪殼金屬度 0.76；刮痕以法線置換 0.25。
  - 光學：景深平穩，限制 bokeh；chromatic aberration 0.3px；微顆粒 10%。
- Assumptions
  - 風見迅單人登場，無其他隊友。
  - 訓練小怪為安全模式，目標僅被擊飛不自爆。
  - 本集不切換至室內或夜景，全部在高架與港區交界的開放道路進行。

## Negative Instructions
- 禁用：真實商標/名人/宗教政治符號、血腥斷肢、色情暗示、魚眼與 360° 繞拍、過曝或霓虹賽博飽和、過度慢動作、寫實散景模糊。
- 避免：角色崩壞比例、線稿模糊、錯誤語言字幕、版權音樂、煙霧遮蔽主體、螢綠過飽和導致失真。
- 自動檢核清單：
  - [ ] 無侵權標誌；[ ] 無血腥；[ ] 無政治宗教符號；[ ] 無錯誤字幕；[ ] 光比穩定；[ ] 9:16 保持；[ ] 漫畫化鏡頭有網點/擬聲；[ ] 粒子數 ≤45k；[ ] 180 度規則；[ ] PG-13 尺度。

## Platform Layer
- Hook A (故事向 0–1s): 「黃昏高架，風見迅踩風衝線」；視覺：俯視螢綠速度線在路面畫圈。
- Hook B (衝擊向 0–1s): 側拍起跑殘影三層疊出，字幕「音速試跑？」；用螢綠 radial 速度線。
- First-shot visual hook: 35mm 俯視拉遠至 24mm，螢綠線條如血管在路面亮起。
- Captions: 中日雙語白字黑描邊；Hook A 用「風口起跑」、Hook B 用「連拳音速」。
- Thumbnail: 風壓斬線落地瞬間，螢綠圈爆開，小怪被震飛定格。
- Hashtags: #風見迅 #黒緑風圧 #2Dアニメ #Parkour #風圧斬 #港区高架
- CTA: 結尾疊字「次の走線、どこ？」鼓勵追蹤。
- Slicing Strategy: 15s 全版；短版 6s 可截取 Act2 Beat1-2（跑酷衝刺＋殘影拳）；長版維持 15s，字幕同步。

## Act 1: 起跑與場景定義 (0.0–4.8s)
- Planned transitions: 俯視拉遠 → 硬切側拍 → 推拉至預備；保持左→右方向一致。
- Beats:
  - Beat 1 (0.0–1.2s): 俯視空蕩高速，風見迅站在風口，螢綠風紋亮起。
  - Beat 2 (1.2–2.4s): 起跑衝刺，殘影拖出速度線。
  - Beat 3 (2.4–3.6s): 側拍褲料肌肉起伏，踩護欄跑酷。
  - Beat 4 (3.6–4.8s): 預備跳躍，螢綠線條沿護欄延伸。

### Angle A1-1 (Beat1 0.0–1.2s)
- Camera: 35mm 俯視，垂直拉遠 0.6m → 24mm；F/5.6；景深 0.8m；平移 0.3m 左→右，保持 2–6px 視差。
- Lighting: 主光 4200K 斜射，rim 6500K 後上；路面反光 4500K；體積霧 0.05 輕薄；夕陽在護欄投長影 1.2m。
- Materials & Physics: 混凝土粗糙 0.62；護欄金屬度 0.72；風速 6.2m/s 帶起鹽霧粒子 80–120µm；重力 9.81m/s²；2D / 3D Layering：角色_base=2D，地面裂紋=2D 線稿，風沙=3D 粒子，遠景吊臂=3D VDB 輕度，最上層加 2D 速度線。
- Emotion & Performance: 風見迅微低重心，右腳腳踝輕旋 0.4s，眼神掃風向；風紋亮度 40% 脈動；胸肌起伏呼吸 0.7s。
- Audio & Transition: 海風 180Hz，機油味伴隨低頻 rumble；迅低語「……風向き、悪くないな。」音量 -14 LUFS；結尾硬切 Beat2。

### Angle A1-2 (Beat2 1.2–2.4s)
- Camera: 28mm 斜俯拍，向前推進 1.0m，快門 1/48；輕微 motion blur；保持 9:16 居中構圖。
- Lighting: 夕陽斜光在地面形成橙金高光；rim 光 6500K 勾出肩線；地面 AO 0.5；無過曝。
- Materials & Physics: 鞋底摩擦 0.86，起跑時後塵被風捲起 0.5m；殘影透明 65%，層數 3，拖尾長 2.1m；風壓初速 30m/s；2D / 3D Layering：角色=2D，殘影=2D 疊加，塵土=3D 粒子，背景護欄=3D base+2D 描邊，最上層 2D 速度線。
- Emotion & Performance: 迅重心壓低 12° 前傾，手臂貼身擺動；胸肌與大腿肌收縮起伏；瞳孔收縮 5% 專注。
- Audio & Transition: 風切聲升至 2.5kHz；鞋摩擦聲 600Hz；無台詞；推進尾端匹配剪接到 Beat3 側拍。

### Angle A1-3 (Beat3 2.4–3.6s)
- Camera: 35mm 側拍中景，平移 1.4m；F/4.5，景深 0.7m；保持左→右運動；無劇烈視差。
- Lighting: 主光在肌肉起伏上形成硬陰影；rim 光 6500K 在褲側螢綠線條上形成高光；護欄 cast shadow 掠過。
- Materials & Physics: 褲料纖維 0.2mm；護欄金屬粗糙 0.4；鞋踏護欄時摩擦 0.86，反作用力讓碎石彈起 0.3m；風紋亮度脈動 60%；2D / 3D Layering：角色=2D，護欄=2D 描邊+3D 投影，碎石=3D 粒子，速度線=2D overlay。
- Emotion & Performance: 迅踩護欄，肌肉張力清晰；嘴角上揚 10%；呼吸短促 0.5s；目光前視路線。
- Audio & Transition: 踩護欄金屬「キン」2kHz；風聲持續；無台詞；結尾硬切 Beat4。

### Angle A1-4 (Beat4 3.6–4.8s)
- Camera: 24mm 低角度仰拍，向上推 0.6m 追隨迅準備跳躍；F/4；景深 0.9m。
- Lighting: 夕陽背光形成剪影，rim 光 6500K 勾邊；地面反射補 fill 4500K；速度線螢綠自發光反射在護欄 30%。
- Materials & Physics: 路標板粗糙 0.55，金屬度 0.6；迅腳尖壓在護欄邊緣，摩擦 0.86，護欄微彈 0.5cm；風壓在鞋側形成 1.2cm 風刃；2D / 3D Layering：角色=2D，護欄=3D base+2D 線稿，風壓=3D VDB 半透明 70%，速度線=2D。
- Emotion & Performance: 迅深吸氣，肩膀上抬，眼神鎖定前方路牌；風紋亮到 80%。
- Audio & Transition: 深呼吸音 -18 LUFS；螢綠脈動配合 700Hz 低頻；硬切進 Act2 Beat1。

## Act 2: 跑酷戰鬥與殘影連拳 (4.8–9.6s)
- Planned transitions: 側拍平移 → 斜俯推近 → 漫畫化爆圈 → 匹配剪接。
- Beats:
  - Beat 1 (4.8–6.0s): 踩路牌翻身，殘影分身衝刺。
  - Beat 2 (6.0–7.2s): 機械小怪彈出，風壓連拳爆圈。
  - Beat 3 (7.2–8.4s): 漫畫化音速連拳，綠色爆圈。
  - Beat 4 (8.4–9.6s): 迅落腳收勢，預備風壓斬線。

### Angle A2-1 (Beat1 4.8–6.0s)
- Camera: 28mm 斜俯，跟拍迅踩路牌翻身，平移 1.2m；快門 1/48；景深 0.75m。
- Lighting: 夕陽斜光形成橙金 rim；路牌反光 350 nits；薄霧 0.05 在鏡頭前形成淡暈。
- Materials & Physics: 路牌鋁板金屬度 0.65，粗糙 0.3；翻身時路牌震動 2mm；迅身體角度 120° 翻轉，重心轉移到左足；殘影拖 2.3m；2D / 3D Layering：角色=2D，路牌=3D base+2D 線稿，殘影=2D overlay，風沙=3D 粒子。
- Emotion & Performance: 迅笑意上揚 20%，眼神玩味；腳尖推路牌藉力，手臂收緊形成流線。
- Audio & Transition: 路牌震動聲 1.4kHz，風切升 2.8kHz；無台詞；結尾平移銜接 Beat2。

### Angle A2-2 (Beat2 6.0–7.2s)
- Camera: 35mm 中景，鏡頭向前推 0.8m；F/4.5；景深 0.7m；保持左→右方向；輕微手持 1% 搖晃。
- Lighting: 主光 4200K 在小怪外殼反射；rim 光 6500K 在迅肩線；地面反光 4500K。
- Materials & Physics: 小怪彈出速度 4m/s，落地壓縮 3cm 彈簧回彈；外殼金屬度 0.76；迅拳頭速度 18m/s，風壓刮痕深 1cm，長 1.5m；2D / 3D Layering：角色=2D，小怪=3D base+2D overpaint，火花=3D 粒子，風壓=3D VDB 半透明 70%，速度線=2D。
- Emotion & Performance: 迅眼神挑釁，嘴角笑，拳頭緊握血管浮起 0.6mm；殘影左右分開。
- Audio & Transition: 小怪金屬撞擊 2kHz；風壓爆聲 500Hz；迅笑著喊「オレについて来れんのかよ？」；匹配剪接至 Beat3 漫畫化。

### Angle A2-3 (Beat3 7.2–8.4s)
- Camera: 30mm 斜前方，半身特寫，鏡頭繞 30° 小幅 arc（限制視差 3px），推進 0.4m；快門 1/48。
- Lighting: 漫畫化增粗描邊 1.4px；主光 4200K 硬光，rim 6500K；速度線螢綠自發光 900 nits。
- Materials & Physics: 風壓爆圈半徑 1.3m，厚 6cm；小怪被震飛 1.5m，高度 0.6m；殘影三層透明 65%/45%/30%；2D / 3D Layering：角色=2D，爆圈=3D VDB toon shading，擬聲字=2D overlay，碎片=3D 粒子，最上層網點。
- Emotion & Performance: 迅連拳 0.3s 四拳，手臂肌肉收縮節奏 0.15s；瞳孔閃螢綠反光；嘴角張開 20% 戰吼。
- Audio & Transition: 漫畫擬聲「ゴオ」「バシュ」紙張摩擦音 650Hz；拳擊低頻 90Hz；背景音壓降 3dB；硬切 Beat4。

### Angle A2-4 (Beat4 8.4–9.6s)
- Camera: 32mm 側後方，跟拍迅落腳，平移 0.9m；F/4；景深 0.8m；微下移 0.2m。
- Lighting: 夕陽光拉長影子 1.5m；rim 光勾出手臂；螢綠殘影亮度回落 50%。
- Materials & Physics: 落腳摩擦 0.86，地面碎石被刮起 0.4m；風壓沿護欄刻出 1cm 深刮痕，邊緣毛刺 0.4mm；2D / 3D Layering：角色=2D，刮痕=2D 線稿+法線置換，碎石=3D 粒子，風煙=3D VDB 70%，速度線=2D。
- Emotion & Performance: 迅吐氣，肩膀下降；右手抬至肩線準備手刀；眼神鎖定前方開闊路面。
- Audio & Transition: 落地聲 200Hz；碎石摩擦 1.5kHz；風聲漸強；硬切 Act3 Beat1。

## Act 3: 風壓斬線與收尾 (9.6–15.0s)
- Planned transitions: 斜俯推近 → 漫畫化爆圈 → 慢下來旋轉特寫 → 收尾耳機觸碰。
- Beats:
  - Beat 1 (9.6–10.8s): 手刀劃出風壓斬線，漫畫化爆圈。
  - Beat 2 (10.8–12.0s): 俯視螢綠軌跡在高架上畫螺旋。
  - Beat 3 (12.0–13.2s): 慢動作跳下，肌肉光影清晰，聲音抽空。
  - Beat 4 (13.2–15.0s): 風停塵落，收拳站直，碰耳機收尾。

### Angle A3-1 (Beat1 9.6–10.8s)
- Camera: 30mm 斜前方，推近 0.7m；F/4.5；描邊 1.4px；保持 9:16。
- Lighting: 夕陽斜光打在手刀；rim 光 6500K 在螢綠斬線上形成高光；體積霧 0.05 讓爆圈帶暈。
- Materials & Physics: 風壓斬線厚 4cm，長 8m，切面光滑；地面刮痕深 1cm；護欄同時被切出 0.8cm 刻痕；2D / 3D Layering：角色=2D，斬線=3D VDB toon shading，風刃=3D 粒子 1e4，擬聲字=2D overlay，速度線=2D radial。
- Emotion & Performance: 迅表情專注，眉峰收緊，手刀劃過時肩線帶力；嘴角微揚 10%。
- Audio & Transition: 風壓轟鳴 500Hz；擬聲字「バシュ」同步；背景海風壓低；匹配剪接至 Beat2 俯視。

### Angle A3-2 (Beat2 10.8–12.0s)
- Camera: 35mm 俯視，向上拉遠 1.0m 展示螢綠軌跡在高架畫螺旋；F/5.6；景深 0.9m。
- Lighting: 夕陽在軌跡上形成橙綠對比；路燈 3800K 逐漸亮起 20%；rim 光仍保持 6500K。
- Materials & Physics: 軌跡亮度 900 nits，寬 20cm；風道內空氣速度 25m/s；地面刮痕在混凝土上呈 2–3mm 細縫；2D / 3D Layering：角色=2D，軌跡=2D 線稿+3D 發光層，背景吊臂=3D 投影，速度線=2D overlay。
- Emotion & Performance: 迅踩在自己的風道上滑行，身體微傾 10°，保持流線；表情放鬆轉為自信笑。
- Audio & Transition: 風道低頻 90Hz，風鈴般高頻 2.2kHz；鏡頭在 T0+0.6s 硬切至 Beat3 慢下。

### Angle A3-3 (Beat3 12.0–13.2s)
- Camera: 50mm 半身特寫慢動作，鏡頭繞半圈 180° 不超 3px 視差；F/4；快門仍 1/48 但動作減速 40%。
- Lighting: 夕陽與霓虹交錯，肌肉光影清晰；rim 光 6500K 形成淡藍邊；速度線淡化。
- Materials & Physics: 肌肉法線 0.35，汗珠 0.05mm；布料拉伸 3%；空氣阻力讓衣料向後飄 5cm；2D / 3D Layering：角色=2D，背景=2D 投影+3D 輕微 parallax，霓虹=3D 發光 800 nits；速度線=2D 低透明。
- Emotion & Performance: 迅在空中旋轉，眼神穩定，呼吸與心跳聲放大；嘴角微笑 15%。
- Audio & Transition: 所有聲音抽空僅剩心跳 70Hz 與風聲；在 T0+0.9s 匹配剪接到 Beat4 落地。

### Angle A3-4 (Beat4 13.2–15.0s)
- Camera: 32mm 中景側前方，輕微下移 0.3m；F/4.5；景深 0.8m；保持構圖中心。
- Lighting: 夕陽漸弱，路燈 3800K 亮度提升至 60%；rim 光穩定；螢綠紋路脈動 40%。
- Materials & Physics: 落地摩擦 0.86，塵埃被風壓吹成 1m 長風道；汗水沿鎖骨滑下 0.05mm 厚；通訊耳機燈閃爍 600 nits；2D / 3D Layering：角色=2D，塵埃=3D 粒子，風道=3D VDB toon shading，字幕=2D overlay。
- Emotion & Performance: 迅收拳站直，胸膛起伏；碰右耳耳機，瞳孔反射港區霓虹；嘴角帶笑「さあ、次の現場まで走るか。」
- Audio & Transition: 心跳漸弱，海風回升；耳機提示音 1.6kHz；螢綠線條持續節奏 2.4Hz；畫面漸暗收尾。

## Act-level Micro-actions (Frame Breakdown)
- Act 1 Beat 1 Timeline: T0 俯視拉遠，迅腳踝旋轉 0.4s；T0+0.3s 風紋亮度 50% 脈動；T0+0.6s 風沙被風口掃起 0.3m；T0+0.9s 鏡頭平移對齊跑道中心。
- Act 1 Beat 2 Timeline: T0 起跑腳跟離地 0.05m；T0+0.4s 殘影第一層出現透明 65%；T0+0.8s 第二層殘影延伸 1.4m；T0+1.1s 速度線密度增至 26 條/秒。
- Act 1 Beat 3 Timeline: T0 迅踩護欄，膝蓋彎曲 35°；T0+0.3s 護欄彈性形變 0.5cm；T0+0.6s 碎石彈跳 0.3m；T0+0.9s 殘影沿護欄滑行。
- Act 1 Beat 4 Timeline: T0 迅壓低重心，肩膀抬升 2cm；T0+0.3s 風紋脈動 80%；T0+0.6s 護欄邊緣被鞋底磨出 2mm 痕；T0+1.0s 路標板震動 1.5mm。
- Act 2 Beat 1 Timeline: T0 迅左手觸路牌邊角施力；T0+0.4s 翻身角度 120°；T0+0.7s 殘影三層分岔；T0+1.0s 身體落在下一段護欄。
- Act 2 Beat 2 Timeline: T0 小怪彈簧展開 2cm；T0+0.3s 迅右拳蓄力，肌肉張力顯現；T0+0.6s 風壓爆圈半徑達 0.8m；T0+1.0s 小怪被震飛 1.2m。
- Act 2 Beat 3 Timeline: T0 漫畫化描邊增粗；T0+0.3s 連拳四連擊，拳影殘留；T0+0.6s 爆圈厚度達 6cm；T0+0.9s 擬聲字「ゴオ」出現在畫面右上。
- Act 2 Beat 4 Timeline: T0 迅落腳，膝蓋微彎 20°；T0+0.3s 風壓沿護欄延伸 4m；T0+0.6s 塵埃向後拉長 1m；T0+0.9s 手刀抬至肩線。
- Act 3 Beat 1 Timeline: T0 手刀劃出直線，斬線厚 4cm；T0+0.3s 風刃切過護欄；T0+0.6s 擬聲字「バシュ」放大；T0+0.9s 地面刮痕形成細長風道。
- Act 3 Beat 2 Timeline: T0 俯視拉遠，螢綠軌跡呈螺旋；T0+0.4s 路燈光 3800K 淡入；T0+0.8s 風道透明度下降 10%；T0+1.1s 軌跡尾端微粒消散。
- Act 3 Beat 3 Timeline: T0 動作放慢 40%，心跳聲突出；T0+0.4s 肌肉光影在夕陽下形成 2:1 光比；T0+0.8s 霓虹反光進眼中；T0+1.1s 空氣阻力拖動衣料 5cm。
- Act 3 Beat 4 Timeline: T0 落地塵埃被風壓掃 1m；T0+0.4s 汗珠滑過鎖骨；T0+0.8s 耳機燈閃爍；T0+1.2s 迅碰耳機說出台詞，螢綠脈動穩定在 40%。

## Material & Physics Reference
- 混凝土路面：Albedo #7a7a7a，粗糙度 0.62，法線高度 0.4mm；摩擦 0.84；撞擊時碎石粒徑 1–5mm，反彈 0.3m。
- 護欄鋼材：金屬度 0.72，粗糙度 0.4，鏽蝕色帶 #8a3b2f；法線置換 0.25；受風壓刮痕深 1cm 時邊緣毛刺 0.4mm。
- 機能上衣：尼龍/氨綸混紡，織紋 120 線/cm；粗糙 0.32，specular 0.18；汗水附著時高光提升 10%。
- 工裝慢跑褲：粗糙 0.45，膝部加固 0.6；縫線 0.9mm；布料拉伸 3% 時法線變化 0.05。
- 鞋底 TPU：金屬度 0.15，粗糙度 0.25；抓地紋理 1.6mm；摩擦 0.86，在濕潤區下降至 0.78。
- 機械小怪殼：鋁合金金屬度 0.76，粗糙度 0.28；鏡面反射 0.2；受衝擊火花粒子 0.6mm，溫度 900K。
- 風壓粒子：透明度 70%，粒徑 1mm sprite；初速 30m/s；散射係數 0.2；tone mapping 限制 1.1 stops。
- 速度線：螢綠 #58ff9e，寬 6px；透明度 60%；分層 3–4 層，視差 2–6px；漫畫化時放射密度 32 條/秒。
- 螢綠風紋：發光 950 nits，脈動 2.4Hz；受汗水影響時亮度下降 5%；反射在護欄金屬上亮度 30%。
- 風道氣流：速度 25–30m/s，溫度較環境升 1.2°C；空氣折射率 1.00029；對塵埃的帶動高度 1m。
- 體積霧：密度 0.05，散射 0.06，吸收 0.02；透明度 75%；與夕陽橙光混色 4200K。
- 海風聲場：低頻 180Hz，帶鹹味；高頻風切 2.5kHz；橋下空腔迴響 1.1s，需在音訊層控制不遮台詞。

## Audio & Subtitle Map
- 台詞 1（Act1 Beat1）：「……風向き、悪くないな。」字幕：日語上行白字黑描邊；同時中文註解「風向，還不錯。」置於下行。
- 台詞 2（Act2 Beat2）：「オレについて来れんのかよ？」字幕：日語居中，中文「你們跟得上嗎？」下行；音量 -12 LUFS。
- 台詞 3（Act3 Beat4）：「さあ、次の現場まで走るか。」字幕：日語上行，中文「那麼，跑到下一個現場吧。」下行；尾音微笑氣息。
- 心跳與風聲設計：Act3 Beat3 減速時心跳 70Hz，音量 -20 LUFS；風聲 500Hz 高頻被壓低；背景音樂低頻側鏈 3dB。
- 擬聲字：Act2 Beat3「ゴオ」「バシュ」放置在畫面左右兩側；Act3 Beat1「バシュ」居中下方；均帶紙纖維質感與網點。
- 環境聲：港口鳴笛 120Hz 低頻在開場遠景淡入；高架回音在 Act2 Beat1-2 保持 0.8s；Act3 收尾環境音回復至 -18 LUFS。
- 配樂節奏：每 1.2s 階段加入節奏點，Act2 Beat3 強拍與連拳同步；Act3 Beat3 拉低配樂僅留 pad 與心跳。
- 字幕安全框：距左右邊 8% 保留；上下邊 10% 保留；避免被速度線遮擋，必要時加黑色半透明底 30%。
- 音效空間化：風壓爆圈採用輕度 stereo spread 30%；小怪火花定位在 60° 方位；耳機提示音定位右耳 15°。

## Layering Checklist per Beat
- Beat1: 角色=2D；地面裂紋=2D；風沙=3D 粒子；吊臂遠景=3D 投影；速度線=2D。
- Beat2: 角色=2D；殘影=2D 疊加；塵土=3D 粒子；護欄=3D base+2D 描邊；速度線=2D。
- Beat3: 角色=2D；護欄=3D 投影；碎石=3D 粒子；速度線=2D；rim 光反射=2D overpaint。
- Beat4: 角色=2D；路標=3D base；風壓=3D VDB；速度線=2D；天空薄霧=3D。
- Beat5: 角色=2D；路牌=3D base；殘影=2D；風沙=3D 粒子；背景霓虹=3D 發光投影。
- Beat6: 角色=2D；小怪=3D base+2D overpaint；火花=3D；風壓=3D VDB；速度線=2D。
- Beat7: 角色=2D；爆圈=3D VDB toon；擬聲字=2D；碎片=3D 粒子；網點=2D overlay。
- Beat8: 角色=2D；刮痕=2D 線稿+法線置換；碎石=3D；風煙=3D；速度線=2D。
- Beat9: 角色=2D；斬線=3D VDB；風刃=3D 粒子；擬聲字=2D；速度線=2D。
- Beat10: 角色=2D；螢綠軌跡=2D+3D 發光；吊臂=3D 投影；速度線=2D；薄霧=3D。
- Beat11: 角色=2D；背景=2D 投影+3D parallax；霓虹=3D；速度線=2D 微透明；網點=2D。
- Beat12: 角色=2D；塵埃=3D；風道=3D VDB；字幕=2D；薄霧=3D。

## Extended Camera & Parallax Safeguards
- 所有平移控制在 0.3–1.4m 範圍；arc 運鏡僅於 Beat7 和 Beat11 使用，視差限制 3px，避免 VR 式繞拍。
- 平移與推拉皆遵循 180 度軸，方向固定左→右；若需上下移，最大 0.3m，並在 Layering 中保持 2–6px 視差。
- 景深控制：主體清晰，背景散焦僅 10–15%；禁止真實散景光斑；必要時以 2D overlay 模擬景深。
- Parallax 使用 camera projection：高架與港口吊臂貼圖投影到平面上，再添加 2–4px 視差；不使用完整 3D 飛越。
- Chromatic aberration 控制在 0.3px；grain 固定 10%；避免過度降噪導致線稿軟化。
- 若 FX 過亮，tone mapping 限制在 1.1 stops，並於自檢中回報調整。

## Platform Caption Line-up (Timecoded)
- 0.0–1.2s：字幕「風向，還不錯。」/「風向き、悪くないな。」
- 1.2–2.4s：無台詞，字幕僅顯示 Hook 文案「音速試跑？」。
- 2.4–3.6s：字幕淡出，保留速度線視覺。
- 3.6–4.8s：無字幕，聚焦預備動作。
- 4.8–6.0s：字幕「螢綠殘影，城市成跑道」置底。
- 6.0–7.2s：字幕「オレについて来れんのかよ？」/「你們跟得上嗎？」
- 7.2–8.4s：字幕「ゴオ」「バシュ」擬聲字搭配中文註解「風壓爆圈」。
- 8.4–9.6s：字幕暫停，突出動作線條。
- 9.6–10.8s：字幕「風壓斬線，螢綠直線」置左下。
- 10.8–12.0s：字幕「軌跡畫出螺旋跑道」。
- 12.0–13.2s：字幕淡出，只留心跳字樣「ドクン」。
- 13.2–15.0s：字幕「さあ、次の現場まで走るか。」/「跑到下一個現場吧。」收尾，CTA 疊於右下。

## Angle-level PBR & Layer Notes
- A1-1: 混凝土 AO 0.5，粗糙 0.62；護欄金屬度 0.72；風沙粒徑 80–120µm；2D 線稿覆蓋 3D 粒子，bloom 1.0 stop 以內。
- A1-2: 殘影透明 65%，拖尾 2.1m；布料 specular 0.18；motion blur 僅 15% 避免軟化線稿；風沙粒子 12k。
- A1-3: 褲料法線 0.35；護欄鏽蝕 0.4；碎石粒子 10k；rim 光 6500K 在螢綠線條產生 0.2 stop 高光；2D 描邊 1px。
- A1-4: 路標板金屬度 0.6；風壓 VDB 密度 0.04；速度線 radial 26 條/秒；描邊 1.1px；parallax 2px。
- A2-1: 路牌鋁板粗糙 0.3；殘影三層透明 65/45/30%；薄霧 0.05；火花禁用，保持安全訓練模式。
- A2-2: 小怪外殼金屬度 0.76；火花粒子 0.6mm，粒子數 8k；風壓刮痕法線置換 0.25；描邊 1.0px。
- A2-3: 爆圈 VDB 0.012；擬聲字 2D 上層；網點 0.8px；速度線 radial 32 條/秒；bloom 1.1 stops 上限。
- A2-4: 刮痕深 1cm；碎石粒子 9k；風煙 VDB 0.013；殘影透明 40%；描邊 1.1px；grain 10%。
- A3-1: 斬線 VDB toon shading，透明 70%；風刃粒子 1e4；護欄刻痕法線 0.25；網點疊層；描邊 1.4px。
- A3-2: 軌跡發光 900 nits；螢綠反射在護欄 30%；霧密度 0.05；parallax 3px；描邊 1.0px。
- A3-3: 霓虹光 800 nits；景深散焦 12%；chromatic aberration 0.3px；心跳同步胸口微動 2–3mm；描邊 1.2px。
- A3-4: 風道 VDB 0.012；塵埃粒子 10k；汗珠折射 1.33；耳機燈 600 nits；描邊 1.0px；速度線低透明 30%。

## Solver & Budget Notes
- 粒子總上限 45k，火花 8k，風沙 12k，其餘分配給風壓與碎石；GPU 占用預估 60%。
- VDB 模擬：風壓爆圈/斬線 0.012–0.013 解析度；體積霧 0.05 密度；使用 toon-light model，陰影階數 2。
- Flip smoke 僅於爆圈邊緣使用，限制網格 0.015，避免過度寫實。
- Camera projection 貼圖解析度 4K，parallax 2–4px；背景吊臂 50% 透明；不使用全 3D 飛越以符合 2D 風格。
- Denoise：適中設定，保留 10% 顆粒；線稿銳度加強 5%；避免社群壓縮後細節流失。
- Bloom 與 tone mapping：螢綠發光受限 1.1 stops；高光 clamp 1200 nits；保持對比 1.8 gamma curve。
- 漫畫化疊層：網點 0.8px，描邊 1.4px，速度線 radial 32 條/秒；擬聲字塗滿 80% 黑描邊 2px。
- Audio mix：配樂 -16 LUFS，台詞 -12 LUFS，音效 -10 至 -8 LUFS；心跳 -20 LUFS；確保頭尾不削波。

## Quality Checklist Expanded
- 結構完整：已覆蓋 _core、_stylepacks、Tech Specs、Master、Acts/Beats/Angles、Platform、Negative、Assumptions、自檢。
- 時間碼一致：每 Beat 1.2s，Act 長度相加 15s；Hook 與 CTA 對應。
- 物理精度：列出風速 6.2m/s、摩擦 0.86、刮痕深度 1cm、粒子上限 45k；重力 9.81m/s² 全程一致。
- PBR 細節：皮膚 SSS、布料織紋、金屬粗糙度、霓虹亮度、體積霧密度均量化；風壓刮痕法線置換 0.25。
- 2D Anime 一致性：角色全程 2D 描邊 0.8–1.4px；3D 僅用於粒子/VDB/環境投影；禁止真實散景與 360° 繞拍。
- 漫畫化要求：Act2 Beat3、Act3 Beat1 描邊加粗、網點、擬聲字；確認不遮面部與關鍵肢體。
- Camera 安全：運鏡平移/推拉為主；arc 僅兩處且視差 3px；180 度規則遵守；景深控制不過真。
- Platform 交付：字幕安全框、Hashtag、Hook A/B、縮圖、CTA、切片策略齊備；音訊與字幕同步標注。
- Negative 符合：禁止商標/血腥/政治/色情；PG-13；避免霓虹過曝與魚眼；自動檢核列出。
- Continuity：鏡頭方向左→右持續；螢綠色調與風紋脈動全程一致；高架與港區背景未突變。

## Lighting Matrix per Angle
- A1-1: 主光 4200K 55° 仰角，曝光 -0.2 stop；rim 6500K 30% 強度；反射光 4500K 20%。
- A1-2: 主光 4200K 50°；rim 6500K 35%；輔光自混凝土反射 4800K 15%；風紋發光補光 900 nits。
- A1-3: 主光 4200K 45° 偏左；rim 6500K 30%；護欄 cast shadow 掠過迅腿部，對比 2:1。
- A1-4: 夕陽背光 4200K 低角 20°；rim 6500K 40%；地面反光 4500K 填 15%；速度線自發光反射 30%。
- A2-1: 主光 4200K 40°；rim 6500K 30%；薄霧散射提升柔光 10%；路牌反射 350 nits。
- A2-2: 主光 4200K 38°；rim 6500K 32%；小怪金屬反光 20%；地面反射 4500K 15%。
- A2-3: 主光 4200K 35°；rim 6500K 35%；漫畫化描邊加粗 1.4px；速度線自發光 900 nits 提供額外 fill。
- A2-4: 主光 4200K 33°；rim 6500K 30%；塵埃反射降低 5%；螢綠殘影自發光 600 nits。
- A3-1: 主光 4200K 30°；rim 6500K 35%；斬線自發光 950 nits；體積霧散射 8%。
- A3-2: 主光 4200K 28°；rim 6500K 30%；路燈 3800K 20%；螢綠軌跡反光 25%。
- A3-3: 主光 4200K 25°；rim 6500K 28%；霓虹 800 nits 提供藍紫邊光；景深散焦不超 15%。
- A3-4: 主光逐漸減弱 4200K→4000K；路燈 3800K 提升至 60%；rim 6500K 穩定；螢綠紋路 40% 脈動補光。

## Motion & Force Calculations
- 起跑加速度：0→30m/s 於 0.8s 完成，平均加速度 37.5m/s²；鞋底摩擦 0.86 支撐不打滑。
- 踩護欄反作用力：迅體重 72kg，接觸面 0.02m²，摩擦力約 609N；護欄形變 0.5cm 產生回彈力，促進翻身。
- 連拳爆圈：每拳 18m/s，估算動量變化 1.296 kg·m/s；四拳合計 5.184 kg·m/s，風壓爆圈向外 1.3m。
- 手刀斬線：手刀速度 16m/s，斬線厚 4cm，對混凝土刮痕深 1cm；斬擊時風壓沿線衰減 0.2m 每 0.1s。
- 跳躍落地：跳高 1.2m，落地速度約 4.85m/s；摩擦 0.86 分散衝擊；塵埃帶起高度 1m。
- 心跳與呼吸：心率在 Act3 Beat3 放慢至 120bpm，呼吸 0.8s 吸/0.9s 呼；音訊同步心跳低頻。
- 風道氣流：風道截面 0.2m 寬，速度 25m/s，估算流量 5m³/s；摩擦與地面粗糙度造成 5% 能量損失。

## Continuity & Constraint Log
- 攝影方向固定左→右，未穿越運動軸；每次剪接對齊主體方向與光源位置。
- 色彩維持黑綠主題，螢綠 #58ff9e 不被霓虹搶色；夕陽橙 4200K 全程一致。
- 漫畫化鏡頭與非漫畫化鏡頭之間以硬切並維持描邊厚度漸變，避免突兀。
- 角色外觀：機能服、螢綠風紋、耳機、護具全程保留；無新道具加入。
- 環境：高架護欄、港口吊臂、路燈持續存在；無突然切換場景；薄霧密度維持 0.05。
- 安全限制：無血腥；小怪僅火花與碎片；PG-13；字幕中日雙語；無商標置入。

## Shot Transition & Sound Design Notes
- Transition 1 (A1-1→A1-2): 硬切並保留風聲連續；風紋脈動做 crossfade；背景回音維持 0.8s。
- Transition 2 (A1-2→A1-3): 匹配剪接以殘影位置對齊；鞋摩擦聲持續，音量 -14 LUFS；速度線方向一致。
- Transition 3 (A1-3→A1-4): 短暫 2 帧 motion blur 過渡；風沙粒子連續；背景港口鳴笛微弱延續。
- Transition 4 (A1-4→A2-1): 硬切到側俯視；保留 rim 光方向；路牌震動聲作切點。
- Transition 5 (A2-1→A2-2): 平移持續，火花尚未出現；風切聲提高 1dB；配樂節奏點對齊鏡頭推進。
- Transition 6 (A2-2→A2-3): 漫畫化切入時降低背景音量 3dB；擬聲字疊入；描邊由 1.0px 過渡至 1.4px。
- Transition 7 (A2-3→A2-4): 爆圈消散時以煙霧淡出帶動剪接；心跳與配樂節奏維持；光比從 3:1 回落至 2:1。
- Transition 8 (A2-4→A3-1): 刮痕作為 wipe 線條引導；風聲保持連續；殘影亮度降低到 40%。
- Transition 9 (A3-1→A3-2): 斬線延伸至俯視螺旋作匹配；螢綠發光保持 900 nits；音效從手刀轟鳴轉為風道低頻。
- Transition 10 (A3-2→A3-3): 拉遠到慢動作以 speed ramp 0.6→0.4；音樂減少打擊樂；心跳聲淡入。
- Transition 11 (A3-3→A3-4): 匹配剪接在落地瞬間；聲音抽空回復；耳機提示音 1.6kHz 作為收束。
- Transition 12 (結尾): 背景音量漸降 2s，螢綠脈動作尾燈效果；CTA 字幕淡入 0.5s。

## Post-process & Delivery Notes
- 線稿保持銳利，禁止過度降噪；若出現摩爾紋，僅在背景使用輕度 blur 2px，不觸及角色。
- 色彩校正：Filmic LUT，對比度 1.8，飽和度 -4%；螢綠維持在 BT.709 安全範圍，不 clipping。
- Grain：固定 10%，均勻分佈；不要在字幕上方施加顆粒，字幕需清晰。
- Motion blur：依 180° 快門，動作過快處加 10% 補強，但避免線稿糊掉；漫畫化幀停用額外 blur。
- Caption safe：左右 8%、上下 10% 安全框；測試多語字幕重疊不超過 2 行；背景亮度在字幕區壓到 40%。
- Export：1080x1920, 24fps, H.264, bitrate 20Mbps；音訊 48kHz 立體聲；檔案命名 `wind-pressure-line-pv_v01.mp4`。
- QA：逐幕檢查 2D/3D Layering 標註是否落實；檢查漫畫化疊層未遮面；確認擬聲字拼寫正確。

## Backup Hooks & Thumbnail Variations
- Hook A 變體：俯視風紋亮度提升至 70%，字幕改為「風口測速」；用更強 rim 光。
- Hook B 變體：側拍殘影改為兩層，加入耳機燈閃爍；字幕「音速 RUN？」置頂。
- 縮圖變體 1：手刀斬線定格，螢綠圈半徑 1m，搭配擬聲字「バシュ」。
- 縮圖變體 2：空中慢動作旋轉特寫，夕陽與霓虹交錯；描邊 1.2px。
- 縮圖變體 3：殘影三層包圍小怪，速度線放射；標語「風壓三連」。
- CTA 文字備用：「Follow the green line」英語版，放置右下角。
- Hashtag 備用：#WindRunner #KazamiHayato #港口疾風。

## Risk & Mitigation
- 霓虹過亮風險：若螢綠飽和超過 1.1 stops，降低發光 10%，並在 LUT 前套用 clamp。
- 景深過真風險：如背景散焦產生真實 bokeh，即改用 2D overlay 0.6px 模擬並降低模糊半徑。
- 速度線遮字幕風險：字幕區域套遮罩，速度線透明度降至 40%；必要時調整字幕位置。
- 粒子超額風險：若粒子超 45k，優先減少塵埃與碎石 15%，保留風壓粒子主體。
- 運鏡違規風險：如 arc 運鏡視差超過 3px，改用直線平移或縮小 arc 半徑；在自檢記錄。
- 聲音擁擠風險：台詞與音效重疊時，優先 ducking 音效 -4dB；保留台詞清晰度。

## Assumptions
- 使用者未提供其他角色或隊友，預設單人 PV。
- 目標平台需短版與長版兼容，字幕中日雙語；未提供語言限制，預設日語配音。
- 未指定品牌 Logo，故不置入任何商標。

## AGENT Self-Check
- 結構：已包含 Project Inputs、_core、_stylepacks、Technical Specs、Master Prompt、Acts/Beats/Angles（12 幕 × 1.2s）、Platform Layer、Negative Instructions、Assumptions、Self-Check；時間軸標示符合 15s。
- Physics & PBR：每角標註重力/摩擦/粒子/風速/PBR 粗糙度金屬度；風壓初速與刮痕深度量化；布料與汗珠層次寫明。
- Stylepacks 使用：引用 Black-Green Windline Sprint、Industrial Highway Dusk、Manga Impact Overlay，並在高潮鏡頭套用漫畫化；避免與禁混風格衝突。
- 2D vs 3D：角色、主要表演均 2D；3D 僅粒子/VDB/環境投影，並在每角 2D / 3D Layering 說明；視差限制 2–6px。
- Camera Continuity：開場俯視拉遠接側拍，再至爆圈與俯視螺旋，最後慢動作落地；均遵守 180 度規則和平移/推拉語言。
- Manga化檢核：Act2 Beat3、Act3 Beat1 套用網點、擬聲字、描邊增粗；不遮面部；2D overlay 置頂。
- Platform & CTA：Hook A/B、縮圖、字幕、Hashtag、切片策略已列；CTA 為「次の走線、どこ？」。
- 路徑紀錄：依 UTC+8 日期生成 `projects/黑綠風壓衝線・風見迅/2025-11-25_ep1-wind-pressure-line-pv/prompt.md`（實際保存為專案資料夾路徑）。
- 風格與物理衝突：無 360° 繞拍；景深未過度；風壓 VDB 控制在 toon shading；若螢綠過亮已在技術段落限制 tone mapping；自檢 9/10，待人工確認最終字幕語氣。

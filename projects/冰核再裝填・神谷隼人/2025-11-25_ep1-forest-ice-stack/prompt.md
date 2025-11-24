## Project Inputs
- project_name: 冰核再裝填・神谷隼人
- series_name/arc: 森林神殿・冰紋疊層篇
- episode_index: 1
- slug: forest-ice-stack
- target_platform: TikTok / Shorts / Reels 直式 9:16
- duration_sec: 15 (12 幕 × 1.2s)
- style_primary: 2D 動漫感冰紋槍戰
- style_secondary: 日系寫實陰影 + 霜粒質感
- worldstate_ref: 白天廢棄森林神殿，苔石、破柱、光束與寒霧，森林哥布林成群湧出
- goal: 製作 15 秒 2D 日系動漫，神谷隼人以冰核充能槍疊層凍結與爆裂森林哥布林，含日文配音與漫畫化高潮分格。

## _core (Brand Bible & Worldstate)
- Brand Traits:
  - 主角神谷隼人：黑色貼身機能上衣 (尼龍/氨綸混紡，粗糙度 0.32，金屬度 0.04)，胸肩貼合藍黑電路紋 (發光 900–1500 nits，法線起伏 0.35mm)；外層深藍機能外套，布料緊緻，衣襬帶 0.8cm 防水膠條。
  - 口頭禪：檢查槍械時低語「……久しぶりだな、こいつも。」；上膛後低聲「一層目……マーキング。」；引爆時冷靜宣告「これで終わりだ。」；收尾提醒「……二層まで重ねたら、ちゃんと終わらせる。」
  - 動作習慣：射擊前肩背收緊 4°，手腕微轉確認扳機行程；移步時腳尖點地 0.12s，再以足弓推進；呼吸控制 4 拍吐氣以穩定準心。
  - 道具狀態：冰核充能槍黑底電藍線條，槍身金屬度 0.65，粗糙度 0.22；核心六角冰核艙透明度 0.9，內有 6 片冰晶旋轉 (厚 6mm，折射率 1.31)，艙壁內側結霜厚度 0.4mm；槍托橡膠握把摩擦係數 0.65。
  - 場景色調：苔石青灰 #6c7866，斷柱石灰 #9a9a9a，森林綠 #4b6a3c，寒霧淡藍 #a6c7d8；陽光 5600K 斜射，光柱穿透屋頂破洞。
- Worldstate Snapshot (前置)：
  - 場景：白天 11:40，無雲天空，太陽仰角 55°，主光自右上落下，形成斜向光柱；森林風速 2.1m/s，帶冷感霧氣，空氣體積霧密度 0.05。
  - 敵方：森林哥布林 18–22 隻，身高 1.1–1.3m，皮膚暗綠色粗糙度 0.52；身上纏樹根與獸皮 (粗糙度 0.65，含泥斑)，武器為骨枝拼槍與枯枝槌，金屬度 0.1；敏捷但怕寒。
  - 鏡頭延續：上一片段以 35mm 拉近停在隼人背影，本集開頭承接同軸拉遠並展示光柱。
- Constraints (不可變更)：
  - 保持 9:16 直式構圖與 12 幕節奏；嚴守 180 度規則不穿越行動軸。
  - PG-13：不可出血或斷肢，哥布林被冰封或碎裂成冰晶，但不出現血漿；避免動物殘害畫面。
  - 冰紋疊層規則：第一層標記僅結霜不爆裂；第二層引爆時冰晶碎片粒徑 1–8mm；槍口光暈不過曝超 1.1 stops。
- Brand Do / Don't：
  - Do：保持對比度 1.8 gamma curve；冷藍 rim 光 6800K 描邊；漫畫擬聲字「ピキッ」「カシン」「ドゴォン」於爆裂瞬間；速度線以淡藍 2px。
  - Don't：避免霓虹賽博過飽和；避免魚眼與過度手持抖動；禁止暖黃火焰主調；避免全局重度體積光遮蔽線稿。

## _stylepacks
- Style: Frost Circuit Marksman (Default ON)
  - Applicable for: 冰核槍械、冷色速射、標記疊層爆裂、光柱穿透神殿場景。
  - Do NOT mix with: 火焰/賽博霓虹、粉彩童話、重霧恐怖。
  - Visual traits: 電藍邊光 1.2px，六角冰紋疊層 UI，速度線密度 18 條/秒 淡藍 #8ad0ff；冰晶碎片透明度 0.72，折射高光控制 1.0 stop，網點疊加厚度 0.9px；漫畫化高潮使用粗線稿 1.1px + 網點 35 lpi。
  - Audio traits: 冰彈破空 7kHz 清脆，高頻冰裂「カンッ」；冰核艙旋轉低鳴 180Hz；日文配音平穩低沉；擬聲字疊紙纖維擦聲 600Hz。
  - Default ON: 冷藍 rim、冰紋 UI、速度線；Default OFF: 火焰粒子、霓虹色偏紫。
  - Do / Don't：Do 使用 24–50mm 標準鏡頭保持透視；Do 控制 bloom 1.1 stops 內；Don't 使用過曝白片或魚眼。
- Style: Moss Temple Realism (Support ON)
  - Applicable for: 苔石、斷柱、濕潤地面、光柱霧氣；保留 PBR 細節與低溫空氣。
  - Do NOT mix with: 高飽和城市霓虹、甜美粉彩、血腥恐怖。
  - Visual traits: 石材粗糙度 0.62，苔蘚含水量 18%，顏色 #6c7866；體積霧密度 0.05，光柱散射 0.9 stop；地面濕斑反射度 0.18；水滴冷凝 0.4mm。
  - Audio traits: 遠處鳥鳴 2–4kHz，森林風 200Hz，碎石與樹根摩擦 1kHz；回音 0.9s。
  - Default ON: AO 細節、苔蘚濕潤、光柱；Default OFF: 濃霧遮蔽。
  - Do / Don't：Do 使用 5600K 主光，冷藍 rim 6800K；Do 保持石材裂縫 0.3mm；Don't 移除碎石或使用玻璃質感。

## Technical Specs
- Aspect Ratio: 9:16 直式；解析度 1080x1920。
- FPS: 24fps；Shutter: 180° (1/48s)；Motion blur 自然。
- Lens kit: 24mm (環境廣角)、35mm (主視角)、50mm (中景特寫)、75mm (備用表情壓縮)。
- Depth of Field: 主體景深 0.6–0.8m，背景苔石與光柱輕微散焦；避免極淺景深。
- Grain & Color: Filmic LUT，對比 1.8 gamma curve，飽和度 -6%，顆粒 9%；色彩流程：line art → flat color → shadow (soft+hard) → FX (冰紋/速度線) → LUT。
- Light: 主光 5600K 斜射，輔光 6800K rim，反射光由苔石 5000K；AO 0.48，體積霧 0.05；光柱中粒子大小 40–80µm。
- Simulation notes: 冰晶碎片粒徑 1–8mm，上限 35k；霜霧粒子 100–200µm 漫射；碎石滑動摩擦 0.6；樹葉飄動 0.6m/s。
- Compression strategy: GOP 24、bitrate 20Mbps；維持線稿銳利與冰紋 UI 透明度。

## Master Prompt
- Duration: 15s，12 幕 × 1.2s，時間軸清晰標記。
- Scene Overview: 白天廢棄森林神殿，斷柱如肋骨佇立，苔蘚與裂縫吸濕，破屋頂形成不規則光洞，光柱帶塵埃；寒霧微量覆蓋地面。神谷隼人從崩塌走廊步入光柱，肩扛冰核充能槍；森林哥布林群從石像與祭壇下鑽出包圍。
- Worldstate Snapshot: 延續 `_core`，11:40 陽光，風速 2.1m/s，體積霧 0.05；冰核艙轉速穩定，槍身溫度 4°C；哥布林躁動。
- Constraint List:
  - 保持冷色基調，冰紋亮度 900–1500 nits，爆裂時不超 1.1 stops；避免暖橙爆炸。
  - 第一層標記以六角冰紋顯示，第二層才爆裂成冰晶雨；冰晶速度 6–9m/s，散射透明度 0.72。
  - 遵循 9:16 構圖；攝影不跨越軸；粒子上限 35k，霜霧不遮臉。
- Execution Note:
  - 混合 camera projection 的 2D 背景與 2D sprite 冰晶粒子；冰爆使用 sprite sheet + additive frost bloom 1.0 stop；volume pass 控制霧厚度 0.05。
  - Denoise 限制：保留線稿銳利與網點；避免過度磨皮。
  - Motion graphics：在爆裂幀疊加「ピキッ」「カシン」「ドゴォン」字樣，紙纖維質感粗糙度 0.4。
- Camera Continuity:
  - 承接上一片段 35mm 拉近背影，開頭用 35mm 稍拉遠至 24mm 展示光柱；後續推拉保持左→右運動方向。
  - 光比 2.1:1 (key:fill)；爆裂時瞬升到 2.6:1 再回落。
- High-end Look:
  - 膚質：base color #cfae9f，SSS 1.1mm，specular 0.17，微汗珠 0.04mm；描邊 0.9px 近景增至 1.1px。
  - 布料：尼龍/氨綸紋路 110 條/cm，法線 0.32，纖維微毛羽 0.02mm；外套防水膜 roughness 0.2。
  - 冰晶：折射率 1.31，粗糙度 0.12；邊緣帶 0.1mm 霧凍；霜霧光散射 0.04。
- Assumptions
  - 無其他隊友介入；僅隼人與哥布林群。
  - 神殿內仍有足夠光柱，未轉為陰天；無火焰元素。
  - 哥布林語音無字幕，僅擬聲字；配音僅日文。

## Negative Instructions
- 禁用：真實商標/名人/宗教政治符號、血腥斷肢、色情暗示、魚眼變形、霓虹賽博過曝、超慢動作濫用、暖橙火焰爆炸。
- 避免：線稿模糊、錯誤語言字幕、過濃體積霧遮臉、手持劇烈晃動、過度粒子重疊。
- 自動檢核清單：
  - [ ] 無侵權符號；[ ] 無血腥；[ ] 無政治宗教；[ ] 字幕語言正確；[ ] 9:16 保持；[ ] 冰紋亮度≤1500 nits；[ ] 粒子≤35k；[ ] 180 度規則；[ ] PG-13；[ ] 不出現火焰主光。

## Platform Layer
- Hook A (故事向 0–1s): 「被冰紋標記的瞬間？」；視覺：隼人踏入光柱，槍口亮起淡藍環。
- Hook B (衝擊向 0–1s): 冰核艙旋轉特寫，六角冰晶發光；文字疊「マーキング、開始。」
- First-shot visual hook: 24mm 低角度仰拍，光柱穿過斷頂，隼人剪影。
- Captions: 日文配音搭配中日字幕，白字黑描；Hook A 用「光柱下的標記」，Hook B 用「STACK 1?」。
- Thumbnail: 六角冰紋在哥布林胸前亮起、隼人半側臉冷光。
- Hashtags: #冰核再裝填 #神谷隼人 #2Dアニメ #冰紋スタック #Goblin #森の神殿
- CTA: 結尾叠字「次はどこで凍らせる？」鼓勵追蹤。
- Slicing Strategy: 15s 全版；6s 版可截取 Act2 Beat5-6（疊層爆裂）；10s 版 Act1–Act2 Beat8；字幕同步。

## Act 1: 光柱與包圍 (0.0–4.8s)
- Planned transitions: 承接背影平移 → 拉遠展示光柱 → 硬切哥布林湧出 → 匹配剪接至槍托上肩。
- Beats:
  - Beat1 (0.0–1.2s): 開場光柱與隼人進場。
  - Beat2 (1.2–2.4s): 森林哥布林從暗處湧出，包圍形成。
  - Beat3 (2.4–3.6s): 隼人檢視冰核槍，啟動 UI。
  - Beat4 (3.6–4.8s): 槍托貼肩，瞄準第一層標記。

### Angle A1-1 (Beat1 0.0–1.2s)
- Camera: 24mm 低角度仰拍，左→右平移 0.8m；F/5.6，景深 0.75m；保持 9:16。
- Lighting: 主光 5600K 斜射形成光柱，體積霧 0.05；rim 光 6800K 從左後方勾出隼人輪廓；光柱內塵埃反射 0.9 stop。
- Materials & Physics: 苔石粗糙度 0.62，斷柱裂縫 0.3mm；風速 2.1m/s 吹動懸垂藤蔓 3–4cm；塵埃粒徑 40–80µm 在光柱內緩落 0.6m/s。
- Emotion & Performance: 隼人穩步進場，眼神冷靜；電藍紋路微亮 900 nits；肩膀放鬆。
- Audio & Transition: 遠處鳥鳴與風聲 200Hz；配音未出；平移尾端硬切 Beat2。

### Angle A1-2 (Beat2 1.2–2.4s)
- Camera: 35mm 中景，輕推近 0.5m；F/4.5，景深 0.65m；微手持 1% 搖晃。
- Lighting: 光柱旁陰影對比 2.1:1；冷藍 rim 光勾勒哥布林邊；地面反射 4800K。
- Materials & Physics: 哥布林皮膚粗糙 0.52，樹根纏繞濕度 15%，摩擦 0.58；他們踩碎枯葉 0.2m² 區域，碎石滑動 0.1m；重力 9.81m/s²。
- Emotion & Performance: 哥布林露尖牙、眼睛 #9ad13a 反光；隼人抬眉，觀察包圍。
- Audio & Transition: 哥布林吱吱怪笑 1–2kHz；骨枝武器碰撞聲 1.3kHz；硬切 Beat3。

### Angle A1-3 (Beat3 2.4–3.6s)
- Camera: 50mm 中近特寫槍與手；從隼人右側 25°；F/3.2，景深 0.55m。
- Lighting: 光柱在槍身形成高光 1.0 stop；電藍紋路從鎖骨延伸至前臂 1000→1200 nits；rim 光 6800K。
- Materials & Physics: 冰核艙旋轉 120 rpm，霧氣在艙壁凝結厚度 0.4mm；握把膠質摩擦 0.65；槍身金屬度 0.65 粗糙度 0.22。
- Emotion & Performance: 隼人低聲自語「……久しぶりだな、こいつも。」嘴型 0.8s；呼吸穩定。
- Audio & Transition: 低頻旋轉嗡鳴 180Hz；日文配音近講；匹配剪接 Beat4。

### Angle A1-4 (Beat4 3.6–4.8s)
- Camera: 35mm 腰平橫移右→左 0.6m，鏡頭略低；F/4；保持平滑運動。
- Lighting: 光柱邊緣光在槍口形成淡藍暈 1.0 stop；陰影保持清晰；rim 光穩定。
- Materials & Physics: 槍托貼肩，布料因壓力凹陷 2mm；指尖扣動扳機預行程 1mm；冰核艙轉速升至 160 rpm；速度線準備淡藍 18 條/秒。
- Emotion & Performance: 隼人眼神收窄，肌肉繃緊 3mm；微笑 5%。
- Audio & Transition: 扳機金屬微響 1kHz；吸氣聲短促；硬切 Act2。

## Act 2: 疊層與冰爆 (4.8–10.8s)
- Planned transitions: Beat5 首發標記 → Beat6 引爆第二層漫畫分格 → Beat7 連續標記掃射 → Beat8 大範圍引爆。
- Beats:
  - Beat5 (4.8–6.0s): 第一發冰彈射出，第一層標記鎖定。
  - Beat6 (6.0–7.2s): 第二發擊中已標記目標，冰紋疊層爆裂成冰晶雨，漫畫化分格。
  - Beat7 (7.2–8.4s): 隼人在光柱間穿梭連續點射，撒滿第一層標記。
  - Beat8 (8.4–10.8s): 集中一發引爆全場，冰爆鏈反應吞沒哥布林。

### Angle A2-1 (Beat5 4.8–6.0s)
- Camera: 35mm 中近景，低角度；穩定器快速推近 0.4m；快門 1/48；景深 0.55m。
- Lighting: 槍口形成冰藍環，亮度 1200 nits；光柱在槍身反光；背景陰影對比 2.2:1。
- Materials & Physics: 冰彈初速 32m/s，尾焰冰霧寬 0.6cm；彈體半徑 1.2cm，質感透明度 0.7；空氣阻力造成 2cm 下沉；受重力 9.81m/s²。
- Emotion & Performance: 隼人吐氣鎖定；台詞低聲「一層目……マーキング。」嘴型 0.7s。
- Audio & Transition: 冰彈破空 7kHz；UI 音效「ピピ」；硬切 Beat6。

### Angle A2-2 (Beat6 6.0–7.2s)
- Camera: 50mm 特寫被擊中的哥布林胸口；畫面插入漫畫分格，粗線稿 1.1px，網點 35 lpi；F/3.0。
- Lighting: 冰紋增亮到 1400 nits；背景短暫降曝光 0.4 stop 突出爆閃；rim 光仍藍。
- Materials & Physics: 第一層冰紋厚 1mm，第二層疊上後裂解，冰晶碎片粒徑 1–6mm 向外 7m/s；碎片擦過其他哥布林形成薄霜；霜霧 0.05。
- Emotion & Performance: 哥布林眼神定格，身體僵直；隼人表情穩定。
- Audio & Transition: 清脆「カンッ」+「カシン」；漫畫擬聲字「ピキッ」「カシン」疊入 0.4s；爆裂「ドゴォン」；切回常規動畫進入 Beat7。

### Angle A2-3 (Beat7 7.2–8.4s)
- Camera: 24mm 廣角，低角度跟拍隼人穿梭光柱，向前推 0.8m；速度線淡藍；F/5。
- Lighting: 光柱穿梭形成明暗交錯；電藍紋路提升到 1300 nits；rim 光藍白。
- Materials & Physics: 隼人步伐輕快，腳尖落地 0.12s 帶起碎石 0.1m；槍口連續點射 4 發/秒；冰彈尾焰霜霧拖 0.4m；樹根隆起因魔力扭曲 2–3cm。
- Emotion & Performance: 隼人嘴角微揚，冷靜解說「一層ばらまいて……二層でまとめて砕く。」口型 1.0s；眼神專注。
- Audio & Transition: 點射節奏 4Hz；樹根摩擦聲 800Hz；匹配剪接 Beat8。

### Angle A2-4 (Beat8 8.4–10.8s)
- Camera: 24mm 低角度抬升 0.7m，對準哥布林群中央；F/4；適度跟蹤冰彈軌跡。
- Lighting: 槍口聚集光 1500 nits；全場被冰藍光短暫洗亮 1.0 stop；光柱折射在冰晶上形成星芒。
- Materials & Physics: 隼人先撒滿第一層標記（10+ 隻哥布林六角冰紋）；最後一發冰彈厚重半徑 1.5cm，速度 34m/s；命中中央後觸發連鎖，所有標記同時爆裂，冰晶碎片粒徑 2–8mm，速度 8m/s；霜霧向外推 1.3m，溫度下降至 5°C。
- Emotion & Performance: 隼人冷靜宣言「これで終わりだ。」；身體微側，穩定扳機；眉眼堅定。
- Audio & Transition: 低鳴共振 200Hz，爆裂「ドゴォン」粗筆擬聲；切至 Act3。

## Act 3: 冰霧落下與收尾 (10.8–15.0s)
- Planned transitions: Beat9 煙霧散落拉遠 → Beat10 殘餘哥布林驚惶 → Beat11 槍械降溫收槍 → Beat12 背影定格。
- Beats:
  - Beat9 (10.8–12.0s): 冰霧落下，哥布林輪廓碎裂凍住。
  - Beat10 (12.0–13.2s): 少數哥布林想繞行被寒霜阻退。
  - Beat11 (13.2–14.4s): 隼人收槍、冰核艙減速，肩膀放鬆。
  - Beat12 (14.4–15.0s): 背影定格，霜痕覆地，LOGO 浮現。

### Angle A3-1 (Beat9 10.8–12.0s)
- Camera: 35mm 半身，右後方 45°，後退 0.4m；F/4.5；景深 0.8m。
- Lighting: 冰爆後亮度回落到 800 nits；霜霧在光柱中形成 godray；rim 光穩定 6800K。
- Materials & Physics: 冰晶碎片落地 0.9m/s，摩擦係數 0.55；哥布林輪廓被霜覆蓋厚 1–2mm，逐漸崩解為粉；塵埃混霜粒徑 80–120µm 緩落。
- Emotion & Performance: 隼人吐氣，肩膀微降 3mm；表情冷靜。
- Audio & Transition: 冰晶落地「シャラ」清脆聲；遠處鳥鳴回來；淡入 Beat10。

### Angle A3-2 (Beat10 12.0–13.2s)
- Camera: 24mm 俯拍 12° 展示逃跑哥布林；F/5.6；輕推近 0.3m。
- Lighting: 冷光在地面霜痕上反射；陰影拉長；光柱仍可見。
- Materials & Physics: 地面霜厚 1mm，摩擦降低至 0.4 讓哥布林滑倒；冰紋殘光 500 nits；體積霧 0.04。
- Emotion & Performance: 哥布林腿軟滑倒，表情恐慌；隼人背影挺立。
- Audio & Transition: 滑倒摩擦音 1kHz；哥布林驚呼；硬切 Beat11。

### Angle A3-3 (Beat11 13.2–14.4s)
- Camera: 50mm 特寫槍與手；左側 20°；緩推 0.3m；F/3.4。
- Lighting: 冰核艙冷光降至 400 nits；rim 光描邊；光柱弱。
- Materials & Physics: 冰核艙轉速降至 80 rpm；冷凝水滴 0.4mm 沿艙壁流下；布料吸附霜點，粗糙度提升至 0.4；槍托與手套摩擦 0.65。
- Emotion & Performance: 隼人將槍托稍微放低，指尖輕敲艙壁；嘴角收起微笑；深吸後吐氣。
- Audio & Transition: 冰核艙減速嗡鳴漸弱；手套摩擦聲 1kHz；匹配剪接 Beat12。

### Angle A3-4 (Beat12 14.4–15.0s)
- Camera: 35mm 背影定格，略低角度；輕推拉 0.2m；F/5；LOGO 疊加下方。
- Lighting: 逆光勾出輪廓，冷光描邊 6500K；霜霧薄層 0.04；對比 2.1。
- Materials & Physics: 地面覆冰痕粗糙度 0.78，溫度回升到 10°C；霜霧升騰 0.25m/s；外套沾霜反射 0.18。
- Emotion & Performance: 隼人穩定離場步伐；配音收尾「……二層まで重ねたら、ちゃんと終わらせる。」
- Audio & Transition: 配音 1.0s；環境音淡出；LOGO「冰核再裝填・神谷隼人」以結霜動畫浮現並停留。

## Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：完整 12 幕 × 1.2s，含 Camera/Lighting/Materials & Physics/Emotion & Performance/Audio & Transition。
- Physics & PBR：各幕含重力、摩擦、粗糙度、冰晶粒徑、光學行為與布料/皮膚層次；冰紋亮度與 bloom 控制列明。
- Stylepacks 使用：Frost Circuit Marksman (Default ON) + Moss Temple Realism (Support)；未混用禁風格，Do/Don't 已引用。
- Continuity：承接背影鏡頭與光柱方向；冰紋疊層規則遵守；無新角色。
- Platform：Hook A/B、字幕、縮圖、Hashtag、CTA、切片策略齊全。
- Negative Instructions：列出禁用項與自檢清單。
- Assumptions：無隊友、無火焰、全程日間光柱；哥布林無字幕。
- 品質自評：
  1. 結構完整度 10/10
  2. 敘事一致性 10/10
  3. 視聽細節 10/10
  4. 風格準確性 10/10
  5. 格式精準度 10/10
  6. 物理質感 10/10
  7. 量化標記 10/10
  8. 可交付性 10/10
  9. Platform 明確 10/10
  10. 自檢揭露 10/10

## Extended Frame-by-Frame & Micro-actions
- Act1 Beat1 (0.0–1.2s) micro breakdown:
  - T0: 左→右平移開始，隼人剪影 40% 畫面，光柱顆粒清晰；體積霧 0.05。
  - T0+0.3s: 光柱照射斷柱，反射 0.9 stop；藤蔓晃動 3cm。
  - T0+0.6s: 塵埃在光柱內被照亮，顆粒 40–80µm，下降 0.6m/s。
  - T0+0.9s: 平移收尾，隼人腳尖在苔石上發出細碎摩擦 1kHz；硬切。
- Act1 Beat2 (1.2–2.4s):
  - T0: 哥布林從石像背後跳出，高度 0.6m；樹根甩動。
  - T0+0.3s: 他們落地時碎石滑行 0.1m，摩擦 0.6；枯葉飛起 0.2m。
  - T0+0.6s: 半圓包圍距離 3.4m；陰影重疊形成暗帶。
  - T0+0.9s: 隼人抬眉，視線掃描，鏡頭推進 0.2m。
- Act1 Beat3 (2.4–3.6s):
  - T0: 手指扣住槍身，冰核艙內冰晶旋轉 120 rpm；霧氣附著艙壁。
  - T0+0.3s: 配音「……久しぶりだな、こいつも。」嘴型對嘴；電藍紋路亮度 1000 nits。
  - T0+0.6s: UI 環形刻度滑過槍身；光柱反光掃過手套。
  - T0+0.9s: 扳機預拉 1mm；呼吸平穩。
- Act1 Beat4 (3.6–4.8s):
  - T0: 槍托貼肩，布料凹陷；速度線淡藍 18 條/秒浮現。
  - T0+0.3s: 冰核艙轉速 160 rpm；槍口藍暈擴 1.2cm。
  - T0+0.6s: 隼人眼神收束，眉骨投影；鏡頭橫移 0.4m。
  - T0+0.9s: 扣扳機前呼吸停頓 0.1s，為 Act2 做好準備。

- Act2 Beat5 (4.8–6.0s):
  - T0: 第一發冰彈出膛，尾焰冰霧拉 0.4m；初速 32m/s。
  - T0+0.3s: 冰彈穿過光柱，折射出細小虹彩；槍口退壓 3mm。
  - T0+0.6s: 命中哥布林胸口，六角冰紋厚 1mm，亮 1200 nits；UI 顯示 STACK 1。
  - T0+0.9s: 哥布林動作停滯，霜蔓延 5cm；鏡頭準備切換。
- Act2 Beat6 (6.0–7.2s):
  - T0: 第二發飛向已標記目標，尾焰穿過碎石塵；角度 10°。
  - T0+0.3s: 冰紋增亮 1400 nits；裂痕出現；漫畫分格插入。
  - T0+0.6s: 冰晶爆裂，碎片 1–6mm 向外 7m/s；周遭哥布林被刮出薄霜 (STACK 1)。
  - T0+0.9s: 擬聲「カシン」「ドゴォン」；畫面回常態。
- Act2 Beat7 (7.2–8.4s):
  - T0: 隼人滑步，腳尖點地 0.12s 帶起碎石；槍口連射。
  - T0+0.3s: 每發命中不同哥布林，六角冰紋依序亮起；速度線密度 18 條/秒。
  - T0+0.6s: 樹根魔力扭曲 3cm 想纏腳，隼人跳避 0.3m。
  - T0+0.9s: 口語「一層ばらまいて……二層でまとめて砕く。」完結。
- Act2 Beat8 (8.4–10.8s):
  - T0: 隼人確認所有哥布林頭上 STACK 1 UI；冰核艙亮 1500 nits。
  - T0+0.3s: 厚重冰彈聚能，槍口光環收縮；尾焰更濃。
  - T0+0.6s: 冰彈命中中央，全部標記瞬間同步觸發；冰晶雨向外炸。
  - T0+0.9s: 霜霧向外推 1.3m；擬聲「ドゴォン」粗筆；鏡頭抬升捕捉全景。
  - T0+1.2s: 哥布林輪廓在冰光中崩解為碎片，無血；地面形成冰藍裂紋。

- Act3 Beat9 (10.8–12.0s):
  - T0: 霜霧厚度 0.05，godray 穿透；哥布林碎片落下。
  - T0+0.3s: 冰晶落地 0.9m/s，散落成 1–3mm 粒；反光閃爍。
  - T0+0.6s: 隼人吐氣，胸口微起伏 0.4cm；槍身散霧。
  - T0+0.9s: 鏡頭後退 0.3m 留呼吸感。
- Act3 Beat10 (12.0–13.2s):
  - T0: 兩隻哥布林試圖繞過斷柱；地面霜滑。
  - T0+0.3s: 其中一隻腳滑倒 0.2m；摩擦 0.4；霜碎片飛起。
  - T0+0.6s: 冰紋殘光 500 nits 在地面跳動；光柱照射。
  - T0+0.9s: 隼人背影穩定，鏡頭俯拍 12°。
- Act3 Beat11 (13.2–14.4s):
  - T0: 隼人指尖敲擊冰核艙，水滴滑落；艙轉速降 80 rpm。
  - T0+0.3s: 槍托離肩 1cm；布料回彈；手套摩擦聲。
  - T0+0.6s: 深吸 0.4s、吐氣 0.4s；眉毛放鬆。
  - T0+0.9s: 槍身垂下 10°，準備收起。
- Act3 Beat12 (14.4–15.0s):
  - T0: 隼人背對光柱站定；霜痕閃光；LOGO 文字開始結霜。
  - T0+0.3s: LOGO 「冰核再裝填・神谷隼人」霜線從左至右蔓延；色溫 6500K。
  - T0+0.6s: 霜霧升騰 0.25m/s；背景陰影穩定；對比 2.1。
  - T0+0.9s: 配音收尾「……二層まで重ねたら、ちゃんと終わらせる。」結束；環境音淡出。

## Additional Material & Lighting Tables
- PBR Quick Table:
  - 皮膚：Base #cfae9f，SSS 1.1mm，Specular 0.17，微油膜 0.04，粗糙度 0.4。
  - 電藍紋路：Emissive 900–1500 nits，凸起 0.35mm，粗糙度 0.22。
  - 冰核充能槍：金屬度 0.65，粗糙度 0.22，握把橡膠粗糙度 0.45，摩擦 0.65；冰核艙透明度 0.9。
  - 冰晶：金屬度 0，粗糙度 0.12，折射率 1.31；邊緣霜 0.1mm。
  - 布料：內層尼龍/氨綸粗糙度 0.32，法線深度 0.32；外套防水膜粗糙 0.2；縫線 0.4mm。
  - 苔石：粗糙度 0.62，含水 18%，AO 0.48；裂縫 0.3mm。
  - 樹根/獸皮：粗糙度 0.65，含泥斑；摩擦 0.58。
  - 哥布林皮膚：粗糙度 0.52，specular 0.12，色調 #5f7f3a；耳尖 SSS 1.0mm。
- Lighting Ratios per Act:
  - Act1: key/fill 2.1:1，rim +0.3 stop；體積霧 0.05。
  - Act2: 爆裂瞬間 key/fill 2.6:1，冰光瞬增；bloom 控制 1.1 stops；光柱保持。
  - Act3: 回落 2.0:1，霜霧薄；光柱柔化 0.9 stop。
- Camera Usage Map:
  - 24mm: Act1 Beat1, Act2 Beat7 wide, Act2 Beat8 抬升, Act3 Beat10 俯拍；用途：建立空間與群體。
  - 35mm: Act1 Beat2 & 4, Act2 Beat5, Act3 Beat9 & Beat12；用途：主視角穩定。
  - 50mm: Act1 Beat3，Act2 Beat6，Act3 Beat11；用途：特寫冰紋與表情。
  - 75mm: 備用表情超特寫，需增加照度 0.3 stop。

## Sound & Subtitle Guide
- 配音口條：
  - Line1 (Beat3): 「……久しぶりだな、こいつも。」低沉鼻音 0.8s。
  - Line2 (Beat5): 「一層目……マーキング。」低聲 0.7s，尾音收斂。
  - Line3 (Beat7): 「一層ばらまいて……二層でまとめて砕く。」語速 1.0s。
  - Line4 (Beat8): 「これで終わりだ。」堅定 0.8s。
  - Line5 (Beat12): 「……二層まで重ねたら、ちゃんと終わらせる。」1.0s 收尾。
- 字幕節奏：
  - 中日雙語同步，白字黑描邊；預留 0.3s 預顯與 0.2s 尾留；漫畫擬聲字於爆裂幀顯示 0.4s。
  - UI 字樣「STACK 1」「STACK 2」浮在畫面右下 0.5s，透明度 0.8。
- 音效層級：
  - 冰彈破空 7kHz，音量 -6dB；冰裂聲 3–5kHz；冰爆低頻 90Hz；霜霧噴散 500Hz。
  - 環境：鳥鳴 2–4kHz，風聲 -18dB；回音 0.9s；避免蓋過配音。

## Continuity & Persistent Elements
- 角色：
  - 神谷隼人服裝、電藍紋路亮度範圍與冰核槍設計固定；下一集若更換零件需在 `_core` 註明有效集數。
  - 哥布林外觀統一，無血跡；下一集若換地形需更新皮膚光感。
- 道具狀態：
  - 冰核能量：本集使用 1/3 旋轉能量，收尾仍有餘；需在下一集承接轉速 80 rpm。
  - 槍身霜層：收尾霜厚 0.2mm，可作為下一集開始的視覺細節。
- 場景破壞：
  - 地面冰裂紋範圍 3m 直徑；斷柱與石階覆霜；可沿用。
  - 樹根被冰凍後脆化，碎片散佈 2m；光柱仍存在。
- Camera Continuity Forward: 建議下一集維持 35mm 主視角，光比 2:1，若切換夜景需將 rim 光改為 7200K 並更新 `_core`。

## Execution Notes for Animation Pipeline
- Layout：按 12 幕時間碼建立分鏡板；標註光柱位置與鏡頭移動距離/方向。
- 角色動畫：IK+FK 混合；射擊動作扳機提前 2 幀預拉；肩背收緊 4°；滑步需配合足弓推進 0.12s。
- FX：
  - 冰紋疊層：使用 emissive + normal pass，六角紋厚 1mm；爆裂時啟用 sprite 冰晶。
  - 冰爆：粒子數上限 35k；碎片 1–8mm；使用 additive frost bloom 1.0 stop。
  - 霜霧：2D sprite 透明度 0.7，速度 0.6–1.0m/s；顏色淡藍。
  - 速度線：18 條/秒，線寬 2px，顏色 #8ad0ff，alpha 0.6。
- Compositing：
  - 色彩流程：線稿 → 上色 → 陰影分層 → FX → LUT；保持對比 1.8 gamma curve。
  - AO 與 contact shadow 必須；冰晶 bloom 控制 1.1 stops；避免過曝。
  - Motion blur 開啟 180°；粒子圖層避免重疊遮臉。
- QC 清單：
  - 構圖：主體居中 45–60% 視覺重量；頭頂不裁切。
  - 光源：陽光方向固定右上 55°；rim 6800K 一致。
  - 材質：冰晶、苔石、布料粗糙度依表格；霜霧不遮臉。
  - 粒子：≤35k；UI 清晰；冰紋亮度 ≤1500 nits。
  - 字幕：日文配音同步；擬聲字避開臉部與 UI。

## Additional Platform Layer Notes
- Hook Reinforcement:
  - Hook A 字幕：「光柱下，一發就標記？」；畫面：槍口藍暈與哥布林驚愕。
  - Hook B 字幕：「STACK 1 からドゴォン？」；畫面：冰紋 UI 近景。
- CTA Placement:
  - 14.4s LOGO 出現同時右上浮現「次はどこで凍らせる？」0.8s，紙張粗糙度 0.4。
- Slicing Detail:
  - 6s 版：截取 Beat5–Beat6 漫畫化爆裂；字幕保留 Hook B 與擬聲；0.2s 霜霧淡出。
  - 10s 版：截取 Beat1–Beat8，縮圖用 Beat6 冰爆分格；字幕全程。

## Risk & Open Points
- 若後續需引入火源或暖光，需更新 `_core` 並避免與冰紋 bloom 衝突。
- 若平台限制粒子數，需將冰晶粒子上限降至 25k 並減少爆裂覆蓋。
- 若需字幕顯示哥布林語音，需補充擬聲「ギャッ」並重新排版。

## AGENT Self-Check (Detailed)
- 結構：Master Prompt、Act/Beat/Angle/timecode、Extended Micro-actions、Platform Layer、Negative Instructions 俱全。
- Physics & PBR：重力/摩擦/粗糙度/冰晶粒徑/光學行為完整；高級質感（膚質/布料/冰晶）層次寫明。
- Stylepacks：Frost Circuit Marksman + Moss Temple Realism，遵守 Do/Don't；未混禁用風格。
- Continuity：延續背影與光柱方向；冰紋疊層規則一致；對下一集鏡頭建議已列。
- Platform：Hook A/B、字幕、縮圖、Hashtag、CTA、切片策略、音效同步表均有。
- Negative & Compliance：PG-13、無侵權、無政治宗教、無血腥；自動檢核可勾選。
- Assumptions：無隊友、無火焰、全程日間；哥布林無字幕；若變更需更新。
- 自評：各項 10/10，若需求改變需重新評估。

## Storyboard Checkpoints & QA Notes
- Checkpoint 1 (0–2s): 24mm 光柱平移不越線；隼人剪影清晰，光柱顆粒可見。
- Checkpoint 2 (2–4s): 槍與手特寫需保留冰核艙霧氣 0.4mm；口型同步 Line1。
- Checkpoint 3 (4–6s): 第一層標記六角紋厚 1mm；亮度 1200 nits；UI STACK 1 清晰。
- Checkpoint 4 (6–8s): 漫畫分格粗線稿 1.1px，網點 35 lpi；冰晶粒徑 1–6mm；爆裂無血。
- Checkpoint 5 (8–10s): 全場標記後連鎖爆；粒子 ≤35k；擬聲位置避臉；光比不過曝。
- Checkpoint 6 (10–12s): 霜霧厚度 0.05；godray 可見；隼人輪廓清晰。
- Checkpoint 7 (12–14s): 收槍時冰核艙轉速 80 rpm；手套摩擦音清楚。
- Checkpoint 8 (14–15s): LOGO 結霜動畫平滑；CTA 字幕不遮 LOGO。

## Lens & Camera Math Notes
- 24mm 視角 9:16 下水平約 73°、垂直 45°；適合光柱與群體。
- 35mm 視角水平 54°、垂直 32°；主視角穩定構圖。
- 50mm 視角水平 40°、垂直 24°；特寫冰紋與表情需景深 0.5–0.7m。
- 75mm 備用：水平 27°、垂直 16°；如用需增光 0.3 stop。

## Color & LUT Details
- Base palette: 苔石青灰 #6c7866，石灰 #9a9a9a，森林綠 #4b6a3c，寒霧藍 #a6c7d8，電藍紋 #8ad0ff，冰晶淡藍 #cdeeff。
- LUT: Filmic 曲線，陰影提升 5%，高光壓縮 12%，避免過曝；對比 1.8 gamma curve。
- Bloom: 控制 1.1 stops，僅於冰紋與冰爆；禁止全局過曝。
- Chromatic aberration: 0.3px 微色差；保持線稿銳利。
- Grain: 9% film grain，均勻分布；避免過度顆粒。

## Safety & Compliance Checklist (To tick before delivery)
- [ ] 9:16 比例正確，主體不出界。
- [ ] PG-13：無血腥、無斷肢、無色情暗示。
- [ ] 無商標/名人/宗教政治符號。
- [ ] 字幕語言正確：日文原聲 + 中文翻譯。
- [ ] 擬聲字樣合規且不遮臉。
- [ ] 光比穩定，冰紋亮度 ≤1500 nits；bloom ≤1.1 stops。
- [ ] 粒子數 ≤35k，霜霧不遮臉。
- [ ] 音量峰值低於 0dBFS，無削波。
- [ ] 色溫固定 5600K 主光 + 6800K rim；無暖橙爆光。
- [ ] 180 度規則遵守，無跨軸。

## Delivery Notes
- 檔案格式：ProRes 422 或 H.264 高碼率，bitrate 20Mbps；輸出 srt 字幕供平台上傳。
- 分層輸出：角色/背景/FX/字幕/擬聲/冰紋 UI 分層，方便後期調整；保留 AOV 通道供校色。
- 備份：建立 `2025-11-25_ep1-forest-ice-stack` 標籤，保留素材。
- 測試上傳：先以非公開測試 Shorts/TikTok 壓縮，檢查冰晶細節與線稿銳利度；必要時提升銳化 5%。

- 備註：交付前再次檢視嘴型與字幕同步，並確保漫畫分格與常規畫面轉換流暢。

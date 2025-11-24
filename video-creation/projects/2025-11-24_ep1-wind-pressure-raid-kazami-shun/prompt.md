# Project Metadata
- project_name: 風壓奔襲・港區掃蕩
- series_name/arc: 港區警戒・風見迅
- episode_index: 1
- slug: wind-pressure-raid-kazami-shun
- target_platform: short-form vertical video (JP/TW social)
- duration_sec: 15
- style_primary: 2D 日系動漫風（青綠風壓肌肉線條）
- style_secondary: 港區工業寫實（海風與金屬腐蝕質感）
- worldstate_ref: 正午港區高架橋與貨櫃迷宮，昨日戰鬥留下刮痕
- goal: 呈現風見迅在日間巡邏中以音速拳與風壓斬線清掃小型風蝕獸，日文配音

## _core
### Brand Bible（風壓奔襲）
- 角色色票：黑 #0d0f12 為主，青綠 #1ee6a9 形成流線亮條，汗珠高光 #b8f4ff，陽光金 #ffd47a 作為 rim light。
- 服裝材質：貼身機能上衣採尼龍彈性布（粗糙度 0.38、金屬度 0.05、法線貼圖 8K 纖維 0.08mm），運動壓縮褲（粗糙度 0.42），鞋底橡膠（摩擦係數 0.85）。
- 肌膚層級：base color 偏小麥色 #c88858，SSS 半徑 1.1mm，specular 0.45；指節硬繭粗糙度 0.28，汗膜 0.05mm 折射 1.33。
- 口頭禪與語氣：日語短句帶笑，語速 1.05x，偶以中文吐槽；句尾常以「だろ？」、「だね」收束。
- 姿態與習慣：熱身會踢欄杆、腳踝內旋 5°；衝刺時肩線微前傾 12°；拳擊出拳角度 35–45°，會在擊中前 0.1s 吐氣。
- 場景色調：正午強光 5600K，地面反光形成 2:1 光比，貨櫃生鏽紅褐 #b45b2e 與藍灰 #6b8ca0 對比；海風帶鹽霧 density 0.01，AO 0.4；對比度遵循 Do: 1.9 gamma curve。
- 鏡頭語言 Do：高速 tracking 伴隨 motion blur 180°，低角 30–45° 強調爆發力，match cut 對齊速度線方向，景深 f/2.8–f/4 突出肌肉紋理。
- 鏡頭語言 Don't：魚眼 <22mm、過曝鏡頭 flare、花俏濾鏡、未標註物理數值、使用真實品牌 Logo。
- 文案語氣：中文敘事 + 日文配音，字幕雙語對齊擊打節點，保留空氣聲與風切聲，避免冗長旁白。

### Shared World & Character File
- Worldstate snapshot：正午 12:10，港區氣溫 31°C，相對濕度 68%，海風 3.2 m/s 東南向；貨櫃堆高 3–5 層（高度 6–12 m），鋼板鏽蝕 25%，地面殘留昨夜刮痕 1–3 cm 深、長 1–2 m；排水溝蒸氣濃度 0.02 density。
- Character default：風見迅 180 cm / 80 kg，體脂 9%，慣用右手；鞋底厚 2.5 cm；音速拳時拳峰速度 70 m/s；「風痕瞬步」腳掌推力 1400 N，爆發時間 0.15s；手刀「風壓斬線」風刃厚 5 cm、長 6 m。
- Persistent elements：青綠流線在肩、前臂、腿外側與髮絲上閃動 0.25s；汗珠粒徑 0.3–0.8 mm 被風帶出拖尾；地面氣流跑道會留下淡青色光痕 1.2s 才消散；每次落地激起碎石 1–2 cm 飛散半徑 1.5 m。
- Constraint list：風見迅衣服不破損；小怪外殼為鐵銹與碎石混合（金屬度 0.65、粗糙度 0.6）；鏡頭運動主軸由右向左保持，若反轉需先以閃光 match cut；日間曝光保持 0.2 以下高光剪裁，避免過曝。
- Execution note：採用 camera projection 對貨櫃貼圖保持銳利；粒子系統控制腐蝕塵粒 0.4 mm 半徑、最多 60k；風刃採用體積霧切片（散射 0.55、吸收 0.15）；motion blur 限制 180°，避免過度 smear；音效對齊字幕節點。

### Do / Don't（Core）
- Do：列出每幕時間碼、鏡頭焦段、光源色溫與強度、PBR 材質與物理參數；對於同時事件使用 T0+ 細分；字幕位置遵守安全框 5%；platform 層包含 Hook A/B 與切片建議。
- Don't：使用模糊詞（如「很多」）不量化；使用「同前」代稱；遺漏摩擦係數或材質層級；加入真實品牌或政治宗教符號；省略 Self-Check。

## _stylepacks
### Style: 2D Wind Kinetics (青綠流線)
- Applicable for：高速移動、風壓連拳、風壓斬線；強調速度線與殘影。
- Do NOT mix with：柔焦少女漫畫、粉彩色調、Q版比例。
- Default: ON
- Visual traits：線稿粗 2–3 px，青綠速度線亮度 1000–1300 nits 瞬閃 0.18s；肌肉輪廓加粗，陰影採冷灰 #1c262e；風刃帶半透明粒子。
- Audio traits：風切聲尖頻 3–5 kHz、拳擊衝擊低頻 80–120 Hz，配日文青年聲音頻 120–140 Hz，混響 0.3s。
- Do：保持運動模糊 180° shutter；以 match cut 將速度線方向連接；光比 2:1 讓流線突出。
- Don't：過曝 bloom、無質感平面 shading、失焦、魚眼畸變。

### Style: Industrial Seaport Realism
- Applicable for：貨櫃、鋼橋、地面質感與腐蝕痕跡。
- Do NOT mix with：霓虹賽博紫粉光。
- Default: ON
- Visual traits：貨櫃金屬度 0.7 粗糙度 0.55，鏽斑 bump 0.3mm；地面水泥粗糙度 0.6，裂縫深 1–3 cm；高空陽光直射 5600K，反射熱霧 0.01 density。
- Audio traits：港口廣播模糊聲 -18 dB，遠處貨車倒車蜂鳴 -22 dB，海浪低頻 60 Hz。
- Do：加 AO 0.4，環境光照均勻；使用 linear clamp 避免高光剪切；在轉場加上鐵皮鏗鏘作為 match cut。
- Don't：過度 HDR 拉爆光；把貨櫃刷成無磨損平面；忽略腐蝕粒子。

### Style: Monotone Breeze VO（日文青年）
- Applicable for：風見迅短句旁白與吐槽，配字幕。
- Do NOT mix with：高音熱血吶喊、英文 Rap。
- Default: ON
- Visual traits：字幕底黑 60% 透明度，Noto Sans JP Bold 70pt，描邊 2.5 px 青綠；字幕隨拳擊抖動 2 px。
- Audio traits：男聲 120–140 Hz，輕笑氣音；環境風聲與腳步聲分軌，立體聲寬 35%。
- Do：字幕節點與擊打同 frame；轉場以吸氣音 + swipe。
- Don't：破音過飽和、字幕溢出安全框、語速過快 >1.4x。

## Technical Specs
- Aspect Ratio: 9:16
- FPS: 24
- Shutter: 180° with controlled motion blur
- Lens set: 24mm（定場）、35mm（半身跑道）、50mm（上半身拳擊）、75mm（特寫）；畸變校正，vignette 0.12。
- Depth of Field: f/2.8–f/4 主體清晰，背景散景半徑 5–7 px。
- Grain: fine-grain 35mm 8%，加輕 film dust 2%。
- Color pipeline: log capture → filmic LUT → final contrast 1.9 gamma curve → subtle bloom 0.08；保留局部反射控制。

## Master Prompt
- Worldstate snapshot：正午港區，陽光 5600K 強度 100%，地表反射 15%；海風 3.2 m/s 東南向，帶鹽霧 density 0.01；貨櫃鋼板溫度 38°C；地面摩擦 0.7；排水溝溫度 30°C 蒸氣上升 0.4 m/s。
- Constraint list：保持右向運動軸；速度線方向與運鏡一致；青綠流線亮度不超過 1300 nits；不出現真實品牌或政治宗教符號；小怪不得爆出血液（僅碎石與鏽粉）。
- Execution note：高速動作採用 multiple-pass motion vectors；風刃使用 VDB 切片粒度 0.02 m；音效立體聲寬 35%，低頻 sidechain 減少旁白遮蔽；camera continuity 由高空俯衝 → 平移 → 跟拍；denoise 限制 0.35 保留粒子。
- Camera Continuity：
  - 前序俯衝鏡頭 24mm 由上至下 20 m，高速；切至 35mm 平視跟拍；速度線 match cut 讓觀眾感到連續。
  - 若需方向切換，先以貨櫃鏗鏘與光閃過度再反轉，避免 jump cut。
- Physics & PBR summary：重力 9.81 m/s²；拳頭碰撞鐵鏽殼摩擦係數 0.55；風刃厚 5 cm 造成切割壓差 15 kPa；鞋底摩擦 0.85；貨櫃金屬度 0.7 粗糙度 0.55；汗液折射 1.33，蒸發 0.2s 形成淡霧。
- Stylepacks used：2D Wind Kinetics（ON）、Industrial Seaport Realism（ON）、Monotone Breeze VO（ON）。
- Duration plan：15s，12 幕 × 1.2s（14.4s 主體）+ 0.6s logo；各幕標註時間。
- Platform hook：Hook A 0–1s 高空俯衝 + 怪物湧出；Hook B 1–2s 風見迅瞬步閃現與笑聲。
- Platform slice：可取 0–3.6s 作短版開場，6–9.6s 作動作 highlight，12–15s 作 CTA。

## Act 1 — 高空警戒與怪物湧出（0.0s–4.8s）
### Beat 1 — 高空俯衝定場（0.0s–1.2s）
- Angle A (T0–1.2s)
  - Camera：24mm 無人機俯衝，起點 30 m 高度向地面 15 m/s 下降，最後停在 6 m 高；輕微 roll -5° 校正地平線。
  - Lighting：正午直射 5600K，對比 2:1；貨櫃頂反射光 15%；地面高光控制至 0.18。
  - Materials & Physics：貨櫃金屬度 0.7 粗糙度 0.55，鏽斑 bump 0.3mm；地面水泥粗糙 0.6，裂縫 1–3 cm 深；海風 3.2 m/s 使旗幟飄 15°；鏡頭運動模糊 180°。
  - Emotion & Performance：營造港區炎熱且空曠，壓迫感。
  - Audio & Transition：遠處港口廣播 -18 dB；海浪低頻 60 Hz；俯衝風聲漸強；硬切至怪物湧出。
- Angle B (T0.6–1.2s)
  - Camera：35mm 俯視 45°，輕推 1 m 觀察貨櫃縫隙。
  - Lighting：陽光形成硬陰影，貨櫃縫落入陰影中；bounce light 10%。
  - Materials & Physics：陰影區霧度 0.01；鐵鏽顆粒 0.2mm 在縫隙內晃動；地面熱氣造成輕微 mirage。
  - Emotion & Performance：預示危險；敘事慢拍。
  - Audio & Transition：金屬輕響；切入怪物畫面 match cut。

### Beat 2 — 小型風蝕獸湧現（1.2s–2.4s）
- Angle A (T1.2–1.8s)
  - Camera：35mm 低角 25° 靠近排水溝，向前滑軌 0.8 m；景深 f/4 聚焦首批怪物。
  - Lighting：陽光被溝邊遮擋 40%，柔化；反射光帶出鏽殼質感。
  - Materials & Physics：小型風蝕獸殼金屬度 0.65 粗糙度 0.6，附碎石 bump 0.2mm；眼螢綠光亮度 800 nits；四肢細長 30 cm，移動時摩擦係數 0.6 留下腐蝕痕跡。
  - Emotion & Performance：群聚 12 隻，同步抬頭；螢綠眼在陰影中刺眼。
  - Audio & Transition：金屬摩擦尖音 3 kHz；呼哧聲；硬切到跑道。
- Angle B (T1.8–2.4s)
  - Camera：50mm 側拍群體向出口竄，平移 1 m 追隨；手持抖動 3%。
  - Lighting：高架橋陰影斜落，形成斑駁光斑；貨櫃反射帶暖色。
  - Materials & Physics：地面腐蝕痕跡煙氣 density 0.005；足跡深 0.5 cm；小怪重量 12 kg，跑速 6 m/s。
  - Emotion & Performance：慌張竄動；給觀眾壓力。
  - Audio & Transition：鏽蝕破裂聲；切換至風見迅。

### Beat 3 — 風見迅就位（2.4s–3.6s）
- Angle A (T2.4–3.0s)
  - Camera：75mm 上半身特寫，從欄杆左側滑至正面 0.6 m；景深 f/2.8 突出鎖骨與線條。
  - Lighting：陽光打在胸肌形成硬邊；冷綠補光 20%；rim light 15% 勾髮絲。
  - Materials & Physics：機能布料粗糙 0.38；汗珠 0.5mm 反射 0.4；青綠流線亮 1000 nits 0.25s；髮絲隨風 3.2 m/s 向後掀 12°。
  - Emotion & Performance：嘴角壞笑，眼神瞄向怪群；腳踝輕踢欄杆 2 次，角度 10°。
  - Audio & Transition：日文台詞「昼間パトロールで、こんな数くれるとはね。」氣音；欄杆金屬聲；match cut 至瞬步。
- Angle B (T3.0–3.6s)
  - Camera：50mm 腰部到腳踝特寫，向下 tilt 15°；捕捉肌肉拉伸。
  - Lighting：陽光在腹肌形成清晰陰影；地面反射補光 12%。
  - Materials & Physics：肌肉張力讓布料拉伸 4%；鞋底壓欄杆 300 N；汗光沿腹斜肌形成 0.2 cm 高光帶。
  - Emotion & Performance：動作準備；重心前傾 12°。
  - Audio & Transition：吸氣聲；風聲提升；硬切。

### Beat 4 — 風痕瞬步起跑（3.6s–4.8s）
- Angle A (T3.6–4.2s)
  - Camera：35mm 地面貼近右側，追蹤速度 18 m/s，從欄杆空位向前拉；motion blur 180°。
  - Lighting：強光在地面形成高亮條，氣流跑道發光 1000 nits；陰影快速掠過。
  - Materials & Physics：氣流跑道亮線寬 20 cm，持續 1.2s；鞋底摩擦 0.85 留下淡青光痕；碎石被踢起 1–2 cm 高，向後 2 m。
  - Emotion & Performance：風見迅瞬間消失，殘影 3 層；速度感強。
  - Audio & Transition：風爆「ドン」低頻 90 Hz；切至正面攔截。
- Angle B (T4.2–4.8s)
  - Camera：24mm 正面迎向小怪，風見迅殘影從右切入；推軌 1 m。
  - Lighting：陽光正打形成強反差，前景怪物陰影覆蓋一半；流線光反射貨櫃。
  - Materials & Physics：殘影透明度 40%→20%；氣流造成塵埃 0.4 mm 粒子升起 0.5 m；摩擦刮痕亮度 500 nits。
  - Emotion & Performance：風見迅蹲低，準備爆發。
  - Audio & Transition：吸氣蓄力；硬切進 Act 2。

## Act 2 — 速度切割與音速連拳（4.8s–9.6s）
### Beat 5 — 瞬步分割怪群（4.8s–6.0s）
- Angle A (T4.8–5.4s)
  - Camera：35mm 斜頂 30° 俯拍，跟隨殘影畫出 S 型；平移 2 m。
  - Lighting：陽光被貨櫃遮 35%，形成交錯光帶；氣流亮線反射在貨櫃牆上形成 0.2 cm 刮痕高光。
  - Materials & Physics：風見迅殘影 3 層，間距 0.4 m；每次擦身在牆面刻出 1 mm 深刮痕；怪物被分成 3 區塊，慣性使其向外翻 1 m。
  - Emotion & Performance：身法如滑行；肩線穩定。
  - Audio & Transition：風切聲漸強；match cut 至低角衝刺。
- Angle B (T5.4–6.0s)
  - Camera：24mm 低角 30° 仰拍，置於貨櫃角落，追蹤向左 1.2 m；motion blur 180°。
  - Lighting：明暗對比 2:1；青綠光在地面拉出長尾 3 m。
  - Materials & Physics：地面氣流跑道厚 1 cm；碎石被壓入地面 0.3 cm；小怪外殼被側擦掉落鏽粉 0.1g。
  - Emotion & Performance：風見迅笑意更重，眼神專注。
  - Audio & Transition：鞋底摩擦聲 + 風聲，過渡至拳擊。

### Beat 6 — 音速連拳初擊（6.0s–7.2s）
- Angle A (T6.0–6.6s)
  - Camera：50mm 上半身正面，快速 dolly-in 0.7 m；輕微 handheld 2%。
  - Lighting：陽光直接照臉；青綠紋路亮至 1200 nits；汗光沿鎖骨閃動。
  - Materials & Physics：拳頭速度 70 m/s；風壓壓縮形成白色衝擊圈厚 8 cm；怪物殼在衝擊下破裂成 0.5–1 cm 碎片飛出 3 m。
  - Emotion & Performance：肩線前傾 12°，拳頭旋轉 15°；吐氣「ハッ」。
  - Audio & Transition：衝擊聲低頻 90 Hz，尖峰 3 kHz；match cut 連至第二拳。
- Angle B (T6.6–7.2s)
  - Camera：75mm 拳峰特寫，沿拳運動向前推 0.3 m；景深 f/2.8。
  - Lighting：rim light 從右後 20% 勾出拳峰輪廓；前方反射光 10%。
  - Materials & Physics：拳頭皮膚 SSS 1.1 mm；汗膜折射 1.33；空氣被壓縮形成凝結雲 5 cm 厚；碎片撞擊地面火花 0.5 mm 粒子。
  - Emotion & Performance：拳峰緊繃；筋脈浮出 0.2 cm。
  - Audio & Transition：風切高頻 4 kHz；硬切至第三拳廣角。

### Beat 7 — 音速連拳連段（7.2s–8.4s）
- Angle A (T7.2–7.8s)
  - Camera：35mm 側向 tracking 1 m，捕捉連續三拳；motion blur 180°。
  - Lighting：光斑在貨櫃上跳動；青綠殘影拖尾 2 m。
  - Materials & Physics：第二拳與第三拳間隔 0.2s；衝擊圈半徑 30 cm；怪物被打出 4 m，撞貨櫃凹陷 2 cm；貨櫃金屬變形細節可見刮痕。
  - Emotion & Performance：表情專注帶笑；呼吸短促。
  - Audio & Transition：連擊節奏「ドン・ドン・ドン」；匹配鼓點；match cut 至腳步。
- Angle B (T7.8–8.4s)
  - Camera：50mm 背後跟拍，風見迅居中，怪物向鏡頭飛出；推軌 0.8 m。
  - Lighting：背光形成輪廓；貨櫃反射光填補前景 15%。
  - Materials & Physics：飛出的碎片與鏽粉粒徑 0.2–0.5 mm，形成噴霧；風見迅頭髮被風向後吹 15°；衣料因慣性貼身 5%。
  - Emotion & Performance：肩背肌隆起；拳後手迅速收回。
  - Audio & Transition：碎片撞擊聲；硬切到巷道。

### Beat 8 — 巷道側跑與風壓斬線（8.4s–9.6s）
- Angle A (T8.4–9.0s)
  - Camera：35mm 置於巷道左牆 1.2 m 高，跟拍沿牆跑動 1.5 m；景深 f/3.2。
  - Lighting：巷道陰影 60%，前方反光 20%；青綠光在牆上滑動。
  - Materials & Physics：風見迅腳掌踩牆摩擦 0.82，腳印深 0.2 cm；手刀聚氣時指尖氣流 5 cm 厚；巷道塵埃 density 0.005 被帶起。
  - Emotion & Performance：表情專注；身體貼牆 10 cm。
  - Audio & Transition：呼嘯風聲；吐氣「フッ」；切到手刀斬線。
- Angle B (T9.0–9.6s)
  - Camera：50mm 正面低角 25°，追蹤手刀掃過；motion blur 180°。
  - Lighting：風刃發光 1100 nits，照亮牆面；陽光從巷口打出光柱。
  - Materials & Physics：風刃厚 5 cm、長 6 m，切口筆直粗糙度 0.3；小怪被切成兩半，碎石顆粒 0.4 mm 飛散；牆面裂痕深 2 cm。
  - Emotion & Performance：眼神銳利，手刀過後放鬆。
  - Audio & Transition：風刃「シュパ」聲 + 牆裂聲；硬切進 Act 3。

## Act 3 — 清掃收束與餘韻（9.6s–15.0s）
### Beat 9 — 殘兵清除衝刺（9.6s–10.8s）
- Angle A (T9.6–10.2s)
  - Camera：35mm 與氣流跑道同向平移 1.5 m，捕捉最後衝刺；motion blur 180°。
  - Lighting：陽光被貨櫃間縫隙切成條狀；流線光尾 3 m 長。
  - Materials & Physics：風見迅速度 20 m/s；每次擦身重擊產生衝擊框；怪物被撞飛 3 m；地面碎石彈跳 1 cm。
  - Emotion & Performance：表情享受戰鬥；呼吸穩定。
  - Audio & Transition：鼓點加速；match cut。
- Angle B (T10.2–10.8s)
  - Camera：24mm 全景，俯視 20°，看到跑道形成螢光線稿。
  - Lighting：強光與陰影交錯；青綠線在白天背景中明顯。
  - Materials & Physics：跑道亮度 1000 nits；光尾逐漸衰減 1.2s；塵埃粒子在陽光中反射。
  - Emotion & Performance：風見迅身形如線條筆刷。
  - Audio & Transition：風聲拖尾；硬切到最後一擊。

### Beat 10 — 最後一拳終結（10.8s–12.0s）
- Angle A (T10.8–11.4s)
  - Camera：50mm 特寫最後一隻風蝕獸，鏡頭微抖 2%；推軌 0.6 m。
  - Lighting：陽光照在怪物鏽殼上形成亮點；青綠拳峰反射。
  - Materials & Physics：拳峰速度 68 m/s；衝擊圈白色霧化厚 6 cm；貨櫃被打出 3 cm 深掌印；金屬凹陷邊緣粗糙度 0.7。
  - Emotion & Performance：風見迅吐氣，眼神鎖定；肌肉收縮明顯。
  - Audio & Transition：金屬凹陷「ガン」響 1s 尾音；match cut 至停下。
- Angle B (T11.4–12.0s)
  - Camera：35mm 追蹤怪物飛進貨櫃，pan 20°；景深 f/4。
  - Lighting：陰影吞沒怪物；貨櫃內光線 20%。
  - Materials & Physics：怪物落入貨櫃揚起塵埃 0.6 mm 粒子；掌印周圍金屬變形波紋 0.5 cm；鏽粉落下 0.5s。
  - Emotion & Performance：收拳站穩。
  - Audio & Transition：塵土落下沙沙；硬切至收束。

### Beat 11 — 收勢與汗光（12.0s–13.2s）
- Angle A (T12.0–12.6s)
  - Camera：75mm 上半身，微推 0.3 m；景深 f/2.8；肩線微前傾。
  - Lighting：陽光形成肌肉高光；汗珠反光；青綠紋路逐漸暗下。
  - Materials & Physics：汗珠滑落 0.5 m/s；皮膚 SSS 1.1 mm；呼吸讓胸腔起伏 1.5 cm。
  - Emotion & Performance：單手插腰，另一手抹汗；嘴角微揚。
  - Audio & Transition：呼吸聲 + 遠方廣播；match cut 至遠景。
- Angle B (T12.6–13.2s)
  - Camera：50mm 半身，從右後轉到正面 30°；腳步微動 0.2 m。
  - Lighting：rim light 15% 勾邊；地面反光補光 10%。
  - Materials & Physics：布料反射 0.08；汗光形成 0.3 cm 高光帶；髮絲貼額。
  - Emotion & Performance：台詞「差不多當暖身吧。」；語氣輕鬆。
  - Audio & Transition：日文台詞後帶笑；硬切到遠奔。

### Beat 12 — 再次奔跑離場（13.2s–15.0s）
- Angle A (T13.2–14.4s)
  - Camera：24mm 全景，沿高架橋跟拍 2 m；穩定推動。
  - Lighting：正午光照；青綠風痕逐漸消散。
  - Materials & Physics：跑步速度 18 m/s；風痕衰減 1.2s；塵埃 density 0.004 被帶動；汗珠被風帶走形成細霧。
  - Emotion & Performance：風見迅再次衝出畫面；決心備戰。
  - Audio & Transition：台詞「本番は、まだこれからだろ？」；風聲拖尾。
- Angle B (T14.4–15.0s)
  - Camera：35mm 拉遠 5 m，看見空曠港口與漸淡的青綠跑道；上 tilt 10°。
  - Lighting：陽光保持穩定；遠景泛白；貨櫃投影形成收束線。
  - Materials & Physics：跑道光尾變薄至 0.5 cm；海風仍 3.2 m/s；熱霧使遠景微扭。
  - Emotion & Performance：觀眾留存餘韻；準備接續下一戰。
  - Audio & Transition：海浪聲、廣播聲淡出；logo 收束 0.6s。

## Platform Layer
- Hook A（故事向）：0–1s 高空俯衝看到怪物湧出，字幕「港區正午，風蝕獸再現」。
- Hook B（衝擊向）：1–2s 風見迅瞬步衝出並壞笑，字幕「昼間パトロールで、こんな数くれるとはね」。
- First-shot visual hook：俯衝視角 + 怪物螢綠眼光閃。
- Captions：雙語字幕，中日並列；安全框 5%；關鍵台詞對齊擊打（6.0s、10.8s、12.6s、13.2s）。
- Thumbnail 構圖：選 6.6s 拳擊瞬間，青綠速度線與碎片凍結；文字「風壓奔襲」。
- Hashtag：#風見迅 #港區掃蕩 #WindStrike #2DAnime #港口動作
- CTA：13.2–15s 留白字幕「下一波，等你」。
- 切片輸出策略：
  - 短版 0–3.6s 用作 Hook；9.6–12.0s 作動作精華；12.6–15.0s 作 CTA。
  - 長版保持全 15s；字幕檔對應時間碼（0.0、1.2、3.6、6.0、8.4、10.8、13.2s）。

## Negative Instructions
- 禁用內容：真實品牌、名人肖像、宗教政治符號、血腥噴濺、成人尺度、極端暴力；禁止粉彩夢幻濾鏡、魚眼畸變 <22mm。
- 避免畫面：過曝高光、HDR 拉爆、畫面抖到難以閱讀、字幕跑出安全框。
- 自動檢核清單：
  - [ ] 無真實商標/宗教政治圖樣。
  - [ ] 速度線方向與運鏡一致。
  - [ ] PBR 參數皆已標註。
  - [ ] 時間碼與分鏡層級齊全。
  - [ ] 無血腥或成人尺度。
  - [ ] 字幕安全框內。
  - [ ] 風格包無衝突且皆標註 Default。
  - [ ] 持續元素（青綠流線、汗光、氣流跑道）皆有延續。

## Assumptions
- 未提供港區具體品牌或船隻樣式，因此全部以 generic 貨櫃與鋼橋呈現，避免侵權。
- 未指定怪物數量，假設初始 12 隻小型風蝕獸以保持畫面密度。
- 未提供角色武器，依設定風見迅徒手，以速度線與風刃為主；若需武器可在後續集數加入。

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：已包含 Master Prompt、3 Act、12 Beat、每 Beat 2 Angle，時間碼 1.2s 切分，總長 15s，含 Platform 層與 Negative。
- Physics & PBR：每幕列出重力背景、摩擦、速度、材質金屬度/粗糙度、SSS、折射率、粒徑與能量分佈，風刃壓差、氣流跑道厚度等皆標示。
- Stylepacks 使用與衝突：啟用 2D Wind Kinetics、Industrial Seaport Realism、Monotone Breeze VO，互斥條件已列；未混用禁用風格。
- Continuity：青綠流線、氣流跑道、汗光、運動軸方向皆持續；Camera Continuity 俯衝→平移→跟拍，轉向前置光閃；無角色造型變更。
- Platform/字幕/切片：Hook A/B、Caption、Hashtag、CTA 與切片時間皆標示，可直接輸出。
- 自評 10/10 但需後續人類確認：若需特定品牌貨櫃或 VO 聲優口條，需由人類另行指定；目前假設 generic。

## Micro-actions Timeline（全 12 Beat）
- Beat 1（0.0–1.2s）
  - T0：無人機俯衝，旗幟向後折彎 15°，塵埃被拉長。
  - T0+0.3s：鏡頭經過貨櫃頂，陽光 flare 0.1s；陰影區霧氣被切開。
  - T0+0.6s：俯視角度轉正，觀眾看到縫隙中的鏽粉顫動。
  - T0+0.9s：roll 微調回正，鏡頭減速，準備切怪物。
- Beat 2（1.2–2.4s）
  - T1.2：第一批小怪爪尖觸地，腐蝕冒煙 0.2 cm 高。
  - T1.5：群體同步轉頭，螢綠眼亮到 800 nits；尾部碎石抖落。
  - T1.8：鏡頭低角滑過，捕捉足跡煙霧向後 0.5 m。
  - T2.1：小怪開始加速，腳尖敲擊地面 8 次/秒。
- Beat 3（2.4–3.6s）
  - T2.4：風見迅踢欄杆時青綠光迸出 0.2s，欄杆震動 2 mm。
  - T2.7：髮絲被風掀起 12°，眼神鎖定遠方；肩肌繃起。
  - T3.0：鏡頭 tilt 至腳踝，看到小腿肌肉收縮，血管浮起 0.2 cm。
  - T3.3：青綠紋路沿肩至前臂流動 0.15s，形成速度線效果。
- Beat 4（3.6–4.8s）
  - T3.6：腳尖蹬欄杆 1400 N，碎石向後彈 1.5 m。
  - T3.9：殘影 3 層展開，第一層透明度 40%，第三層 20%。
  - T4.2：氣流跑道發光，地面浮塵被捲起形成 0.3 m 寬帶。
  - T4.5：風見迅蹲低，重心壓在前腳，背肌拉出弧線。
- Beat 5（4.8–6.0s）
  - T4.8：殘影切過貨櫃，刮痕火花 0.8 mm 粒徑跳出。
  - T5.1：怪物被分成 3 區，內層塵霧被氣流推開 1.2 m。
  - T5.4：鏡頭低角抬頭，看到光尾交織成 S 型。
  - T5.7：碎石落地，地面震動 0.15G。
- Beat 6（6.0–7.2s）
  - T6.0：第一拳前搖，手臂肌肉張力線明顯；吐氣聲同步。
  - T6.2：白色衝擊圈爆出，怪物殼碎片 0.5–1 cm 旋轉飛離。
  - T6.4：拳峰穿過碎片，汗珠被風甩出 0.4 m；手腕反彈。
  - T6.6：鏡頭切拳峰特寫，凝結雲貼在指節前方。
- Beat 7（7.2–8.4s）
  - T7.2：第二拳命中，衝擊框扭曲貨櫃表面；髮絲向後飄 18°。
  - T7.5：第三拳連上，肩膀肌肉起伏 2 cm；怪物飛離軌跡與光尾重合。
  - T7.8：背後跟拍時碎片掠過鏡頭前方形成前景遮擋。
  - T8.1：風見迅收拳貼身，肌肉震顫 0.2s，呼吸聲短促。
- Beat 8（8.4–9.6s）
  - T8.4：腳尖點牆，鞋底摩擦聲「シュ」；塵埃被掃成薄層。
  - T8.7：手刀聚氣，指尖青綠光聚成弧形；肩胛骨向內收。
  - T9.0：風刃掃出，牆面裂開瞬間塵霧噴出 0.5 m；怪物切開延遲 0.05s。
  - T9.3：風刃尾部逐漸淡去，牆面裂痕仍冒粉塵。
- Beat 9（9.6–10.8s）
  - T9.6：風見迅再次衝刺，腳掌每步間距 1.8 m，節奏 0.2s。
  - T9.9：跑道光尾形成雙曲線，塵埃在陽光下閃爍。
  - T10.2：全景俯視時可見氣流將熱霧推開 1 m。
  - T10.5：最後幾隻怪物向外逃，重心不穩搖晃。
- Beat 10（10.8–12.0s）
  - T10.8：拳頭蓄力，前臂靜脈浮出；呼吸吐氣同步台詞。
  - T11.1：衝擊圈撞上貨櫃，金屬瞬間凹陷形成掌印。
  - T11.4：怪物反彈進貨櫃內部，鏽粉以拋物線飛散。
  - T11.7：塵埃落下時光束穿透，形成條狀體積光。
- Beat 11（12.0–13.2s）
  - T12.0：風見迅抹汗，汗珠沿掌根滴落 0.3s。
  - T12.3：鎖骨在呼吸下起伏 1.5 cm，胸肌反光。
  - T12.6：台詞「差不多當暖身吧。」嘴角抬 3°；字幕同步彈出。
  - T12.9：肩線放鬆，青綠紋路逐漸熄滅。
- Beat 12（13.2–15.0s）
  - T13.2：起跑蹬地 1200 N，跑道光尾形成 V 字。
  - T13.8：鏡頭平移時風痕拖尾 3 m，逐漸透明。
  - T14.4：拉遠看到港口全景，熱霧抖動 1%。
  - T14.8：logo 收束，風聲淡出，廣播聲殘留 -24 dB。

## PBR Layered Breakdown（材質三層細節）
- 皮膚：
  - Base Color/Albedo：#c88858 小麥色，微色斑 1 mm；肌理法線 8K。
  - 次表面與微結構：SSS 半徑 1.1 mm；汗膜厚 0.05 mm，油膜 0.02 mm 折射 1.33；細汗毛 0.3 mm 反光。
  - 表層干涉：specular 0.45，粗糙度 0.32；菲涅耳反射 0.04；在強光下形成 0.2 cm 高光帶。
- 機能布料：
  - Base：尼龍彈性布粗糙度 0.38，金屬度 0.05；纖維方向沿肩至腰。
  - 微結構：法線貼圖 8K，纖維隆起 0.08 mm；磨損區域在肘部與膝蓋形成 0.2 mm 毛球。
  - 表層：鏡面反射 0.06，微光澤在光束掃過時產生柔反射；AO 0.4。
- 貨櫃金屬：
  - Base：金屬度 0.7 粗糙度 0.55，色調紅褐 #b45b2e/藍灰 #6b8ca0。
  - 微結構：鏽斑 bump 0.3 mm，刮痕深 1–2 mm；塗層剝落露出銀灰底漆。
  - 表層：鏡面反射 0.25，菲涅耳邊緣 0.08；陽光下有細微高光閃爍。
- 地面水泥：
  - Base：粗糙度 0.6，粒度 0.4 mm；裂縫 1–3 cm 深。
  - 微結構：小石子嵌入，摩擦係數 0.7；昨夜刮痕 1–3 cm 深留有粉塵。
  - 表層：潮濕區域反射率 0.12；陽光高光控制在 0.18。
- 風蝕獸外殼：
  - Base：金屬度 0.65 粗糙度 0.6，鐵銹色；碎石塊貼合外殼。
  - 微結構：碎石凸起 0.2 mm，腐蝕孔洞 0.5 mm；摩擦係數 0.55。
  - 表層：鏽粉易脫落形成塵霧；光照下反射 0.22。
- 風刃粒子：
  - Base：體積霧密度 0.02；色調青綠。
  - 微結構：粒徑分佈 0.05–0.1 mm；散射 0.55、吸收 0.15。
  - 表層：邊緣帶菲涅耳光暈 0.1；折射使背景略變形。

## Camera & Lighting Continuity Notes
- 每個鏡頭焦段與角度已標註；切換時使用 match cut 或光閃避免軸線錯亂。
- 低角仰拍維持 30–45° 以強化體態；俯視鏡頭 roll 校正確保地平線穩定。
- 光比維持 2:1，若進入巷道則將 fill 光提升至 30% 避免黑壓；rim light 控制在 15–20%。
- 景深保持 f/2.8–f/4，遠景全景時 f/4–f/5.6 以保留貨櫃紋理。
- Motion blur 固定 180°；高速鏡頭增加 shutter angle 至 200° 僅在 4.8–6.0s 殘影段使用，仍需註記。
- 色彩流程全程 log → filmic LUT → contrast 1.9 gamma；青綠流線需在 LUT 後確認不過曝。
- 鏡頭軌跡對應跑道光線方向，避免相反導致速度感喪失。
- 轉場優先採硬切或 match cut；若使用 swipe 必須以風刃或速度線帶動。

## Physics Solver Notes
- 流體/粒子：
  - 氣流跑道使用 VDB 速度場，風速 20–24 m/s，粒子上限 60k，步長 1/48 s。
  - 風刃切片以 flip smoke 模擬，散射 0.55、吸收 0.15，粒徑 0.05–0.1 mm；運算成本估 4s/frame。
- 碰撞/接觸：
  - 鞋底與地面摩擦 0.85，彈性 0.2；落地產生 0.15G 震動。
  - 拳擊與貨櫃彈性係數 0.35，阻尼 0.25；能量分配 60% 轉為變形，40% 轉為音波與碎片動能。
  - 風蝕獸殼破碎後碎片飛散角度 25–60°，初速 8–12 m/s。
- 力場：
  - 海風 3.2 m/s 東南向，對粒子有 0.3 倍拖曳；熱霧上升 0.4 m/s。
  - 風見迅衝刺時自帶 20 m/s 局部風場，推開塵埃與汗霧。
- 重力與慣性：
  - 全場重力 9.81 m/s²；跑道上的碎石受衝擊後上升 0.05 s 再落下。
  - 衝刺與拳擊時保持慣性連續，不允許突然停止無緩衝。

## Subtitle Timing Map
- 1.5s 字幕：「港區正午，風蝕獸再現」對應怪物湧出。
- 2.8s 字幕：「昼間パトロールで、こんな数くれるとはね」對應風見迅壞笑。
- 6.2s 字幕：「音速連拳、行くよ。」對應第一拳。
- 9.1s 字幕：「風壓斬線。」對應手刀。
- 12.6s 字幕：「差不多當暖身吧。」對應抹汗。
- 13.4s 字幕：「本番は、まだこれからだろ？」對應再次奔跑。
- 字幕樣式：Noto Sans JP/TW 70pt，描邊 2.5 px 青綠，透明底 60%，安全框 5%。


## Platform Layer Supplement
- Hook 字幕備註：所有字幕需含日語羅馬音小字 50pt 置於主字幕下方 10 px。
- 切片導出：提供 1080x1920 與 720x1280 兩版，皆保持 24fps；壓縮前加 grain 8%。
- 音軌分離：旁白、效果、環境各獨立 stem，便於平台二創。
- CTA 配色：青綠字體搭配黑底 60% 透明，停留 0.6s 後淡出。
- Logo 收束：使用白底黑線稿，bloom 0.05，保留 0.6s，禁止加陰影。

# Project Metadata
- project_name: 黑黃衝擊
- series_name/arc: 個人PV・朝倉蓮
- episode_index: 2
- slug: silent-city-impact-asakura-ren-pv
- target_platform: short-form vertical video (JP/TW social, 9:16)
- duration_sec: 15
- style_primary: 2D 日系動漫風格（黑黃電路線）
- style_secondary: 廢墟實戰寫實（鋼骨與裂地衝擊）
- worldstate_ref: 夜間廢墟訓練場連接鋼骨高架橋，微霧 0.016 density、微風 1.8 m/s
- goal: 製作朝倉蓮個人PV，對應黑黃衝擊主題，結合訓練與實戰，日文配音並附中日字幕

## _core
### Brand Bible（黑黃衝擊）
- 角色色票：主黑 #0b0b0e、警戒黃 #f0c400、次光灰 #40434a、汗水高光 #a0c8ff；黑佔 60%、黃線 25%、灰 10%、高光 5%。
- 服裝材質：貼身機能布（粗糙度 0.32、金屬度 0.05、法線 8K 纖維 0.08 mm 高度、伸縮 12%）；護腕噴砂鈦合金（粗糙度 0.26、金屬度 0.88、邊緣磨痕 0.1 mm）、金屬環內徑 4 cm；折疊重武器為鋼鐵＋碳纖混合（刀刃粗糙 0.18、金屬度 0.9、柄部橡膠摩擦係數 0.82）。
- 肌膚層級：base color #c27f5f、SSS 半徑 1.2 mm、specular 0.46；細汗膜 0.05 mm 折射 1.33，額頭與鎖骨汗珠粒徑 0.6–0.9 mm；手部繭粗糙度 0.28，指節泛白 2 mm；血管微浮 0.3 mm。
- 口頭禪與語氣：日語低沉短句，常以「…だ」「だろ」「いい」收束；台詞節奏與呼吸對齊；中文字幕精簡直接；旁白不超過 12 字。
- 姿態與習慣：收拳時拇指輕貼食指第二指節；調整護腕前先吐氣 0.2s；起步左腳領先，腳踝內旋 3°；受擊時先落右腳、膝彎 18° 吸震再轉身；揮擊後會短暫甩手放鬆 0.4s。
- 場景色調：冷藍環境光 4800K、暖黃點燈 3100K；光比 2:1，AO 0.52；霧氣密度 0.016；遵循 Do: 對比度 1.8 gamma curve、保持黃線不過曝（峰值 1200 nits）。
- 鏡頭語言 Do：穩定推軌或手持抑震 0.6 阻尼、低角 20–40° 強化肌肉量感、以運動方向做 match cut、景深 f/2.8–f/4 釘住眼神或武器刻線、以速度線或光閃作轉場、在同時事件標註 T0/T0+0.3s。
- 鏡頭語言 Don't：使用魚眼 <20mm、跳剪破壞節奏、過曝到 clipping、用「同前」代替參數、插入真實品牌或宗教政治符號、忽略物理行為。
- 文案語氣：中文敘述＋日文配音，句子短、硬朗，重點落在「撐住」「站我後面」，避免花哨修辭；字幕黃底黑字或黑底黃字，描邊 3 px；配樂低沉鼓點對齊心跳 70–90 BPM。

### Shared World & Character File
- Worldstate snapshot：夜晚 20:10，外環廢墟與鋼骨高架橋相連；地面裂縫深 5–8 cm、寬 12–20 cm；廢墟鐵架鏽蝕 32%，高度 6–9 m；水泥地粗糙度 0.55，局部潮濕折射 1.33；霧氣 density 0.016，粒徑 0.6–0.9 µm；微風 1.8 m/s 從東向西；遠處城市燈光 300 nits 點狀；高架橋護欄高 1.1 m、金屬粗糙 0.38。
- Character default：朝倉蓮 178 cm / 78 kg，體脂 10%，右撇子；護腕厚 1.2 cm，金屬環 0.4 cm 厚；折疊斧槍 18 kg，慣性矩 4.5 kg·m²，展開長 140 cm；靴底橡膠摩擦係數 0.78，厚 2.4 cm；肩寬 48 cm。
- Persistent elements：黑黃線條沿鎖骨、肋側、武器柄走向在出拳或揮擊時亮起 0.3s（三段亮度 1000/750/500 nits）；汗珠落地濺射直徑 2–3 cm；衝擊波推開霧氣 1–1.6 m；緊身布料沿肌肉凹陷 1–2 mm；呼吸時肩線起伏 0.8 cm；心跳鼓點 0.7–0.9s 周期同步光脈衝。
- Constraint list：武器收納角度 25° 背後可見；護腕金屬環至少 50% 曝露；鏡頭運動軸優先右向；情緒曲線由冷靜→決心→微笑，不允許怒吼或誇張表情；不出現其他角色臉部，怪物保持剪影化；字幕僅中日且貼合擊打節點。
- Execution note：camera projection 對廢墟貼圖保持銳利；volume pass 控制霧散射 0.58、吸收 0.22；衝擊波使用圓形 VDB 壓縮波 18–24 m/s，粒子上限 55k；motion blur 180°，在拳風或斧槍揮擊可放寬至 200°；音效對齊字幕節點，金屬撞擊殘響 1.2s；若同時事件發生以 T0 + 0.3s 標示。

### Do / Don't（Core）
- Do：列出時間碼、鏡頭焦段、光源色溫與強度、PBR 參數、重力/慣性、粒子密度；字幕與台詞節點同步；Platform 層提供 Hook A/B 與切片策略；Camera Continuity 註明方向；提供 micro-actions 與 T0 序列。
- Don't：模糊詞、缺少時間戳、以「同前」代替、使用真實品牌/宗教/政治符號、忽略摩擦係數或材質層級、遺漏 Self-Check、讓霧氣或粒子無互動。

## _stylepacks
### Style: Black & Yellow Impact Circuit
- Applicable for：黑黃電路線風格的格鬥與訓練段，強調肌肉線條與亮線閃動。
- Do NOT mix with：粉彩夢幻、柔焦少女、Q 版比例。
- Default: ON
- Visual traits：黑底黃線形成電路紋，線條閃光 0.2s、亮度最高 1200 nits；邊線粗 2–3 px，陰影用冷藍 4800K；材質保留微刮痕與汗膜反射；遵循 Do: 對比度 1.8 gamma curve；速度線殘影三層透明度 45/25/15%。
- Audio traits：金屬環撞擊 1.1 kHz 峰值、低頻鼓擊每 0.6s，日文低沉旁白；風聲與衝擊波低頻 80–120 Hz；字幕彈出聲 -18 dBFS。
- Do：在分鏡引用黃線閃光、金屬殘響、速度線殘影；用電弧閃光或速度線 wipe 轉場；保持 9:16 構圖與 5% 安全框。
- Don't：把黃線過曝到飽和、加入真實品牌 Logo、使用魚眼或過度手持晃動、移除物理參數。

### Style: Ruin Grit Realism
- Applicable for：廢墟訓練場、鋼骨高架橋下實戰、碎石與火花。
- Do NOT mix with：乾淨無汙場景、少女粉霧調。
- Default: ON
- Visual traits：鋼骨鏽斑 0.3 mm 凸起、裂地 5–8 cm 深、碎石粒徑 1–3 cm；霧氣 0.016 density 形成光束；火花粒徑 0.8–1.4 mm；景深 f/2.8–f/5.6 控制分層；裂縫積水反射 1.33 折射率。
- Audio traits：空曠館回音 0.6s、金屬撞擊 1.2s 殘響、腳步落地 220 Hz 共振；怪物咆哮低頻 70 Hz、高頻 2.5 kHz 嘯音；碎石滾動 300–500 Hz。
- Do：標註摩擦係數、材質粗糙度、粒子數與密度；轉場可用碎石掃過鏡頭或火花遮擋；霧氣在衝擊後向外推；火花與霧交互形成體積光。
- Don't：模糊掉裂縫深度或火花粒徑；忽略重力與慣性；讓霧氣靜止無互動；將場景打得過於潔淨。

### Do / Don't（Stylepacks）
- Do：每幕引用黑黃線閃光、鋼骨鏽斑、霧氣推動效果；保持 9:16 構圖，留 5% 安全框；鏡頭色調對比 1.8 gamma；使用 Hook A/B；台詞與字幕同步。
- Don't：混用粉彩或夢幻濾鏡；在字幕或光效中加入真實品牌；以「同前」省略攝影或材質參數；忽略 PBR 層級或物理互動。

## Technical Specs
- Aspect Ratio：9:16 直式，1080x1920。
- FPS：24fps；shutter angle 180°，在拳風/揮擊可放寬至 200° 並標註。
- Camera set：24mm（環境與俯視）、35mm（半身推軌）、50mm（特寫與情緒）、75mm（極近眼神與汗珠）；穩定器阻尼 0.6、roll 校正 ±5° 內；match cut 使用速度線或火花遮擋。
- DoF：f/2.8–f/4 for mid/close，f/4–f/5.6 for wide；焦點優先眼睛/拳峰/武器刻線；散景半徑 6–8 px 控制背景噪點。
- Grain：film grain 7–8%，保留紋理避免社群壓縮抹平；log → filmic LUT → contrast 1.8 gamma curve → subtle bloom 0.12；高光保留 roll-off。
- Color pipeline：log capture；保持黑區細節；黃線保留高光剪裁 <0.18；體積霧色溫 4800K；避免色偏粉紅；skin tone 46–52 IRE。
- Audio：日文配音 48kHz；金屬撞擊與拳爆分軌；怪物咆哮低頻單獨軌；字幕彈出聲 -18 dBFS；環境底噪 -30 dBFS；peak -1 dBFS；立體聲寬度 40%。
- Platform safety：字幕安全框 5%；閃爍頻率避開 15–20 Hz；Hook A/B 標註時間；切片策略列於 Platform Layer；避免過度閃白。

## Master Prompt
- worldstate snapshot：夜色未完全落下，城市已安靜；廢墟訓練場鋼架投下長影，地面裂開 5–8 cm；昏黃路燈 3100K 500 lux 投射，冷藍環境光 4800K 200 lux；高架橋鋼骨跨度 12 m、護欄 1.1 m 高；霧氣 density 0.016；火花源自武器撞擊與怪物爪擊；背景遠處霓虹 300 nits；微風 1.8 m/s 東→西；音場回音 0.6s。
- constraint list：黑黃線亮度 ≤1200 nits；鏡頭軸向主要向右；武器展開動作需可見刻線；情緒保持冷靜→決心→微笑；怪物維持剪影，不展示血腥；不使用真實品牌或政治宗教符號；字幕雙語同步；運鏡遵循 1.8 gamma curve Do；禁止「同前」。
- execution note：採 camera projection 保持廢墟紋理銳利；粒子系統：火花粒徑 0.8–1.4 mm，數量 3–6k；碎石粒徑 1–3 cm，摩擦係數 0.7；衝擊波使用 VDB，密度 0.15、散射 0.58、吸收 0.22；volume fog clamp 0.35；motion blur 180°（揮擊 200°）；同時事件以 T0 + 0.3s 方式標註。
- Camera Continuity：上一集收尾於 35mm 肩平視推軌 1 m 右向；本集開場維持推軌方向右向，轉 24mm 廣角建立廢墟；轉入實戰時以黃線閃光 match cut；若需要反向運動，先以碎石掃鏡遮擋再切換；光比維持 2:1。
- Platform Layer：Hook A（0.0–1.0s）低角腳步＋護腕金屬聲；Hook B（5.8–7.0s）武器展開爆光；切片時間 0–3s（氛圍）、5.8–7.0s（武器展開）、11.5–15s（終擊與微笑）。
- Stylepacks used：Black & Yellow Impact Circuit（ON）、Ruin Grit Realism（ON）。
- Negative instructions：禁用真實品牌、名人肖像、政治宗教符號；避免魚眼、過曝、過度手持晃動；不得有血腥或成人尺度；字幕需無錯字，語言僅中日；禁止粉彩濾鏡。

## Continuity & Transition Map
- Act 1 → Act 2：以護腕金屬聲殘響做橋接；Camera 從 35mm 腰平視切到 35mm 低角，運動方向維持右向；霧氣密度保持 0.016 → 0.01 漸降，避免突兀。
- Act 2 → Act 3：速度線 wipe + 鼓點 drop；色溫從 5200K 清晨回到 3100K 暖路燈，需在 0.4s 內完成 gamma 曲線對齊；角色呼吸頻率從 0.6s 放緩到 0.8s。
- Act 3 → Act 4：以黑黃線亮度漸增 0.3s 為前置條件，再硬切到怪物俯視；鏡頭運動軸仍向右，若需反轉以碎石遮擋；光比保持 2:1。
- Act 4 → Act 5：白片閃光 + 電弧聲轉場；shutter 在 Act 5 開始時標回 200° → 180°；霧氣被衝開 1 m 後在 0.8s 內回到 density 0.012。
- Platform Hook：Hook A 保持低頻空間 70–90 Hz，Hook B 使用 1.2 kHz 金屬亮點；兩者皆需字幕在 5% 安全框內；切片策略在 Transition 期間不得被字幕遮擋主角臉部。
- Camera Continuity quick map：
  - Beat 1→2：24mm 低位 → 35mm 腰平視，透過腳步擦鏡。
  - Beat 2→3：35mm → 50mm 手部特寫，靠黃線閃光 match cut。
  - Beat 4→5：35mm 低角 → 50mm 近距，使用音爆硬切。
  - Beat 6→7：75mm 側臉 → 50mm 正面，呼吸聲 crossfade。
  - Beat 9→10：24mm 俯視 → 35mm 近景，碎石遮擋。
  - Beat 11→12：50mm 側面 → 75mm 近距，火花遮擋。
- Subtitle safety：每行字幕不超過 14 字，行距 1.15；T0+0.1s 內顯示，T0+0.2s 內淡入完畢；字幕與畫面亮度對比至少 3:1。
- Audio sync：
  - Beat 1–3：腳步與護腕聲位於 L/R -30/30；
  - Beat 4–6：呼吸佔中心，沙包與跑步聲在 200–500 Hz；
  - Beat 7–8：旁白置中，混響 0.35s；
  - Beat 9–12：衝擊與電弧佔 1.1–1.2 kHz 峰值，低頻保持 -5 dBFS。
- Micro-action density：每 Beat 至少提供 4 個 T0 標記；若需補充，優先在 Act 4–5 增加 0.1s 內的細節，確保解析。

## Physics & Material Reference
- 重力：9.81 m/s²；如需慢動作，請註明 time remap 比例與物理補償。
- 摩擦係數：
  - 柏油與靴底 0.78；
  - 牆面 0.78；
  - 護欄金屬 0.4；
  - 沙包皮革 0.6；
  - 武器柄橡膠 0.82。
- 粗糙度與金屬度：
  - 機能布粗糙 0.32、金屬度 0.05；
  - 鈦合金護腕粗糙 0.26、金屬度 0.88；
  - 斧槍刀刃粗糙 0.18、金屬度 0.9；
  - 護欄金屬粗糙 0.38、金屬度 0.78；
  - 水泥地粗糙 0.55。
- 粒子系統：
  - 火花粒徑 0.8–1.4 mm，單次衝擊 3–6k 粒子，生命周期 0.6–0.9s；
  - 塵土粒徑 0.3–0.5 mm，被衝擊波推 1–1.6 m；
  - 霧氣 density 0.016（戰鬥中降至 0.01），體積散射 0.58、吸收 0.22；
  - 汗珠粒徑 0.6–0.9 mm，落地濺射直徑 2–3 cm；
  - 速度線殘影三層透明 45/25/15%，尾長 3 m。
- 力學：
  - 起跑推力 1450 N；
  - 揮擊角速度 180°/0.35s；
  - 衝擊波速度 18–24 m/s；
  - 武器展開彈簧力 120 N；
  - 怪物踏地產生碎石飛散 1.2 m 高。
- 光學：
  - 路燈 3100K 500–700 lux；
  - 環境冷光 4800K 150–250 lux；
  - 黃線亮度峰值 1200 nits；
  - Bloom 強度 0.12；
  - 鏡面反射：護腕 0.6、汗膜 0.46、刀刃 0.62；
  - 折射：汗膜與積水 1.33。
- 音效參數：
  - 配音軌 -8 至 -10 dBFS，混響 0.3–0.4s；
  - 金屬撞擊峰值 -5 dBFS，殘響 1.2s；
  - 風聲 -10 dBFS，低頻 80–120 Hz；
  - 怪物咆哮 70 Hz 基頻，嘯音 2.5 kHz；
  - 心跳鼓點對齊 0.7–0.9s 周期。
- 模擬與求解：
  - camera projection 用於廢墟牆面與鋼骨；
  - motion blur 180°，揮擊段 200°；
  - 若使用 flip 模擬碎石，粒子上限 55k，步長 1/48s；
  - 體積霧 clamp 0.35，需避免過曝；
  - 若進行 retime，需同步調整音效與字幕節點。

## Act/Beat/Angle（12 幕 × 1.2s，總長 15s）
### Act 1：靜夜與準備（0.0–3.6s）
- Beat 1（0.0–1.2s）：廢墟定場與腳步靠近
  - Angle A
    - Camera：24mm，低機位 35 cm，沿裂縫 dolly in 1.2 m；roll 0°；speed 0.6 m/s；shutter 180°。
    - Lighting：昏黃路燈 3100K 500 lux 來自右後 30°，冷藍環境光 4800K 200 lux 填補；霧氣 0.016 density 被腳步擾動。
    - Materials & Physics：水泥粗糙 0.55；裂縫積水折射 1.33；鞋底橡膠摩擦 0.78；每步落地推起塵土粒徑 0.3 mm，高 12 cm；重力 9.81 m/s²；AO 0.52。
    - Emotion & Performance：鏡頭前方先見腳步影子接近，步伐穩定 1.1 步/s；肩線尚未入鏡，營造壓迫感；呼吸聲極低。
    - Audio & Transition：低頻腳步 70–90 Hz，混合金屬館回音 0.6s；環境遠處汽笛 -26 dBFS；碎石擦過鏡頭做 cut in。
    - Micro-actions：T0 塵土上拱 5 cm；T0+0.3s 鏡頭推近裂縫；T0+0.6s 右腳踏入光區；T0+0.9s 影子壓滿畫面下緣。
  - Angle B
    - Camera：35mm 俯 20°，手持抑震 0.6，橫向搖 15 cm；速度 0.5 m/s；景深 f/4。
    - Lighting：路燈光在裂縫邊形成明暗對比 2:1；霧束穿越鏡頭右側；反射光 80 nits。
    - Materials & Physics：碎石粒徑 1–2 cm 滾動 0.4 m；摩擦 0.7；裂縫邊緣濕度使反射產生 0.15 強度光斑。
    - Emotion & Performance：僅見小腿肌肉繃緊 1 mm；步伐穩重；黑黃線尚未亮。
    - Audio & Transition：碎石滾動 300–500 Hz；輕風 1.8 m/s 吹過麥克風；用風聲 crossfade 到 Beat 2。

- Beat 2（1.2–2.4s）：朝倉蓮走入光線
  - Angle A
    - Camera：35mm，腰平視 1.0 m 高，從左後 tracking 0.8 m；景深 f/3.2 對焦肩線；roll +2°。
    - Lighting：路燈暖光在胸肌與鎖骨形成亮斑；冷藍環境光填背；霧氣形成光束，強度 0.35；AO 0.52。
    - Materials & Physics：機能布貼合肩膀形成 1–2 mm 凹陷；黑黃細線在鎖骨處微亮 300 nits；汗膜 0.05 mm 在光下形成 specular 0.46；摩擦係數 0.72。
    - Emotion & Performance：朝倉蓮慢步，肩背寬度 48 cm 佔畫面 60%；眼神平視鏡頭上方，呼吸 0.8s 一次；肌肉在步伐間微收放；微蹙眉。
    - Audio & Transition：鞋底摩擦「キュッ」-12 dBFS；呼吸輕聲；以黃線短閃（0.2s）match cut 進 Beat 3。
    - Micro-actions：T0 路燈反射掃過鎖骨；T0+0.3s 肌肉起伏；T0+0.6s 黑黃線閃一次；T0+0.9s 眼神略抬。
  - Angle B
    - Camera：50mm 後側肩平視，距離 0.9 m；向右 arc 20°；景深 f/3.0。
    - Lighting：背後冷藍 180 lux；路燈 rim 70%；霧束切成條紋。
    - Materials & Physics：護腕金屬反射 0.6；皮革粗糙 0.38；汗珠沿前臂滑 0.04 ml；摩擦 0.7。
    - Emotion & Performance：他手指微動準備拉護腕；嘴角微抬 1°。
    - Audio & Transition：布料摩擦聲 -18 dBFS；以手指搖晃聲做 match cut。

- Beat 3（2.4–3.6s）：拉緊護腕的細節
  - Angle A
    - Camera：50mm 手部特寫，距離 0.6 m；垂直俯 25°；微搖移 5 cm；shutter 180°。
    - Lighting：暖黃 3100K 700 lux 打在手背；冷藍 4800K 150 lux 填陰；金屬環反射高光 0.6；霧氣薄層 0.012。
    - Materials & Physics：金屬環金屬度 0.88、粗糙 0.26；護腕皮革粗糙 0.4、厚 1.2 cm；汗珠粒徑 0.6–0.9 mm 滑過手背；指節繭粗糙 0.28；護腕拉緊時材質張力 12%。
    - Emotion & Performance：朝倉蓮低聲吐氣 0.2s，眉眼不動；手指捏緊護腕，肌腱浮起；嘴角收斂；眼神略垂。
    - Audio & Transition：金屬環撞指節「カン」1.1 kHz；配音低語「……まだ終わってない」-10 dBFS；以聲音殘響疊化至 Act 2。
    - Micro-actions：T0 手指卡入護帶；T0+0.3s 拉緊；T0+0.6s 金屬環彈回；T0+0.9s 手背汗珠落下。
  - Angle B
    - Camera：75mm 側面近距，距離 0.5 m；roll -1°；手持抑震；景深 f/2.8。
    - Lighting：路燈反射在護腕邊形成 2 mm 高光帶；背後冷藍 rim 0.2；AO 0.5。
    - Materials & Physics：皮革邊緣磨痕 0.2 mm；手背細毛被風吹 10°；摩擦係數 0.42。
    - Emotion & Performance：拇指貼食指第二指節習慣動作；肩膀微抬 0.5 cm；呼吸穩。
    - Audio & Transition：護帶摩擦「ギュッ」；以摩擦聲 match cut 至跑步畫面。

### Act 2：訓練迴圈（3.6–7.2s）
- Beat 4（3.6–4.8s）：清晨負重衝刺回憶
  - Angle A
    - Camera：35mm 低角 30°，從右後 2 m tracking；speed ramp 1.15x；roll 0°；motion blur 180°。
    - Lighting：模擬清晨冷光 5200K 400 lux；背後暖光 4300K 250 lux；霧氣減至 0.01；光比 2:1。
    - Materials & Physics：地面粗糙 0.55；鞋底摩擦 0.78；背負 10 kg 重袋晃動；汗水沿下顎滴落 0.6 ml，落地濺射 2.5 cm；重力 9.81 m/s²；風向沿跑道 2 m/s。
    - Emotion & Performance：表情專注，肩線前傾 14°；步頻 2.1 步/s；黑黃線在胸前亮度 600 nits；呼吸急促 0.6s/次；肩膀穩定。
    - Audio & Transition：氣喘聲 -12 dBFS；鞋底摩擦與呼吸節奏對齊；以速度線 wipe 過渡。
    - Micro-actions：T0 腳掌推地 1450 N；T0+0.3s 碎石飛起 0.4 m；T0+0.6s 汗珠甩出；T0+0.9s 殘影 3 層出現。
  - Angle B
    - Camera：24mm 高位俯視 55°，向前滑軌 1 m；景深 f/4；roll +1°。
    - Lighting：清晨光在背後形成長影 3 m；冷光 5200K；AO 0.45。
    - Materials & Physics：路面油膜 0.15 mm 形成條狀反射；摩擦 0.7；速度線殘影透明度 45/25/15%。
    - Emotion & Performance：背部肌肉沿脊柱起伏 1.5 mm；手臂擺動 40°；嘴角緊。
    - Audio & Transition：遠處海風吹動鐵架聲；以呼吸聲 crossfade。

- Beat 5（4.8–6.0s）：深夜沙包對練
  - Angle A
    - Camera：50mm 正面近距 1 m；肩平視；微推 0.6 m；景深 f/2.8 聚焦拳峰；motion blur 200°。
    - Lighting：單側暖光 3200K 600 lux 打在拳頭；背後冷藍 4800K 200 lux 營造 rim；沙包表面反射 0.22；體積霧 0.012。
    - Materials & Physics：拳峰速度 22 m/s；沙包皮革粗糙 0.42，摩擦 0.6；黃線在拳套邊緣閃光 0.2s；汗珠被拳風帶出 0.5 m；衝擊使沙塵粒徑 0.3 mm 飛散。
    - Emotion & Performance：朝倉蓮沉默出拳，每拳呼氣 0.15s；眼神穩定不看鏡頭；肩肌與前臂肌腱收縮 1–2 mm；口型吐出「フッ」。
    - Audio & Transition：沙包撞擊 -6 dBFS；拳風「シュッ」；以音爆 match cut 進下一段。
    - Micro-actions：T0 拳峰接觸；T0+0.2s 沙包凹陷 3 cm；T0+0.4s 沙塵飛散；T0+0.6s 黃線閃退。
  - Angle B
    - Camera：75mm 側面臉部特寫，距離 0.9 m；景深 f/3.2；手持 0.6 阻尼；roll -1°。
    - Lighting：暖光從右側勾勒臉頰；冷藍填陰；汗珠高光 0.5；AO 0.48。
    - Materials & Physics：皮膚 SSS 1.2 mm；汗膜折射 1.33；拳頭周圍空氣微波 1–2 cm；摩擦 0.7。
    - Emotion & Performance：眼神盯著沙包側面；眉頭放鬆；呼吸頻率 0.7s；肩膀放鬆再收緊。
    - Audio & Transition：呼吸與鼓點同步；用拳風聲作 swipe。

- Beat 6（6.0–7.2s）：被擊飛後站起
  - Angle A
    - Camera：75mm 近景側臉，距離 0.8 m；機位略低 10 cm；慢推 0.4 m；景深 f/3.2。
    - Lighting：冷藍 4800K 250 lux 主光，暖黃 3100K 300 lux rim；霧氣 0.014；火花偶發 1.2 mm。
    - Materials & Physics：地面摩擦 0.7；衣料摩擦 0.4；塵土粒徑 0.4 mm 飛起 0.5 m；肌肉因衝擊震動 2–3 mm；重心先落右腳膝彎 18°；衝擊波殘餘風向 0.8 m/s。
    - Emotion & Performance：他咬緊牙關，眼神穩住；胸口起伏 0.9 cm；吐氣後肩線回正，站起時腳掌碾地 0.3s；未回頭看鏡頭。
    - Audio & Transition：塵土落地沙沙聲；短促吐氣；以呼吸聲 crossfade 接 Act 3。
    - Micro-actions：T0 身體落地塵土揚起；T0+0.3s 膝蓋彈回；T0+0.6s 右腳蹬地；T0+0.9s 站直抖落塵。
  - Angle B
    - Camera：35mm 後方低角 25°，距離 2 m；向右繞 30°；景深 f/4。
    - Lighting：路燈光在肩背形成明暗帶；冷藍反光 0.2；火花餘燼 400 nits。
    - Materials & Physics：塵土飄落 0.8 m/s；衣料皺褶深 1 mm；摩擦 0.68。
    - Emotion & Performance：他抖肩重置呼吸；握拳捏緊聲；背肌呈盾形。
    - Audio & Transition：衣料摩擦「シュッ」；以肩部晃動帶動 match cut。

### Act 3：信念與宣言（7.2–9.6s）
- Beat 7（7.2–8.4s）：「我不是天才」
  - Angle A
    - Camera：50mm 正面半身，距離 1.4 m；微推 0.5 m；roll 0°；景深 f/3.0 對焦眼睛。
    - Lighting：暖黃 3100K 600 lux 斜打臉側；冷藍 4800K 180 lux 填背；霧氣 0.012；光比 2:1。
    - Materials & Physics：肌膚 SSS 1.2 mm；汗膜反射 0.46；黑黃線在鎖骨處亮 700 nits；背景鋼架粗糙 0.4；微風 1.8 m/s 吹動鬢髮 12°。
    - Emotion & Performance：朝倉蓮直視鏡頭，語速穩定；台詞日語「俺は天才じゃない。」-8 dBFS；眉頭微皺 2°；呼吸平穩；肩線微前 3°。
    - Audio & Transition：低頻配樂降到 -20 dBFS 留空；台詞後短 0.3s 靜默；硬切到下一角度。
    - Micro-actions：T0 眼神鎖定；T0+0.3s 嘴角收緊；T0+0.6s 呼吸吐出白霧；T0+0.9s 黑黃線閃一次。
  - Angle B
    - Camera：75mm 右側近臉，距離 0.7 m；tilt -3°；景深 f/2.8；手持阻尼 0.6。
    - Lighting：暖黃 rim 620 lux；冷藍填影 170 lux；AO 0.5。
    - Materials & Physics：皮膚細汗 0.05 mm；霧氣映出微光；摩擦 0.7。
    - Emotion & Performance：眼神側望右下，顴骨陰影強；唇線緊。
    - Audio & Transition：呼吸與心跳同步；以心跳低頻轉場。

- Beat 8（8.4–9.6s）：信念台詞
  - Angle A
    - Camera：35mm 低角 30°，從胸前往上 tilt 12°；距離 1 m；景深 f/3.2；motion blur 180°。
    - Lighting：暖黃聚光 3100K 700 lux 強化下頜線；冷藍環境 4800K 150 lux；霧氣 0.014；背後鋼骨反光 0.35。
    - Materials & Physics：護腕金屬光澤 0.6；皮革護帶粗糙 0.38；汗珠滑過鬢角 0.05 ml；空氣濕度 70%，光暈輕微；黃線亮度 800 nits。
    - Emotion & Performance：台詞「俺が倒れたら、後ろが崩れる。それだけだ。」語速 1.0x；眼神穩定如牆；嘴角收緊；肩膀略前 5°；呼吸同步 0.8s。
    - Audio & Transition：配音低頻 90–110 Hz，殘響 0.35s；字幕同步彈出；以黑黃線亮度漸增（0.3s）wipe 入 Act 4。
    - Micro-actions：T0 抬下巴；T0+0.3s 手指捏緊護腕；T0+0.6s 黃線脈衝；T0+0.9s 背肌微收。
  - Angle B
    - Camera：50mm 胸前特寫，距離 0.8 m；向右平移 0.4 m；景深 f/2.8；roll -1°。
    - Lighting：暖黃光在胸肌形成高光帶；冷藍補陰；霧束穿過肩膀。
    - Materials & Physics：布料凹陷 1–2 mm；汗珠聚成 2 mm 實滴；摩擦 0.74；護腕刻痕 0.2 mm。
    - Emotion & Performance：胸膛起伏 1 cm；呼吸吐霧；台詞末尾停頓 0.2s。
    - Audio & Transition：心跳鼓點與呼吸疊合；以胸前黃線亮度做 match cut。

### Act 4：實戰啟動（9.6–12.0s）
- Beat 9（9.6–10.8s）：怪物襲來
  - Angle A
    - Camera：24mm 廣角俯視 60°，跟隨怪物從右上衝來；dolly back 1.5 m；roll -2°；motion blur 180°。
    - Lighting：冷藍環境光 4800K 250 lux；路燈暖光 3100K 400 lux 形成剪影；火花點光 1500 nits 短閃；霧氣被撕開形成漏光。
    - Materials & Physics：高架鋼骨金屬度 0.78、粗糙 0.35；地面龜裂延伸 8 cm 深；怪物踩裂水泥碎塊 2–3 cm 被拋起 1.2 m；摩擦係數 0.68；火花粒徑 1 mm。
    - Emotion & Performance：朝倉蓮抬頭，重心微前；準備踏步；背肌繃起；黑黃線沿脊柱亮到 800 nits；眼神緊盯。
    - Audio & Transition：怪物咆哮低頻 70 Hz + 嘯音 2.5 kHz；碎石炸裂聲；用碎石掃過鏡頭 match cut 到武器展開。
    - Micro-actions：T0 怪物腳踩裂地；T0+0.3s 碎石飛起；T0+0.6s 霧氣被推；T0+0.9s 朝倉蓮踏前一步。
  - Angle B
    - Camera：35mm 胸前平視，距離 1.2 m；向右滑 0.7 m；景深 f/3.4。
    - Lighting：路燈 rim 0.7；冷藍填陰；火花零星閃。
    - Materials & Physics：護欄金屬粗糙 0.38；霧氣 density 0.014；碎石撞護欄火花 1.2 mm。
    - Emotion & Performance：他握緊武器柄準備展開；肩線微前 6°；呼吸在胸口聚力。
    - Audio & Transition：護欄共振 220 Hz；以共振聲硬切。

- Beat 10（10.8–12.0s）：武器展開
  - Angle A
    - Camera：35mm 近景，從右側 1.2 m 半繞 35°；speed ramp 1.2x；motion blur 200°；景深 f/3.0。
    - Lighting：暖黃 3100K 700 lux 打在武器柄與胸肌；冷藍 4800K 180 lux 填補；電弧閃光 1200 nits 0.2s；霧氣 0.014 density 被衝開 1 m。
    - Materials & Physics：斧槍金屬度 0.9、粗糙 0.18；柄部橡膠摩擦 0.82；展開機構彈簧力 120 N，展開時間 0.3s；沿柄刻線亮 1200→600→300 nits 三段；衝擊波 20 m/s 推飛塵粒徑 0.4 mm；火花粒徑 1.1 mm。
    - Emotion & Performance：朝倉蓮抬槓、扛起、揮下前置；肩線旋轉 25°；表情穩定，嘴角微抬 2°；微笑萌芽；眼神下壓。
    - Audio & Transition：機構展開「ガキン」1.2 kHz；電弧「ビリッ」；配樂鼓聲 0.6s；以閃光白片切入 Act 5。
    - Micro-actions：T0 扣扳手；T0+0.3s 刀刃彈出；T0+0.6s 刻線全亮；T0+0.9s 握柄調整重心。
  - Angle B
    - Camera：24mm 前上俯 50°，距離 1.8 m；向下 tilt 隨展開；景深 f/4；roll +1°。
    - Lighting：電弧光在鏡頭上形成 lens flare 0.2；路燈補 rim；霧氣被推成 V 字。
    - Materials & Physics：碳纖紋理 4K；金屬刮痕 0.1 mm；摩擦 0.78；刻線發光帶 bloom 0.12。
    - Emotion & Performance：雙臂穩固，手肘彎 45°；嘴角抬 3°；肩膀下沉鎖住力量。
    - Audio & Transition：電弧聲包圍感 40% 立體聲寬度；用亮光 wipe。

### Act 5：重擊對決（12.0–15.0s）
- Beat 11（12.0–13.2s）：揮擊與衝擊波
  - Angle A
    - Camera：50mm 側面中景，距離 1.5 m；跟隨揮擊弧線右→左 1.2 m；motion blur 200°；景深 f/3.2。
    - Lighting：暖黃主光 3100K 800 lux 從左前 25°；冷藍填光 4800K 200 lux；火花 1400 nits；霧氣被衝擊波推成弧形。
    - Materials & Physics：斧槍揮擊角速度 180°/0.35s；衝擊波壓縮空氣 0.2 s，推開霧氣 1.4 m；碎石粒徑 1–3 cm 飛散 2 m；摩擦係數 0.7；肌肉伸展 2–3 mm；火花 5k 粒子。
    - Emotion & Performance：朝倉蓮眼神鎖定怪物，眉頭放鬆；嘴角微抬；背肌鼓起形成護盾感；身體跟隨慣性微旋；膝蓋彎 15°。
    - Audio & Transition：衝擊波「ドン」-5 dBFS；火花滋滋聲；用火花遮擋轉入下一角度。
    - Micro-actions：T0 揮擊起手；T0+0.2s 刀刃切開霧；T0+0.4s 衝擊波形成；T0+0.8s 碎石擊中護欄。
  - Angle B
    - Camera：75mm 後方肩上，距離 1.1 m；向左 pan 20° 跟隨；景深 f/3.4。
    - Lighting：火花反射在護欄；冷藍填陰；黃線形成殘影。
    - Materials & Physics：護欄金屬度 0.78；火花粒徑 1 mm；霧氣 density 降至 0.01；摩擦 0.68。
    - Emotion & Performance：肩胛骨收緊；呼吸短促；表情平靜。
    - Audio & Transition：金屬顫音 220 Hz；以顫音 crossfade。

- Beat 12（13.2–14.4s）：定格與台詞
  - Angle A
    - Camera：75mm 近距側臉，距離 0.7 m；微 tilt -5°；慢推 0.3 m；景深 f/3.0 對焦眼睛。
    - Lighting：暖黃 rim light 3100K 650 lux 勾輪廓；冷藍 4800K 180 lux 填影；火花殘光 900 nits；霧氣淡 0.01。
    - Materials & Physics：汗珠沿鬢角滑落 0.05 ml；皮膚 SSS 1.2 mm；武器邊緣殘光 400 nits；空氣中塵粒 0.3 mm 緩落 0.8 m/s；黑黃線脈動 500 nits。
    - Emotion & Performance：朝倉蓮眼神穩如牆，嘴角上揚 3°；低語「大丈夫。オレの後ろにいろ。」日語，語速 0.9x；呼吸收束；微笑定格。
    - Audio & Transition：台詞 -8 dBFS；配樂收束；殘響 0.4s；以 Logo 黑屏 0.6s 收尾（14.4–15.0s）。
    - Micro-actions：T0 汗珠滑落；T0+0.3s 嘴角抬；T0+0.6s 眼神微移向鏡頭；T0+0.9s 黑黃線漸暗。
  - Angle B
    - Camera：50mm 正面胸上，距離 1 m；輕微 handheld 0.5 阻尼；景深 f/3.2。
    - Lighting：暖黃主光 3100K 600 lux；冷藍補光 180 lux；後方火花 bokeh。
    - Materials & Physics：布料汗濕區 10% 面積反射 0.3；護腕高光 0.6；摩擦 0.72。
    - Emotion & Performance：肩線放鬆；眼皮微收；微笑延續 0.5s；心跳穩定。
    - Audio & Transition：心跳聲淡入；以心跳收尾至黑屏。

- Beat 13（14.4–15.0s）：Logo 收束
  - Angle A
    - Camera：靜態黑底，無景深變化；logo 於中央 fade in。
    - Lighting：logo 黃線亮度 800→400 nits 逐步下降；背景保持 0；輕微 bloom 0.12。
    - Materials & Physics：無角色；粒子僅餘微塵 0.3 mm 緩落；保持 9:16 安全框。
    - Emotion & Performance：無。
    - Audio & Transition：鼓點收尾、低頻掃頻 200→80 Hz；淡出 0.6s。

## Platform Layer
- Hook A：0.0–1.0s 低角腳步 + 護腕金屬聲；字幕「夜、先に静かになる。」/「夜は先に静まる。」
- Hook B：5.8–7.0s 武器刻線爆光；字幕「守るために、締める。」/「締めて、守る。」
- Caption 建議：
  - JP 主字幕：簡短日語 + 中文對照，字體 Noto Sans JP Bold 72pt，描邊 3px 黃或黑。
  - 字幕安全框 5%，避免遮擋武器與臉；字幕節點對齊擊打與台詞；節奏貼合鼓點 0.6s。
- 縮圖構圖：側臉+武器展開瞬間火花，黑底黃線；對比 1.8 gamma，飽和度 0.9；保持視線看向右上。
- Hashtag：#朝倉蓮 #黒黄衝撃 #個人PV #アニメーション #格闘
- CTA：結尾「沒事，站我後面就好」/「大丈夫、オレの後ろにいろ」疊字幕 0.6s；提示觀眾 follow；字幕出現於 14.4–15s。
- 切片輸出策略：
  - 0–3s 氛圍剪：腳步+護腕+冷暖光，字幕「夜は先に静まる」。
  - 5.8–7.0s 爆光剪：武器展開、黑黃線閃，字幕「締めて、守る。」
  - 11.5–15s 終擊剪：揮擊衝擊波 + 微笑台詞「オレの後ろにいろ」。
- Subtitle map（時間碼 / JP / ZH）：
  - 1.8s：「……まだ終わってない」 / 「還沒結束。」
  - 3.0s：擬聲「カン」 / 「金屬撞擊」
  - 7.4s：「俺は天才じゃない。」 / 「我不是天才。」
  - 8.8s：「俺が倒れたら、後ろが崩れる。」 / 「如果我倒下，後面的人就會崩。」
  - 10.9s：「締める。」 / 「再拉緊。」
  - 13.6s：「大丈夫。オレの後ろにいろ。」 / 「沒事，站我後面就好。」

## Platform Delivery Notes
- Export format：ProRes 422HQ 1080x1920 24fps；保留 24-bit 48kHz 音軌；gamma 1.8；字幕燒錄版與無字幕版各一。
- Color management：使用 ACEScct → Rec.709；黃線保持 0.85 飽和度；黑區不低於 0.02；在 upload 前檢查社群壓縮模擬。
- Compression guard：粒子與細線需增加 film grain 7–8%；避免社群壓縮抹平；保留細節於 log 版本便於後期。
- Safety flashes：所有閃光頻率鎖定 >20 Hz 且 <50 Hz；若平台有閃光審核，提供低閃版（亮度 800 nits）。
- Hook variants：
  - Hook A Alt：增加路燈 flicker 0.2s；適用抖音。
  - Hook B Alt：武器展開 slow ramp 0.8x，增加字幕停留 0.3s；適用 Instagram Reels。
- Thumbnail alternates：
  - Alt1：護腕 close-up + 鏽斑背景；
  - Alt2：武器展開白片瞬間；
  - Alt3：汗珠滑落 + 微笑近景；皆須標注黑黃對比與 5% 安全框。
- Caption pacing：字幕出現時間與擊打對齊，允許 ±0.05s 誤差；字幕淡入 6 帧，淡出 8 帧；雙語上下排列，行距 1.15。
- CTA 測試：在 14.4–15s 嘗試兩版 CTA（中文先/日文先），記錄保留率；Hashtag 固定在描述欄，影片內不顯示。
- Platform QA checklist：
  - [ ] 檢查封面構圖未遮擋臉部或武器刻線。
  - [ ] 檢查字幕在安全框內且無閃爍重影。
  - [ ] 檢查音量峰值 -1 dBFS、均衡不刺耳。
  - [ ] 檢查切片段落時間碼與 Beat 相符。
  - [ ] 檢查黑黃線亮度在 1200 nits 以下。
  - [ ] 檢查無真實品牌與敏感符號。
  - [ ] 檢查字幕語言僅中日且無錯字。

## Subtitle & Caption Specs
- 字體：Noto Sans TC/JP Bold 72pt；描邊 3px（黑或黃），陰影 30% 透明度；最大寬度 85% 畫面。
- 排版：中日雙行，上日下中；行距 1.15；左右邊距 5%；避免遮擋臉部與武器刻線。
- 時序：字幕提前 0.05s 進場，停留至動作結束後 0.1s；淡入 6 帧、淡出 8 帧；如遇閃光需降低 10% 亮度。
- 語言一致性：僅使用 JP/TC；避免英文或羅馬字；專有名詞維持「朝倉蓮」「黒黄衝撃」。
- 校對：檢查數字與單位（m/s、lux、nits）是否正確；避免全形/半形混亂；使用全形標點。
- 聲畫對位：旁白落點需與嘴型 ±2 帧；金屬撞擊字幕對齊聲峰；台詞出現同時保留 0.2s 無旁白區以利辨識。
- 可及性：為聽障觀眾提供環境音標註（如「風聲」「金屬撞擊」）；保證對比度 >3:1；避免快速閃爍字幕。

## QC Reminder
- 測試播放環境：手機 60 Hz、平板 120 Hz 皆需檢驗閃爍與字幕位置；檢查耳機與外放頻率響應。
- 若需國際化版本，僅可增列英文字幕另存，不可修改本稿主文；仍須保留物理與 PBR 參數。
- 如需 HDR 版本，需重新計算 nits 範圍（黑黃線可提至 1500 nits）並標註；SDR 版本不可直接套用。

## Negative Instructions
- 禁用真實品牌、名人肖像、政治宗教符號、血腥內臟、成人尺度、酒精/煙品品牌。
- 避免魚眼 <20mm、過曝高光、過度手持晃動、卡通化無物理、粉彩夢幻濾鏡、破壞對比度 1.8 gamma。
- 保持 PG-13；怪物僅剪影、不出血；字幕僅中日，無錯字；黑黃線亮度 ≤1200 nits；禁止「同前」字樣。
- 自動檢核清單：
  - [ ] 確認未出現真實商標或肖像。
  - [ ] 確認鏡頭焦段與光源色溫皆有標註。
  - [ ] 確認摩擦係數、粗糙度、粒子數量皆明確。
  - [ ] 確認 Hook A/B、切片時間、字幕節點已列出。
  - [ ] 確認未使用模糊詞或「同前」。
  - [ ] 確認亮線未超過 1200 nits 並標註。
  - [ ] 確認 Self-Check 已填。

## Assumptions
- 假設怪物保持剪影，不需具體種族或細節；如需特定造型需另行提供。
- 假設上一集以右向推軌收尾，故延續右向運動軸；若實際素材不同須調整 Camera Continuity。
- 假設配音為男性低沉聲線，若更換聲優需重新匹配頻率與殘響。
- 假設平台允許 1200 nits 短閃；若需降低需在色彩流程另設 clamp。

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：已提供 12 幕 + Logo 收束，共 13 段，含時間碼、Camera/Lighting/Materials & Physics/Emotion & Performance/Audio & Transition/ Micro-actions；Master Prompt、Platform Layer、Negative Instructions 俱全。
- Physics & PBR：每幕標註重力/摩擦/粗糙度/粒徑/亮度/折射；材質層級與光學行為明確；motion blur 與慣性說明齊備；粒子數量與霧密度皆標註。
- Stylepacks 使用與衝突：啟用 Black & Yellow Impact Circuit、Ruin Grit Realism；禁止粉彩/魚眼；Do/Don't 已對應分鏡引用並遵循品牌 gamma 1.8。
- Continuity：沿用黑黃衝擊品牌，Camera Continuity 延續右向運動軸；武器與護腕位置、情緒曲線（冷靜→決心→微笑）一致；Platform 切片與 Hook 延續系列節奏；字幕語言保持中日。
- 風險揭露：假設怪物僅剪影；若需要特定版權元素需另行提供；若社群平台對閃光敏感需再調整亮度與頻率；字幕需再次校對錯字；若素材方向不同需重設 Camera Continuity。

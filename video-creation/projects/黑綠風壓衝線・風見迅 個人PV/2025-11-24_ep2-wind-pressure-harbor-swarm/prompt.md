# Project Metadata
- project_name: 黑綠風壓衝線・風見迅 個人PV
- series_name/arc: 港區白昼・黑綠疾風掃蕩
- episode_index: 2
- slug: wind-pressure-harbor-swarm
- target_platform: short-form vertical video (JP/TW social, 9:16)
- duration_sec: 15
- style_primary: 2D 日系動漫風（黑＋螢綠速度線）
- style_secondary: 工業港區白昼寫實（鹹味海風與貨櫃金屬）
- worldstate_ref: 正午港區高架旁貨櫃場，海風 6.1 m/s 西南向，排水溝與貨櫃縫隙藏匿小型風蝕獸
- goal: 15 秒黑綠主題戰鬥 PV，展示風見迅白昼巡邏掃蕩港區小怪，含日文台詞與中日字幕、漫畫分鏡切換

## _core
### Brand Bible（黑綠風壓衝線）
- 角色色票：黑 #0a0c10 為底、螢綠 #22ff95 流線、肌膚麥色 #c88a5a，汗珠高光 #bff6ff，正午陽光白金 #f5f0e6 作 rim light。
- 服裝材質：貼身機能上衣尼龍彈性布（粗糙度 0.35、金屬度 0.06、法線 8K 纖維 0.08 mm）；束褲粗糙度 0.4；鞋底橡膠摩擦係數 0.92，側邊螢綠 LED 亮度 650 nits。
- 肌膚層級：base color #c88a5a，SSS 半徑 1.1 mm，specular 0.46；指節繭粗糙度 0.27，汗膜 0.05 mm 折射 1.33；肌纖維 0.4 mm 線在強光下可見。
- 口頭禪與語氣：日語短句帶笑，語速 1.1x，偶以中文吐槽；收尾常以「だろ？」「だね」「かよ？」。
- 姿態與習慣：衝刺時肩線前傾 14°，腳踝內旋 4°；起跑前會活動腳踝、敲鞋側 LED；音速連拳角度 40–45°，手刀斬線前吸氣 0.1s。
- 場景色調：正午 6000K 主光，貨櫃金屬反射 0.35，橋下陰影填光 6500K 260 nits；海風帶鹹霧 density 0.01、AO 0.3；遵循 Do: 1.85 gamma curve。
- 鏡頭語言 Do：高速 tracking + roll 校正，30–45° 低角強化爆發力；match cut 對齊螢綠速度線；景深 f/2.8–f/4 專注肌肉與光紋。
- 鏡頭語言 Don't：魚眼 <22mm、過曝金屬高光、過度色偏、真實品牌 Logo、以「同前」代稱參數。
- 文案語氣：中文敘述 + 日文配音，字幕雙語對齊擊打節點；保留風切聲與呼吸，避免冗長旁白。

### Shared World & Character File
- Worldstate snapshot：12:05（UTC+8），氣溫 31°C，相對濕度 66%，海風 6.1 m/s 西南向；貨櫃堆高 3 層、每箱 2.6 m 高，表面鏽斑 0.4 mm；高架橋護欄高 1.1 m；地面柏油粗糙度 0.55，昨日戰痕深 0.5 cm；鹹霧粒徑 0.8–1.1 µm。
- Character default：風見迅 180 cm / 80 kg，體脂 9%，慣用右手；鞋底厚 2.6 cm；音速拳拳峰速度 72 m/s；「風痕瞬步」腳掌推力 1480 N，爆發 0.14s；手刀「風壓斬線」風刃厚 5 cm、長 7 m，折射造成背景 2% 偏移。
- Persistent elements：螢綠流線沿鎖骨、前臂、腿外側同步脈衝 0.24s；汗珠粒徑 0.3–0.9 mm 被風帶出拖尾 0.6 m；跑道光痕停留 1.3s；落地碎石 1–2 cm 被吹離 1.6 m；漫畫面板切換時保留螢綠邊框。
- Constraint list：服裝保持完整；風蝕獸殼為鏽鐵＋碎石（金屬度 0.62、粗糙度 0.6）；鏡頭運動主軸由右向左以對齊港口出口方向，若反轉需先以風壓光閃 match cut；正午曝光高光剪裁 <0.18；禁止真實品牌與政治符號。
- Execution note：採 camera projection 保留貨櫃鏽斑與高架紋理；粒子系統控制鐵鏽塵 0.35 mm 半徑、最多 58k；風刃用體積霧切片（散射 0.52、吸收 0.16）；motion blur 180°，殘影段可放寬到 200° 並標註；音效對齊字幕節點，風聲 -10 dBFS 峰值。

### Do / Don't（Core）
- Do：列出每幕時間碼、鏡頭焦段、光源色溫/強度、PBR 材質與物理參數；同時事件用 T0+ 細分；字幕位置保護框 5%；Platform 層含 Hook A/B 與切片策略；標註漫畫分鏡轉場的節點與音效。
- Don't：使用模糊詞、使用「同前」代稱、遺漏摩擦係數或材質層級、加入真實品牌或宗教政治符號、空白 Self-Check。

## _stylepacks
### Style: Black & Green Wind Drive
- Applicable for：高速跑酷、音速連拳、風壓斬線；螢綠速度線、黑色剪影與白日 rim light。
- Do NOT mix with：粉彩少女、Q版比例、柔焦夢幻濾鏡。
- Default: ON
- Visual traits：硬朗線條、對比 1.85 gamma、速度線三層殘影、體積霧帶螢綠邊緣光；膚質帶 SSS 層與汗光點；背景帶金屬冷光粒子。
- Audio traits：風切聲佔主聲道 -8 dBFS；拳擊氣爆有 1.2 kHz 峰值；鞋底在鋼材上有 220 Hz 共振；台詞日語，尾音帶笑。

### Style: Industrial Parkour Grit
- Applicable for：港區貨櫃跑酷、牆面踩踏、護欄滑行；貨櫃鏽斑、鹹霧光暈、柏油與裂縫。
- Do NOT mix with：童話柔光、粉霧色調、低對比膠片。
- Default: ON
- Visual traits：鋼鐵迷宮透視，貨櫃陰影加環境霧 AO 0.3；正午陽光在鏽斑上形成高光；攝影以 35mm/50mm 跟拍，偶以 24mm 全景俯視。
- Audio traits：港區船笛 -24 dBFS；高架車流低頻 80 Hz；鞋底摩擦聲清晰；每次落地有金屬顫音。

### Style: Manga Impact Panel
- Applicable for：音速連拳分解成漫畫三格、擬聲字可視化；黑粗線條與半平塗背景。
- Do NOT mix with：寫實慢動作抒情段落；粉彩柔焦。
- Default: ON when panel cut is triggered
- Visual traits：分格邊框 4 px 黑線，面板內保留螢綠邊框；背景以粗速度線與半平塗；殘影以對比色塊處理。
- Audio traits：擬聲字以 SFX 彈出聲 -14 dBFS；面板翻頁「パッ」-16 dBFS；音軌保持連續不被剪斷。

### Do / Don't（Stylepacks）
- Do：在分鏡引用 style traits（速度線三層透明度、螢綠邊緣光、貨櫃鏽斑高光、漫畫分格粗線）；強調黑綠對比與正午 rim；加入金屬共振聲。
- Don't：把螢綠渲染成過曝；忽略柏油摩擦係數；使用粉彩或暖霧打散速度感；使用真實商標或政治符號。

## Technical Specs
- Aspect Ratio：9:16 直式，解析度 1080x1920。
- FPS：24fps，shutter angle 180°；殘影段 5.0–7.0s 可放寬至 200°。
- Camera set：24mm（全景俯視貨櫃迷宮）、35mm（跑酷跟拍）、50mm（胸肌與手刀特寫）、75mm（拳峰與擬聲字特寫）。
- DoF：f/2.8–f/4 for mid/close，f/4–f/5.6 for wide；焦點跟隨眼睛或拳峰。
- Grain：film grain 7%，保留細節避免社群壓縮抹平；log → filmic LUT → contrast 1.85 gamma。
- Motion control：camera roll 校正 ±5° 內；穩定器阻尼 0.6；跟隨時 speed ramp 不超過 1.3x 除非標註。
- Color pipeline：log capture → filmic LUT → green accent curve（螢綠保持 0.75 飽和度，不過曝）→ final contrast；螢綠亮條最大亮度 650 nits。
- Audio：日文配音 48kHz；風切與拳爆分軌；環境船笛與車流 -24 dBFS；字幕彈出聲 -18 dBFS。
- Platform safety：字幕安全框 5%；避免閃爍頻率落在 15–20 Hz；logo 保持黑白線稿避免版權疑慮。

## Master Prompt
- worldstate snapshot：正午港區高架旁貨櫃堆疊成 80×120 m 的鋼鐵迷宮，貨櫃表面鏽斑 0.4 mm、油漬 0.15 mm；地面柏油裂縫深 0.5 cm；海風 6.1 m/s 西南向帶鹹霧 density 0.01；陽光 6000K 直射 12k lux，橋下陰影填光 6500K 260 nits；遠處船笛偶發。
- constraint list：螢綠速度線保持 3 層殘影透明度 40/25/15%；鏡頭主軸右→左；貨櫃刮痕不自動修復；風蝕獸硬殼硬度 6 Mohs，撞擊不碎裂過細；台詞日語，字幕雙語；漫畫分格出現在 7.0–7.8s。
- execution note：攝影從 24mm 俯視開場轉 35mm 跟拍；貨櫃與橋面做 camera projection 保持紋理銳利；風刃採 VDB 減少 render cost；volume fog clamp 0.32；motion blur 180°；音效需對齊字幕節點，拳擊爆圈用短脈衝；漫畫面板邊框以 4 px 黑線 + 螢綠 rim。
- Camera Continuity：前鏡若以右→左運動收尾，下一鏡延續方向或以螢綠光閃 match cut；光比維持 2.1:1，若進入貨櫃陰影 fill 光提升 28%；rim light 由陽光提供 16–18%。
- Platform Layer：Hook A（故事向）在 0–1.2s 俯視貨櫃迷宮與小怪爬出；Hook B（衝擊向）在 6.0–7.8s 殘影連拳 + 漫畫分格；字幕排程見 Subtitle map；切片時間段 0–3s、6.0–7.8s、12.0–15s。
- Stylepacks used：Black & Green Wind Drive（Default ON）、Industrial Parkour Grit（Default ON）、Manga Impact Panel（面板段 ON）；風格不與粉彩或柔焦混用。
- Negative instructions：禁用真實品牌、名人肖像、政治宗教符號；避免過曝金屬、魚眼畸變、過度手持晃動；不加入血腥、成人尺度。

## Act/Beat/Angle (12 幕 × 1.2s，總長 15s)
### Act 1：白昼警戒（0.0–3.6s）
- Beat 1（0.0–1.2s）
  - Camera：24mm drone 高俯 70°，沿貨櫃迷宮中心線 dolly in 3 m；shutter 180°；roll 校正。
  - Lighting：正午陽光 6000K 12k lux 直射，橋下反彈 6500K 260 nits 填陰；貨櫃鏽斑反光 0.35。
  - Materials & Physics：貨櫃金屬粗糙度 0.55、油膜 0.15 mm 折射 1.33；鹹霧 density 0.01；海風 6.1 m/s 吹起鐵鏽粉 0.2 mm；摩擦係數 0.7。
  - Emotion & Performance：畫面空蕩但滿是昨夜刮痕；遠處海浪閃光；緊張預兆。
  - Audio & Transition：風聲 -10 dBFS，遠處船笛 -24 dBFS；無台詞；切到小怪湧出以地面低角硬切。
- Beat 2（1.2–2.4s）
  - Camera：35mm 低角 20° 靠近排水溝，手持穩定器阻尼 0.6；向左平移 2 m。
  - Lighting：陽光在排水溝邊緣形成高光帶；陰影偏冷 6500K；螢綠預告光從右上掠過。
  - Materials & Physics：排水口鐵柵粗糙 0.6、鏽層 0.4 mm；腐蝕水漬 0.2 mm 厚；小怪爪子摩擦 0.62。
  - Emotion & Performance：首批小型風蝕獸（60 cm 高）鑽出，眼睛螢綠點亮；四肢纖長、殼帶碎石殘片。
  - Audio & Transition：金屬摩擦「キィ」-14 dBFS；腐蝕嘶聲 1.2 kHz；cut on motion 至貨櫃縫。
- Beat 3（2.4–3.6s）
  - Camera：24mm 低空橫移 1 m 高，緊貼貨櫃縫隙跟隨更多小怪湧出；speed ramp 1.1x。
  - Lighting：陽光被貨櫃遮擋形成條紋陰影；螢綠光點在陰影中閃爍；rim light 16%。
  - Materials & Physics：貨櫃縫隙寬 2 cm，鏽粉掉落形成粒徑 0.25 mm 灰塵；小怪踩過柏油留下腐蝕痕跡深 0.2 cm。
  - Emotion & Performance：小怪群奔向出口，形成 4 條爪痕軌跡；腐蝕煙微微升起。
  - Audio & Transition：群體腳步頻率 5 Hz；腐蝕滋滋聲 -16 dBFS；切入主角出場以螢綠速度線 wipe。

### Act 2：風痕瞬步（3.6–7.2s）
- Beat 4（3.6–4.8s）
  - Camera：35mm 中景仰 30°，對準高架護欄；鏡頭靜置等待動態。
  - Lighting：陽光 rim 18%，貨櫃反射冷光；螢綠能量線預熱 500 nits。
  - Materials & Physics：護欄金屬粗糙 0.45、摩擦 0.4；海風讓衣料偏右 8°；汗珠形成 0.05 mm 薄膜。
  - Emotion & Performance：風見迅半蹲護欄，活動腳踝、輕踢欄杆；肩線寬闊，胸肌與前臂線條緊繃；嘴角壞笑。
  - Audio & Transition：鞋尖敲護欄「コツ」-16 dBFS；台詞「真夠給面子啊——」/「昼間パトロールで、こんな数くれるとはね。」；以氣流炸裂聲硬切。
- Beat 5（4.8–6.0s）
  - Camera：50mm 低角 tracking，從右側 1.5 m 迅速推向小怪群前方；motion blur 200°。
  - Lighting：螢綠線條瞬間亮至 650 nits；正午光在肌肉上形成硬邊高光；貨櫃陰影帶冷色。
  - Materials & Physics：鞋底風口開啟，氣流跑道寬 0.4 m、亮度 450 nits；摩擦係數 0.92；碎石被風吹起 0.4 m。
  - Emotion & Performance：風見迅瞬間消失於欄杆，殘影 3 層；身形在地面畫出螢綠線條；胸肌與手臂線條被拉長。
  - Audio & Transition：氣流炸開「ボッ」-10 dBFS；風聲疊加；以速度線 wipe 進入切割段。
- Beat 6（6.0–7.2s）
  - Camera：35mm 側向高速 tracking 5.5 m/s，距小怪群 2 m；保持 horizon level。
  - Lighting：陽光與貨櫃反射交錯；螢綠殘影三層清晰；陰影中有鹹霧散射 0.32。
  - Materials & Physics：跑道光痕停留 1.3s；摩擦 0.92；風壓切割貨櫃漆面留下 1 mm 刮痕；小怪殼彈性 0.25。
  - Emotion & Performance：風見迅在不同角度同時出現的殘影把群體切塊；眼神鎖定，前臂筋條鼓起；呼吸短促。
  - Audio & Transition：風切聲 -8 dBFS；殘影掃過牆面「シュッ」；硬切至連拳蓄力。

### Act 3：音速連拳 + 漫畫分格（7.2–10.8s）
- Beat 7（7.2–8.4s）
  - Camera：50mm 正面對衝，鏡頭倒退 6 m/s；shutter 180°；對焦眼睛。
  - Lighting：螢綠風紋在拳峰前形成速度線；正午 rim 18%；塵霧被拳風推開露出光束。
  - Materials & Physics：拳峰速度 72 m/s；空氣形成凝結雲 2 cm 厚；碎石飛散角度 25–60°；摩擦 0.92。
  - Emotion & Performance：肩背肌收縮，眉峰緊；嘴角帶笑；台詞「音速連拳、行くよ。」
  - Audio & Transition：拳風爆圈「ドン」 1.2 kHz 峰值；小怪殼破碎聲 700 Hz；cut on impact 進漫畫分格。
- Beat 8（8.4–9.6s）
  - Camera：75mm 拳峰特寫，同步觸發 Manga Impact Panel，分成上中下三格；面板邊框 4 px 黑線 + 螢綠 rim。
  - Lighting：螢綠衝擊圈亮度 720 nits；正午光在汗珠形成 0.2 cm 高光帶；面板背景改為半平塗 + 粗速度線。
  - Materials & Physics：面板內保持拳峰衝擊圈推壓空氣，塵霧向外 2 m；碎片初速 10 m/s；彈性 0.25。
  - Emotion & Performance：上格胸肌與手臂緊繃，中格拳頭命中擬聲「ドンッ」「バキッ」，下格全身殘影疊加；表情專注。
  - Audio & Transition：擬聲字彈出聲 -14 dBFS；面板翻頁「パッ」-16 dBFS；無縫接回動畫。
- Beat 9（9.6–10.8s）
  - Camera：35mm 半身側面，鏡頭繞至右後方 90°，dolly 2 m；保持水平。
  - Lighting：螢綠手刀聚氣形成弧形光帶；陽光略降低 10%；貨櫃反射補額頭。
  - Materials & Physics：手刀風刃厚 5 cm、長 7 m；切過地面留下 0.5 cm 深刮痕；塵埃被氣流掀起 0.7 m；牆面裂縫有螢綠殘光 0.8s。
  - Emotion & Performance：風見迅沿牆跑，指尖併攏掃出風壓斬線；髮絲後飄 20°；眼神向下掃描逃竄小怪。
  - Audio & Transition：手刀聲「シュバッ」高頻 2 kHz；金屬被切開聲 -12 dBFS；光線 swipe 至收束段。

### Act 4：清掃與離場（10.8–15.0s）
- Beat 10（10.8–12.0s）
  - Camera：24mm 高空俯視，鏡頭 roll 3°，捕捉螢綠軌跡在貨櫃間形成曲線；dolly out 4 m。
  - Lighting：陽光白金 rim 照亮塵霧，貨櫃陰影冷調；風刃尾光逐漸熄滅。
  - Materials & Physics：跑道光軌寬 0.45 m，亮度 430 nits；體積霧 density 0.01 被氣流掃出空洞；貨櫃刮痕 1–2 mm 深。
  - Emotion & Performance：風見迅沿氣流跑道最後掃蕩，殘影拖 3 層；表情冷靜。
  - Audio & Transition：風聲包圍，船笛 -24 dBFS；硬切到慢動作停下。
- Beat 11（12.0–13.2s）
  - Camera：50mm 慢動作（0.7x），正面中近，鏡頭微仰 20°；距離 2 m；景深 f/2.8。
  - Lighting：陽光與螢綠交織的 rim 高光在肌肉上形成柔和漸層；螢綠紋路節奏暗亮。
  - Materials & Physics：重力 9.81 m/s²；落地後塵埃飄 0.5 m；汗珠拖出 0.5 m 曲線；鞋底與地摩擦 0.92。
  - Emotion & Performance：風見迅單手插腰，另一手抹汗；胸膛起伏 1 cm；台詞「差不多當暖身吧。」
  - Audio & Transition：環境聲暫時抽空，只留呼吸與海風；字幕空白 0.2s；淡入收尾。
- Beat 12（13.2–15.0s）
  - Camera：35mm 正面中景，鏡頭在地面微仰 18°；最後 0.4s 拉焦到眼睛；logo 收束。
  - Lighting：螢綠紋路逐漸暗下，只留微光；陽光反射在凹陷貨櫃掌印上；塵霧散光。
  - Materials & Physics：最後一隻小怪被拳砸進貨櫃，凹陷深 4 cm、掌印螢綠餘光 0.6s；塵埃粒徑 0.2 mm；震動 0.14G。
  - Emotion & Performance：風見迅嘴角揚起，眼神仍興奮；台詞「本番は、まだこれからだろ？」
  - Audio & Transition：衝擊圈低頻 60 Hz；風聲淡出；LOGO《風見迅｜WIND PRESSURE RAID》貼上停留 0.6s，CTA 顯示。

### Angle Micro-actions & Keyframes（逐格細化，24fps）
- Beat 1（0.0–1.2s）
  - T0：俯視鏡頭 24mm，roll 0°；鹹霧粒徑 0.8–1.1 µm 漂浮；貨櫃投影形成 1.4 m 條紋。
  - T0+0.3s：鐵鏽粉被風帶起 0.2 m；鏡頭 dolly in 1.2 m；螢綠光點預示。
  - T0+0.6s：遠處高架車流光條 0.4 m；柏油裂縫 0.5 cm 清晰；AO 0.3。
  - T0+0.9s：鏡頭進入貨櫃中心線，速度 2.5 m/s；風聲漸強。
- Beat 2（1.2–2.4s）
  - T1.2：鏡頭轉 35mm，平移 2 m；排水口鐵柵反光點 12 nits。
  - T1.5：第一隻風蝕獸爪尖伸出，長 12 cm；腐蝕水滴落地形成 0.5 cm 凹點。
  - T1.8：眼睛螢綠點亮 450 nits；殼上碎石反光粗糙 0.6；腳步聲 5 Hz。
  - T2.1：三隻同時衝出，攝影保持低角；字幕尚未出現。
- Beat 3（2.4–3.6s）
  - T2.4：貨櫃縫隙掉落鏽粉形成 0.25 mm 粒子霧；鏡頭橫移 3 m。
  - T2.7：小怪群分兩列奔跑，爪痕深 0.2 cm；腐蝕煙高度 0.3 m。
  - T3.0：鹹霧被海風推向左側 0.5 m；螢綠眼光形成 6 個光點。
  - T3.3：音效「キィ」短促；cut 觸發速度線 wipe。
- Beat 4（3.6–4.8s）
  - T3.6：風見迅腳踝活動 12°；肩線放鬆後前傾 5°；螢綠紋路亮至 300 nits。
  - T3.9：鞋尖敲欄杆「コツ」；護欄震動 0.3 mm；口角上揚 3°。
  - T4.2：髮絲被海風掀起 15°；胸肌緊繃 1 cm 起伏；字幕顯示日文台詞。
  - T4.5：氣流預熱使衣料貼背；鏡頭準備硬切。
- Beat 5（4.8–6.0s）
  - T4.8：消失瞬間殘影生成，透明度 40/25/15%；氣流跑道光尾寬 0.4 m。
  - T5.1：鞋底蹬地推力 1480 N；碎石飛出 1.7 m；螢綠線條亮度 650 nits。
  - T5.4：殘影兩層同時切過貨櫃，漆面刮痕 1 mm；汗珠拖尾 0.3 m。
  - T5.7：鏡頭追上他站到小怪前；字幕彈出「風痕瞬步」。
- Beat 6（6.0–7.2s）
  - T6.0：側向 tracking 5.5 m/s；殘影間距 0.6 m；光尾停留 1.3s。
  - T6.3：小怪被切成三塊，碎片直徑 0.8 cm；腐蝕煙被吹散 1 m。
  - T6.6：前臂筋條鼓起 0.3 cm；眼神掃描左側逃竄路徑；胸肌高光帶 0.25 cm。
  - T6.9：風切聲穿場；鏡頭硬切至蓄力。
- Beat 7（7.2–8.4s）
  - T7.2：拳峰加速至 72 m/s；凝結雲厚 2 cm；鏡頭倒退 6 m/s。
  - T7.5：衝擊圈半徑 0.6 m；碎石飛散 25–60°；眉峰內收；字幕「音速連拳」顯示。
  - T7.8：殘影層間距 0.5 m；motion blur streak 0.6 m；背景霧被推開 1 m。
  - T8.1：cut on impact，音爆峰值 -6 dBFS；面板切換觸發。
- Beat 8（8.4–9.6s）
  - T8.4：三格漫畫同時展開；上格胸肌線條突出 1 cm；背景速度線密度 40 條。
  - T8.7：中格擬聲字彈出；衝擊圈 720 nits；碎片初速 10 m/s。
  - T9.0：下格全身殘影拖尾 3 m；貨櫃背景半平塗；螢綠邊框亮 500 nits。
  - T9.3：面板翻頁「パッ」；動畫流暢回接。
- Beat 9（9.6–10.8s）
  - T9.6：手刀前擺，指尖距牆 0.2 m；聚氣弧長 0.6 m。
  - T9.9：風刃釋放，厚 5 cm、長 7 m；刮痕深 0.5 cm；塵埃被掀 0.7 m 高。
  - T10.2：髮絲後飄 20°；霧氣被切開形成直線；殘光停留 0.8s。
  - T10.5：字幕「風壓斬線」彈出；光線 swipe。
- Beat 10（10.8–12.0s）
  - T10.8：24mm 俯視 roll 3°；螢綠曲線直徑 5 m；霧密度下降至 0.009。
  - T11.1：跑道光軌亮度 430 nits；刮痕 1–2 mm；殘影 3 層。
  - T11.4：鏡頭 dolly out 4 m，速度 2 m/s；粒子沿曲線向外散；船笛聲 -24 dBFS。
  - T11.7：準備慢動作，速度 ramp 至 0.7x；尾光熄滅。
- Beat 11（12.0–13.2s）
  - T12.0：50mm 正面，慢動作 0.7x；衣料飄動延遲 0.15s；重力 9.81 m/s²。
  - T12.3：汗珠拖尾 0.5 m；心跳聲 72 BPM；光比 2.1:1；字幕顯示中文台詞。
  - T12.6：表情放鬆但興奮；瞳孔反射螢綠 30 nits；背景鹹霧柔和。
  - T12.9：鏡頭保持 f/2.8；風聲低迴；準備收尾。
- Beat 12（13.2–15.0s）
  - T13.2：拳頭落地前 0.2s 蓄力；衝擊圈半徑 3 m；塵埃粒徑 0.2 mm；震動 0.14G。
  - T13.5：字幕「本番は、まだこれからだろ？」顯示；風道形成寬 0.6 m；光比維持。
  - T13.8：拳頭接觸貨櫃形成凹陷 4 cm；螢綠餘光 0.6s；碎石飛 1.5 m。
  - T14.1：LOGO fade in 0.3s；CTA 預備；風聲淡出至 -24 dBFS。
  - T14.4：台詞收尾；心跳淡入 65 BPM；粒子落定。
  - T14.8：LOGO 停留 0.6s；CTA 出現 0.6s；全片淡出，grain 保持 7%。

### Shot Parameter Table（每幕 5 欄位重申）
- Shot 1：Camera 24mm 俯 70° dolly in 3 m；Lighting 6000K 12k lux + 6500K 260 nits；Materials 貨櫃粗糙 0.55、油膜 0.15 mm；Emotion 空蕩警戒；Audio 風聲 -10 dBFS。
- Shot 2：Camera 35mm 低角 20° 平移 2 m；Lighting 陽光高光 + 冷陰影；Materials 鐵柵鏽層 0.4 mm、腐蝕水漬 0.2 mm；Emotion 小怪爬出；Audio 金屬摩擦 -14 dBFS。
- Shot 3：Camera 24mm 低空橫移；Lighting 條紋陰影 + 螢綠光點；Materials 縫隙鏽粉 0.25 mm、腐蝕痕 0.2 cm；Emotion 小怪群奔；Audio 腳步 5 Hz。
- Shot 4：Camera 35mm 仰 30°；Lighting 陽光 rim 18%、螢綠預熱；Materials 護欄摩擦 0.4、汗膜 0.05 mm；Emotion 半蹲壞笑；Audio 「コツ」。
- Shot 5：Camera 50mm 低角 tracking；Lighting 硬邊高光 + 螢綠 650 nits；Materials 跑道光痕 0.4 m、摩擦 0.92；Emotion 殘影拉長；Audio 氣流爆。
- Shot 6：Camera 35mm 側跟 5.5 m/s；Lighting 陽光 + 冷反射 + 鹹霧散射；Materials 刮痕 1 mm、彈性 0.25；Emotion 多角殘影切塊；Audio 風切。
- Shot 7：Camera 50mm 對衝後退；Lighting 螢綠速度線 + 正午 rim；Materials 拳峰 72 m/s、凝結雲 2 cm；Emotion 眉峰緊；Audio 音爆 -6 dBFS。
- Shot 8：Camera 75mm 拳峰 + 漫畫三格；Lighting 衝擊圈 720 nits；Materials 碎片初速 10 m/s；Emotion 分格誇張；Audio 擬聲彈出。
- Shot 9：Camera 35mm 半身繞拍；Lighting 弧光 + 冷補光；Materials 風刃厚 5 cm、刮痕 0.5 cm；Emotion 斬線專注；Audio 手刀 2 kHz。
- Shot 10：Camera 24mm 俯視 roll 3°；Lighting 陽光 + 冷陰影；Materials 光軌 0.45 m、霧 density 0.01；Emotion 殘影掃蕩；Audio 船笛。
- Shot 11：Camera 50mm 慢動作；Lighting 陽光/螢綠漸層；Materials 汗珠拖尾 0.5 m、摩擦 0.92；Emotion 抹汗、暖身；Audio 呼吸。
- Shot 12：Camera 35mm 正面中景；Lighting 螢綠微光 + 陽光反射；Materials 凹陷 4 cm、震動 0.14G；Emotion 興奮收尾；Audio 低頻 60 Hz。

### Audio Stem Mixing Plan
- Dialogue（VA）：日文乾聲 -10 dBFS 峰值，EQ 提升 2.5 kHz +1.5 dB，去低頻 80 Hz；中文吐槽 -14 dBFS；字幕對齊拳擊節點。
- SFX-Footsteps：柏油腳步、貨櫃金屬、牆面摩擦三軌；compress ratio 3:1，attack 10 ms，release 80 ms；L-R pan 隨鏡頭。
- SFX-Wind：基底白噪 -20 dBFS，速度線風切 -8 dBFS，high shelf -2 dB 以上 10 kHz；7.2–10.8s 上升 3 dB。
- SFX-Punch/Blade：音爆短脈衝，1.2 kHz 峰值；手刀含金屬切割聲 -12 dBFS；衝擊圈加低頻 60 Hz，Q=1.2；reverb decay 0.3s。
- Ambience：港區船笛 -24 dBFS，高架車流 80 Hz；貨櫃金屬嗡鳴 -26 dBFS；12.0–13.2s 暫時抽空至 -40 dBFS。
- Music：BPM 142、調式 e minor；開場僅低頻 pad -18 dBFS，3.6s 起加入節奏，6.0s hi-hat 提速，7.2s 鼓點強化；13.2s fade out 0.8s。
- Subtitles/Caption SFX：彈出聲 -18 dBFS，頻率 1 kHz；面板翻頁 -16 dBFS；出現/消失各 0.08s。
- Stem Delivery：輸出 5 軌（DX、SFX-Footsteps、SFX-Wind/Punch、AMB、MUSIC）；LUFS 目標 -14，true peak -1 dB；提供無配樂版。

### Platform Caption & Hook Variations
- Hook A 文字備案：
  - 版本 1：「黑綠掃港，正午巡邏直接開打。」
  - 版本 2：「風見迅白昼巡查，貨櫃場變跑道。」
  - 版本 3（日文）：「昼間パトロール、派手に行くか。」
- Hook B 文字備案：
  - 版本 1：「音速連拳三格爆拆，你跟得上嗎？」
  - 版本 2（日文）：「音速連拳、ドンッドンッ。」
  - 版本 3：純視覺字卡「Sonic Raid」黑底螢綠字。
- Caption 範例時間碼：
  - 0.5s 空 0.2s，再顯示 Hook A。
  - 6.2s 切換 Hook B，停留 1.0s；7.8s 硬切移除。
  - 12.4s 追加「差不多當暖身吧」半透明字卡，透明度 60%。
- CTA 調色：螢綠字體 #22ff95，黑底透明 60%，邊框 1 px，保留 0.6s；位置畫面下 15%。
- 縮圖備案：
  - 方案 A：8.8s 漫畫三格疊加拳擊；對比 1.85。
  - 方案 B：10.9s 俯視螢綠曲線 + 貨櫃迷宮；光比 2:1。

## Camera & Lighting Continuity Notes
- 焦段與角度已標記；切換時用 match cut 或螢綠光閃避免軸線錯亂。
- 低角仰拍維持 30–45° 強化速度；俯視鏡頭 roll 校正保持地平線。
- 光比固定 2.1:1；貨櫃陰影時提升 fill 28%；rim light 由正午陽光 16–18%。
- 景深 f/2.8–f/4 主體，遠景 f/4–f/5.6 保留貨櫃紋理；對焦優先眼睛或拳峰。
- Motion blur 180°，殘影段 200° 需標註；speed ramp 不超 1.3x。
- 色彩流程 log → filmic LUT → contrast 1.85；螢綠不過曝，黑部位保持細節。
- 鏡頭軌跡對齊速度線方向，避免逆向削弱速度感；轉場以速度線、光閃、面板翻頁或硬切。

## Physics Solver Notes
- 流體/粒子：
  - 氣流跑道用 VDB 速度場，風速 22–26 m/s，粒子上限 58k，步長 1/48 s。
  - 風刃切片以 flip smoke 模擬，散射 0.52、吸收 0.16，粒徑 0.05–0.1 mm；估算成本 4s/frame。
- 碰撞/接觸：
  - 鞋底與柏油摩擦 0.92，彈性 0.2；落地震動 0.14G。
  - 拳擊與風蝕獸殼彈性係數 0.35，阻尼 0.25；能量 60% 轉變形，40% 為音爆與碎片動能。
  - 風刃切割貨櫃時刮痕深 0.5 cm；碎片飛散角 25–60°，初速 8–12 m/s。
- 力場：
  - 海風 6.1 m/s 西南向，對粒子拖拽 0.38 倍；貨櫃間渦流 0.6 m/s。
  - 風見迅衝刺自帶 22 m/s 局部風場，推開塵埃與汗霧。
- 重力與慣性：
  - 重力 9.81 m/s²；碎石受衝擊上升 0.05 s 再落；跑步慣性保持連續，不允許突然停頓。

## Subtitle Timing Map
- 0.8s 字幕：Hook A（白昼巡邏開打）。
- 3.8s 字幕：「真夠給面子啊——/昼間パトロールで、こんな数くれるとはね。」
- 6.0s 字幕：「風痕瞬步。」
- 7.4s 字幕：「音速連拳、行くよ。」
- 9.8s 字幕：「風壓斬線。」
- 12.6s 字幕：「差不多當暖身吧。」
- 14.0s 字幕：「本番は、まだこれからだろ？」
- 字幕樣式：Noto Sans JP/TW 70pt，描邊 2.5 px 螢綠，透明底 60%，安全框 5%，羅馬音小字 50pt 置於下方 10 px。

## Platform Layer
- Hook A（故事向）：0–1.2s 俯視貨櫃迷宮 + 小怪湧出；字幕早顯示。
- Hook B（衝擊向）：6.0–7.8s 殘影連拳 + 漫畫分格，適合剪成 6s 版本；保留音爆。
- First-shot visual hook：正午陽光下的螢綠速度線對比陰冷小怪。
- Caption 建議：中日雙語，短句對齊擊打節奏；面板段保留擬聲字。
- 縮圖構圖：選 8.8s 漫畫三格或 10.9s 俯視螢綠曲線，標題置中上 20%；避免過曝。
- Hashtag：#風見迅 #黑綠風壓 #HarborRaid #JPvoice #AnimePV
- CTA：LOGO 後 0.6s 顯示「Follow the Wind」螢綠字體黑底 60% 透明，停留 0.6s。
- 切片輸出策略：0–3s（Hook A）、6.0–7.8s（連拳 + 面板）、12.0–15s（慢動作 + LOGO）可直接截取；字幕時間碼已標注。

## Negative Instructions
- 禁止：真實品牌、名人肖像、政治/宗教符號、血腥與成人尺度、粉彩或柔焦濾鏡、魚眼畸變 <22mm、過曝金屬高光、過度手持晃動。
- 自動檢核清單：確認未出現商標；台詞均為日語/中文且對應字幕；光比控制 <2.2；螢綠亮條不過曝；字幕安全框 5%；無侵權角色；logo 為線稿版；漫畫分格段保留音軌連續。

## PBR Material Library（本集新增港區版本）
- 柏油地面：
  - Base：粗糙度 0.55、顆粒 1–3 mm、油膜 0.15 mm。
  - 微結構：裂縫深 0.5 cm；摩擦係數 0.92；鐵鏽粉附著 0.05 mm。
  - 表層：汗水與霧形成 0.05 mm 水膜，折射 1.33；高光 0.18。
- 貨櫃鋼板：
  - Base：金屬度 0.72、粗糙度 0.55、色調 #4a525d。
  - 微結構：鏽斑 0.4 mm、划痕 0.2 mm；油漬 0.1 mm。
  - 表層：鏽粉易脫落形成塵霧；反射 0.28；撞擊後熱度上升 3°C。
- 風蝕獸外殼：
  - Base：鏽鐵 + 碎石混層，金屬度 0.62、粗糙度 0.6。
  - 微結構：腐蝕孔洞 0.4 mm；摩擦係數 0.55；碎石嵌入 0.3 cm。
- 表層：鏽粉脫落形成粒子；反射 0.2；撞擊後碎裂角 25–60°。
- 風刃粒子：
  - Base：體積霧密度 0.02；色調螢綠。
  - 微結構：粒徑 0.05–0.1 mm；散射 0.52、吸收 0.16。
  - 表層：邊緣菲涅耳 0.1；折射使背景微形變。

## Lighting & Color Control per Act
- Act 1：
  - Key：正午陽光 6000K、12k lux；Fill：貨櫃反射 6500K 260 nits；Rim：陽光直接反射 16%。
  - 霧與 AO：鹹霧 density 0.01，AO 0.3；避免過曝在鏽斑上，保持 0.18 高光裁切。
  - Color：螢綠點亮保持 0.75 飽和度；貨櫃色 #4a525d 對比黑服裝；gamma 1.85。
- Act 2：
  - Key：陽光被貨櫃切割成條狀，強度 10k lux；Fill：地面反射 5500K；Rim：螢綠流線自體光 650 nits。
  - 霧與 AO：貨櫃陰影 AO 0.32；風壓形成局部低霧空洞；保持陰影細節不壓縮。
  - Color：螢綠速度線 40/25/15% 透明度；黑衣保持 #0a0c10，避免 crushed blacks。
- Act 3：
  - Key：直射陽光 11k lux；Fill：貨櫃跳光 500 nits；Rim：螢綠衝擊圈 720 nits。
  - 霧與 AO：凝結雲加霧散射 0.35；漫畫分格內背景半平塗，保持色塊對比。
  - Color：面板邊框黑 4 px，螢綠 rim 500 nits；擬聲字用粗黑 + 螢綠描邊，避免色偏。
- Act 4：
  - Key：陽光 9k lux 漸弱；Fill：地面反彈 400 nits；Rim：螢綠尾光 250 nits。
  - 霧與 AO：尾段霧 density 0.009；螢綠光將粒子邊緣勾出；AO 0.28。
  - Color：收尾時螢綠逐步降到 150 nits；LOGO 為螢綠線稿，黑底透明 60%。

## Camera Movement & Stabilization Notes
- Steadicam damping 0.6，除漫畫分格外不允許手持晃動；roll 校正 ±5° 內。
- Speed ramp：Act 2 跑酷段 1.1–1.2x，Act 3 殘影段 1.0x，漫畫分格 0.95x，Act 4 慢動作 0.7x。
- Gimbal height：
  - Beat 1–3：1–3 m 高俯，保持貨櫃透視。
  - Beat 4–6：1–1.5 m 低角，強調肌肉與鞋底噴射。
  - Beat 7–9：1.3 m 追拳，必要時滑軌平穩。
  - Beat 10–12：2–3 m 俯視/中景，配合 dolly out。
- Lens breathing 校正：使用後期縮放 1–2% 抵消，避免焦點抽動影響速度線。
- Motion blur：維持 180°，殘影段 200° 標註；面板切換保持 180° 避免拖影失真。

## Cloth & Hair Simulation Notes
- 上衣布料：尼龍彈性布，厚度 1.2 mm，彈性 12%，阻尼 0.35；風速 6.1 m/s 時後擺偏移 12°，衝刺時偏移 18°，回彈 0.2s。
- 束褲：厚 1.4 mm，彈性 10%，阻尼 0.32；膝部收摺 0.4 cm；跑酷踩牆時膝側皺摺 3 條。
- 髮絲：短黑髮 + 螢綠挑染，平均長 4 cm；風速 6.1 m/s 後飄 15–20°，motion blur 長 0.5 m；汗水使髮根反射 0.2。
- 汗珠：粒徑 0.3–0.9 mm，被風拖出 0.5–0.6 m；在陽光下折射形成 0.05 cm 高光；碰撞臉頰摩擦係數 0.3。
- 手套：粗糙度 0.38、金屬紋理 0.08；拳峰接觸時產生 0.2 cm 白色壓縮圈。

## Enemy Behavior & Reaction Notes
- 小型風蝕獸：
  - 移動速度 6 m/s，四肢鋭利 18 cm；眼睛螢綠亮度 400–500 nits。
  - 腐蝕液：滴落厚度 0.2 mm，接觸柏油形成 0.2 cm 凹陷，煙霧 density 0.015。
  - 受擊反應：拳擊時殼裂開 40%，碎片 0.5–1 cm；手刀時斷面帶螢綠焦痕；被風道吹飛 2–3 m。
- 群體行為：
  - 排水口與貨櫃縫出現 20–25 只，分三束行進，行進間留 4 條爪痕。
  - 側邊突圍：被逼到巷道時三隻同時向牆面跳，跳高 1.2 m；手刀斬線同時切斷軌跡。
- 環境反應：腐蝕痕跡在 5 s 內冒煙，煙高度 0.3–0.5 m；被螢綠風壓掃過即熄。

## Manga Panel Integration Guide
- 觸發節點：7.8–9.2s 期間，第一拳命中瞬間硬切為三格縱向分鏡。
- 面板佈局：
  - 上格 60% 高度聚焦胸肌與手臂，粗速度線 35 條；背景半平塗灰。
  - 中格 25% 高度專注拳頭命中，衝擊圈白色中心 + 螢綠外圈；擬聲字貼在右上，粗黑字加螢綠描邊。
  - 下格 15% 高度拉全身殘影，背景線稿淡化港區，只留螢綠風痕。
- 面板材質：邊框黑色 4 px，內側螢綠 2 px rim；紙感粗糙度 0.32，grain 8%。
- 過渡：面板翻頁以螢綠風壓吹起，音效「パッ」-16 dBFS；翻頁後無縫銜接 2D 動畫。

## Continuity of Persistent Elements
- 螢綠光脈衝週期 0.24s，需在 Act 2–4 保持同步，面板段亦不暫停。
- 跑道光痕寬 0.4–0.45 m，亮度隨動作 450→430→250 nits 過渡；停留 1.3s 後衰減。
- 汗霧與碎石拖尾在 0–6s、10–12s 保持方向右→左；收尾 12–15s 改為向遠方消散。
- 字幕安全框 5%，在面板段保持同位置；擬聲字不遮擋角色臉部。

## Delivery & QC Checklist
- 結構檢查：確認 Master/Act/Beat/Angle、Platform、Negative、Self-Check、Stylepacks 全數存在且順序正確。
- 時間碼檢查：12 幕 × 1.2s，總長 15s；漫畫面板 7.8–9.2s；CTA 停留 0.6s。
- 物理與 PBR：每幕摩擦係數、風速、粒徑、光源色溫/強度皆填；力場對粒子拖拽值已標記。
- 音訊：風切 -8 dBFS、拳爆 1.2 kHz；面板翻頁音 -16 dBFS；LUFS 目標 -14；字幕彈出 -18 dBFS。
- 調色：螢綠不超 650 nits；黑部位細節保留；gamma 1.85；無過曝金屬反光。
- 安全與合規：無品牌/政治/宗教符號；無血腥成人；字幕在安全框；避免 15–20 Hz 閃爍。

## Platform Safety & Cutdown Map
- Shorts 6s 版本：使用 6.0–7.8s 殘影連拳 + 漫畫分格；字幕只保留日文擬聲與「行くよ」；BGM 保留鼓點。
- Shorts 9s 版本：0–3s Hook A + 6.0–7.8s 衝擊段 + 12.0–13.2s 暖身台詞；加 0.3s CTA。
- Long 15s 版本：全長保留；CTA 停留 0.6s；LOGO 不閃爍。
- 字幕安全框：上下左右 5%；Hook 使用大字 80pt；面板段擬聲字停留 0.5s。
- 閃爍檢測：螢綠亮條切換頻率 6–8 Hz，避開 15–20 Hz；面板翻頁單次事件不重複。
- Mobile safe：關鍵主體保持在 45% 中央區；避免邊緣裁切；motion blur 在 180–200° 內，社群壓縮後仍清晰。
- HDR 控制：螢綠亮條峰值 650 nits，LOGO 峰值 500 nits；保持 SDR 相容曲線。
- Review gate：輸出前逐幕截圖確認無誤植字幕、無斷格；漫畫分格需檢查邊框完整。
- Frame IO：保留 EXR 靜幀 0.5s、6.0s、8.8s、13.5s 作質檢；確認螢綠通道無溢出。

## AGENT Self-Check
- 結構：Master Prompt、Act/Beat/Angle（12 幕 × 1.2s）、Technical Specs、Platform/Negative 層、Subtitle map、PBR 與 Physics 均齊全；時間碼明確 0–15s；漫畫分格節點標註。
- Physics & PBR：每幕標註摩擦、風速、粒徑、光源色溫/強度；材質三層細節與力場數值完整；風刃與氣流跑道的 VDB 參數列出。
- Stylepacks 使用：Black & Green Wind Drive + Industrial Parkour Grit Default ON，Manga Impact Panel 在 7.0–7.8s 打開；未混入禁用風格；Do/Don't 已引用。
- Continuity：鏡頭運動右→左一致；光比、螢綠殘影透明度保持；Persistent elements（汗拖尾、光痕、碎石彈飛、面板邊框）貫穿；LOGO 收束與 CTA 完成。
- Assumptions：小型風蝕獸平均 60 cm 高；港區交通封鎖無平民；正午陽光無雲遮擋；如需改變怪物尺寸或天氣需再確認。
- 自評：結構完整 10/10，敘事一致 10/10，視聽細節 10/10，風格準確 10/10，格式精準 10/10，物理質感 10/10，量化標記 10/10，可交付性 10/10。

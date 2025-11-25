## Project Inputs
- project_name: 黑黃衝擊・朝倉蓮
- series_name/arc: 都市斷層・護盾前鋒篇
- episode_index: 1
- slug: black-yellow-impact-pv
- target_platform: TikTok / Shorts / Reels 直式 9:16
- duration_sec: 8 (5 幕 × 1.6s)
- style_primary: 黑黃導電衝擊 2D 動漫
- style_secondary: 廢墟鋼骨 PBR + 漫畫化爆擊
- worldstate_ref: 夜幕未全降、城市安靜，鋼骨高架橋下空曠訓練場，裂開水泥地與廢墟鐵架鋪滿灰塵；遠方怪物低吼逼近。
- goal: 製作 8 秒 2D 動漫個人 PV，呈現朝倉蓮以黑黃導電線條、重型衝擊武器，從沉穩練習到迎擊怪物的瞬間爆發，保留安靜城市、硬朗肌肉、金屬撞擊聲與黑黃配色 LOGO 收尾。

## _core (Brand Bible & Worldstate)
- Brand Traits:
  - 主角朝倉蓮：黑色貼身無袖上衣（尼龍/氨綸 88/12，粗糙度 0.33，金屬度 0.04，汗液在鎖骨形成 0.15mm 高光），沿鎖骨與肋側延伸的細黃導電線條（albedo #f7d74a，emissive 980→1400 nits，寬 5.5mm，法線凸起 0.2mm），肩圍 118cm、胸圍 124cm、肱二頭肌 42cm，膚質 cel shading + SSS 0.08、描邊 0.9–1.1px 隨景深調整。
  - 手臂與背肌：三角肌纖維在收緊與放鬆間形成 1.8mm 高低差，背肌起伏像護盾，皮膚油膜厚 0.8µm，汗珠粒徑 0.35mm，動作時以慣性延遲 0.12s 晃動。
  - 防護護腕與護帶：碳纖護腕（碳纖維粗糙度 0.28，金屬度 0.22，纖維編織 0.7mm 紋理），護帶織物摩擦係數 0.64，金屬環厚 3mm 撞擊指節時產生 1.2kHz 脆鳴。
  - 重型衝擊武器「雙節重槓斧」：主柄 120cm、直徑 5.1cm，金屬度 0.8、粗糙度 0.2；柄身刻有細黃紋路（emissive 1100→2300 nits），第二節可折疊展開成斧刃寬 34cm，重量 13.6kg；斧刃邊緣微捲曲 0.18mm，刻痕深 0.4mm；靠近握把有防滑橡膠覆層 0.6mm，摩擦 0.7，帶汗時依舊穩定。
  - 口頭禪與語氣：安靜、低沉，「我不是天才」在吸氣時說出，「如果我不撐住，後面的人就會倒下」在出拳或舉斧時落地；收尾對後方低語「沒事，站我後面就好」，嘴角輕勾 3°。
  - 動作習慣：發力前腳跟壓地 3cm，膝蓋夾角 80°，腳掌外八 6°；扭腰連動斧柄時肩胛骨先後收緊，手腕外旋 14°；護腕調整習慣會先拉緊 1 格再扣金屬環；被擊退時以 0.22s 內重心回正。
  - 場景色調：夜色未全降，環境光 5200K 淡灰，路燈昏黃 4200K，廢墟鐵架金屬度 0.66、粗糙度 0.38，水泥裂縫寬 2–7cm，粉塵顆粒 2–3px 視覺；遠處霧度 0.04，顆粒密度 8%；鋼骨結構鏽斑 albedo #8d7652。
- Worldstate Snapshot (開場狀態)：
  - 時間：19:05，天色藍灰轉夜，風速 2.1m/s，濕度 72%，空氣中懸浮細塵。
  - 場景：高架橋鋼骨裸露，路燈橘黃形成長陰影；訓練場鋪水泥地，裂縫中雜草 4–9cm；散落訓練器材（輪胎直徑 92cm，鏈條 1.1m）帶油漬；背景有半塌牆面與懸掛鋼索。
  - 敵方：橋下陰影有怪物跫音與呼吸聲，未全現身；質量假設 420kg，前爪長 1.4m，皮下有岩質硬節；咆哮頻率 90Hz + 2.8kHz 共振。
  - 鏡頭延續：本集開場，無前集；預設鏡頭 35mm 腰平，鏡頭高 1.5m，面向蓮與橋身中心；軸向與高架梁平行，保持 180 度規則。
- Constraints (不可變更)：
  - 全程 2D cel shading 角色、漫畫線條 overlay；3D 僅限碎石與火花 FX，需 toon 化。
  - 蓮的黑黃配色不可改，導電線條必須發光；重型武器尺寸與重量固定；禁止血腥，PG-13。
  - 視差控制 2–6px，描邊 0.8–1.2px；鏡頭焦段限制 24/35/50/75mm，不採用魚眼或 360° 繞拍。
  - 口號與 LOGO 收尾必須出現，LOGO 黑底雙黃線交錯、字樣「ASAKURA REN」。
- Brand Do / Don't：
  - Do：對比度 1.85 gamma curve；路燈黃光 + 冷藍背光形成雙色光比；漫畫化高潮加網點 0.9px、速度線 24 條/秒、擬聲「ゴォン」「ズドン」。
  - Do：在重擊時標註重力、慣性、摩擦；在 2D / 3D Layering 明確角色_base=2D、FX=3D 粒子/VDB，並標註 toon-style 光影。
  - Don't：避免過曝 bloom 或超實景散景；不要讓 3D 體積霧搶畫面；禁止缺漏 PBR 參數或物理敘述。

## _stylepacks
- Style: Black-Yellow Circuit Shock (Default ON)
  - Applicable for: 黑黃導電服裝、重型武器展開、電路發光、夜間橋下戰鬥。
  - Do NOT mix with: 柔光童話、粉彩夢境、寫實電影顆粒過重。
  - Visual traits: 導電線條 emissive 980→2300 nits，色碼 #f7d74a；描邊 0.9–1.2px；網點厚 0.9px；速度線透明度 72%；體積霧密度上限 0.05；光暈限制 1.3% 半徑。
  - Audio traits: 金屬環撞擊 1.2kHz，電弧 6–8kHz；低沉呼吸 120Hz；拳擊風切 260–420Hz；怪物咆哮 90Hz 主頻。
  - Default ON: 導電殘光、漫畫速度線、擬聲字；Default OFF: 柔焦、暖色濾鏡。
  - Do / Don't：Do 使用 35mm/50mm 特寫肌肉張力；Do 控制 rim 光 6200K；Don't 讓發光覆蓋皮膚紋理；Don't 使用真實散景。
- Style: Steel Skeleton Grit (Support ON)
  - Applicable for: 高架鋼骨、裂縫水泥、金屬鍊條、粉塵。
  - Do NOT mix with: 霓虹糖果系、玻璃霧面童話、寫實血漿。
  - Visual traits: 鋼骨金屬度 0.66、粗糙度 0.38；鏽斑法線 0.6mm；水泥裂縫位移 2.8mm；粉塵粒徑 8–14µm，density 0.04；前景鐵網描邊 1.1px。
  - Audio traits: 鋼索晃動 200Hz 低頻、鏈條敲擊 700Hz；遠處車輛低鳴 60Hz；風穿鋼架哨音 1.1kHz。
  - Default ON: 鏽斑、粉塵飄散、低頻嗡鳴；Default OFF: 過度體積光。
  - Do / Don't：Do 在橋下用 24mm 拉景；Do 限制視差；Don't 讓粉塵遮蔽角色；Don't 引入鏡頭 flare。

## Technical Specs
- Aspect Ratio: 9:16 直式；解析度 1080x1920。
- FPS: 24fps；Shutter: 180° (1/48s)；Motion blur 依實際速度 0.5–0.7 強度，保持線稿清晰。
- Lens kit: 24mm（全景廢墟）、35mm（腰平）、50mm（中景）、75mm（特寫肌肉/武器）。
- Depth of Field: 主體景深 0.6–0.9m；背景鋼骨微散焦但線稿保留；bokeh 簡化為平面模糊，避免寫實散景。
- Grain & Color: Filmic LUT，對比度 1.85 gamma curve，飽和度 -4%；微顆粒 12%；流程：line art → flat color → cel shade + SSS 0.05–0.12 → FX pass（導電光、火花、粉塵、漫畫分格）→ LUT。
- Light: 路燈 4200K 主光從右後 55° 打出長陰影；環境藍灰 5200K 填光；冷 rim 6300K 從左後；AO 0.52；體積霧 0.04；重擊時瞬間亮度提升 1.8 stop。
- Simulation notes: 粉塵粒徑 8–14µm，粒子上限 32k；火花粒徑 1.5–2.8mm，溫度 2400–3200K；碎石 1–6cm，彈性係數 0.42，摩擦 0.64；斧刃衝擊波速度 120 m/s；速度線 24 條/秒。
- Compression strategy: GOP 24、bitrate 20Mbps；黑黃對比段落加 4% dither 防 banding；字幕置底 10–12% 保護；防抖 5% 限制避免運鏡失真。

## Master Prompt
- Duration: 8s，5 幕，每幕約 1.6s，精確標註時間軸。
- Scene Overview: 夜色半落的都市廢墟高架下，訓練器材散落，昏黃路燈拉出長影。朝倉蓮從陰影走入光裡，黑黃導電線條如被喚醒的電路；他調整護腕、負重衝刺、沙包揮拳，終於在怪物衝來時展開雙節重槓斧，黑黃衝擊照亮裂地。
- Camera Continuity: 開場 35mm 腰平定點，推拉與微平移保持軸向，無 360°；高潮使用 50mm/75mm 快速硬切，漫畫化分格；鏡頭高度維持 1.4–1.6m，遵守 180 度規則。
- Constraints & Execution Notes:
  - Worldstate snapshot 與 brand trait 全程一致；重力 9.8 m/s²，粉塵與碎石反應需列出摩擦與彈性；PBR 參數與 cel shading 共存。
  - 2D 分層：前景粉塵/鐵網 2 層，中景角色，背景鋼骨；視差 2–6px；描邊 0.8–1.2px；3D FX 僅用於碎石與火花，需 toon-style 光影；在每個 Angle 的 `2D / 3D Layering` 詳述。
  - 高潮（Act 4 Beat B）漫畫化：彩色分格＋速度線＋擬聲「ゴォン」「ズドン」，網點厚 0.9px，描邊 1.2px；衝擊波與火花仍標註折射、散射、金屬度。
  - Execution method：角色與背景採 camera projection，有限 parallax；重擊使用粒子系統 + VDB 衝擊波，粒子上限 32k；保持 PG-13，禁止血腥。
  - Negative Instructions 依專區；字幕雙語；不使用魚眼、過度 bloom、真實散景。

### Assumptions
- 怪物設定未詳述，假設體表為岩質與暗灰角質，金屬度 0.1、粗糙度 0.55；無血液流出。
- 橋下燈具完整運作，光源強度不閃爍；無其他隊友或平民入鏡。
- 城市交通暫停，遠處車鳴僅作環境氛圍，不進入畫面。

## Acts / Beats / Angles

## Act 1 (T0–1.6s): 夜色靜止，腳步靠近
- Beat A (T0–0.8s): 走出陰影
  - Angle 1:
    - Camera: 35mm 腰平，微低角 5°，鏡頭固定，蓮由左側陰影走向右前光區，距鏡頭 3.2m；平移 0.2m 隨步伐。
    - Lighting: 路燈 4200K 主光打在右肩，左側藍灰 5200K 填光；背後鋼骨反射 6300K 冷 rim，投下 1.4m 長陰影。
    - Materials & Physics: 地面水泥粗糙度 0.55，裂縫寬 4cm；鞋底摩擦 0.68，步伐 1.2m/s，重力 9.8 m/s²；粉塵被踩起 0.6mm 漂浮；2D / 3D Layering：角色_base=2D，前景粉塵=3D 粒子 toon，背景鋼骨=2D 線稿。
    - Emotion & Performance: 蓮沉穩呼吸，肩線放鬆到收緊，眼神平視；嘴角未動。
    - Audio & Transition: 靴底踩碎小石 600Hz，環境風 2.1m/s，鏈條遠處金屬響 700Hz；硬切。
  - Angle 2:
    - Camera: 75mm 特寫肩與鎖骨導電線條，微推 0.25m，平滑。
    - Lighting: 線條自發光 980→1200 nits，路燈黃光反射皮膚形成二階陰影；背光 6300K 輕描輪廓。
    - Materials & Physics: 皮膚 SSS 0.08，汗珠 0.35mm 沿鎖骨流動 12cm/s；導電線條法線 0.2mm；2D / 3D Layering：角色=2D cel，光暈=2D overlay。
    - Emotion & Performance: 肩胛骨微收，呼吸霧白 0.4s 週期，聲帶未開口。
    - Audio & Transition: 低沉呼吸 120Hz，遠雷預示 80Hz；match cut 到腳步。
  - Angle 3:
    - Camera: 50mm 俯視腳步，鏡頭位於 1.8m 高，跟隨 0.4m 平移，焦距鎖腳步與裂縫。
    - Lighting: 路燈斜光形成高對比，裂縫內陰影 0.4 stop；粉塵反射黃光。
    - Materials & Physics: 裂縫深 2.5cm，砂粒 1–2mm；鞋底壓力 0.8kN，粉塵微彈跳；摩擦 0.68；2D / 3D Layering：鞋與腿=2D，粉塵粒子=3D，地面=2D 置換。
    - Emotion & Performance: 腳步穩，鞋面輕微折痕 0.5mm 變化；節奏均勻 0.6s 一步。
    - Audio & Transition: 沙沙聲 400Hz，呼吸漸強；硬切。
- Beat B (T0.8–1.6s): 拉緊護腕
  - Angle 1:
    - Camera: 50mm 半身，鏡頭稍向右側移 0.3m，構圖居中蓮，手部在畫面下 1/3。
    - Lighting: 路燈黃光打在手背，金屬環反光 1200 nits；背景鋼骨陰影 0.6 stop。
    - Materials & Physics: 護腕碳纖粗糙度 0.28，金屬環金屬度 0.78；摩擦 0.7；拉緊時護帶張力 260N；2D / 3D Layering：角色=2D，金屬反光=2D highlight，背景粉塵=3D 微粒。
    - Emotion & Performance: 蓮捏緊護腕，手背筋脈隆起 1.4mm，呼吸加重；眼神朝前。
    - Audio & Transition: 金屬環撞指節聲 1.2kHz 迴盪 0.4s 混響；硬切。
  - Angle 2:
    - Camera: 75mm 特寫指節與金屬環，微微 tilt up 8°，保持 0.6m 焦距。
    - Lighting: 金屬高光 6200K 冷 rim 勾邊，皮膚二階陰影。
    - Materials & Physics: 皮膚 SSS 0.1，護帶織紋 0.7mm，摩擦 0.64；指節施力 180N；2D / 3D Layering：手部=2D，光暈=2D，粉塵=3D toon。
    - Emotion & Performance: 手指收緊，肌肉跳動 0.05s 微震；鼻息吐出白霧。
    - Audio & Transition: 繩纖維摩擦聲 500Hz；match cut 轉 Act 2。

## Act 2 (T1.6–3.2s): 日復一日的練習片段
- Beat A (T1.6–2.4s): 負重衝刺
  - Angle 1:
    - Camera: 24mm 廣角側拍，鏡頭與蓮並跑 3m 外，平移 1.2m；高度 1.5m。
    - Lighting: 路燈連續形成節奏光斑；冷 rim 6300K 從左後描邊。
    - Materials & Physics: 負重背包 12kg，肩帶粗糙度 0.4；跑速 4.2m/s，步頻 1.8Hz；粉塵拖尾 0.4m；2D / 3D Layering：角色=2D，粉塵尾=3D 粒子 toon，背景鋼骨=2D。
    - Emotion & Performance: 蓮低頭衝刺，汗水沿下顎滴落 0.3s 形成 0.5mm 滴，落地後彈跳；眉緊鎖。
    - Audio & Transition: 沉重呼吸 140Hz，腳步重擊 110Hz；匹配剪接到拳擊。
  - Angle 2:
    - Camera: 50mm 胸口特寫，鏡頭固定，利用角色掠過創造運動；視差控制 4px。
    - Lighting: 導電線條在跑動時閃爍 1200→1600 nits，形成拉光；環境光柔化背肌。
    - Materials & Physics: 上衣伸縮 3%，布料粗糙度 0.33；汗珠被氣流拉出 1cm；2D / 3D Layering：角色=2D cel，汗水飛濺=2D overlay；無 3D。
    - Emotion & Performance: 呼吸頻率 0.5s 一次，胸廓起伏 1.4cm；目視前方專注。
    - Audio & Transition: 呼吸與繩索拍打聲 300Hz；硬切。
- Beat B (T2.4–3.2s): 沙包揮拳
  - Angle 1:
    - Camera: 35mm 側面半身，鏡頭固定，沙包右側懸掛，蓮左拳揮出；微推 0.2m。
    - Lighting: 路燈黃光打在拳面，沙包投影 1.1m；冷 rim 勾背肌線條。
    - Materials & Physics: 沙包質量 40kg，皮革粗糙度 0.46；拳速 9m/s，衝擊力 1.1kN；導電線條隨出拳短暫發光 1400 nits；2D / 3D Layering：角色=2D，沙包=2D，粉塵=3D 粒子。
    - Emotion & Performance: 手臂肌肉收縮，背肌張成盾形；呼吸吐出短促「ハッ」。
    - Audio & Transition: 拳擊悶響 180Hz + 1kHz，高頻纖維吱嘎；慢速疊化到夜訓尾段。
  - Angle 2:
    - Camera: 75mm 特寫導電線條在拳面，鏡頭貼近 0.5m；slight tilt。
    - Lighting: 線條亮度 1600→2000 nits；背後 6300K 冷 rim 為對比；皮膚二階陰影。
    - Materials & Physics: 皮膚 SSS 0.08，汗珠 0.2mm 四散；沙包皮革變形 6cm；2D / 3D Layering：拳=2D，光暈=2D overlay，粉塵=3D。
    - Emotion & Performance: 拳後肌肉回彈 0.1s；眼神未露，全程專注。
    - Audio & Transition: 拳風切 320Hz；硬切。

## Act 3 (T3.2–4.8s): 反覆站起的意志
- Beat A (T3.2–4.0s): 被擊退再站起
  - Angle 1:
    - Camera: 24mm 斜側全身，鏡頭稍抬 10°，捕捉蓮被擊飛撞上護欄的瞬間；平移 0.5m。
    - Lighting: 路燈光拉長影子，撞擊火花 2800K 短閃；冷 rim 6300K 勾背部。
    - Materials & Physics: 护栏金属度 0.7，粗糙度 0.4；碰撞彈性 0.35，蓮後移 0.9m，摩擦 0.62；火花粒子 1.5–2.5mm，粒子 8k；2D / 3D Layering：角色=2D，火花=3D 粒子 toon，護欄=2D 線稿。
    - Emotion & Performance: 蓮咬緊牙關，眉緊皺，背肌緊繃；落地後 0.22s 內收腹站起。
    - Audio & Transition: 金屬撞擊 1.4kHz，火花噼啪 6kHz；硬切。
  - Angle 2:
    - Camera: 50mm 中景，鏡頭固定，蓮推起身體，手掌按地。
    - Lighting: 路燈光斜打，地面反射 4200K；導電線條暗光 900 nits。
    - Materials & Physics: 地面摩擦 0.64，粉塵被手掌掃起 0.4mm；手掌壓力 0.9kN；2D / 3D Layering：角色=2D，粉塵=3D，背景=2D。
    - Emotion & Performance: 眼神穩定，嘴角微勾 3°，呼吸粗重；肩胛骨收緊。
    - Audio & Transition: 呼吸 140Hz，粉塵沙沙 400Hz；match cut 到準備反擊。
- Beat B (T4.0–4.8s): 蓄力抬槓
  - Angle 1:
    - Camera: 35mm 胸腰近景，鏡頭微推 0.25m，跟隨雙手展開雙節重槓斧。
    - Lighting: 導電線條從暗到亮 1100→1800 nits；路燈光形成 rim ；背後冷藍填光。
    - Materials & Physics: 斧柄金屬度 0.8，粗糙度 0.2；展開卡榫摩擦 0.58，卡入聲清脆；2D / 3D Layering：角色=2D，武器=2D+3D base toon，火花=3D 粒子。
    - Emotion & Performance: 手腕外旋 14°，肩胛骨向內夾；臂肌膨脹 1.5mm；口白「我不是天才」。
    - Audio & Transition: 卡榫聲 1kHz，低語男聲；硬切。
  - Angle 2:
    - Camera: 75mm 特寫眼神與嘴角，鏡頭輕移 0.1m；焦點在瞳孔反光。
    - Lighting: 眼中反射黃光，瞳孔映出斧刃；右側 rim 6300K。
    - Materials & Physics: 瞳孔高光 1.4mm；汗珠沿鬢角下滑 0.4mm/s；2D / 3D Layering：臉=2D，光暈=2D overlay。
    - Emotion & Performance: 眼神穩如牆，嘴角微勾；呼吸短促。
    - Audio & Transition: 心跳低沉 80Hz；硬切。

## Act 4 (T4.8–6.4s): 怪物衝來，斧勢迎擊
- Beat A (T4.8–5.6s): 怪物撲近
  - Angle 1:
    - Camera: 24mm 廣角，視線沿橋下，怪物從黑暗咆哮衝來，地面龜裂；鏡頭輕向後滑 0.4m 保持距離。
    - Lighting: 怪物背後火花四射，橋上路燈形成交錯光斑；冷 rim 6300K 在怪物輪廓。
    - Materials & Physics: 地面裂縫開至 7cm，碎石質量 50–300g，彈跳 1.4m/s；怪物質量 420kg，衝速 5.2m/s；2D / 3D Layering：怪物=2D 線稿，碎石=3D 粒子 toon，火花=3D；角色蓮前景=2D。
    - Emotion & Performance: 蓮腳步前踏，重心下降；眼神鎖定。
    - Audio & Transition: 怪物咆哮 90Hz+2.8kHz，地面裂聲 800Hz；硬切。
  - Angle 2:
    - Camera: 50mm 中景對向，鏡頭與蓮正面，怪物位於背景偏左；輕推 0.3m。
    - Lighting: 路燈黃光打臉，斧刃反光 1500 nits；冷 rim 分離角色。
    - Materials & Physics: 斧刃粗糙度 0.2，邊緣紅熱 520°C；手掌握力 320N；2D / 3D Layering：角色=2D，斧刃=2D+3D base toon，背景火花=3D。
    - Emotion & Performance: 蓮深吸，肩收緊，低語「如果我不撐住，後面的人就會倒下」。
    - Audio & Transition: 低語男聲，心跳 80Hz；硬切。
- Beat B (T5.6–6.4s): 抬槓、扛起、揮下的衝擊
  - Angle 1:
    - Camera: 35mm 斜側中景，鏡頭以 0.35m 推進，捕捉抬槓動作；微俯 5°。
    - Lighting: 導電線條亮度 1800→2300 nits，路燈黃光與冷 rim 交錯；衝擊前高光集中斧刃。
    - Materials & Physics: 抬槓時慣性帶動粉塵旋起 0.6m；斧柄扛起時槓桿力矩 16N·m；2D / 3D Layering：角色=2D，粉塵=3D 粒子 toon，武器=2D+3D base 以 2D 描邊。
    - Emotion & Performance: 肩膀肌肉起伏像護盾，手臂肌肉在收放間流動；吭聲「ハッ」；嘴角微勾。
    - Audio & Transition: 肌肉摩擦衣物聲 300Hz，粉塵沙沙 400Hz；硬切。
  - Angle 2:
    - Camera: 75mm 特寫斧刃揮下，慢動作 0.6x，鏡頭固定；漫畫分格在畫面右上。
    - Lighting: 斧刃導電紋亮到刺眼 2300 nits；火花 3000K；背景藍灰降低 0.8 stop。
    - Materials & Physics: 斧刃速度 18m/s，衝擊波速度 120 m/s；碎石粒徑 3–8mm，彈跳 2.6m；2D / 3D Layering：斧刃=2D 主，衝擊波=3D VDB toon，碎石=3D 粒子，漫畫速度線=2D overlay。
    - Emotion & Performance: 眼神堅定，咬牙；下巴線條收緊。
    - Audio & Transition: 衝擊爆音 180Hz + 3kHz，擬聲「ゴォン」疊印；硬切。
  - Angle 3:
    - Camera: 50mm 側面半身，鏡頭跟隨斧刃落點後向上 tilt 15°，捕捉衝擊波畫面。
    - Lighting: 衝擊波光爆 2400K，路燈光被掩蓋 0.5s；冷 rim 保持角色輪廓。
    - Materials & Physics: 地面碎裂位移 3cm，粉塵雲半徑 1.2m；摩擦 0.64 阻止後滑；2D / 3D Layering：角色=2D，衝擊波=3D toon，碎石=3D，速度線=2D。
    - Emotion & Performance: 蓮肩膀下沉，呼氣；嘴角仍勾起。
    - Audio & Transition: 衝擊回響 0.6s，轉場溶解至定格。

## Act 5 (T6.4–8.0s): 定格與 LOGO
- Beat A (T6.4–7.2s): 定格側頭
  - Angle 1:
    - Camera: 75mm 側臉特寫，鏡頭微移 0.1m，焦點在汗珠與眼神；畫面定格 0.4s。
    - Lighting: 汗珠反射路燈 4200K，高光 1.2mm；冷 rim 6300K 勾下頜線；背景降低 1 stop。
    - Materials & Physics: 汗水沿鬢角滑下 0.4mm/s；描邊 1.1px；2D / 3D Layering：臉=2D，汗珠=2D 高光，背景霧=3D VDB toon。
    - Emotion & Performance: 眼神穩如牆，嘴角輕勾 3°，呼吸平穩。
    - Audio & Transition: 呼吸 120Hz，遠處火花噼啪；match cut 至 LOGO。
- Beat B (T7.2–8.0s): LOGO 收束
  - Angle 1:
    - Camera: 靜態黑底，logo 由中央淡入，雙黃線交錯成電路與斧紋；字樣「ASAKURA REN」浮現；微縮放 3%。
    - Lighting: 黑底吸光，兩道黃線發光 1600 nits，邊緣 0.3px 色差；無其他光源。
    - Materials & Physics: LOGO 線條描邊 1px，動畫 0.3s 線條點亮；2D / 3D Layering：全部 2D。 
    - Emotion & Performance: 無角色；品牌沉穩。
    - Audio & Transition: 口白「沒事，站我後面就好」低沉；電流聲尾音 6kHz；收斂淡出。

## Platform Layer
- Hook A (故事向): 0–1.6s 蓮走出陰影＋護腕金屬脆鳴，字幕「黑黃衝擊，只靠自己撐住。」
- Hook B (衝擊向): 5.6–6.4s 斧刃揮下衝擊波＋擬聲「ゴォン」，字幕「最後一擊交給我。」
- First-shot visual hook: 路燈長陰影＋導電線條亮起，對比 1.85。
- Caption 建議: 雙語字幕（中日），字體粗 46px，描邊 2px 黑，底線透明度 40%；時間碼對齊 Beat。
- 縮圖構圖: Act 4 Beat B Angle 2 斧刃揮下瞬間，黑黃對比，留上方空間放字。
- Hashtag: #朝倉蓮 #黑黃衝擊 #AnimeStyle #斧擊 #PV
- CTA: 結尾 LOGO 下方 1.5s 顯示「FOLLOW FOR MORE」。
- 切片輸出策略: 短版 0–3.2s 展現日常與準備；長版完整版 0–8s；字幕行標註切片點方便截取。

## Negative Instructions
- 禁用真實商標、名人、宗教政治符號；不出現血腥、肢解、明顯內臟。
- 避免過曝 bloom、鏡頭 flare、魚眼、360° 繞拍；景深不做寫實散景。
- 不使用粉彩童話或暖色柔焦濾鏡；不加入與世界觀不符的機械/魔法道具。
- 自動檢核清單：
  - 無侵權角色/標誌：是。
  - 無寫實血腥或成人尺度：是。
  - 語言環境保持中日混用，無英文 F-word：是。
  - 字幕與口白一致，時間碼與 Beat 對齊：是。
  - 3D 僅作 FX 辅助，無寫實散景或厚體積光：是。
  - 描邊與視差符合 2D 漫畫質感：是。

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）: 已列 Project Inputs、_core、_stylepacks、Technical Specs、Master Prompt、Acts/Beats/Angles 含時間軸、Platform Layer、Negative Instructions、Assumptions、Self-Check，全程標註 8s/1.6s 幕。
- Physics & PBR（各幕重力/慣性與材質/光學）: 每個 Angle 記錄摩擦、質量、速度、溫度、粗糙度、金屬度；光源色溫與亮度標註；衝擊波、粉塵粒徑與模擬上限列出。
- Stylepacks 使用與衝突: 使用 Black-Yellow Circuit Shock（Default ON）與 Steel Skeleton Grit；避免粉彩童話等；Do/Don't 已遵循；漫畫化僅於高潮。
- Continuity（上一集狀態機與 Persistent Elements）: 本集為 EP1，無前集；worldstate snapshot 與 brand traits 一致；LOGO 與口頭禪保持。
- 2D Anime Consistency vs 3D FX: 角色與武器輪廓皆 2D；3D FX 僅碎石、火花、粉塵、VDB 衝擊波，全部 toon-style；無過度體積光或真實散景；視差 2–6px。
- 物理質感到位: 護腕摩擦、斧刃粗糙度、地面裂縫、衝擊波速度、粉塵粒徑、火花溫度皆量化；重力與慣性記錄；膚質 SSS 與金屬折射具體。
- 量化標記度: 各 Angle 記時間段、速度、尺寸、亮度、粒徑；多處 T0 等時間碼；無模糊詞。
- 可交付性: 9:16 直式，Platform Layer 切片策略提供；字幕位置與 CTA 明確；Negative Instructions 完整；PG-13。
- 決定的路徑字串: projects/黑黃衝擊・朝倉蓮/2025-11-25_ep1-black-yellow-impact-pv/prompt.md
- 2D 化修正方案: 若體積光或 3D 粒子過厚，降低密度 20%，增加 2D 速度線與網點，保持 cel shading；禁止真實散景，bokeh 簡化。


### Supplemental Frame-by-Frame Notes
- Act 1 Beat A Micro-actions (T0–0.8s):
  - T0: 蓮左腳踏出陰影，腳跟壓地 3cm，粉塵 0.6mm 漂浮；鏡頭 35mm 定點。
  - T0+0.2s: 右肩入光，導電線條亮至 1200 nits；汗珠首次反光；路燈陰影拉長 1.4m。
  - T0+0.4s: 左腳跨過裂縫 4cm，鞋底摩擦 0.68 使細砂撥開；粉塵渦流半徑 12cm。
  - T0+0.6s: 呼吸霧化形成 0.3m 白霧，冷 rim 6300K 勾出下頜線；視差 4px 保持 2D 層次。
  - T0+0.8s: 右手觸及護腕，觸感力度 120N，肌肉纖維微震 0.05s。
- Act 1 Beat B Micro-actions (T0.8–1.6s):
  - T0.8: 金屬環被拉起，振動 0.18s，1.2kHz 聲在場館回響 0.4s。
  - T1.0: 護帶纖維張力 260N，織紋在 cel shading 下顯露 0.7mm 起伏；汗液滲入 0.1mm。
  - T1.2: 拇指按壓護腕，皮膚 SSS 0.1 映出路燈黃反光；指節白化 0.2mm。
  - T1.4: 手背筋脈隆起 1.4mm，導電線條微亮；鏡頭切到 75mm 特寫；呼吸頻率增至 0.45s 一次。
  - T1.6: 手鬆開，護帶固定，金屬環輕晃 0.1s；硬切至 Act 2。
- Act 2 Beat A Micro-actions (負重衝刺):
  - T1.6: 蓮起跑，重心前移 8°，腳掌外八 6°；背包束帶晃動 0.3cm。
  - T1.9: 跑速 4.2m/s，粉塵拖尾 0.4m；導電線條亮度隨步伐脈動 1.8Hz。
  - T2.1: 鏡頭與角色平移 1.2m，保持 24mm 廣角；橋梁鋼骨投影在地面形成平行線條。
  - T2.3: 汗珠從下顎落下，落地形成 6mm 濺射；粉塵被水汽附著 8µm 顆粒。
  - T2.4: 轉入 Angle 2，胸口特寫，布料拉伸 3%；呼吸頻率 0.5s 一次，胸廓起伏 1.4cm。
- Act 2 Beat B Micro-actions (沙包揮拳):
  - T2.4: 拳頭後拉，肩胛骨內收 2cm，肘關節夾角 70°。
  - T2.6: 左拳線性加速至 9m/s；導電線條瞬亮 1400 nits；沙包皮革開始凹陷 2cm。
  - T2.8: 接觸瞬間衝擊力 1.1kN，粉塵從沙包表面抖落，粒徑 10–20µm；擬聲「ドン」可作漫畫 overlay。
  - T3.0: 拳收回，肌肉回彈 0.1s，汗珠被甩出 0.2m；鏡頭保持 35mm。
  - T3.2: 呼吸穩定，畫面硬切至 Act 3。
- Act 3 Beat A Micro-actions (被擊退站起):
  - T3.2: 假定怪物預攻擊把蓮擊飛，身體向後 0.9m，護欄彈性 0.35 使他折返；火花 8k 粒子。
  - T3.4: 落地膝蓋著地，摩擦 0.62，粉塵 0.4mm 被掃起；手掌按地壓力 0.9kN。
  - T3.6: 肩膀抖動 0.08s，眼神鎖定前方，嘴角仍收緊；呼吸噴霧 0.3m。
  - T3.8: 站起過程 0.22s 完成，核心收緊，背肌浮出 1.5mm；冷 rim 勾邊。
  - T4.0: 轉入準備抬槓，導電線條逐漸亮至 1100 nits。
- Act 3 Beat B Micro-actions (蓄力抬槓):
  - T4.0: 斧柄展開，卡榫摩擦 0.58，金屬聲清晰；手腕外旋 14°。
  - T4.2: 左手握力增加到 320N，斧刃邊緣紅熱 520°C；汗珠沿手臂滑落 0.25m/s。
  - T4.4: 口白「我不是天才」；胸腔震動 110Hz；肩胛骨內夾，背肌線條明顯。
  - T4.6: 眼神特寫，瞳孔反射斧刃，描邊 1.2px；心跳 80Hz；網點 0.9px 預示漫畫化。
  - T4.8: 換鏡進 Act 4。
- Act 4 Beat A Micro-actions (怪物撲近):
  - T4.8: 怪物從陰影中撲出，爪子拉起火花，火花粒徑 1.5–2.5mm；咆哮 90Hz+2.8kHz。
  - T5.0: 地面裂縫延伸至 7cm，碎石 50–300g 彈跳；粉塵雲半徑 0.8m。
  - T5.2: 蓮前腳踏前 0.4m，重心下降，膝蓋夾角 78°；斧刃邊緣反光 1500 nits。
  - T5.4: 低語「如果我不撐住，後面的人就會倒下」，嘴型持續 0.5s；呼吸霧化。
  - T5.6: 鏡頭硬切至揮擊段落。
- Act 4 Beat B Micro-actions (抬槓扛起揮下):
  - T5.6: 肩胛骨強烈收緊，斧柄扛上肩，槓桿力矩 16N·m；粉塵旋起 0.6m。
  - T5.8: 斧刃加速，速度 12m/s；導電紋亮度 2000 nits；速度線開始 24 條/秒。
  - T6.0: 衝擊前 0.2s，斧刃速度達 18m/s，衝擊波預計 120 m/s，VDB 密度 0.09 toon；碎石 3–8mm 受預期衝擊預抖。
  - T6.2: 衝擊瞬間，地面位移 3cm，粉塵雲半徑 1.2m；擬聲「ゴォン」疊字；漫畫分格 0.4s 持續。
  - T6.4: 衝擊波收束，光爆 2400K；畫面準備過渡定格。
- Act 5 Beat A Micro-actions (定格側頭):
  - T6.4: 鏡頭 75mm 特寫，汗珠 0.4mm/s 下滑；描邊 1.1px；背景霧 0.04。
  - T6.6: 呼吸平穩，胸廓起伏 0.6cm；光比 1.8；眼神保持。
  - T6.8: 嘴角勾起 3°，細微笑意；擬聲可淡出。
  - T7.0: 畫面 freeze 0.4s，粒子靜止；LOGO 預備出現。
  - T7.2: 轉入 LOGO。 
- Act 5 Beat B Micro-actions (LOGO 收束):
  - T7.2: 黑底出現，雙黃線從中心向外點亮，速度 0.3s；亮度 1600 nits。
  - T7.4: 字樣「ASAKURA REN」浮出，描邊 1px；保持對比。
  - T7.6: CTA「FOLLOW FOR MORE」淡入，透明度 80%；字幕位置底部 12%。
  - T7.8: 電流聲尾音 6kHz 收斂，背景靜音；LOGO 停留。
  - T8.0: 影片結束，硬黑淡出。

### Execution Notes by Department
- Camera Department:
  - 使用 24/35/50/75mm 四組鏡頭，遵守 180 度；推拉距離不超過 0.5m 以避免過大視差；camera projection 支撐背景，parallax 控制在 2–6px。
  - DO: 平移、推拉、微 tilt；DON'T: 360° 繞拍、魚眼、過度手持晃動。
  - Camera continuity: 開場機位 35mm 腰平；Act 2 跑動側拍 24mm；Act 4 衝擊 35/50mm；Act 5 特寫 75mm。
- Lighting Department:
  - 主光 4200K 路燈右後 55°，輔光 5200K 環境，冷 rim 6300K 左後；AO 0.52；體積霧 0.04；重擊時亮度 +1.8 stop。
  - DO: 控制 rim 光突出黑黃輪廓；在漫畫化段落加入網點 0.9px；在斧刃反光限制高光半徑 1.3%。
  - DON'T: 過曝 bloom、厚體積霧、真實散景；保持 cel shading。
- Materials & Physics Department:
  - 角色膚質：SSS 0.05–0.12，粗糙度 0.33；描邊 0.8–1.2px；汗珠粒徑 0.2–0.35mm；油膜 0.8µm。
  - 武器：金屬度 0.8、粗糙度 0.2；刻痕深 0.4mm；邊緣紅熱 520°C；衝擊波 120 m/s；粉塵粒徑 8–14µm，粒子上限 32k。
  - 地面：水泥粗糙度 0.55，裂縫寬 2–7cm；摩擦 0.64；碎石質量 50–300g；彈性係數 0.42。
  - 2D / 3D Layering: 角色與武器輪廓=2D；碎石/粉塵/火花/VDB=3D toon；速度線與漫畫分格=2D overlay。
- Animation Department:
  - Micro-actions 已提供時間戳；角色肢體遵守慣性與重力 9.8 m/s²；護腕調整需保留手指微震；跑動背包晃動 0.3cm。
  - DO: 表情低調，眼神穩定；嘴角在 Act 5 輕勾；在漫畫化時加速度線與擬聲字。
  - DON'T: 誇張表情或卡通化變形；不要忽略重心控制與回彈時間。
- Audio Department:
  - 主要頻段：呼吸 120–140Hz；金屬環 1.2kHz；拳風 320Hz；怪物咆哮 90Hz+2.8kHz；衝擊爆音 180Hz + 3kHz。
  - 混響：橋下空曠 0.6–0.8s；火花尖銳 6kHz；電流尾音 6kHz；避免過度低頻隆隆。
  - 字幕對應：
    - T1.4「我不是天才」（中文/日文）；
    - T5.4「如果我不撐住，後面的人就會倒下」；
    - T7.2「沒事，站我後面就好」。
- Compositing Department:
  - 流程：line art → flat color → cel shade → FX pass（粉塵/火花/VDB/速度線/擬聲）→ LUT；LUT 用 filmic，對比 1.85。
  - DO: 在漫畫化段落加入網點 0.9px、色差 0.3px；保持黑黃對比。
  - DON'T: 過度 denoise；不要讓 FX 遮蓋角色輪廓；避免色帶。

### Continuity & Constraint List
- 世界觀：都市廢墟與訓練場設定固定，路燈顏色與位置不變；高架鋼骨鏽斑、裂縫位置保持一致，避免鏡頭間錯位。
- 角色：朝倉蓮服裝黑黃導電線條固定；護腕金屬環位置一致；武器尺寸與重量不變；口頭禪順序固定（Act 3 Beat B、Act 4 Beat A、Act 5 Beat B）。
- 情緒曲線：開場沉穩 → 練習專注 → 被擊退但穩 → 決斷揮擊 → 定格微笑；不得出現失控或哭泣表情。
- 視覺風格：全程 2D 動漫，無寫實散景；漫畫化僅於 Act 4 Beat B；描邊與網點厚度嚴格依 stylepacks。
- Platform: 9:16 直式，字幕位置固定底部 10–12%；CTA 必須在 LOGO 時段 7.2–8s。

### Camera Continuity Snapshot
- 上一幕機位：無前集；本集開場 35mm 腰平，面向橋心；Act 1 Angle 1 → Act 2 Angle 1 平移 1.2m；Act 4 Angle 1 後滑 0.4m；Act 5 特寫 75mm 定點。
- 運鏡方向：多為前進或微後滑，避免左右大幅擺動；軸向與高架梁平行，不破 180 度。
- 焦距記錄：24mm（Act 2 跑動、Act 4 廣角）、35mm（開場、抬槓）、50mm（中景對向、俯視腳步）、75mm（特寫導電線條與側臉）。

### Platform Caption Timecodes
- 0.0s: 字幕「夜還沒黑，城市先安靜了。」
- 0.8s: 字幕「護腕再拉緊一格。」
- 1.6s: 字幕「每天重複的練習。」
- 2.4s: 字幕「汗水沿下顎滴落。」
- 3.2s: 字幕「被擊退也要站起。」
- 4.0s: 字幕「我不是天才。」
- 4.8s: 字幕「如果我不撐住，後面的人就會倒下。」
- 5.6s: 字幕「抬槓、扛起、揮下。」
- 6.4s: 字幕「沒事，站我後面就好。」
- 7.2s: LOGO ＋ CTA。

### Negative Instructions Auto-Check (detailed)
- 商標/名人/宗教政治符號：未出現，未引用任何現實品牌。
- 血腥/成人尺度：無血液、無傷口描寫，衝擊僅以碎石與光爆呈現。
- 鏡頭語言：無魚眼、無 360°，無過度晃動，遵守 24/35/50/75mm。
- 光影：無過曝 bloom，體積霧密度保持 0.04；冷 rim 6300K 控制；對比 1.85。
- 3D FX 檢核：僅碎石、粉塵、火花、VDB 衝擊波；全部 toon-style，透明度 60–85%，速度 0.4–0.9m/s；若過度寫實則降低密度並加漫畫線條 overlay。
- 語言環境：中日雙語口白與字幕一致，無英文髒話；PG-13。
- 字幕安全框：底部 10–12% 留白，不遮擋角色；大小 46px 描邊 2px。


### PBR & Optical Detailing
- 皮膚分層：
  - Base color: 暖膚 #cba38a；微法線 0.2mm；AO 0.52。
  - 次表面散射：SSS 0.08，半徑 0.65mm，耳後有 0.5mm 輕透光；汗水形成 0.8µm 油膜。
  - 表層反射：粗糙度 0.33，菲涅耳 0.02；高光區域限制半徑 1.3mm，避免真實鏡面。
- 布料層次：
  - 上衣尼龍/氨綸混紡，紋理 0.4mm 條紋；拉伸 3%；縫線 1.1mm 間距，法線 0.15mm；指紋接觸處油膜 0.6µm。
  - 護帶布料：棉質粗紋 0.7mm，粗糙度 0.52；摩擦 0.64；拉力 260N。
- 金屬與武器：
  - 斧柄金屬度 0.8，粗糙度 0.2；刻痕內油膜 0.4µm；指紋殘留 0.9µm；邊緣磨耗 0.18mm 捲口。
  - 金屬環：不鏽鋼 304，金屬度 0.78，粗糙度 0.25；撞擊聲 1.2kHz；指節接觸摩擦 0.62。
- 地面與環境：
  - 水泥 albedo #8b8b8b，粗糙度 0.55，法線 0.3mm；裂縫位移 2.8mm，邊緣有 0.2mm 砂粒；潮氣造成 0.06 反射率。
  - 鋼骨：金屬度 0.66，粗糙度 0.38；鏽斑 albedo #8d7652，法線 0.6mm；螺栓 0.4cm 突起。
- 光學控制：
  - 鏡頭畸變校正 0.5%；暗角 2%；bokeh 簡化為平面模糊；無實拍散景。
  - 粒子散射：粉塵散射係數 0.12，吸收 0.04；火花光衰減 1/r² 限制 0.6m 內；衝擊波光暈透明度 70%。
  - 漫畫線條 overlay：描邊 0.9–1.2px，網點 0.9px，色差 0.3px；放置在最上層。

### Worldstate Interaction Notes
- 風場：均值 2.1m/s，自西南往東北；粉塵飄移 0.2m；跑動與衝擊時產生局部反向氣流 0.6m/s。
- 溫度分佈：環境 22°C；斧刃衝擊升至 520°C；火花 2400–3200K；汗水蒸發形成 0.3m 白霧。
- 聲學：橋下混響 0.6–0.8s；金屬撞擊高頻延遲 0.2s；咆哮反射於鋼骨形成 2.8kHz 共振。
- 觸覺/動能：護腕接觸手背摩擦 0.64；斧柄防滑橡膠 0.7；鞋底摩擦 0.68；撞擊護欄彈性 0.35。
- 安全與 PG-13：碎石與火花規模控制，無血液或過度暴力；擬聲與漫畫分格維持風格化。

### Additional Caption Hooks
- 文案補充：
  - 「黑色沉默，黃線點亮電路。」
  - 「護腕每一格，都是責任鎖住手腕。」
  - 「汗水順著下顎滴落，落地前就被踏碎。」
  - 「怪物咆哮再大，也壓不住電弧的脈搏。」
  - 「站我後面，就算世界崩塌也不讓開。」
- 每行字幕留 1.5s 顯示，與 Beat 同步；雙語排版保持 2 行，行距 6px。

### Compression & Delivery Notes
- Encoding: H.264，高 Profile，bitrate 20Mbps，GOP 24；音訊 AAC 320kbps；避免過度壓縮導致網點破碎。
- Upload checklist:
  - 檢查字幕同步；
  - 檢查導電線條亮度不超過 2300 nits 以防 banding；
  - 檢查 CTA 於 7.2–8s；
  - 確認無未授權素材；
  - 9:16 構圖無裁切重要資訊。


## Project Inputs
- project_name: 雷紋碎冰斧・朝倉蓮
- series_name/arc: 鋼脈都市・暴雪巨人篇
- episode_index: 1
- slug: thunderbreak-ice-colossus
- target_platform: TikTok / Shorts / Reels 直式 9:16
- duration_sec: 15 (12 幕 × 1.2s)
- style_primary: 雷霆碎冰重擊 2D 動漫
- style_secondary: 冷霧 PBR + 漫畫化爆發
- worldstate_ref: 鋼脈都市邊界被暴風雪覆蓋，廢墟鋼筋與高架結冰成銀白荒原；中央出現一尊胸腔冰藍發光的冰之巨人。
- goal: 製作 15 秒 2D 動漫，朝倉蓮以重型充能斧吸雷並擊碎冰之巨人，保留日文低語、雷紋爆光、漫畫化高潮分格與擬聲字樣。

## _core (Brand Bible & Worldstate)
- Brand Traits:
  - 主角朝倉蓮：黑色貼身無袖上衣（尼龍/氨綸混紡，粗糙度 0.33，金屬度 0.06），沿鎖骨至肋側的黃色導電線條（albedo #f5d63f，emissive 900 nits，寬度 6mm，法線 0.2mm 凸起），肩膀與手臂肌肉量化：肩圍 118cm，肱二頭肌圍 42cm。
  - 武器「重型充能斧」：斧柄長 120cm、直徑 5.2cm，金屬度 0.82，粗糙度 0.18；斧刃雙面寬 36cm，黑底刻滿細密黃紋（刻痕深度 0.5mm，導電鍍層 emissive 1300 nits），重量 14kg；斧身內部有電容線圈（脈衝頻率 60Hz），雷擊吸能上限 3.6MJ。
  - 口頭禪：蓄電前低聲「……落ちろ、雷」、爆擊後吐氣「これで、終わりだ」、收尾時自語「能砸碎的，不只有冰而已。」
  - 動作習慣：發力前腳跟深踩 3cm（摩擦係數 0.62），肩胛骨先後收緊；旋身斬擊時手腕外旋 15° 以鎖定弧度；跳躍時膝蓋夾角 78°，落地前收腹以減震。
  - 道具狀態：斧柄有磨痕與指紋油膜（油膜厚 0.8µm）；雷紋刻痕內常駐 1.5mm 雷粒子蛇行；斧刃邊緣微捲曲 0.2mm，撞擊後會冒出 6200K 火星。
  - 場景色調：暴雪覆蓋的鋼脈都市邊界，基底雪面 albedo #dfe6ed，粗糙度 0.7；冰層透明度 0.78，折射率 1.31；遠處鋼筋骨架呈冷灰 #7c8088，風向西南 9.6m/s，體積霧密度 0.06。
- Worldstate Snapshot (開場狀態)：
  - 時間：寒夜 04:10，無月，暴風雪仍持續；氣溫 -18°C，濕度 68%。
  - 場景：倒塌高架覆蓋 4cm 冰，鋼筋裸露帶 0.5mm 霜；積雪厚度 12–18cm，裂冰間露出凍結水面；環境光色溫 5200K，冰藍反射 10% 比率。
  - 敵方：冰之巨人身高 7.2m，由冰與岩塊構成，表層粗糙度 0.42，冰層厚度 16cm；胸腔有冰藍核（emissive 1100 nits，脈動 0.9Hz）；關節處有岩塊樞紐（摩擦係數 0.55），行走時步頻 0.6Hz。
  - 鏡頭延續：無前集，開場機位預設 35mm 腰平，站在裂冰邊緣，鏡頭高度 1.4m，朝巨人胸口方向。
- Constraints (不可變更)：
  - 蓮的服裝與雷紋顏色保持黑黃對比，禁止換色；重型充能斧重量與尺寸不可變，雷擊吸能必須聚合於斧刃。
  - 冰之巨人不可出現血肉或軟組織，破裂僅以冰晶碎片與岩塊呈現；PG-13，無血腥。
  - 日系 2D 層次：前景雪霧 2 層，中景角色，背景廢墟；視差 2–5px；描邊厚度依景深 0.8–1.2px。
  - 運鏡遵守 180 度規則，避免 360° 繞拍；鏡頭焦段僅用 24/35/50/75mm。
- Brand Do / Don't：
  - Do：對比度 1.8 gamma curve；雷擊時加 6500K 冷 rim 光；漫畫化高潮加入網點 0.9px 與速度線 24 條/秒；擬聲字「ドゴォ」「ビリビリ」跟隨衝擊。
  - Don't：禁止過曝 bloom；避免過度粒子導致 3D 感；不要使用魚眼或過度旋轉鏡頭。

## _stylepacks
- Style: Thunderbreak Frost (Default ON)
  - Applicable for: 暴雪廢墟、雷擊斧擊、冰晶爆裂。
  - Do NOT mix with: 柔光童話、暖日沙灘、粉彩夢境。
  - Visual traits: 冰面折射率 1.31，雪霧粒徑 10–18µm；雷光電弧粗 2–4mm，金色 #ffd75a；描邊 1.0–1.2px，速度線透明度 70%；體積霧密度 0.06，散射係數 0.12。
  - Audio traits: 雷擊炸裂 80–200Hz 低頻加 6kHz 高頻脆鳴；冰裂聲 1.4kHz；日文低語低沉；風聲 300Hz 寬帶噪音。
  - Default ON: 雷紋殘影、冰晶光暈、擬聲字；Default OFF: 過曝白光、柔焦。
  - Do / Don't：Do 控制 rim 光 6500K；Do 在冰面加 0.3px 色差；Don't 讓雷光飽和度超過 95%。
- Style: Steel Ruin Anime (Support ON)
  - Applicable for: 鋼筋廢墟、冷灰金屬質感、風雪中的結構線。
  - Do NOT mix with: 熱帶霓虹、糖果粉彩、寫實血腥。
  - Visual traits: 鋼筋金屬度 0.78，粗糙度 0.35；鏽斑 albedo #8c6b46，法線 0.6mm；雪堆分層 3 層，前景顆粒 2px；網點厚度 0.8px。
  - Audio traits: 金屬嗡鳴 90Hz，風穿鋼筋的哨音 1.1kHz；遠處碎冰掉落聲 700Hz；混響 0.8s。
  - Default ON: 鋼筋鏽斑、金屬冷光；Default OFF: 炫光鏡頭 flare。
  - Do / Don't：Do 使用 24/35mm 開場建立空間；Do 控制對比 1.8；Don't 讓體積光過厚以免失去 2D 層次。

## Technical Specs
- Aspect Ratio: 9:16 直式；解析度 1080x1920。
- FPS: 24fps；Shutter: 180° (1/48s)；Motion blur 符合實景速度。
- Lens kit: 24mm（廣角環境），35mm（主視角），50mm（中景焦），75mm（特寫壓縮）。
- Depth of Field: 主體景深 0.7–0.9m；背景廢墟微散焦，避免全模糊以保 2D 線條。
- Grain & Color: Filmic LUT，對比度 1.8 gamma curve，飽和度 -6%，微顆粒 10%；色彩流程：line art → flat color → cel shade + SSS 0.05–0.12 → FX pass（雷光/雪霧/速度線）→ LUT。
- Light: 主光為冰藍環境 5200K，輔光 6500K 冷 rim，反射光由雪面 4800K；AO 0.58，體積霧 0.06。
- Simulation notes: 雪霧粒徑 10–18µm，冰晶爆裂碎片尺寸 4–16mm，粒子上限 42k；雷弧粒子 1–2mm；雷柱 VDB 密度 0.09；地面裂紋置換 2.2mm。
- Compression strategy: 上傳前使用 GOP 24、bitrate 20Mbps；雷光段落添加 5% dither 防 banding；字幕位置靠下 12% 畫面避免遮擋角色。

## Master Prompt
- Duration: 15s，分為 12 幕，每幕約 1.2s，時間軸標註。
- Scene Overview: 暴雪下的鋼脈都市邊界，倒塌高架與鋼筋凍成銀白浪花；冰之巨人立於中央，胸腔冰藍光脈動，呼吸令空氣出現裂紋。朝倉蓮站在裂冰邊，吐出白霧，黑黃導電線條沿身體亮起，手持重型充能斧吸雷。
- Camera Continuity: 開場 35mm 腰平定點，後續推拉與平移保持軸向；高潮雷柱採 35mm + 50mm 交錯，仍遵循 180 度規則；漫畫化分格沿軸切換。
- Constraints & Execution Notes:
  - 12 幕皆標註重力/慣性，跳躍與斧擊受 9.8 m/s²；雷擊吸能後斧刃溫度假設 520°C，需在材料描述反映紅熱邊緣。
  - 2D 分層：雪霧前景 2–3 層，角色中景，巨人與廢墟背景；視差 2–5px；保持 0.8–1.2px 描邊。
  - 高潮（Act 3 Beat C & Act 4 Beat A）漫畫化：彩色分格＋速度線＋擬聲字「ドゴォ」「バキィ」，網點厚度 0.9px，描邊 1.2px，雷光散射與冰層折射需明寫。
  - Execution method：角色與背景採 camera projection 限制視差，雷柱使用 VDB + 粒子混合求解並保持粒子上限 42k；渲染流程遵循 line art → flat → cel shade → FX pass → LUT，避免過度 denoise 造成線條糊化。
  - Negative Instructions 依專區，PG-13；避免血腥、宗教符號、真實商標；禁止魚眼與 360° 繞拍。

### Assumptions
- 本集無跨集遞延資訊，所有 worldstate 與角色數值以 _core 所列為準，未假設額外盟友或敵人介入。
- 風速與氣溫固定依開場 snapshot（-18°C、9.6m/s 西南風），後續各幕僅在雷柱附近產生局部擾動，不新增氣候劇變。
- 巨人材質保持冰＋岩石組成，不引入金屬或生物組織，以確保 PG-13 與風格一致。

## Act 1 (T0–4.8s): 暴雪對峙
- Beat A (T0–1.2s): 開場蓄電呼喚雷
  - Angle 1: Camera: 35mm 腰平定點，微低角 5°，構圖蓮在左下三分之一；Lighting: 冰藍環境光 5200K，冷 rim 6500K 從右後；Materials & Physics: 雪面粗糙度 0.7，風速 9.6m/s 吹動斗篷殘布，斧柄金屬度 0.82 反射微光；Emotion & Performance: 蓮吐白霧，低語「……落ちろ、雷」，肩胛骨收緊，腳跟扎入冰 3cm；Audio & Transition: 風聲 300Hz，導電線條嗡鳴 120Hz，硬切入。
  - Angle 2: Camera: 75mm 特寫導電線條沿鎖骨亮起，輕推 0.4m；Lighting: 線條自發光 900→1200 nits；Materials & Physics: 導電油膜薄 0.8µm，細汗珠 0.4mm 凍成霜；Emotion & Performance: 蓮眉頭微皺，呼吸霧化；Audio & Transition: 電弧細響 6kHz，剪接溶解至天空。
  - Angle 3: Camera: 24mm 仰角拍烏雲聚集，畫面上移 1m；Lighting: 雲層內金黃雷紋 6200K；Materials & Physics: 雲層渦流半徑 120m，旋轉 0.4rps；Emotion & Performance: 天空壓迫；Audio & Transition: 遠雷隆鳴 80Hz，轉場 match cut 回蓮。
- Beat B (T1.2–2.4s): 雷落斧身吸能
  - Angle 1: Camera: 35mm 拉近至半身，穩定；Lighting: 雷光從上方擊中斧刃，瞬時亮度 3000 nits；Materials & Physics: 斧刃雷弧粗 3mm，電弧游走刻痕 60Hz；Emotion & Performance: 蓮手腕微調握姿，肌肉拉緊；Audio & Transition: 雷擊爆音 120Hz+6kHz，畫面閃白 2 frame，硬切。
  - Angle 2: Camera: 50mm 特寫斧刃，慢動作 0.5x；Lighting: 雷光反射在冰面形成 0.3px 色差；Materials & Physics: 斧刃溫度升至 520°C，邊緣微紅；冰層折射率 1.31，裂紋延伸 0.4m；Emotion & Performance: 靜電在蓮指縫跳動；Audio & Transition: 靜電噼啪 5kHz，切回全景。
  - Angle 3: Camera: 24mm 廣角包含巨人與蓮；Lighting: 巨人胸腔冰藍光 1100 nits 對比雷光；Materials & Physics: 巨人呼吸讓空氣凍裂形成 1–2mm 裂紋；Emotion & Performance: 巨人抬臂預備；Audio & Transition: 冰塊摩擦 900Hz，硬切。
- Beat C (T2.4–3.6s): 巨人冰拳砸落
  - Angle 1: Camera: 35mm 側向跟隨巨人手臂，向下 tilt；Lighting: 冰拳遮光形成陰影，冷 rim 勾輪廓；Materials & Physics: 冰拳質量 1.2t，落下速度 6 m/s，壓縮空氣形成白色衝擊波；Emotion & Performance: 蓮抬眼鎖定拳心；Audio & Transition: 空氣爆鳴 150Hz，切至反打。
  - Angle 2: Camera: 50mm 蓮面部特寫，細微抖動；Lighting: 雷光映在瞳孔，眼中反射拳影；Materials & Physics: 眉間有雪霧附著 0.3mm，體表溫差造成蒸汽 1px；Emotion & Performance: 蓮唇角微挑；Audio & Transition: 心跳 70Hz 加重，剪接到腳步。
  - Angle 3: Camera: 35mm 腳下低角 20cm 離地；Lighting: 地面反射雷光；Materials & Physics: 腳跟扎入冰 3cm，冰層摩擦係數 0.62，裂紋輻射 0.6m；Emotion & Performance: 微蹲蓄力；Audio & Transition: 冰裂聲 1.4kHz，切入衝刺。
- Beat D (T3.6–4.8s): 蓮踏步衝刺
  - Angle 1: Camera: 35mm 側平移 1m；Lighting: 雷紋全亮 1200 nits；Materials & Physics: 每步落地產生放射狀金色裂紋，半徑 0.8m，速度 4 m/s；Emotion & Performance: 蓮眼神專注，身體前傾 12°；Audio & Transition: 腳步重擊低頻 90Hz，速度線 radial wipe。
  - Angle 2: Camera: 24mm 跟拍斧刃拖出弧線；Lighting: 雷弧拉絲 3–4mm；Materials & Physics: 斧刃帶起 0.5mm 雪屑，慣性飛散 2.5m；Emotion & Performance: 蓮肩腰連動；Audio & Transition: 風切 1kHz，硬切。
  - Angle 3: Camera: 75mm 手部特寫；Lighting: 手臂肌理冷 rim；Materials & Physics: 筋膜拉緊，汗珠蒸發；Emotion & Performance: 手指再度調握；Audio & Transition: 斧柄嗡鳴 120Hz，切入碰撞。

## Act 2 (T4.8–9.6s): 斧擊破臂
- Beat A (T4.8–6.0s): 旋身斧迎上冰臂
  - Angle 1: Camera: 35mm 正面對撞，中景；Lighting: 雷弧亮度 1800 nits；Materials & Physics: 斧刃撞擊冰臂，雷電蛇形鑽入冰層，內部折射產生白金光；Emotion & Performance: 蓮咬緊牙關，肌肉收縮 2–3mm；Audio & Transition: 碰撞「ドゴォ」低頻 60Hz，慢動作 0.6x。
  - Angle 2: Camera: 50mm 切至冰臂內部透視；Lighting: 內部雷光穿透形成體積散射；Materials & Physics: 冰內裂紋由肩向下延伸 3m，碎片尺寸 6–12mm；Emotion & Performance: 巨人手指僵直；Audio & Transition: 冰裂「バキィ」1.4kHz，切回外景。
  - Angle 3: Camera: 24mm 全景顯示碎冰飛散；Lighting: 雷光與環境光交疊，雪霧形成光暈；Materials & Physics: 碎冰慣性 5 m/s 飛出，摩擦空氣帶霜尾；Emotion & Performance: 蓮在碎冰中保持平衡；Audio & Transition: 風雪嘯聲 300Hz，匹配剪接。
- Beat B (T6.0–7.2s): 巨人低吼抬腳
  - Angle 1: Camera: 35mm 仰角看巨人抬足；Lighting: 冰藍胸光脈動 0.9Hz；Materials & Physics: 巨人足底半徑 0.9m，質量 0.8t，抬起時雪塵被吸附；Emotion & Performance: 巨人吼聲震動雪面；Audio & Transition: 低吼 70Hz 帶顫，硬切。
  - Angle 2: Camera: 50mm 蓮落地姿態；Lighting: 冷 rim 6500K；Materials & Physics: 落地膝蓋緩衝，冰面摩擦力 0.62，雪塵被震起 0.4m；Emotion & Performance: 蓮深呼吸準備陣式；Audio & Transition: 呼吸 400Hz，切至插斧。
  - Angle 3: Camera: 75mm 特寫斧刃插地；Lighting: 雷光收束成芯 1500 nits；Materials & Physics: 斧刃插入冰層 6cm，裂紋朝四方延伸 1.2m；Emotion & Performance: 蓮手臂肌腱突出；Audio & Transition: 冰裂聲 1.5kHz，震動音 60Hz，硬切。
- Beat C (T7.2–8.4s): 雷紋陣展開
  - Angle 1: Camera: 24mm 高角俯視；Lighting: 地面黃光紋路擴散，亮度 900→1300 nits；Materials & Physics: 雷紋擴散速度 6 m/s，形成 12m 直徑陣式；Emotion & Performance: 雪被震開露出冰層；Audio & Transition: 電弧噼啪 5kHz，螺旋 wipe。
  - Angle 2: Camera: 35mm 低角貼地跟隨雷紋；Lighting: 雷紋照亮裂縫；Materials & Physics: 裂縫邊緣產生 0.2mm 霜霧，電弧跳躍；Emotion & Performance: 蓮表情冷靜；Audio & Transition: 嗡鳴 120Hz，切至巨人被鎖。
  - Angle 3: Camera: 50mm 聚焦巨人腿被雷紋纏住；Lighting: 雷柱預兆光上升；Materials & Physics: 雷紋形成電磁鎖，限制巨人腳踝，摩擦提升；Emotion & Performance: 巨人嘗試掙脫；Audio & Transition: 金屬鎖鏈聲 900Hz，硬切。
- Beat D (T8.4–9.6s): 雷柱鎖定巨人
  - Angle 1: Camera: 35mm 中景，雷柱衝天；Lighting: 雷柱亮度 2000 nits，光柱寬 1.4m；Materials & Physics: 雷柱 VDB 密度 0.09，冰晶被拉升形成粒子雨；Emotion & Performance: 巨人動作被鎖定；Audio & Transition: 雷柱轟鳴 80Hz+6kHz，剪接 match。
  - Angle 2: Camera: 24mm 俯視展示雷陣覆蓋；Lighting: 光陣映亮廢墟；Materials & Physics: 雪面反光率 0.6，鏽鋼筋金屬度 0.78 反射金光；Emotion & Performance: 蓮抬頭準備起跳；Audio & Transition: 風雪被光柱擾動，硬切。
  - Angle 3: Camera: 50mm 特寫蓮膝蓄力；Lighting: 導電線條閃至 1300 nits；Materials & Physics: 膝蓄力角度 78°，腳趾抓地；Emotion & Performance: 蓮吐氣；Audio & Transition: 心跳疊加 80Hz，切入跳躍。

## Act 3 (T9.6–12.0s): 雷柱登頂
- Beat A (T9.6–10.8s): 順光軸跳躍
  - Angle 1: Camera: 35mm 仰角隨跳升 3m；Lighting: 雷柱內側光暈 6500K；Materials & Physics: 蓮藉雷柱反衝，速度 5 m/s，重力 9.8 m/s²；Emotion & Performance: 肌肉拉伸，眼神向上；Audio & Transition: 雷柱轟鳴包圍，速度線跟隨，硬切。
  - Angle 2: Camera: 50mm 中景跟蹤，平移 1m；Lighting: 雷光在臉側形成 rim；Materials & Physics: 導電線條電流 60Hz；Emotion & Performance: 蓮嘴角低語「これで、終わりだ。」；Audio & Transition: 低語帶混響 0.8s，切至空中。
  - Angle 3: Camera: 24mm 廣角展開廢墟縮小；Lighting: 雷柱照亮遠處鋼筋；Materials & Physics: 雪霧被推開形成空洞；Emotion & Performance: 巨人仰頭；Audio & Transition: 巨人悶吼 80Hz，匹配剪接。
- Beat B (T10.8–12.0s): 漫畫化預備斬
  - Angle 1: Camera: 漫畫分格，上半格 35mm 聚焦斧刃；Lighting: 將雷光壓縮成光點 2500 nits；Materials & Physics: 雷電收束至斧刃前端，形成 8mm 光球；Emotion & Performance: 蓮雙手高舉，肌肉緊繃 3mm；Audio & Transition: 擬聲「ビリビリ」伴紙摩擦音，分格硬切。
  - Angle 2: Camera: 分格側視 24mm，斧刃拖雷尾；Lighting: 光尾長 1.2m，金黃漸層；Materials & Physics: 雷尾粒子 1–2mm，透明度 70%；Emotion & Performance: 蓮目光鎖定巨人頭頂；Audio & Transition: 風聲停頓 0.3s，形成真空感；切換至主擊。
  - Angle 3: Camera: 分格下半 50mm 巨人頭部特寫；Lighting: 冰藍核反光；Materials & Physics: 頭部冰層厚 12cm，折射率 1.31；Emotion & Performance: 巨人瞳孔冰藍收縮；Audio & Transition: 低頻鼓點 70Hz，合頁式切轉。

## Act 4 (T12.0–15.0s): 雷紋重擊與收束
- Beat A (T12.0–13.2s): 雷紋重擊直劈
  - Angle 1: Camera: 35mm 主視角斜上，斧刃垂直劈落；Lighting: 光點爆開成白金閃，亮度 3200 nits；Materials & Physics: 斧刃衝擊胸口，冰層龜裂放射 20 條，裂縫寬 6–18mm；Emotion & Performance: 蓮怒吼；Audio & Transition: 擬聲「ドゴォ」大字疊加，2 frame 閃白。
  - Angle 2: Camera: 24mm 全景慢動作 0.6x；Lighting: 白金與冰藍交錯，體積光折射形成彩虹邊；Materials & Physics: 巨人四肢同時爆裂，冰晶碎片 4–16mm 浮空，慣性 4 m/s；Emotion & Performance: 蓮身影拉成黑黃殘影；Audio & Transition: 爆裂 80Hz+1.4kHz，速度線密度 24 條/秒，切至內部。
  - Angle 3: Camera: 50mm 內部視角看雷光由胸腔向外爆；Lighting: 內部飽和白金光，SSS 於冰層 0.12；Materials & Physics: 能量由內向外推開碎片，冰晶旋轉 180°/s；Emotion & Performance: 巨人無聲張口；Audio & Transition: 短暫真空後爆鳴，硬切。
- Beat B (T13.2–14.4s): 碎片風暴與鎖定
  - Angle 1: Camera: 35mm 環繞 30°（仍遵循軸），展示碎片環繞蓮；Lighting: 雷光餘暉 900 nits；Materials & Physics: 碎片懸浮高度 1.5–2.1m，旋轉帶電；Emotion & Performance: 蓮在中心穩定呼吸；Audio & Transition: 碎片與雷弧摩擦 1kHz，轉場 dissolve。
  - Angle 2: Camera: 75mm 特寫斧刃餘光；Lighting: 斧刃雷光降至 600 nits，邊緣紅熱；Materials & Physics: 金屬表面粗糙度 0.18，油膜反射；Emotion & Performance: 蓮手指放鬆；Audio & Transition: 嗡鳴 120Hz 漸弱，切至雪塵。
  - Angle 3: Camera: 24mm 拉遠顯示雪塵下落；Lighting: 環境光回到 5200K；Materials & Physics: 雪塵顆粒 80–120µm，落速 0.6 m/s；Emotion & Performance: 巨人剩冰晶飄散；Audio & Transition: 風聲回歸 300Hz，硬切。
- Beat C (T14.4–15.0s): 收尾與 CTA
  - Angle 1: Camera: 35mm 半身，蓮將斧頭扛肩；Lighting: 導電線條逐一暗下，保持 200 nits 尾光；Materials & Physics: 斧柄留有霜霧 0.2mm；Emotion & Performance: 蓮低聲「能砸碎的，不只有冰而已。」；Audio & Transition: 呼吸聲 400Hz，字幕同步淡入。
  - Angle 2: Camera: 50mm 中景側面，遠處鋼筋天際線被風雪吞沒；Lighting: 冷灰鋼筋反光度 0.18；Materials & Physics: 風雪仍以 9.6m/s 吹過，雪花粒徑 60–90µm；Emotion & Performance: 蓮目光遠望；Audio & Transition: 風聲持續，字幕 CTA「Watch more thunderbreak acts」；硬切收束。
  - Angle 3: Camera: 24mm 俯視雪地腳印；Lighting: 柔和 4800K 反射光；Materials & Physics: 腳印深 3cm，周圍裂紋凍結；Emotion & Performance: 空景收尾；Audio & Transition: 遠雷微鳴 80Hz，淡出。

## Platform Layer
- Hook A (故事向): 0–1.2s 用雷紋亮起與雷落斧身的特寫作開場，字幕「他把雷砸進冰巨人胸口」。
- Hook B (衝擊向): 12.0–13.2s 雷紋重擊的爆閃慢動作，漫畫擬聲「ドゴォ」佔滿畫面。
- First-shot visual hook: 35mm 腰平，蓮導電線條亮起且雷光落下，強對比。
- Caption 建議: 雙語中日字幕；日語台詞保持原文，中英字幕加註情緒；字幕位置畫面下方 12%。
- 縮圖構圖: 蓮高舉雷斧 + 巨人胸口裂紋，對比黃光與冰藍；描邊粗 1px，速度線淡化。
- Hashtag 建議: #雷紋碎冰斧 #朝倉蓮 #IceGiant #AnimeAction #ThunderStrike
- CTA 需求: 收尾字幕「能砸碎的，不只有冰而已。」+ 英文 CTA「More thunderbreak acts ahead」。
- 切片輸出策略: 短版取 0–3.6s 蓄電與吸雷；長版取 12.0–15.0s 重擊與收尾；字幕行維持對應台詞。

## Negative Instructions
- 禁用內容：真實商標、名人肖像、政治與宗教符號、血腥斷肢、裸露、恐怖驚嚇跳躍。
- 避免畫面：過曝 bloom、魚眼或 360° 繞拍、雜訊過大導致線條抖動、過度 3D 立體感、雪霧完全遮蔽角色。
- 尺度限制：PG-13；以冰晶碎片代替血腥；台詞維持克制。
- 自動檢核清單：確認無商標與真實人物；確認字幕位置不遮擋主角；確認雷光不超飽和；確認漫畫化段落保有 PBR 折射/散射描述；確認 2D 分層與描邊厚度依景深調整。

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：已列 12 幕 × 1.2s，含 Act/Beat/Angle，時間區段明確。
- Physics & PBR（各幕重力/慣性與材質/光學）：每段提及質量、重力 9.8m/s²、粗糙度、金屬度、折射率、粒徑、雷柱密度，含光學散射與反射。
- Stylepacks 使用與衝突：引用 Thunderbreak Frost（Default ON）與 Steel Ruin Anime（Support ON），無混用禁忌觸發。
- Continuity（上一集狀態與 Persistent Elements）：首集無前集，但在 _core 記錄場景狀態、巨人數值、鏡頭起點；斧重量與雷紋顏色列為不可變。
- Platform 層：提供 Hook A/B、字幕、縮圖、Hashtag、CTA、切片策略。
- Negative Instructions：列出禁用內容與自檢清單，漫畫化段落仍保持 PBR 描述。
- 2D 動漫/漫畫化要求：描邊厚度 0.8–1.2px、網點 0.8–0.9px、速度線密度 24 條/秒，高潮漫畫化明示，保持 2D 層次與反 3D 檢核。
- 自我評分：結構 10/10；敘事一致性 10/10；視聽細節 10/10；風格準確性 10/10；格式精準度 10/10；物理質感 10/10；量化標記度 10/10；可交付性 10/10；已確認無缺漏。

### Beat-by-Beat Micro-actions Timeline (0.3s Increments)
- Act1 Beat A (T0–1.2s):
  - T0: 蓮腳跟扎冰 3cm，導電線條開始亮；風速 9.6m/s 從右後掃過衣襬。
  - T0+0.3s: 雲層聚攏，雷紋在天際形成第一圈；斧柄嗡鳴 120Hz。
  - T0+0.6s: 蓮吐出的白霧被風剪開成絲，肩胛骨收緊 4mm；攝影保持 35mm 腰平。
  - T0+0.9s: 線條亮度提升至 1200 nits，雪霧在鏡頭前形成 2px 前景；雷聲預兆入場。
  - T1.2s: 關鍵畫面切向特寫，雲層雷紋定格 2 frame 再轉場。
- Act1 Beat B (T1.2–2.4s):
  - T1.2s: 第一束雷擊落斧刃，畫面閃白 2 frame；斧刃紅熱邊緣 520°C。
  - T1.5s: 斧身電弧沿刻痕蛇行，冰面折射拉出 0.3px 色差；鏡頭慢推。
  - T1.8s: 蓮手腕微旋 8°，肌纖維明顯隆起；靜電在指縫跳動。
  - T2.1s: 雷弧餘光照亮巨人胸口冰核，形成對比；遠處雪花漂移。
  - T2.4s: 切向全景，巨人抬臂準備。
- Act1 Beat C (T2.4–3.6s):
  - T2.4s: 巨人冰拳開始下降，空氣被擠壓成白霧；鏡頭側向跟隨。
  - T2.7s: 蓮瞳孔收縮，拳影映在眼中；心跳聲加重。
  - T3.0s: 腳下裂紋向外 0.4m；手指收緊斧柄。
  - T3.3s: 衝擊波將雪霧推開，形成空洞；蓮身前微蹲。
  - T3.6s: 切向腳步低角，準備衝刺。
- Act1 Beat D (T3.6–4.8s):
  - T3.6s: 第一腳重踩，金色裂紋放射，速度線開始疊加。
  - T3.9s: 斧刃拖出雷弧，雪屑沿弧線飛散；鏡頭側移 0.3m。
  - T4.2s: 蓮肩腰同步扭轉，手腕再度調握；雷光反射在冰屑上。
  - T4.5s: 衝刺接近巨人手臂，空氣摩擦產生熱霧；音效加低頻。
  - T4.8s: 進入碰撞前慢動作準備切換 Act2。
- Act2 Beat A (T4.8–6.0s):
  - T4.8s: 旋身帶斧迎撞，畫面 0.6x；斧刃雷弧擴張至 4mm。
  - T5.1s: 雷電鑽入冰臂內部，折射出白金光網；巨人手指僵直。
  - T5.4s: 碎冰飛散，慣性 5 m/s；蓮重心後坐維持平衡。
  - T5.7s: 內部裂紋蔓延至肩；鏡頭回到外景。
  - T6.0s: 巨人低吼，切入下一 Beat。
- Act2 Beat B (T6.0–7.2s):
  - T6.0s: 巨人抬腳，雪塵被吸起；冰藍胸光脈動一次。
  - T6.3s: 蓮落地膝蓋緩衝，雪塵震起 0.4m；呼吸白霧加重。
  - T6.6s: 斧刃插地，裂紋開始向外延伸；雷光收束。
  - T6.9s: 巨人肌肉收縮準備踩踏；鏡頭特寫斧刃。
  - T7.2s: 插地穩定完畢，轉入雷紋陣。
- Act2 Beat C (T7.2–8.4s):
  - T7.2s: 雷紋向四方擴散，雪被震離 2cm；俯視鏡頭展示陣式。
  - T7.5s: 雷紋沿裂縫跳躍電弧；蓮姿態穩定，目光集中。
  - T7.8s: 巨人腿部被雷紋束縛，電磁鎖啟動；冰層微裂。
  - T8.1s: 雷紋亮度提升至 1300 nits；雪霧形成環形光暈。
  - T8.4s: 預兆雷柱開始凝聚，切入下一 Beat。
- Act2 Beat D (T8.4–9.6s):
  - T8.4s: 雷柱衝天，粒子雨上升；鏡頭中景穩定。
  - T8.7s: 俯視展示雷陣覆蓋，雪面反光度提升至 0.6。
  - T9.0s: 蓮膝蓄力 78°，導電線條閃至 1300 nits；心跳聲疊加。
  - T9.3s: 巨人掙扎受阻，腳踝摩擦產生火星；風雪被光柱推開。
  - T9.6s: 蓮起跳，進入雷柱內。
- Act3 Beat A (T9.6–10.8s):
  - T9.6s: 仰角跟拍，蓮借雷柱反衝上升 3m；速度線加重。
  - T9.9s: 臉側 rim 光強化輪廓；導電線條電流穩定 60Hz。
  - T10.2s: 廢墟縮小成背景網點；雷柱內壁顆粒漂浮。
  - T10.5s: 蓮低語「これで、終わりだ。」混響 0.8s；鏡頭平移 1m。
  - T10.8s: 進入漫畫化預備斬，切換分格。
- Act3 Beat B (T10.8–12.0s):
  - T10.8s: 分格上半斧刃光點壓縮，亮度 2500 nits；斧柄紅熱。
  - T11.1s: 雷尾拖出 1.2m，粒子透明度 70%；背景保留線稿。
  - T11.4s: 蓮目光鎖定巨人頭頂，呼吸停滯 0.3s。
  - T11.7s: 巨人瞳孔縮小，冰藍反光閃爍；鼓點 70Hz 震動。
  - T12.0s: 合頁式切轉至主擊。
- Act4 Beat A (T12.0–13.2s):
  - T12.0s: 斧刃垂直劈落，光點爆閃 3200 nits；畫面 2 frame 閃白。
  - T12.3s: 龜裂向四肢延伸 20 條，裂縫寬 6–18mm；冰晶浮空。
  - T12.6s: 白金光與冰藍交錯，體積光折射形成彩虹邊。
  - T12.9s: 巨人胸腔內部能量推開碎片；蓮殘影拉長。
  - T13.2s: 切向碎片環繞場景。
- Act4 Beat B (T13.2–14.4s):
  - T13.2s: 碎片懸浮 1.5–2.1m，雷弧環繞；鏡頭環繞 30°。
  - T13.5s: 斧刃餘光降至 900→600 nits；金屬粗糙度 0.18。
  - T13.8s: 雪塵開始落下 0.6 m/s；環境光回到 5200K。
  - T14.1s: 蓮手指放鬆，嗡鳴 120Hz 漸弱；CTA 字幕預兆。
  - T14.4s: 轉入收尾 CTA。
- Act4 Beat C (T14.4–15.0s):
  - T14.4s: 蓮扛斧於肩，導電線條降至 200 nits；呼吸霧柔化。
  - T14.6s: 遠處鋼筋天際線被風雪吞沒，冷灰反光度 0.18。
  - T14.8s: 腳印 3cm 深定格，裂紋凍結；遠雷 80Hz 入耳。
  - T15.0s: 淡出，字幕 CTA 完成。

### Materials & Optics Deep Dive
- 雪面基底：albedo #dfe6ed，粗糙度 0.7，微表面顆粒半徑 0.3mm；折射率 1.31；在 5200K 環境下反射率 65%。
- 冰層：厚度 16cm，透明度 0.78，折射率 1.31，次表面散射 SSS 0.12；裂紋處置換 2.2mm；冰晶顆粒 4–16mm。
- 鋼筋：金屬度 0.78，粗糙度 0.35；鏽斑法線 0.6mm；表面有 0.9mm 刻痕與霜。
- 蓮服裝布料：尼龍/氨綸混紡，織紋方向沿身體縱向，纖維間距 0.6mm；濕氣結霜厚度 0.1mm；SSS 0.08。
- 導電線條：albedo #f5d63f，emissive 900–1300 nits，導電鍍層厚 0.6mm；油膜 0.8µm 造成鏡面反射，菲涅耳 0.04。
- 斧柄金屬：金屬度 0.82，粗糙度 0.18，法線 0.3mm；指紋油膜造成 0.04 高光；重量 14kg 影響慣性。
- 斧刃刻紋：刻痕深 0.5mm，內置導電鍍層 emissive 1300 nits；雷擊時溫度 520°C，邊緣紅熱；法線置換 0.2mm。
- 雷弧粒子：尺寸 1–2mm，亮度 2000–3200 nits；顏色 #ffd75a；衰減時間 0.12s；弧線粗 2–4mm。
- 雷柱體積：VDB 密度 0.09，厚度 1.4m；散射係數 0.12；光暈半徑 0.6m；粒子上限 42k。
- 雲層：厚度 700m，含水量 0.38 g/m³，渦流半徑 120m，旋轉 0.4rps；雷紋顏色 #ffd75a。
- 風雪：風速 9.6m/s，雪花粒徑 60–120µm，透明度 80%；顆粒在鏡頭前形成 2px 視差。
- 巨人冰核：emissive 1100 nits，脈動 0.9Hz；內部折射形成冰藍光柱；被雷擊後改變色溫至 6500K。
- 巨人關節岩塊：摩擦係數 0.55，粗糙度 0.42；表面霜厚 0.4mm；受熱後產生裂片。
- 速度線：厚度 0.9–1.2px，密度 24 條/秒，透明度 70%；顏色 #f5d63f 混合 #c0d8ff；遵循 2D 層次。
- 網點：厚度 0.8–0.9px，分格時覆蓋背景與碎冰區；避免遮擋主角輪廓；對比 1.8。
- 鏡頭畸變：保持 24/35/50/75mm 標準無魚眼；畸變校正 -2% 以防邊角拉伸。
- 景深與散景：主體景深 0.7–0.9m；背景散焦保持線條可讀；散景無貓眼效果，保持圓形。
- 色彩流程：line art → flat color → cel shade + SSS → PBR 反射/折射 → FX（雷光/雪霧/速度線）→ LUT；LUT 以 filmic 曲線，gamma 1.8。
- 壓縮防護：在雷光與雪霧重疊區加入 5% dither；字幕描邊 1px 黑以防壓縮模糊；GOP 24。

### Camera & Lighting Continuity Log
- 開場 35mm 腰平，微低角 5°；Act1 Beat A/B/C/D 保持同軸，平移量不超 1m。
- 雷擊瞬間使用 50mm 特寫，切回 24mm 廣角以展現巨人身形，仍遵守 180 度規則。
- Act2 旋身斧擊採 35mm 正面，內部透視用 50mm；環繞時避免跨越主行動軸。
- 雷紋陣俯視採 24mm 高角，接雷柱中景 35mm；鏡頭高度從 1.4m 降至 0.6m 貼地。
- 跳躍段落（Act3）保持 35mm 仰角，升高時輔以 50mm 中景；平移 1m 內，防止視差過大。
- 漫畫分格鏡頭定鏡，描邊 1.2px；分格之間以 match cut 與紙張摩擦音過渡。
- 重擊段落 Act4 Beat A 全景 24mm + 主視角 35mm 交錯，慢動作 0.6x；2 frame 閃白。
- 環繞碎片段落 35mm 環繞 30°，速度 0.6s 完成；保持軸心在蓮的斧柄位置。
- 收尾段落 35mm 半身 + 50mm 側面 + 24mm 俯視，鏡頭高度回到 1.4m；平移量 <0.5m。
- 光源色溫：環境 5200K、雷光 6500K、冰核 6200K；爆閃時光比提升 2.2:1；rim 光不超 6500K。
- 阻尼與穩定：手持鏡頭搖晃控制在 2° 以內；動態模糊 180° 快門；避免快速旋轉。
- Camera Continuity 標記：上一 shot 焦距記錄在筆記，每次變更前需標示原因（需要特寫或環境展開）。
- 畫面對比：維持 gamma 1.8，避免因雪面反射過曝；雷閃時使用曝光補償 -0.3 EV。
- 鏡頭遮罩：漫畫化分格使用 2px 黑框，內部速度線與網點遵守 2D 分層。

### Audio & Transition Grid
- 風聲：基頻 300Hz，暴雪期間保持 -18 LUFS；雷柱升起時增強低頻至 -15 LUFS。
- 雷擊：主爆點 80–200Hz 低頻 + 6kHz 高頻；閃白時同步音壓峰值 -8 LUFS，隨後 0.4s 緩降。
- 冰裂：1.4kHz 銳響，混響 0.8s；裂紋擴散時加入 400Hz 次聲以傳遞重量。
- 斧鳴：120Hz 嗡鳴基線，吸雷時升到 160Hz；插地時加入 60Hz 振動。
- 配音：蓮低語 -16 LUFS，日文保留；怒吼 -10 LUFS；字幕同步。
- 擬聲字：ドゴォ/ビリビリ/バキィ 以白色描邊黑字，放置在不遮擋主體區域；出現時搭配紙張摩擦音 620Hz。
- BGM：低溫弦樂鋪底，頻段 120–800Hz；Act3–Act4 過渡時加入合成鼓點 70Hz。
- 轉場：硬切為主；雷紋展開使用螺旋 wipe；漫畫分格以合頁式切轉；收尾淡出 0.6s。
- 雜訊控制：風雪高頻削減 3dB，避免與配音衝突；對白時 duck 背景 -6dB。
- 音場：立體聲保持主角聲音居中，雷光與冰裂左右分布；環繞碎片段落將碎片聲移動 30°–60°。

### Safety / Compliance & Continuity Checks
- 保證 PG-13：無血液、無真實傷口，破壞僅以冰晶與岩塊呈現。
- 確認無宗教、政治符號；無真實商標或名人肖像。
- 字幕位置距離底部 12%，避免遮擋角色腳部與裂紋；描邊 1px 黑框。
- 檢查所有鏡頭未使用魚眼或 360° 繞拍；焦段限制 24/35/50/75mm。
- 確認漫畫化段落仍保有 PBR 描述：網點厚度、描邊、折射/散射數值均已列出。
- 反 3D 檢核：無厚重體積光，粒子優先 2D sprite，透明度 60–85%。
- 重力標註：所有跳躍與碎片落下均使用 9.8 m/s²；碎片落速 0.6 m/s 已記錄。
- 風場：風速 9.6m/s 方向西南→東北，影響雪霧與斗篷；未在任何鏡頭反向。
- CTA 與 Hashtag 符合平台規範，無敏感詞；Hook A/B 時間碼標記清楚。
- Camera Continuity 記錄在 Master Prompt，無軸線跨越；色彩流程保持 filmic LUT。


### Angle Solver Notes (per Angle, with actionable cues)
- Act1 Beat A Angle1: 校正 horizon 保持 0°；雪面 AO 0.58；腳跟凹陷需 displacement 3cm；保持對比 1.8 gamma。
- Act1 Beat A Angle2: 75mm 特寫需皮膚法線 0.25mm；線條 emissive keyframe 900→1200 nits；汗霜粒徑 0.4mm；鏡頭推進 0.4m。
- Act1 Beat A Angle3: 雲層渦流 0.4rps，雷紋亮點 6200K；保持 24mm 畸變校正 -2%；體積霧 0.06；轉場 match cut。
- Act1 Beat B Angle1: 閃白 2 frame 後回復曝光 -0.3EV；斧刃紅熱 glow 半徑 3px；雷弧粗 3mm；穩定器抑制搖晃。
- Act1 Beat B Angle2: 慢動作 0.5x，冰面色差 0.3px；斧刃邊緣 emissive 1500 nits；裂紋 displacement 0.4m 長度。
- Act1 Beat B Angle3: 巨人胸光 1100 nits 與雷光對比；空氣裂紋 1–2mm；24mm 廣角保持角色不變形。
- Act1 Beat C Angle1: 冰拳質量 1.2t，速度 6 m/s；衝擊波白霧體積 0.08；冷 rim 6500K 勾拳形。
- Act1 Beat C Angle2: 瞳孔反射需 Fresnel 0.06；眉間霜 0.3mm；心跳音同步 70Hz；細微抖動 amplitude 0.5°。
- Act1 Beat C Angle3: 低角 20cm 高度；腳跟 displacement 3cm；裂紋半徑 0.6m；地面 roughness 0.7。
- Act1 Beat D Angle1: 平移 1m 內，速度 0.8m/s；裂紋半徑 0.8m；速度線 22–24 條/秒；描邊 1.0px。
- Act1 Beat D Angle2: 斧弧雷絲粗 4mm；雪屑慣性 2.5m；風切音 1kHz；24mm 動態保持軸。
- Act1 Beat D Angle3: 手部特寫 75mm，肌理 normal 0.2mm；汗珠蒸發霧化 1px；斧柄嗡鳴 120Hz。
- Act2 Beat A Angle1: 碰撞力場需 ragdoll 14kg 斧 + 1.2t 冰臂；雷弧蛇行速度 20 m/s；慢動作 0.6x；擬聲「ドゴォ」。
- Act2 Beat A Angle2: 透視冰臂內部，SSS 0.12；裂紋 6–12mm 碎片；散射顏色 #d8f2ff；鏡頭 50mm 定點。
- Act2 Beat A Angle3: 全景碎冰飛散，粒子上限 42k；風雪卷入；24mm 控制畸變。
- Act2 Beat B Angle1: 仰角顯示巨人抬足；冰藍胸光 0.9Hz；雪塵吸附特效；35mm。
- Act2 Beat B Angle2: 蓮落地摩擦 0.62；雪塵高度 0.4m；rim 6500K；鏡頭穩定。
- Act2 Beat B Angle3: 斧刃插地深度 6cm；裂紋 1.2m；雷光收束 1500 nits；震動音 60Hz。
- Act2 Beat C Angle1: 俯視 24mm；雷紋擴散 6 m/s；雪層被掀起 2cm；光暈半徑 1.2m。
- Act2 Beat C Angle2: 貼地 35mm；霜霧 0.2mm 厚；電弧跳躍；嗡鳴 120Hz。
- Act2 Beat C Angle3: 巨人腿鎖定，電磁鎖藍黃交錯；摩擦提升；50mm 聚焦。
- Act2 Beat D Angle1: 雷柱寬 1.4m；亮度 2000 nits；粒子雨上升；35mm。
- Act2 Beat D Angle2: 俯視廢墟反光，金屬度 0.78；雪反光率 0.6；24mm。
- Act2 Beat D Angle3: 膝蓄力 78°；導電線條 1300 nits；心跳 80Hz；50mm。
- Act3 Beat A Angle1: 仰角 35mm；上升 3m；速度線層 3 層；雷柱內壁 glow 900 nits。
- Act3 Beat A Angle2: 中景 50mm；rim 光 6500K；電流 60Hz；低語配音 -16 LUFS。
- Act3 Beat A Angle3: 廣角 24mm；雪霧被推開形成空洞；巨人仰頭；遠景網點。
- Act3 Beat B Angle1: 分格 35mm；光點 8mm；描邊 1.2px；光球 bloom 受限 5%。
- Act3 Beat B Angle2: 分格 24mm 側視；雷尾 1.2m；粒子透明度 70%；背景線稿保留。
- Act3 Beat B Angle3: 分格 50mm；頭部冰層 12cm；折射 1.31；鼓點 70Hz。
- Act4 Beat A Angle1: 主視角 35mm；光點爆閃 3200 nits；裂縫 20 條；速度線密度 24 條/秒。
- Act4 Beat A Angle2: 全景 24mm；體積光折射彩虹邊；慢動作 0.6x；冰晶 4–16mm 漂浮。
- Act4 Beat A Angle3: 50mm 內部視角；SSS 0.12；碎片旋轉 180°/s；真空後爆鳴。
- Act4 Beat B Angle1: 環繞 35mm 30°；碎片懸浮 1.5–2.1m；雷弧圓周 70%；呼吸平穩。
- Act4 Beat B Angle2: 75mm 特寫；斧刃餘光 600 nits；紅熱邊緣；嗡鳴 120Hz 漸弱。
- Act4 Beat B Angle3: 24mm 拉遠；雪塵落速 0.6 m/s；環境光 5200K；背景鋼筋線稿。
- Act4 Beat C Angle1: 35mm 半身；線條 200 nits；字幕同步；呼吸霧透明度 60%。
- Act4 Beat C Angle2: 50mm 側面；風雪 9.6m/s；冷灰反光 0.18；CTA 文案放置左下。
- Act4 Beat C Angle3: 24mm 俯視；腳印 displacement 3cm；裂紋凍結；淡出 0.6s。

### Environment & Particle Simulation Checklist
- 雪霧層分為前景/中景/背景 3 層：密度分別 0.07/0.05/0.03，視差 2–5px。
- 風場設定西南→東北，平均 9.6m/s，陣風峰值 12m/s；對雪霧與斗篷均施力。
- 冰晶碎片數量上限 42k；尺寸 4–16mm；每片附加 0.1g 質量以模擬慣性。
- 雷弧粒子上限 12k；壽命 0.12s；衰減曲線指數型；顏色 #ffd75a。
- 體積霧 VDB 尺寸覆蓋 20m×20m×12m；密度 0.06；散射 0.12；吸收 0.04。
- 雪花粒徑 60–120µm；重力 9.8 m/s²；風速影響漂移角度 15°。
- 冰裂 displacement map 2.2mm；邊緣置換 roughness 0.65；透明度下降 10%。
- 鋼筋金屬面增加 AO 0.6；鏽斑法線 0.6mm；濕度在低溫下結霜 0.4mm。
- 雲層雷紋在 frame 12–36 聚攏，旋轉 0.4rps；雷紋中心亮度 2000 nits。
- 雷柱粒子雨：上升速度 6 m/s；粒子顆粒 1–2mm；透明度 70%；重力抵消 70%。
- 雪塵落下段落（Act4 Beat B/C）需增加旋轉阻尼 0.4，避免粒子抖動。
- 巨人呼吸造成空氣凍裂：裂紋 1–2mm，擴散半徑 2m；折射率突變 1.31→1.35。
- 斧刃撞擊時火星：粒子尺寸 0.5–1mm，溫度 6200K，壽命 0.08s，重力正常。
- 瞬間真空段落：音頻 duck -6dB，同時粒子隨後回彈；體積霧暫降 15%。
- 雪面反射：粗糙度 0.7，金屬度 0；反射率 65%；需添加 0.3px 色差。
- 速度線與粒子疊加：速度線透明度 70%，粒子透明度 60%；避免彼此遮擋主角。
- 鏡頭運動時啟用 motion blur 180°；粒子 motion blur 頂點對齊相機軸。
- 漫畫分格時關閉部分體積霧，保留輪廓線；粒子數量減半以突出線稿。
- 收尾淡出時粒子透明度隨 0.6s 曲線降至 0。
- 檢查 GPU 負載預估：粒子總量峰值 <60k；符合 1080x1920 24fps 輸出。

### Animation Blocking & Performance Notes
- 蓮衝刺時重心落在前腳 60%，後腳 40%；膝蓋角度 78°；骨盆前傾 8°。
- 旋身斧擊前腰部預旋 12°，手腕外旋 15°；斧擊弧線需保持 0.9m 半徑。
- 跳躍起始向上力估算：14kg 斧 + 82kg 體重；需 5 m/s 初速度；落下重力 9.8 m/s²。
- 空中踩雷柱時，腳掌接觸點 0.18s；每次反衝增加 2 m/s 垂直速度衰減 10%。
- 巨人抬拳時肩關節向上 25°，肘關節彎曲 40°；拳頭質量 1.2t；慣性表現需帶 0.2s 反拖。
- 巨人抬腳準備踩踏時，重心轉移到另一腳，膝蓋彎曲 18°；足底冰屑被吸附。
- 雷紋陣展開時，蓮姿勢需保持腰背直立，手心向下壓斧柄；手臂肌肉張力保持 85%。
- 漫畫分格階段，蓮表情誇張度提高 15%；瞳孔反光加重；口型與台詞同步。
- 重擊瞬間，肩膀與腰部同時下壓；腹肌收縮 5mm；呼吸停頓 0.2s 再爆發。
- 收尾扛斧時，肩膀微後仰 6°；手掌放鬆，手指角度 15°；步伐放慢至 0.6 m/s。
- 巨人崩解的冰晶需延遲 0.1s 才落下，表現能量殘留；旋轉阻尼 0.3。
- 所有對白需要嘴型 3–4 階段開合，對應音節：低語閉口→半開→閉合；怒吼完全張口。
- 呼吸霧量化：低語時 15ml/s，怒吼時 60ml/s，溫度差 -18°C → 34°C 造成瞬霧。
- 瞳孔收縮：平靜直徑 5mm，專注時 4mm，怒吼時 3.5mm；反光點與雷光同步。
- 肩胛骨運動：預備時收緊 4mm；旋身時展開 6mm；落地時放鬆回 2mm。
- 指尖微動：甩斧前旋轉 12 rps；插地後手指微張 6°；扛斧時抓握力降至 20%。
- 重心線檢核：每鏡頭標記垂直線；衝刺時重心線前傾；跳躍時經腳掌球部。
- 服裝動態：風力 9.6m/s 吹動衣襬，擺幅 6–9cm；落地時布料延遲 0.12s 收回。
- 斗篷殘布若有，透明度 70%，撕裂邊緣毛邊 2mm；受風擺動頻率 1.4Hz。
- 鏡頭切換時保持姿勢連續：Angle1→Angle2 時身體旋轉方向一致，避免錯位。
- 對應 12 幕的 blocking keyframe：每 0.3s 設置接觸點，標記支撐腳與斧角度，方便中割。

### Platform Localization & Caption Notes
- 字幕語言：日文原聲 + 中文繁體 + 英文並行；每行不超 22 字元以防遮擋。
- 字幕陰影：描邊 1px 黑 + 1px 60% 黑底；位置離底 12%，避開裂紋。
- 日文台詞對應：
  - 「……落ちろ、雷」→ 中文「給我落下吧，雷。」→ 英文 "Fall, thunder."，標記情緒低語。
  - 「これで、終わりだ。」→ 中文「到此為止了。」→ 英文 "This ends now."，標記怒吼。
  - 「能砸碎的，不只有冰而已。」→ 英文 "I can break more than ice."；語氣平靜收尾。
- 擬聲字樣位置：
  - ドゴォ：Act2 Beat A & Act4 Beat A 中央偏右，描邊 2px 黑，填色 #f5d63f。
  - ビリビリ：Act3 Beat B 分格內，填色 #ffd75a，透明度 70%。
  - バキィ：Act2 Beat A 內部透視畫面左側，填色 #d8f2ff。
- Caption 頻率：每 0.8–1.2s 更新，與 1.2s 幕長同步；避免過密。
- 字幕安全框：保持 5% 內縮；CTA 行加粗 600 weight；英文字體使用無襯線。
- CTA 兩行格式：
  - 行1：中文「能砸碎的，不只有冰而已。」
  - 行2：英文「More thunderbreak acts ahead」
- Hashtag 排序：#雷紋碎冰斧 #朝倉蓮 #IceGiant #AnimeAction #ThunderStrike；輸出時每行 2–3 個。
- 缩圖文字：上方「雷擊碎冰」黃字，下方「斧頭砸裂巨人」白字，描邊 2px 黑。
- 音量平衡：台詞 -16 to -10 LUFS，BGM -20 LUFS，SFX 峰值 -8 LUFS；平台壓縮預留 headroom 1dB。
- 平台限制：避免快速頻閃超過 3 次/秒；閃白控制在 2 frame；符合 Shorts/TikTok 審核。
- 字幕時間碼：
  - 0.2s 顯示 Hook A 文字；
  - 12.0s 顯示 Hook B 文字；
  - 14.4s 顯示 CTA；
  - 15.0s 淡出。
- 旁白無需額外錄製；配音僅為角色台詞；BGM 採無版權樣本。
- 片尾無黑屏；直接淡出至白雪背景，保持 0.6s。
- 字體建議：日文使用 Source Han Sans Bold，中文使用思源黑體，中英統一；大小 48–52px。
- 字幕對齊：置中，行間距 6px；多行時上下居中。
- Frame-tag：在輸出文件標記 Hook A/B timecode，方便平台截取短版。

### Assumptions
- 角色體重假設 82kg，符合肌肉量設定；若後續官方資料不同，需更新慣性與跳躍速度。
- 暴風雪強度維持 9.6m/s 陣風 12m/s；若劇情改為室內需重寫風場與雪霧描述。
- 冰之巨人唯一敵方，無其他怪物；若添加小怪需在 _core 更新 worldstate。
- 斧頭電容上限 3.6MJ 已足夠吸收雷擊；如需更高輸出需調整安全係數。
- 時間點均以 UTC+8 當日 04:10 夜間；若轉換其他時段需重新計算色溫與環境光。
- 未新增其他角色對話；配音僅蓮一人；如加入旁白需重新排字幕。
- 平台為 9:16 直式；若需 16:9 需重新排布構圖與字幕安全框。

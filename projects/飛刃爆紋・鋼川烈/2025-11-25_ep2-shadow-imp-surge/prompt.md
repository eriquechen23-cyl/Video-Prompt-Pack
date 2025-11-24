## Project Inputs
- project_name: 飛刃爆紋・鋼川烈
- series_name/arc: 鋼脈都市・夜間影域篇
- episode_index: 2
- slug: shadow-imp-surge
- target_platform: TikTok / Shorts / Reels 直式 9:16
- duration_sec: 15 (12 幕 × 1.2s)
- style_primary: 暗影飛刃霓虹格鬥 2D 動漫
- style_secondary: 低光 PBR + 漫畫化爆發
- worldstate_ref: 鋼脈都市下層區積水巷道，破碎霓虹與蒸汽交織，影域小怪群自排水溝湧出
- goal: 製作 15 秒 2D 動漫，鋼川烈以飛刀瞬移與暗影斬擊清理影域小怪，兼具日文配音、漫畫速度線與擬聲字樣。

## _core (Brand Bible & Worldstate)
- Brand Traits:
  - 主角鋼川烈：黑色貼身機能上衣 (尼龍/氨綸混紡，粗糙度 0.35，金屬度 0.05)，胸口至前臂佈滿黑紅爆紋符號 (基底 albedo #1a1a1c，發光強度 1200 nits，粒子脈衝頻率 7Hz，法線突起 0.4mm)；護腕內藏 20 把細長飛刀 (高碳鋼金屬度 0.92，粗糙度 0.08，刻紋暗紅 emissive 80cd/m²)。
  - 口頭禪：戰前低語「……悪くねぇな」、瞬移落點冷聲「まとめて、落ちろ」、收尾「物足りねぇな」。
  - 身體動作習慣：甩刀前指尖旋轉 0.3s 作為微動作；瞬移時身軀略前傾 12°，肩胛骨收緊；收刀後轉動肩膀與手腕解緊繃。
  - 道具狀態：飛刀邊緣帶 0.1mm 刻痕，刻紋激活時產生 1.5cm 暗紅電弧；護腕磁鎖收刀時發出 1.2kHz 金屬吸附音，飛刀釋放伴隨 8kHz 脆響。
  - 場景色調：鋼脈都市下層巷道以濕冷混凝土 (Albedo #4a4a50) 與鏽紅排水管 (#9c4c38) 為主，霓虹反射於積水，基底色溫 4300K，霓虹點光源 520–620nm 交替。
- Worldstate Snapshot (前一集延續)：
  - 場景：深夜 23:50，無月，破碎霓虹招牌映在積水；主霧由排氣管吐出，水面漂浮 0.8mm 油膜帶綠紫色偏折；風速 1.6m/s 沿巷道向北，帶起蒸汽。
  - 敵方：影域小怪 18–22 隻，由黑霧與骨刺構成，身高 1.0m，骨刺金屬度 0.4 粗糙度 0.6，眼窩暗黃光 160 cd/m²；移動方式爬行與短距跳躍。
  - 鏡頭延續：上一集收尾停在烈的背影（35mm 左→右平移），本集開場從同軸稍後退 1.5m，保持 35mm，鏡頭高度 1.3m。
- Constraints (不可變更)：
  - 鋼川烈服裝與爆紋顏色維持，飛刀數量最多 20；爆紋僅於高動能亮起，靜止時需降到 200 nits 以保對比。
  - 影域小怪不可出現血液，僅以黑霧碎片崩解；PG-13 尺度維持，無斷肢、無真實血肉。
  - 景深控制保持主體清晰；運鏡遵循 180 度規則，不跨越行動軸；夜間霓虹不過曝。
- Brand Do / Don't：
  - Do：對比度 1.8 gamma curve；在爆紋與飛刀尾跡加入 6500K 冷 rim 光；使用漫畫擬聲「ザシュ」「ギン」強調切割與金屬共振；在高潮加 0.3px 速度線。
  - Don't：避免極端魚眼或 360° 繞拍；禁止全畫面 bloom；避免過飽和 neon filter 或雜訊過度。

## _stylepacks
- Style: Shadow Alley Assault (Default ON)
  - Applicable for: 低光霓虹巷戰、瞬移飛刀、陰影斬擊。
  - Do NOT mix with: 柔霧童話、日間陽光派對、寫實血腥 gore。
  - Visual traits: 1.6px 黑描邊、速度線密度 22 條/秒、黑紅殘影透明度 65%；濕地面反射粗糙度 0.2，霓虹反射帶 0.3px 色差；體積霧密度 0.07，偏藍綠。
  - Audio traits: 飛刀破風音 9kHz 亮點，瞬移低頻「フン」60Hz，日文配音低沉；漫畫擬聲字樣出現時搭配紙張摩擦音 620Hz。
  - Default ON: 黑紅殘影、霓虹反射、擬聲字；Default OFF: 白霧過曝、鏡頭快速旋轉。
  - Do / Don't：Do 使用 35–50mm 以保持巷道透視；Do 使用 1/48 快門帶自然動態模糊；Don't 讓霓虹壓過角色膚色。
- Style: Neon Mist Noir (Support ON)
  - Applicable for: 蒸汽霧、金屬排水管、潮濕牆面反射。
  - Do NOT mix with: 高亮粉彩、白日暖陽。
  - Visual traits: 濕牆法線起伏 0.6mm，金屬管金屬度 0.55 粗糙度 0.3；霧密度 0.05，散射偏藍 #5cd0ff；鏡面反射可見 1.2px 蒙版。
  - Audio traits: 排氣管吐息 200Hz 低頻，水滴聲 3kHz，霓虹電流嗡鳴 120Hz；混響 0.9s。
  - Default ON: 霓虹閃爍、蒸汽分層；Default OFF: 霧牆遮蔽主角。
  - Do / Don't：Do 控制 rim 光 6500K；Do 讓地面反射保持可見；Don't 讓噪點過多導致動畫線條抖動。

## Technical Specs
- Aspect Ratio: 9:16 直式；解析度 1080x1920。
- FPS: 24fps；Shutter: 180° (1/48s)；Motion blur 符合實景速度。
- Lens kit: 24mm (環境廣角)、35mm (主視角)、50mm (中景焦)、75mm (特寫壓縮)。
- Depth of Field: 主體景深 0.6–0.8m；背景霓虹微散焦，避免過淺景深。
- Grain & Color: Filmic LUT，對比度 1.8 gamma curve，飽和度 -8%，微顆粒 10%；色彩流程：line art → flat color → cel shade + SSS 0.05–0.12 → FX pass (爆紋/殘影/速度線) → LUT。
- Light: 主光為霓虹混合 520nm 綠與 610nm 紅，輔光 6500K 冷 rim，反射光由濕地面 4300K；AO 0.55，體積霧 0.07。
- Simulation notes: 蒸汽粒徑 0.5–1.2µm，黑霧粒徑 5–8µm，粒子上限 38k；飛刀電弧粒子 0.3–0.6mm；瞬移黑紅殘影採 2D sprite 疊加。
- Compression strategy: 上傳前使用 GOP 24、bitrate 20Mbps；避免霓虹閃爍被壓縮成 banding，可加 dither 5%。

## Master Prompt
- Duration: 15s，分為 12 幕，每幕約 1.2s，時間軸標註。
- Scene Overview: 深夜鋼脈都市下層積水巷道，破碎霓虹在水面拉出扭曲光帶；排氣管白霧與黑影交織。鋼川烈從巷口黑暗步出，飛刀在指間旋轉，暗紅紋路脈動；影域小怪從排水溝與牆縫湧出，骨刺外露。
- Camera Continuity: 延續上一集 35mm 左→右平移，起點機位後退 1.5m，鏡頭高度 1.3m，保持 180 度軸；高潮使用 35mm 及 50mm 快速跳切但軸向一致。
- Constraints & Execution Notes:
  - 12 幕均標註重力/慣性，飛刀拋物線受 9.8 m/s² 影響；瞬移殘影需遵守 0.12s 尾跡衰減。
  - 2D 層次：前景 2–3 層速度線與蒸汽，中景主角，背景霓虹與建物；視差 2–6px。
  - 高潮（Act 3 Beat C）漫畫化：彩色分格＋速度線＋擬聲字「ドン」「ギン」，描邊 1.2px，網點厚度 0.9px，散射光與折射寫明。
  - Negative Instructions 參照專區；PG-13，無血腥；避免魚眼與 360° 繞拍。

## Act 1 (T0–4.8s): 霓虹巷道前奏
- Beat A (T0–1.2s): 開場銜接，烈從黑暗走出
  - Angle 1: Camera: 35mm 腰平，左→右平移 0.8m；Lighting: 霓虹綠 520nm 主光+紅 610nm 補光，rim 6500K；Materials & Physics: 上衣粗糙度 0.35，爆紋 200→600 nits 漸亮，地面水深 8mm 形成鏡面反射；Emotion & Performance: 烈低語「……悪くねぇな」，肩膀收緊，步伐踩出 0.3m 水花；Audio & Transition: 霓虹電流嗡鳴 120Hz，腳踩水花 1kHz，硬切入。
  - Angle 2: Camera: 24mm 俯視 15°，推至烈指尖特寫；Lighting: 霓虹綠反射在刀背，冷 rim；Materials & Physics: 飛刀金屬度 0.92，刻紋微光 80cd/m²，指尖旋轉 12 rps；Emotion & Performance: 指尖多重旋轉 0.3s；Audio & Transition: 飛刀脆響 8kHz，轉場以蒸汽 wipe。
  - Angle 3: Camera: 50mm 中景，向前推 0.6m；Lighting: 霧中 4300K 填光；Materials & Physics: 霧密度 0.07，風速 1.6m/s 吹動衣角；Emotion & Performance: 烈抬頭掃視，瞳孔反射霓虹；Audio & Transition: 低頻鼓點 80Hz 漸入。
- Beat B (T1.2–2.4s): 影域小怪湧出
  - Angle 1: Camera: 24mm 低角 20cm 離地，向上 tilt；Lighting: 地面反射冷光；Materials & Physics: 黑霧粒徑 5–8µm 湧動，骨刺粗糙度 0.6；Emotion & Performance: 小怪爬行堆疊，眼光閃爍；Audio & Transition: 黑霧低鳴 90Hz，transition 硬切。
  - Angle 2: Camera: 35mm 手持搖 2°，推向溝口；Lighting: 霓虹紅反射在濕牆；Materials & Physics: 水面油膜產生 0.3px 色差；Emotion & Performance: 小怪撲向鏡頭邊緣；Audio & Transition: 擬聲「ゴゴゴ」字幕貼牆；速度線覆蓋邊框。
  - Angle 3: Camera: 50mm 中景回到烈；Lighting: rim 6500K 勾輪廓；Materials & Physics: 爆紋脈動 7Hz；Emotion & Performance: 烈微笑，手腕後擺準備甩刀；Audio & Transition: 心跳低頻 70Hz 疊加，切至下一 Beat。
- Beat C (T2.4–3.6s): 第一把飛刀標記
  - Angle 1: Camera: 35mm 側向跟拍，平移 1m；Lighting: 霓虹綠主光，刀身反射紅光；Materials & Physics: 飛刀拋物線仰角 20°，受重力 9.8m/s²；Emotion & Performance: 烈甩出第一把飛刀，眼神鎖定；Audio & Transition: 飛刀破風 9kHz，字幕「ギン」伴紙摩擦音。
  - Angle 2: Camera: 75mm 特寫刀背插入地面；Lighting: 刀背暗紅 emissive 80cd/m²；Materials & Physics: 刀插地面濺起 1.2mm 水珠；Emotion & Performance: 小怪驚嚇停滯；Audio & Transition: 金屬刺入 2kHz，切入瞬移。
  - Angle 3: Camera: 35mm 定點；Lighting: 霧光 4300K 填；Materials & Physics: 瞬移殘影 0.12s 衰減，透明度 65%；Emotion & Performance: 烈身影被影子吞沒消失；Audio & Transition: 低頻「フン」60Hz，動態模糊跟進。

## Act 2 (T4.8–9.6s): 瞬移連鎖與巷戰
- Beat A (T3.6–4.8s): 瞬移落點爆裂
  - Angle 1: Camera: 35mm 腰平，向前推 0.5m；Lighting: 爆紋瞬間提升至 1600 nits；Materials & Physics: 膝、腰、肩連動發力，紅能量沿手臂爆衝，飛刀尾跡殘影；Emotion & Performance: 烈低吼「まとめて、落ちろ」；Audio & Transition: 低頻衝擊 60Hz，漫畫擬聲「ドン」。
  - Angle 2: Camera: 24mm 俯視 20°，扇形斬擊；Lighting: 6500K rim 勾出動作弧線；Materials & Physics: 斬擊氣流產生 0.4m 扇形黑霧裂開，碎片慣性 3 m/s；Emotion & Performance: 小怪被掃成霧片；Audio & Transition: 霧破音 1kHz，速度線 radial wipe。
  - Angle 3: Camera: 50mm 特寫手臂；Lighting: 冷光強調肌理；Materials & Physics: 肌肉隆起 2–3mm，汗珠 0.5mm 反光；Emotion & Performance: 烈眼神銳利；Audio & Transition: 呼吸聲 400Hz，切至下一 Beat。
- Beat B (T4.8–6.0s): 多飛刀路標
  - Angle 1: Camera: 35mm 側平移 1m；Lighting: 霓虹反射在刀上形成色帶；Materials & Physics: 連續甩出 6 把飛刀，角速度 14 rps；Emotion & Performance: 烈冷靜投擲；Audio & Transition: 「ギン」「ギン」連打字幕，紙摩擦音 620Hz。
  - Angle 2: Camera: 24mm 仰角 10°，看刀軌交錯；Lighting: 霓虹藍補光；Materials & Physics: 刀軌形成紅線路標，殘影透明度 70%；Emotion & Performance: 小怪跟隨軌跡跳躍；Audio & Transition: 黑霧摩擦 300Hz，硬切。
  - Angle 3: Camera: 50mm 追焦第一把落刀；Lighting: 霧光柔化；Materials & Physics: 刀背刻紋放電 1.5cm 電弧，噴濺水珠 1mm；Emotion & Performance: 烈準備再次瞬移；Audio & Transition: 瞬移前低頻蓄力，模糊過渡。
- Beat C (T6.0–7.2s): 連續瞬移格鬥
  - Angle 1: Camera: 35mm 手持，平移 0.8m；Lighting: 黑紅殘影自發光；Materials & Physics: 瞬移位移 2.5m，殘影衰減 0.12s；Emotion & Performance: 烈出拳擊碎小怪胸骨霧塊；Audio & Transition: 拳擊低頻 90Hz，擬聲「ドス」。
  - Angle 2: Camera: 50mm 特寫反踢；Lighting: 6500K rim 強化腿部肌理；Materials & Physics: 反踢角速度 420°/s，骨刺彈飛 3m；Emotion & Performance: 烈神色冷靜；Audio & Transition: 骨刺落地 2kHz，切至下鏡。
  - Angle 3: Camera: 24mm 旋轉 8° 跟隨轉身斬擊；Lighting: 霓虹閃爍；Materials & Physics: 斬擊帶出 0.5m 弧形黑霧裂隙；Emotion & Performance: 小怪崩成霧碎；Audio & Transition: 擬聲「ザシュ」，剪接匹配動作方向。

## Act 3 (T9.6–12.0s): 高潮漫畫化爆裂
- Beat A (T7.2–8.4s): 霧中攔截
  - Angle 1: Camera: 35mm 中景，輕搖 2°；Lighting: 蒸汽透光，霓虹紅閃；Materials & Physics: 霧密度 0.07，爆紋亮至 1700 nits；Emotion & Performance: 烈左右換手截擊；Audio & Transition: 低頻鼓點 80Hz，速度線加重。
  - Angle 2: Camera: 75mm 特寫眼神；Lighting: 6500K rim 形成 catch light；Materials & Physics: 瞳孔反射刀光；Emotion & Performance: 眼神專注；Audio & Transition: 呼吸 400Hz，切特寫刀刃。
  - Angle 3: Camera: 50mm 特寫刀刃斬過黑霧；Lighting: 刀刃反射霓虹；Materials & Physics: 黑霧被切開形成 0.6m 裂口；Emotion & Performance: 小怪碎散；Audio & Transition: 擬聲「シュパ」，切入漫畫分格。
- Beat B (T8.4–9.6s): 漫畫化連打
  - Angle 1: Camera: 漫畫分格 3 欄，35mm 基礎；Lighting: 對比提升 1.8 gamma；Materials & Physics: 網點 0.9px，描邊 1.2px；Emotion & Performance: 烈瞬移連擊 3 次；Audio & Transition: 擬聲「ドドド」，紙張摩擦音。
  - Angle 2: Camera: 24mm 全景分格；Lighting: 爆紋光暈強；Materials & Physics: 速度線密度 26 條/秒；Emotion & Performance: 小怪成片崩解；Audio & Transition: 爆裂低頻 70Hz，分格間硬切。
  - Angle 3: Camera: 50mm 特寫拳頭穿霧；Lighting: 霧中 rim；Materials & Physics: 粒子噴射 0.6mm；Emotion & Performance: 烈低吼；Audio & Transition: 擬聲「ドン」。
- Beat C (T9.6–10.8s): 飛刀集束準備終結
  - Angle 1: Camera: 35mm 拉遠顯示飛刀懸浮；Lighting: 刀紋同時亮到 1800 nits；Materials & Physics: 飛刀磁鎖懸浮 0.5m 高，排列半徑 1.2m；Emotion & Performance: 烈雙臂展開蓄力；Audio & Transition: 金屬顫音 6kHz，鏡頭微震。
  - Angle 2: Camera: 24mm 仰角，視角包覆刀圈；Lighting: 霓虹反射於刀背；Materials & Physics: 刀圈旋轉 180°/s；Emotion & Performance: 小怪在中心擁堵；Audio & Transition: 緊張弦樂；匹配剪接。
  - Angle 3: Camera: 50mm 聚焦烈表情；Lighting: 6500K rim；Materials & Physics: 爆紋脈動頻率 9Hz；Emotion & Performance: 烈吐氣「終わりだ」；Audio & Transition: 深呼吸聲，切入最終爆破。

## Act 4 (T12.0–15.0s): 圓形衝擊與收束
- Beat A (T10.8–12.0s): 黑紅衝擊波
  - Angle 1: Camera: 35mm 中景，穩定；Lighting: 黑紅能量瞬時提升 2000 nits；Materials & Physics: 圓形衝擊波半徑 2.2m，速度 9 m/s，折射扭曲水面 0.5%；Emotion & Performance: 烈雙臂張開，低吼「散」；Audio & Transition: 低頻爆震 50Hz，擬聲「ドン」大字疊加。
  - Angle 2: Camera: 24mm 高角俯視，展示衝擊波掃過巷道；Lighting: 霓虹被衝擊波拉出光跡；Materials & Physics: 小怪崩為黑霧碎片，慣性向外 4 m/s；Emotion & Performance: 烈居中央站穩；Audio & Transition: 風壓聲 200Hz，硬切。
  - Angle 3: Camera: 50mm 慢推特寫飛刀碎片；Lighting: 刀碎片餘光 900 nits；Materials & Physics: 碎片落地濺水 0.7mm；Emotion & Performance: 場面靜止 0.2s；Audio & Transition: 短暫無聲後帶入回響。
- Beat B (T12.0–13.2s): 霧散與收刀
  - Angle 1: Camera: 35mm 右→左平移 0.6m；Lighting: 霧密度降至 0.05；Materials & Physics: 飛刀碎片磁鎖回收，收刀動畫 0.4s；Emotion & Performance: 烈肩膀放鬆，眼神仍鋒利；Audio & Transition: 磁鎖金屬吸附 1.2kHz，轉場 dissolve。
  - Angle 2: Camera: 75mm 特寫護腕；Lighting: 冷 rim；Materials & Physics: 刻紋光衰減至 200 nits；Emotion & Performance: 手指微動；Audio & Transition: 呼吸聲；硬切。
  - Angle 3: Camera: 50mm 半身；Lighting: 霓虹反射在濕衣；Materials & Physics: 水滴沿衣襬落下，慣性 0.5 m/s；Emotion & Performance: 烈抬眼確認無敵；Audio & Transition: 遠處警笛 900Hz 淡入。
- Beat C (T13.2–15.0s): 收尾與 CTA
  - Angle 1: Camera: 35mm 拉遠 1m 展現空巷；Lighting: 霓虹恢復穩定，色溫 4300K；Materials & Physics: 蒸汽薄霧 0.04；Emotion & Performance: 烈呼吸平穩，嘴角帶戰意；Audio & Transition: BGM 收束，字幕「物足りねぇな」。
  - Angle 2: Camera: 24mm 俯視 LOGO；Lighting: LOGO 燃邊 1800K；Materials & Physics: LOGO 粗糙度 0.7；Emotion & Performance: LOGO 熾亮；Audio & Transition: CTA 旁白，Hashtag 淡入。
  - Angle 3: Camera: 50mm 中景定格；Lighting: 6500K rim；Materials & Physics: 爆紋降回 200 nits；Emotion & Performance: 烈轉動肩膀解緊繃；Audio & Transition: CTA 完成，淡出。

## Platform Layer
- Hook A (故事向): 0–1s 霓虹光下的黑影步出，字幕「沒有月亮的夜，只有刀光」。
- Hook B (衝擊向): 0–1s 第一把飛刀落地瞬移，字幕「瞬移一刀，影子全滅」。
- 字幕/Caption：日文原聲 + 繁中雙語；保留擬聲字樣。「……悪くねぇな」「まとめて、落ちろ」「散」「物足りねぇな」。
- 縮圖構圖：烈半身+飛刀懸浮+霓虹反射，對比 1.8 gamma；保留暗紅爆紋。
- Hashtag：#鋼川烈 #影域小怪 #霓虹巷戰 #瞬移飛刀 #短影音
- CTA：尾段「關注鋼川烈，獲取下一集影域追擊」。
- 切片輸出策略：
  - 短版 7s：取 T2.4–9.6s 瞬移連鎖；字幕保留「ギン」「ドン」。
  - 長版 15s：完整版；可於 T10.8–12.0s 做主爆破 highlight。

## Negative Instructions
- 禁用內容：真實商標、名人臉、政治宗教符號、明顯血腥或斷肢、成人尺度。
- 避免畫面：過曝、過度 bloom、魚眼畸變、360° 繞拍、過度手持抖動、低解析貼圖。
- 語言環境：保持日文配音 + 中文字幕；不得出現其他語言錯置。
- 自動檢核清單：檢查擬聲字位置不遮臉；檢查霧不遮主體；檢查粒子數 ≤38k；檢查色溫 4300K 基底 + 6500K rim；檢查 180 度軸線未跨越。

## Assumptions
- 假設影域小怪為非智慧生物，崩解為黑霧無血液，符合 PG-13。
- 假設巷道寬 3.5m、高 5m，可容納瞬移與大範圍衝擊波。
- 假設烈上一集未受傷，體力充足，可執行高速連鎖瞬移。
- 假設霓虹電力穩定，除高潮爆破外不熄滅。

## Self-Check (請逐項確認)
- 結構：Master/Act/Beat/Angle/timecode 皆標註，12 幕 × 1.2s。
- Physics & PBR：重力、慣性、粗糙度、金屬度、霧密度、粒子數、折射扭曲皆有標；瞬移尾跡衰減明確。
- Stylepacks：Shadow Alley Assault + Neon Mist Noir 套用並列出 Do/Don't；高潮漫畫化遵循動漫特別規範。
- Continuity：延續上一集鏡頭軸與品牌色；爆紋亮度控制在 200–2000 nits；服裝與飛刀數量一致。
- Platform：Hook A/B、字幕、縮圖、Hashtag、CTA、切片策略皆填。
- Negative：禁用內容與 PG-13 檢核列出。
- 未確定處：無其他未定義角色；如需新怪物形態需先審核。

## Technical & Timing Checkpoints
- Checkpoint 1 (0–2s): 開場爆紋亮度從 200→600 nits 平滑；水花粒徑 1–2mm，速度 1 m/s。
- Checkpoint 2 (2–4s): 飛刀拋物線重力 9.8 m/s²；瞬移殘影透明度 65% 衰減 0.12s。
- Checkpoint 3 (4–6s): 扇形斬擊扇面 0.4m，黑霧碎片半徑 ≤1.2m；速度線密度 22–26 條/秒。
- Checkpoint 4 (6–8s): 連續瞬移距離 ≤2.5m/次；骨刺彈飛高度 ≤1.2m；無血腥。
- Checkpoint 5 (8–10s): 漫畫分格描邊 1.2px，網點 0.9px；擬聲字不遮臉。
- Checkpoint 6 (10–12s): 刀圈半徑 1.2m，電弧長 1.5cm；衝擊波半徑 2.2m，水面折射扭曲 0.5%。
- Checkpoint 7 (12–14s): 收刀磁鎖 0.4s；霧密度降至 0.05；rim 光仍辨識輪廓。
- Checkpoint 8 (14–15s): LOGO 粗糙度 0.7，燃邊 1800K；CTA 字幕出現 0.8s 不遮擋 LOGO。

## Lens & Camera Math Notes
- 24mm 視角在 9:16 下水平約 73°，垂直約 45°，保持巷道兩壁透視；避免頭頂裁切。
- 35mm 視角水平約 54°，垂直約 32°；適合主視角與腰平橫移，防止透視誇張。
- 50mm 視角水平約 40°，垂直約 24°；特寫時注意景深 0.5–0.7m，避免焦外過度。
- 75mm 備用：水平約 27°，垂直約 16°；如需額外特寫請提升照度並控景深 0.4m。

## Color & LUT Details
- Base palette: 濕混凝土 #4a4a50，鏽紅排水管 #9c4c38，爆紋紅 #e03c2f，霓虹綠 #5cd0ff，霧藍 #4ba3c7，影域黑 #0a0a0c。
- LUT: Filmic 曲線提升陰影 5%，高光壓縮 10%，防止霓虹過曝；對比度 1.8 gamma curve 一致。
- Bloom: 控制在 1.0–1.1 stops，僅於爆紋與飛刀刻紋；禁止全局過曝。
- Chromatic aberration: 0.3px 微色差；保持線稿銳利，霓虹反射有輕微分色。
- Grain: 10% film grain，均勻分佈，避免過度顆粒。

## Safety & Compliance Checklist (To tick before delivery)
- [ ] 9:16 比例未被裁切，主體未出界。
- [ ] PG-13：無血腥、無斷肢、無色情暗示。
- [ ] 無商標/名人/宗教政治符號。
- [ ] 字幕語言正確：日文原聲 + 中文翻譯。
- [ ] 擬聲字樣合法且不侵犯品牌。
- [ ] 光比穩定，無閃爍；爆紋亮度在 200–2000 nits 範圍。
- [ ] 粒子數 ≤38k，霧不遮臉；霓虹不過曝。
- [ ] 音量峰值低於 0dBFS，無削波。
- [ ] 色溫固定：基底 4300K + rim 6500K；火焰/LOGO 1800K。
- [ ] 180 度規則遵守，沒有軸線跨越。

## Delivery Notes
- 檔案格式：ProRes 422 或 H.264 高碼率，bitrate 20Mbps；同時輸出 srt 字幕檔。
- 分層輸出：角色/背景/FX/字幕/擬聲分層，保留 AOV 通道供校色。
- 備份：建立 `2025-11-25_ep2-shadow-imp-surge` 標籤，保留素材與 LUT 版本。
- 測試上傳：先上傳非公開到 TikTok/YouTube Shorts 測試壓縮；檢視霓虹與速度線是否被模糊；必要時提升銳化 5%。
- 備註：交付前再次人工檢視嘴型與字幕同步。

## Micro-Actions Timeline (frame-by-frame)
- T0.0–0.3s: 烈右腳踩入 8mm 積水，水花向兩側 45° 飛散，粒徑 1–2mm，重力落回 0.6s；肩膀抬高 3°。
- T0.3–0.6s: 指尖旋轉飛刀 12 rps，刻紋亮度從 80→120cd/m²；膝蓋微蹲 5cm 預備瞬移。
- T0.6–0.9s: 爆紋脈衝 7Hz，同步胸肌收縮；霓虹綠反射在頰側形成 0.2 stop 高光。
- T0.9–1.2s: 烈抬頭掃視，瞳孔縮小 0.2mm；呼吸冷氣形成 5cm 霧氣。
- T1.2–1.5s: 小怪第一批從排水溝鑽出，黑霧密度 0.07→0.08；骨刺折射周遭霓虹，反射率 0.4。
- T1.5–1.8s: 小怪前肢撐地，爬行速度 1.4 m/s；眼窩暗黃光閃爍 2Hz。
- T1.8–2.1s: 烈右手向後收，飛刀尾跡形成 0.3s 殘影；爆紋亮度提升至 800 nits。
- T2.1–2.4s: 第一把飛刀甩出，初速度 14 m/s，仰角 20°；鏡頭追焦保持刀尖清晰。
- T2.4–2.7s: 飛刀落地刺入，地面水珠彈起 1.2mm；黑霧被切開 0.2m 槽。
- T2.7–3.0s: 烈身影被影子吞沒，殘影透明度 65%，尾跡長 0.5m。
- T3.0–3.3s: 瞬移落點膝、腰、肩連動，爆紋飆到 1600 nits；氣壓推動霧氣向外 0.4m。
- T3.3–3.6s: 扇形斬擊形成 0.4m 擴散，碎片慣性 3 m/s；擬聲字「ドン」閃現 0.2s。
- T3.6–3.9s: 烈手臂肌肉隆起 2–3mm，汗珠受光形成 0.1 stop 高光。
- T3.9–4.2s: 連續甩出第 2–4 把飛刀，角速度 14 rps；刀軌殘影透明度 70%。
- T4.2–4.5s: 小怪跟隨刀軌跳躍，重心高度 0.5m；黑霧沿刀軌被拉長。
- T4.5–4.8s: 烈再瞬移 2.5m，殘影衰減 0.12s；拳擊落點 0.3m 前方。
- T4.8–5.1s: 拳擊接觸黑霧胸塊，形成 0.5m 漣漪；小怪被震開 0.8m。
- T5.1–5.4s: 反踢 420°/s，骨刺被彈飛 3m；速度線沿腿部輻射。
- T5.4–5.7s: 轉身斬擊帶出 0.5m 弧形裂隙，黑霧碎片 6µm 粒徑四散。
- T5.7–6.0s: 烈短暫停頓 0.1s，呼吸聲 400Hz，瞳孔收縮。
- T6.0–6.3s: 漫畫分格開始，描邊粗度 1.2px；網點疊加 0.9px。
- T6.3–6.6s: 連擊 3 次，每次瞬移距離 1.5m；爆紋 1700 nits 峰值。
- T6.6–6.9s: 速度線密度提升至 26 條/秒；黑霧碎片向外 4 m/s。
- T6.9–7.2s: 刀圈開始懸浮，磁鎖音 6kHz；刀距地面 0.5m。
- T7.2–7.5s: 刀圈旋轉 180°/s，紅紋同步閃爍 9Hz；霧被離心力推開。
- T7.5–7.8s: 烈深呼吸，胸腔擴張 12mm；準備爆破。
- T7.8–8.1s: 衝擊波預震，水面形成 0.5% 折射扭曲；字幕「終わりだ」。
- T8.1–8.4s: 黑紅衝擊波釋放，半徑快速擴展至 2.2m；小怪崩解。
- T8.4–8.7s: 衝擊波後靜默 0.2s，只有水滴聲；刀碎片餘光 900 nits。
- T8.7–9.0s: 飛刀碎片磁鎖回收，收刀動畫 0.4s；護腕顯示紅紋收束。
- T9.0–9.3s: 烈肩膀放鬆，轉動手腕；霧密度降至 0.05。
- T9.3–9.6s: LOGO 俯視燃邊 1800K；CTA 字幕淡入 0.8s。

## Materials & PBR Breakdown
- 皮膚：Base color #f2c9b5，SSS 0.08，粗糙度 0.32，specular 0.24；汗珠微法線 0.1mm。
- 機能上衣：尼龍/氨綸混紡，albedo #1a1a1c，粗糙度 0.35，金屬度 0.05；磨損位置於肩部與肘部，法線刮痕 0.2mm。
- 爆紋：albedo #2b0c0c，emissive 1200–2000 nits，邊緣有 0.1mm 法線起伏；菲涅耳反射 0.04。
- 飛刀：高碳鋼 albedo #b0b0b5，金屬度 0.92，粗糙度 0.08；刃口 0.05mm 刃角，刻紋暗紅 emissive 80→1800 nits；指紋痕跡 0.02mm。
- 護腕：黑鈦合金 albedo #2b2d32，金屬度 0.7，粗糙度 0.18；磁鎖凹槽 AO 0.4。
- 巷道混凝土：albedo #4a4a50，粗糙度 0.6，AO 0.55；水漬形成 0.2 光澤；法線凹洞 0.5mm。
- 排水管：銅鏽與鐵鏽混合，金屬度 0.55，粗糙度 0.3，鏽蝕色帶 #9c4c38；指紋與油污法線 0.1mm。
- 積水：厚度 8mm，IOR 1.33，表面油膜色偏綠紫；roughness 0.2，反射霓虹色差 0.3px。
- 黑霧：密度 0.07–0.08，顆粒 5–8µm，吸收係數 0.2，散射偏黑紫；邊緣帶 0.4px 漸層。
- 體積霧：密度 0.05–0.07，散射偏藍 #4ba3c7，吸收 0.12；相位函數 0.2 forward。
- LOGO：金屬漆 albedo #d8d0c8，粗糙度 0.7，邊緣燃燒 1800K，粒子直徑 0.4mm。

## Physics & Simulation Notes
- 重力：標準 9.8 m/s² 作用於飛刀、水花、碎片；瞬移不影響重力但造成氣壓波。
- 摩擦：地面濕滑摩擦係數 0.42；鞋底橡膠摩擦 0.65，確保站穩；骨刺與刀刃碰撞彈性係數 0.3。
- 慣性：小怪質量等效 12kg，衝擊時因霧化減半，慣性 6kg；衝擊波推力 120N。
- 流體：蒸汽溫度 28°C，密度 1.2 kg/m³；油膜表面張力 0.03 N/m，形成微反射。
- 粒子上限：FX 粒子總數 ≤38k，其中飛刀電弧 3k、黑霧碎片 20k、蒸汽 10k、火花 5k；每粒子壽命 0.5–1.2s。
- 碰撞：飛刀與骨刺碰撞使用彈性 0.25，摩擦 0.4；碰撞後能量 30% 轉為火花，70% 轉為霧震。
- 折射：衝擊波扭曲水面折射 0.5%；油膜折射偏差 0.3°，產生輕微彩虹 fringe。
- 動態模糊：依 1/48s 快門，自然模糊量 0.6–0.8px；瞬移尾跡額外 0.4px。
- 景深：主體清晰範圍 0.6–0.8m；背景散焦 bokeh 控制 0.4 圓度，不可形成明顯散景。

## Audio & VO Map
- VO 日文：
  - T0.8s「……悪くねぇな」低沉，-10 LUFS。
  - T3.8s「まとめて、落ちろ」瞬移前，-8 LUFS。
  - T10.9s「散」爆破瞬間，-6 LUFS 峰值。
  - T13.8s「物足りねぇな」收尾，-9 LUFS。
- 擬聲字：
  - 「ギン」出現在刀落地與刀軌重疊處，持續 0.2s。
  - 「ドン」出現在衝擊波與拳擊重點，持續 0.25s，描邊 1.2px。
  - 「ザシュ」於斬擊畫面，帶 0.9px 網點。
- BGM：低頻鼓點 80Hz 節奏，加入 120Hz 霓虹嗡鳴；高潮增加 600Hz 金屬打擊。
- 環境音：排氣管吐息 200Hz，水滴 3kHz，遠處警笛 900Hz 淡入尾段。
- 混音：峰值不超 0dBFS，Loudness 整體 -12 LUFS；爆破瞬間 duck BGM -3dB 讓擬聲字突出。

## Camera & Lighting Continuity Table
- Act1: 35mm/24mm/50mm 組合，色溫 4300K 基底 + 6500K rim，曝光 -0.2 EV。
- Act2: 35mm/24mm/50mm，霓虹主光稍增 0.1 EV；殘影需額外 0.3px motion blur。
- Act3: 漫畫分格使用 35mm/24mm/50mm，對比 +10%，飽和 -8%；速度線 26 條/秒。
- Act4: 35mm/24mm/50mm，衝擊波時快門維持 1/48s 以保自然模糊；衝擊波 glow 控制 1.1 stops。
- Rim 光：全片保持 6500K，強度 0.6，確保輪廓；不可超過主光。
- AO：穩定在 0.55，避免角色浮空；霧層不遮擋面部。

## Continuity & Constraint Log
- 前集 LOGO 位置：右下 12% 占比，本集維持；字幕區域避開 LOGO。
- 爆紋顏色與紋理一致，不新增顏色；發光範圍僅胸口到前臂。
- 飛刀總數 20，使用後回收完畢；不得無故增加。
- 敌方僅影域小怪，不引入其他生物；黑霧崩解不產生血液。
- 鏡頭軸線保持左→右；沒有反向切。

## Additional Platform Slice Notes
- 竪屏字幕預留安全區：左右各 10% 不放字幕；擬聲字放置在速度線空隙。
- Shorts 上傳需加 1px 黑邊避免 UI 遮蔽；TikTok 建議封面取 T8.1 爆破定格。
- Caption 建議：日文原聲 +「暗影飛刃・鋼川烈 vs 影域小怪群」標題。
- CTA 動畫：Hashtag 從下方 20% 區域淡入，時長 0.8s，透明度從 0→100%。

## Mangaization Details (高潮必備)
- 彩色分格 3 欄：左欄瞬移殘影，中欄斬擊，中欄上方擬聲字；右欄刀圈蓄力。
- 描邊：1.2px 黑線，根據景深 0.6–1.2px 自適應。
- 網點：厚度 0.9px，密度 25%，套用於背景與速度線交會處。
- 速度線：26 條/秒，方向跟隨動作弧；透明度 65%。
- 爆光：控制在 1.1 stops，配合 PBR 發光，不遮蔽材質細節。
- 2D 層次：前景擬聲字、速度線；中景主角；背景霓虹建物；視差 2–6px。

## Negative Audit Checklist (自動檢核)
- [ ] 無真實品牌或商標出現。
- [ ] 無政治、宗教、現實名人元素。
- [ ] 無血腥 gore，影域小怪僅霧化。
- [ ] 無魚眼、無 360° 繞拍、無過度抖動。
- [ ] 霓虹不過曝，亮度受控；爆紋不常亮。
- [ ] 擬聲字與字幕未遮擋面部。
- [ ] 粒子數與霧密度在上限內。
- [ ] 鏡頭軸線遵守 180 度規則。

## Rendering & Export Notes
- Render passes: Beauty、Shadow、Spec、Emission、Z-Depth、Normal、ID、FX（霧/殘影/火花）、字幕/擬聲分層。
- Denoise: 僅對背景霧層輕度 denoise，主角與刀保持銳利；使用 radius 0.3。
- Color pipeline: linear → ACEScg → log → filmic LUT → final contrast；確保霓虹不飽和裁切。
- Motion blur: 依 1/48s，自然 blur；漫畫分格鏡頭可降低 blur 20% 保線條。
- Export: ProRes 422 HQ；備份 H.264 高碼率 20Mbps，音訊 48kHz 24bit。

## QA Review Slots
- Pass 1：檢查分鏡與時間軸標註是否完整。
- Pass 2：檢查 PBR 參數與霓虹亮度；爆紋在 200–2000 nits。
- Pass 3：檢查字幕、擬聲字位置與安全區；雙語同步。
- Pass 4：檢查音量與混音；峰值不超 0dBFS；LUFS -12。
- Pass 5：檢查漫畫分格的網點與描邊厚度。
- Pass 6：最終播放確認無掉幀、無 banding；壓縮後霓虹仍清晰。

## Shot Math & Geometry
- 巷道寬 3.5m，鏡頭腰平 1.3m；24mm 拍攝時左右留白 0.4m 確保字幕空間。
- 35mm 平移 0.8–1m 時，人物在畫面中央 40%，背景視差 4px；保留霓虹倒影。
- 50mm 特寫時，景深 0.6–0.8m；臉部清晰，背景霓虹散焦半徑 0.4m。
- 75mm 射 LOGO 時，LOGO 占 18% 畫面；需增加照度 0.2 EV 防止噪點。
- 衝擊波全景 24mm，鏡頭仰角 5°；確保圓形衝擊波不切邊。
- 漫畫分格內，各分格描邊 1.2px，分隔線 2px 白邊；速度線方向與分格對齊。
- 刀圈懸浮畫面需保持 9:16 安全區，刀圈外緣不超出 80% 畫幅。

## Lighting Keyframes
- KF1 T0–1.2s：霓虹綠主光 4300K，紅補光 610nm；爆紋 200→600 nits；rim 6500K 0.6。
- KF2 T1.2–2.4s：增加排氣白霧反射 4300K，地面反射提升 0.1 EV。
- KF3 T2.4–3.6s：飛刀亮度 800 nits；刀影在水面形成 0.2 stop；霓虹保持。
- KF4 T3.6–4.8s：爆紋飆至 1600 nits；rim 加到 0.7；霧反射 0.05。
- KF5 T4.8–6.0s：刀軌紅光尾跡；霓虹藍補光加強；背景維持 4300K。
- KF6 T6.0–7.2s：漫畫分格對比 +10%，飽和 -8%；光比維持 3:1。
- KF7 T7.2–8.4s：刀圈亮度 1800 nits；地面反射強化，ripple 0.5%；rim 穩定。
- KF8 T8.4–9.6s：衝擊波瞬間全片曝光 +0.3 EV，再回落；霧亮度降低。
- KF9 T9.6–11.0s：霧退去，基底光回到 4300K；rim 0.5；LOGO 燃邊 1800K。
- KF10 T11.0–15.0s：光比穩定 2.5:1，色溫一致，方便後期銜接。

## Sound Staging & Spatial Notes
- 左右聲道：飛刀聲從左側開始，瞬移後在右側響起，立體呈現移動軌跡。
- 低頻管理：衝擊波與拳擊低頻 50–90Hz，使用 sidechain 壓縮 BGM 3dB。
- 環境聲：蒸汽與滴水保持 -20 LUFS 背景；警笛在尾段右上方 900Hz。
- 擬聲字配音：紙張摩擦音與字體彈出同步，立體聲置中。
- 混響：巷道混響 0.9s，pre-delay 60ms；瞬移音效 pre-delay 0ms 直接衝擊。
- 配音位置：烈台詞置中，輕微室外混響 0.3s，距離感 1m。

## Safety Frames for Editors
- 提供無字幕無擬聲版本；字幕安全區上下各 15%。
- 重要動作前後至少留 4 帧緩衝，方便剪接。
- 檢查每幕開頭結尾無錯位殘影；若有需手動清除。
- 動作線方向標註在素材說明：主動線由左向右。
- 標註所有 Hook 時間戳供平臺裁切：Hook A 0–1s，Hook B 0–1s，爆破 10.8–12s。

## Color Grading Notes
- Lift/Gamma/Gain：Lift -0.02，Gamma 0.95，Gain +0.03；保持暗部細節。
- Hue shift：輕微將霓虹綠轉向青 3° 以避免過飽和；紅色保持 #e03c2f。
- Saturation：全片 -8%，漫畫分格 -10%；膚色維持自然。
- Highlights roll-off：壓縮 10%，避免爆紋溢出；使用 filmic curve。
- Shadow tint：加 2% 藍提升夜間氣氛；不可喧賓奪主。
- Grain：保持 10%；若平台壓縮模糊，備用版本 12% grain。

## Subtitle & Caption Map
- T0.0: 「沒有月亮的夜，只有刀光」
- T0.8: 「……悪くねぇな」
- T1.6: 「影域小怪湧出」
- T2.4: 「第一把飛刀標記」
- T3.8: 「まとめて、落ちろ」
- T5.2: 「連鎖瞬移斬擊」
- T7.0: 「漫畫化連打」
- T8.2: 「終わりだ」
- T10.9: 「散」
- T13.5: 「物足りねぇな」
- T14.2: CTA + Hashtag

## Backup & Versioning
- 檔名規則：`shadow-imp-surge_v01.mov`、`shadow-imp-surge_v01_srt.srt`。
- Git 標籤：`2025-11-25_ep2-shadow-imp-surge`；若調色更新，使用 `_colorfix1` 後綴。
- 備份位置：主存儲與雲端各一份；保留 LUT 與字幕模板。
- 版本日誌：記錄每次修改的光比、粒子數、字幕變更；提交前需自檢。

## QC Questions to Resolve
- [ ] 是否需要新增影域小怪變種？目前假設僅單一形態。
- [ ] CTA 文案是否需品牌授權？如需修改請提供。
- [ ] 平台是否允許 1800K 燃燒 LOGO？若需降亮度可調至 1600K。
- [ ] 如果需英文字幕，是否另行提供？目前僅繁中 + 日文。

## Editor Handoff Notes
- 提供 AE 專案檔含字幕與擬聲字分層；字體使用思源黑體 + 手寫擬聲。
- 提供 LUT cube 檔與 ACES 設定；說明檔包含色彩流程。
- 動態模板：速度線與殘影模板可重複使用；標註粒子數上限。
- 配音軌：單獨提供 VO、BGM、環境音、SFX 四軌，方便混音。

## Risk Assessment
- 風險 1：霓虹過曝導致 banding → 已加入 dither 5%，控制曝光。
- 風險 2：瞬移殘影與速度線疊加造成線稿抖動 → 控制透明度 65%，粒子不超 38k。
- 風險 3：字幕遮擋臉部 → 安全區設計，擬聲字放在速度線間。
- 風險 4：平台壓縮模糊 → 測試上傳並視需要提升銳化 5%。
- 風險 5：音量峰值 → 混音峰值 <0dBFS，LUFS -12。

## Final AGENT Self-Check
- 結構完整：Master、_core、_stylepacks、Technical、Act/Beat/Angle/timecode、Platform、Negative、Assumptions、Checkpoints 完整。
- 物理與 PBR：重力、慣性、摩擦、流體、粒子、粗糙度、金屬度、折射均有數值；爆紋與刀紋亮度範圍清楚。
- 風格：動漫 2D 層次、漫畫化高潮、速度線、擬聲字、描邊/網點厚度皆符合根規範。
- 延續性：鏡頭軸、色溫、品牌特徵延續；飛刀數與爆紋一致；上一集的鏡頭平移方向保留。
- 平台：Hook A/B、字幕、縮圖、Hashtag、CTA、切片策略皆備；安全區標註。
- 負面：禁用元素列舉並有自動檢核；PG-13 無血腥。
- 未解事項：QC 問題已列；如有新需求需回報。

## Extra Notes
- 若需慢動作重播，限用 0.75x 並標記為回放，不可影響主節奏。
- 如果平台字幕被 UI 遮蔽，可上移 5% 並縮短文案至 18 字內。
- 飛刀材質需維持微刮痕與指紋；禁止過度拋光。
- 若加雨效果，需更新流體參數與霧密度，並重新計算反射；目前預設無雨。
- 若新增角色或道具，需同步更新 _core 的 Brand Traits 與 Constraints。
- 如需改變鏡頭焦段，必須更新 Camera Continuity 與安全區計算。
- 所有數值如有調整，需在版本日誌中紀錄並提交審核。

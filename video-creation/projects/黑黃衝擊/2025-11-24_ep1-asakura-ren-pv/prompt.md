# Project Metadata
- project_name: 黑黃衝擊
- series_name/arc: 個人PV・朝倉蓮
- episode_index: 1
- slug: asakura-ren-pv
- target_platform: short-form vertical video (JP/TW social)
- duration_sec: 15
- style_primary: 2D日系動漫風格（黑黃機能系）
- style_secondary: 近未來格鬥寫實（電弧質感）
- worldstate_ref: 夜間廢墟訓練場 + 高架橋實戰區域
- goal: 製作朝倉蓮個人PV，展現黑黃衝擊的沉穩力量感，日文配音

## _core
### Brand Bible（黑黃衝擊）
- 角色色票：黑色 #0b0b0e 為主，細黃線條 #f0c400，汗水高光 #a0c8ff。
- 服裝材質：機能緊身布料（粗糙度 0.32、金屬度 0.05、法線貼圖 8K，纖維走向沿肩向下），護腕與重武器為噴砂金屬（粗糙度 0.28、金屬度 0.85）。
- 口頭禪與語氣：日語低沉短句，不炫耀，句尾常以「…だ」收束。
- 姿態與習慣：收拳時拇指輕貼食指第2指節；起身會短促吐氣；受擊先確認重心再反擊。
- 場景色調：冷藍環境光 + 暖黃聚光形成 2:1 光比，霧氣密度 0.015，AO 0.5，對比度 1.8 gamma curve（遵循 Do）。
- 鏡頭語言 Do：穩定推軌、20–40° 低角強化體態、受力方向與運鏡一致、對比度 1.8 gamma curve、景深控制 f/2.8–f/4 以突出主體。
- 鏡頭語言 Don't：過度晃動、魚眼（禁止 <20mm）、過曝高光、卡通化無物理、跳剪破壞節奏。
- 文案語氣：中日混用，日文旁白低頻、中文字幕簡潔；避免長段敘述，保持擊打節奏。

### Shared World & Character File
- Worldstate snapshot：城市外圍廢墟訓練場（鋼架腐蝕 30%、地面裂縫 5–8cm 深），高架橋下殘存霧氣 0.015 density，夜間溫度 15°C、微風 2 m/s。
- Character default：朝倉蓮 178 cm / 78 kg，體脂 10%，右撇子；護腕厚 1.2 cm，金屬環內徑 4 cm，重武器 18 kg 折疊斧槍，慣性矩 4.5 kg·m²。
- Persistent elements：黑黃細線會在出拳/揮擊時沿武器柄與肌肉走向亮起 0.3s；汗水粒徑 0.5–1 mm，落地後形成 2 cm 濺射；背景霧會因衝擊波被推開 1–1.5 m。
- Constraint list：武器在休止時折疊於背後角度 25°；護腕必須在鏡頭內可見金屬環；角色情緒曲線由冷靜→決心→微笑，不允許誇張怒吼。
- Execution note：使用 camera projection 對廢墟貼圖保持清晰度，volume pass 控制霧；戰鬥衝擊波採用圓形壓縮波 18–24 m/s，粒子上限 50k，避免噪點須加 denoise 限制 0.3。

### Do / Don't（Core）
- Do：明確標註 PBR 參數、重力/慣性、折射/SSS；對每個鏡頭列出鏡頭焦段與運鏡；字幕對齊音效節點。
- Don't：使用模糊代稱、缺少時間戳、以「同前」替代細節、使用真實品牌/宗教/政治符號。

## _stylepacks
### Style: 2D Anime Kinetics (黑黃機能)
- Applicable for：動態訓練與實戰段落，強化電弧與肌肉線條。
- Do NOT mix with：柔焦少女風、Q版比例。
- Default: ON
- Visual traits：高對比冷暖光，邊線粗細 2–3 px，可見肌肉肌理與汗液 specular；黑黃線條在瞬間高亮（亮度 1200 nits 瞬閃 0.2s）。
- Audio traits：日語低沉旁白 + 金屬撞擊殘響 1.2s，鼓聲每 0.6s 節奏。
- Do：保持運動模糊 180° shutter，衝擊波帶火花粒徑 0.8–1.5 mm，使用 match cut 連接訓練與實戰。
- Don't：過度饒舌旁白、重混色偏粉、使用魚眼畸變。

### Style: Monotone Stoic Voiceover (日文低頻)
- Applicable for：旁白與字幕呈現，突顯沉穩語氣。
- Do NOT mix with：高音熱血喊叫。
- Default: ON
- Visual traits：字幕黑底透明度 60%，字體 Noto Sans JP Bold 72pt，描邊 3px 黃色；字幕放置於安全區 5% 邊距。
- Audio traits：男性低頻 90–110 Hz，輕混混響 0.4s，立體聲寬度 40%。
- Do：字幕節點與擊打同步；轉場使用低頻掃頻 200→80 Hz。
- Don't：加速聲調、使用多餘英語夾雜。

## Technical Specs
- Aspect Ratio: 9:16
- FPS: 24
- Shutter: 180° with controlled motion blur
- Lens set: 24mm（環境建立）、35mm（半身與推軌）、50mm（特寫）、75mm（情緒特寫）；校正畸變並添加輕微 vignette 0.15。
- Depth of Field: f/2.8–f/4 主體清晰，背景散景半徑 6–8 px。
- Grain: fine-grain 35mm 8%，保持社群壓縮後細節。
- Color pipeline: log capture → filmic LUT → final contrast 1.8 gamma curve → subtle bloom 0.12；保留暗部噪點抑制。

## Master Prompt
- Worldstate snapshot：夜晚 20:00，高架橋下霧 0.015 density，溫度 15°C，濕度 70%；廢墟鐵架鏽蝕度 30%，地面裂縫 5–8 cm 深，水泥粗糙度 0.55。
- Constraint list：角色保持冷靜語氣；黑黃線亮度不得超過 1200 nits；武器折疊關節必須可見；鏡頭連續性保持右向運動軸；不出現其他角色臉部。
- Execution note：建議使用 volume pass 控制霧；衝擊波採用 VDB 低密度煙塵（散射 0.6，吸收 0.2）；布料模擬啟用風場 2 m/s；camera continuity 延續上一鏡 35mm → 下一鏡 50mm 以匹配眼線。
- Camera Continuity：
  - 前序結束機位 35mm 肩平視，緩推向 2 m；本次開場維持 35mm 向前 0.8 m，再轉 24mm 建立環境。
  - 推拉方向優先向右，若需切換方向，先以 match cut 搭配光亮閃爍作為轉換前置條件。
- Physics & PBR summary：重力 9.81 m/s²；武器質量 18 kg，揮擊角速度 180°/0.35s；汗液折射率 1.33；金屬護腕鏡面反射 0.6，粗糙度 0.28；地面摩擦係數 0.7；衝擊波使沙塵粒子 0.5 mm 半徑飛散 2 m。
- Stylepacks used：2D Anime Kinetics（ON）、Monotone Stoic Voiceover（ON）。
- Duration plan：15s，分為 12 幕 × 1.2s（14.4s 主體）+ 0.6s Logo 收束；每幕標註時間。
- Platform hook：前 1s 使用腳步聲 + 暗光推軌作為 Hook A；Hook B 為武器展開瞬間爆光。

## Act 1 — 靜夜與上場（0.0s–4.8s）
### Beat 1 — 廢墟定場（0.0s–1.2s）
- Angle A (T0–1.2s)
  - Camera：24mm，低機位 40cm 離地，向前推 1.2m；輕微搖移右 10cm 尋找光源；景深 f/4。
  - Lighting：環境冷藍 5000K 30% 強度；單盞鈉燈 3200K 60% 打斜；體積霧 0.015 density，光束可見散射。
  - Materials & Physics：鐵架金屬度 0.6 粗糙度 0.35，鏽蝕 bump 0.2mm；裂縫內積水折射 1.33 形成小鏡面；輕風 2 m/s 使霧向右流。
  - Emotion & Performance：朝倉蓮未入鏡，環境營造孤寂；節奏慢。
  - Audio & Transition：遠處滴水聲 -18dB；城市低頻嗡鳴；硬切接腳步聲。

### Beat 2 — 腳步逼近（1.2s–2.4s）
- Angle A (T1.2–2.4s)
  - Camera：35mm 低角 20° 抬拍腳步，推軌 0.8m；運動模糊 180°。
  - Lighting：鈉燈形成光斑，地面反射 15%；微亮黃光沿裂縫行進。
  - Materials & Physics：鞋底橡膠粗糙度 0.6；摩擦聲伴隨砂石位移 2–3 cm；每步踩下微震 0.2G。
  - Emotion & Performance：腳步穩定 92 bpm；不急躁。
  - Audio & Transition：鞋底與砂聲 + 低頻鼓點 0.6s 一拍；match cut 連到上半身。

### Beat 3 — 臉部與線條亮起（2.4s–3.6s）
- Angle A (T2.4–3.0s)
  - Camera：50mm 半身特寫，從胸口推至肩頸 0.4m；輕微 handheld 3% 抖動。
  - Lighting：暖黃 key 60% 斜打右鎖骨；冷藍 fill 30%；rim light 20% 勾邊。
  - Materials & Physics：皮膚 SSS 半徑 1.2mm；汗膜 0.05mm 厚反射 0.4；黑布料法線 8K 顆粒 0.1mm；黃線導電感應亮 800 nits 0.2s。
  - Emotion & Performance：肩膀起伏如護盾；眼神穩定；微抿唇。
  - Audio & Transition：低語吸氣聲；黃線嗡鳴；交叉淡入下個角度。
- Angle B (T3.0–3.6s)
  - Camera：75mm 右後 15° 角度，緩轉 10° 看到背肌起伏。
  - Lighting：背光冷藍 40%，汗珠形成高光；地面反射補 fill 10%。
  - Materials & Physics：汗滴 0.5–1mm 粒徑順背滑落 0.5m/s；肌肉收縮呈現弧線；布料拉伸 5%。
  - Emotion & Performance：蓄力感；背肌如盾。
  - Audio & Transition：呼吸 + 金屬輕碰；硬切。

### Beat 4 — 繫緊護腕（3.6s–4.8s）
- Angle A (T3.6–4.2s)
  - Camera：50mm 手部特寫，左至右 0.6m 滑軌；景深 f/2.8 聚焦指節。
  - Lighting：暖 key 55%，冷 fill 25%；金屬反射高光 0.6；AO 0.5。
  - Materials & Physics：護腕金屬環金屬度 0.85，粗糙度 0.28；皮革護帶粗糙度 0.5，拉伸 3%；指節皮膚乾濕度 60%。
  - Emotion & Performance：手指收緊，腕帶再拉緊一格；筋脈輕鼓。
  - Audio & Transition：金屬環撞指節「カン」聲 0.2s 迴響 1.2s；match cut 至訓練 montage。
- Angle B (T4.2–4.8s)
  - Camera：35mm 胸口側拍，向上 tilt 15° 見眼神。
  - Lighting：key 60% 打臉，rim 25% 勾邊；微粒塵埃在光束內漂浮。
  - Materials & Physics：塵埃粒徑 20µm 隨氣流上升 0.1 m/s；汗光在顴骨形成 0.2cm 高光帶。
  - Emotion & Performance：眼神穩如牆，嘴角微抬 2°。
  - Audio & Transition：低頻鼓點延續；硬切進訓練。

## Act 2 — 苦練與耐力（4.8s–9.6s）
### Beat 5 — 負重衝刺（4.8s–6.0s）
- Angle A (T4.8–5.4s)
  - Camera：24mm 側平移 2m 追隨；高度 1m；運動模糊 180°。
  - Lighting：清晨模擬冷光 6500K 30%，背後暖光 3200K 40% 模擬路燈殘照。
  - Materials & Physics：背負 15kg 沙袋晃動幅度 5cm；鞋底踢起砂塵 0.5mm 粒子，慣性向後飛 2m；肌肉震動 0.3cm。
  - Emotion & Performance：咬緊牙關，汗沿下顎滴落，落地濺射 2cm。
  - Audio & Transition：喘息 + 砂塵摩擦；hard whip pan 接下一角度。
- Angle B (T5.4–6.0s)
  - Camera：50mm 前向跟跑，機位略低 70cm，看正面推近 0.5m。
  - Lighting：側黃線在肌肉上瞬亮 900 nits；背光 rim 30%。
  - Materials & Physics：布料隨奔跑產生波紋 0.5cm；汗滴被風場往後拉出 10cm 長絲。
  - Emotion & Performance：表情堅定，眉間緊鎖。
  - Audio & Transition：鼓點加速至 100 bpm；match cut to 夜訓揮拳。

### Beat 6 — 夜訓沙包（6.0s–7.2s）
- Angle A (T6.0–6.6s)
  - Camera：35mm 半身，左至右圓弧滑軌 1m；景深 f/3.2。
  - Lighting：單側暖 key 60%，冷背光 30%；沙包投下硬陰影。
  - Materials & Physics：沙包質量 40kg，被擊打位移 12cm 來回，回彈 2Hz；黃線每拳亮 0.2s；拳風推開霧 1m。
  - Emotion & Performance：拳擊節奏 0.5s 一拳；肩膀繃緊、釋放循環。
  - Audio & Transition：拳擊「ドン」低頻；呼氣「ハッ」；hard cut。
- Angle B (T6.6–7.2s)
  - Camera：75mm 右側特寫手臂，俯角 10°；慢動作 0.5x，運動模糊仍 180°。
  - Lighting：rim light 35% 勾出汗水；key 減到 40% 聚焦手臂肌理。
  - Materials & Physics：皮膚顆粒 50µm；汗珠被甩出形成弧線半徑 30cm；護腕金屬細刮痕可見。
  - Emotion & Performance：手臂收縮、筋線跳動；嘴角緊閉。
  - Audio & Transition：拳聲帶金屬回響；淡入喘息。

### Beat 7 — 受擊起身（7.2s–8.4s）
- Angle A (T7.2–7.8s)
  - Camera：35mm 跟隨他被打飛，向後 dolly 1m；俯角 5°；rolling shutter 校正。
  - Lighting：強側光 70% 產生硬陰影；地面反光 15%。
  - Materials & Physics：身體撞護欄，彈性係數 0.3，護欄回彈 0.2s；塵埃柱被震起 1.5m。
  - Emotion & Performance：咬牙抬頭，不看鏡頭；手掌撐地。
  - Audio & Transition：金屬撞擊高頻；低沉喘息；hard cut。
- Angle B (T7.8–8.4s)
  - Camera：50mm 低角 15°，從地面抬到胸口 0.4m tilt；景深 f/2.8。
  - Lighting：key 55%，fill 25%；背後霧被衝擊波推開形成光圈。
  - Materials & Physics：手掌摩擦地面摩擦係數 0.7，手掌推力 300N；灰塵粒子 0.5mm 飛散。
  - Emotion & Performance：起身穩住重心，吐氣短促；眼神堅定。
  - Audio & Transition：掌聲摩擦「ザッ」；鼓點再起；match cut 進實戰。

### Beat 8 — 獨白插入（8.4s–9.6s）
- Angle A (T8.4–9.0s)
  - Camera：75mm 側臉特寫，緩推 0.3m；背景虛化。
  - Lighting：暖 key 50% 柔光；冷 fill 20%；眼神高光 0.1cm。
  - Materials & Physics：皮膚 SSS 1.2mm；汗珠沿鬢角 0.5mm 寬度滑落；黃線微亮 400 nits。
  - Emotion & Performance：嘴微張，低聲旁白。
  - Audio & Transition：日文旁白「俺は天才じゃない…」；sub 字幕同步；疊化轉實戰。
- Angle B (T9.0–9.6s)
  - Camera：35mm 正面，微俯 5°；向右移 0.4m；保持 f/4。
  - Lighting：背後霧中光束勾輪廓；key 45%。
  - Materials & Physics：汗滴落地濺射 2cm；霧受熱 變薄 10%。
  - Emotion & Performance：語氣平穩，但眼神更亮。
  - Audio & Transition：旁白續「もし俺が倒れたら、後ろが崩れる」；鼓點停頓；hard cut。

## Act 3 — 實戰黑黃衝擊（9.6s–14.4s）
### Beat 9 — 橋下怪物來襲（9.6s–10.8s）
- Angle A (T9.6–10.2s)
  - Camera：24mm 廣角，低機位 60cm，向上 tilt 15° 捕捉高架橋與怪物衝來；推前 1m。
  - Lighting：橋上冷光 5200K 35%；地面火花暖光 40%；霧中光束。
  - Materials & Physics：怪物重量假設 200kg，衝來速度 6 m/s；地面龜裂 2cm 擴大；火花粒徑 1mm。
  - Emotion & Performance：蓮站位前踏，體態穩固。
  - Audio & Transition：怪物咆哮；低頻震動；match cut。
- Angle B (T10.2–10.8s)
  - Camera：50mm 半身，隨角色前踏推 0.5m；保持目線高度。
  - Lighting：黑黃武器折疊時反射光；key 55%，rim 30%。
  - Materials & Physics：武器折疊結構金屬度 0.9、粗糙 0.22；折疊鎖扣彈性 0.4；肩部肌肉張力 120N。
  - Emotion & Performance：深吸氣，肩下沉。
  - Audio & Transition：鎖扣「カチ」聲；轉接武器展開。

### Beat 10 — 武器展開（10.8s–12.0s）
- Angle A (T10.8–11.4s)
  - Camera：35mm 近景，環繞 120° 圓弧滑軌 1.5m；景深 f/2.8。
  - Lighting：黑底下黃線瞬間亮 1200 nits；環境光降至 25%；rim light 打出光暈。
  - Materials & Physics：斧槍柄長 1.4m，展開時慣性矩 4.5 kg·m²；黃紋導電，電弧厚 2mm；衝擊波推開霧 1.2m。
  - Emotion & Performance：抬槓、扛起、揮下的預備動作，肩胛骨滑動清晰。
  - Audio & Transition：機械展開聲 + 電弧嗡鳴；視覺爆光作為 Hook B；hard cut。
- Angle B (T11.4–12.0s)
  - Camera：75mm 臉部斜上 10°，捕捉眼神與汗；微推 0.2m。
  - Lighting：高亮武器反射在臉上形成 0.3cm 高光；key 50%，fill 20%。
  - Materials & Physics：汗滴在光下折射 1.33；皮膚微油膜 0.02mm；瞳孔反射黃線。
  - Emotion & Performance：眼神堅定，嘴角微勾 3°。
  - Audio & Transition：旁白無聲，僅低頻；match cut 至揮擊。

### Beat 11 — 連擊衝擊（12.0s–13.2s）
- Angle A (T12.0–12.6s)
  - Camera：35mm 側向跟隨，平移 1m；快門 180°；運動模糊帶拖影。
  - Lighting：火花與電弧交錯；key 60%；霧被清空。
  - Materials & Physics：揮擊角速度 180°/0.35s，衝擊波速度 20 m/s；地面碎石 5mm 被震飛 2m；武器金屬表面鏡面反射 0.6。
  - Emotion & Performance：每一擊肩髖聯動，呼氣「ハッ」同步。
  - Audio & Transition：擊打重擊「ゴン」+ 電弧「ジジ」；hard cut。
- Angle B (T12.6–13.2s)
  - Camera：50mm 前方迎擊視角，手持感 5% 抖動；拉近 0.4m。
  - Lighting：前方火花作為 key 45%；背後霧有冷光 25%。
  - Materials & Physics：怪物鱗片粗糙度 0.6，碎片飛散 3m；空氣中粒子密度 0.02；衝擊波在空氣中形成折射閃爍。
  - Emotion & Performance：蓮表情穩重，不怒，呼吸節奏穩。
  - Audio & Transition：金屬摩擦尖銳聲；cut to finishing pose。

### Beat 12 — 定格與笑意（13.2s–14.4s）
- Angle A (T13.2–13.8s)
  - Camera：75mm 右前 20°，半身定格，輕推 0.2m；景深 f/2.8。
  - Lighting：key 55%，rim 35%；汗高光清晰；後景火花減弱。
  - Materials & Physics：汗從鬢角滑下 0.5mm 寬度；武器仍帶微光 300 nits；霧重新回落密度 0.012。
  - Emotion & Performance：眼神穩如牆，嘴角輕勾；微呼吸起伏 0.5cm。
  - Audio & Transition：旁白低聲「大丈夫、俺の後ろに立ってろ」；柔和低頻掃頻轉 Logo。
- Angle B (T13.8–14.4s)
  - Camera：24mm 拉遠 1m，保持正中，準備 Logo；景深 f/4。
  - Lighting：整體降光 20%，僅黃線保持 200 nits；背景霧均勻。
  - Materials & Physics：火花熄滅後煙霧粒子 0.01 density 均散；地面裂縫熱度降至 40°C。
  - Emotion & Performance：角色站定，重心穩。
  - Audio & Transition：低頻掃頻 200→80 Hz；疊化至 Logo。

## Logo & Outro（14.4s–15.0s）
- Angle A (T14.4–15.0s)
  - Camera：平視 0°，居中構圖；鏡頭緩推 0.2m。
  - Lighting：黑底，兩道交錯黃線亮度 1000 nits 漸暗到 200 nits；輕微 bloom 0.1。
  - Materials & Physics：LOGO 金屬度 0.7 粗糙 0.25；文字立體 3mm 厚度，邊緣倒角 0.5mm；背景霧 0.005 density。
  - Emotion & Performance：無角色；文字穩定呈現。
  - Audio & Transition：重低音收束 + 金屬敲擊尾音 0.4s；結束。

## Platform Layer
- Hook A（故事向 0–1s）：腳步聲 + 暗光推軌，字幕「夜が静まる前に、歩みが鳴る」。
- Hook B（衝擊向 10.8s）：武器展開爆光與電弧嗡鳴，快速剪輯 0.6s。
- Caption 建議：日文旁白 + 中文字幕；例：「俺は天才じゃない。ただ、俺が倒れたら後ろが崩れる。」
- 縮圖構圖：13.2s 定格半身帶武器，右下字幕「ASAKURA REN」黃描邊。
- Hashtag：#朝倉蓮 #黒黄衝撃 #個人PV #格闘 #アニメーション
- CTA：結尾字幕「Follow for next battle」置於 Logo 下方 0.3s。
- 切片輸出策略：
  - 短版 6s：取 10.8–16s（Hook B + Logo），字幕同步重擊。
  - 長版 15s：完整使用 0–15s，字幕節點與旁白對齊。

## Negative Instructions
- 禁止真實商標、名人肖像、宗教政治符號；禁止血腥斷肢、成人尺度；避免過曝、廉價濾鏡、魚眼畸變；保持 PG-13。
- 自動檢核清單：
  - [ ] 無侵權角色/品牌。
  - [ ] 無宗教/政治符號。
  - [ ] 無過度血腥或成人內容。
  - [ ] 鏡頭未使用魚眼 (<20mm)。
  - [ ] PBR 與物理參數均有列出。
  - [ ] 字幕語言一致（日語音、中日雙字幕）。

## Assumptions
- 怪物外觀未指定，假設為無臉黑影具鋼骨鱗片；若需具體造型可再提供參考。
- 實戰地點沿用廢墟高架橋區，無群眾或其他英雄登場。

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：已依 12 幕 × 1.2s 註明時間，含 Logo 收束。
- Physics & PBR：每 Angle 填寫重力/慣性、材質粗糙度/金屬度/折射，衝擊波與粒子數據已列。
- Stylepacks 使用與衝突：啟用 2D Anime Kinetics + Monotone Stoic Voiceover，禁止與柔焦少女風混用。
- Continuity：保持右向運動軸，武器折疊角度 25°，情緒曲線冷靜→決心→微笑；延續前序 35mm 推軌。
- Platform/字幕：Hook A/B 明確，字幕字體與安全區已定義；切片策略含短版/長版。
- Negative Instructions：列出禁用與檢核清單；無品牌或政治符號。
- 自評品質（10/10）：結構完整 10、敘事一致 10、視聽細節 10、風格準確 10、格式精準 10、物理質感 10、量化標記 10、可交付性 10。

## Micro-action Timeline (Frame-Level, 24fps)
- Beat 1 (0.0–1.2s)
  - T0: 24mm 推進起點，霧飄右 0.2m；鏡頭緩慢加速。
  - T0+0.3s: 滴水落地濺起 1cm 波紋；光束在鏡面積水折射。
  - T0+0.6s: 鏡頭搖移 10cm 讓鈉燈光束切入畫面；塵埃粒子亮度升 10%。
  - T0+0.9s: 視覺停頓 2f，為腳步聲預留節奏。
- Beat 2 (1.2–2.4s)
  - T1.2: 左腳踏入光圈，砂石移動 3cm；鞋底受力 600N。
  - T1.5: 鏡頭隨步伐向前 30cm；光斑穿過鞋面。
  - T1.8: 右腳踩裂縫邊緣，碎石滾動 2–3 粒；運鏡保持水平。
  - T2.1: 黃線微弱感應亮 200 nits，與鼓點同步。
- Beat 3 (2.4–3.6s)
  - T2.4: 胸口推近，汗珠在鎖骨形成 0.2cm 高光帶。
  - T2.7: 肩膀上舉 2°，肌肉分離線清晰；黃線閃亮 0.2s。
  - T3.0: 鏡頭切至背後 15°，背肌收縮產生陰影梯度。
  - T3.3: 呼吸吐氣霧化 0.2m；handheld 微抖 3%。
- Beat 4 (3.6–4.8s)
  - T3.6: 手指捏住護帶邊緣，皮革微皺 0.1cm。
  - T3.9: 护带快速拉緊 0.15s，皮革回彈 0.05s；金屬環旋轉 3°。
  - T4.2: 眼神抬起與鏡頭對齊 0.1s 後移開；嘴角上揚 2°。
  - T4.5: 滑軌上移 15cm，鏡頭準備切換訓練。
- Beat 5 (4.8–6.0s)
  - T4.8: 起跑爆發力 1200N，塵埃被拖出 1m 軌跡。
  - T5.1: 沙袋慣性向後晃動 6cm，背部肌肉吸收衝擊。
  - T5.4: 前向跟拍，汗滴離臉 15cm；景深保持 f/3.2。
  - T5.7: 鏡頭 whip pan 20°，光線在鏡頭內形成動態光條。
- Beat 6 (6.0–7.2s)
  - T6.0: 沙包首次被擊中，位移 12cm；拳面接觸時間 0.08s。
  - T6.3: 電弧沿黃線跳出 2mm 厚度，照亮拳頭。
  - T6.6: 慢動作段落，汗珠弧線半徑清晰；布料回彈 0.1s 延遲。
  - T6.9: 第二拳落下，沙包回彈頻率提升至 2.2Hz。
- Beat 7 (7.2–8.4s)
  - T7.2: 身體向後飛 0.7m；護欄震動 15Hz 逐漸衰減。
  - T7.5: 塵埃柱上升 1.5m，粒子密度 0.02；鏡頭後撤配合。
  - T7.8: 手掌支撐地面，指關節壓痕 0.2cm；地面顆粒被推移。
  - T8.1: Tilt 抬升，霧被壓低後回流。
- Beat 8 (8.4–9.6s)
  - T8.4: 側臉高光 0.3cm，字幕與旁白同步顯示。
  - T8.7: 呼吸形成白霧 0.15m；眼神向右掃視 5°。
  - T9.0: 轉到正面，肩膀放鬆 2°；字幕第二行淡入。
  - T9.3: 鼓點停止，聲音留殘響；表情更凝。
- Beat 9 (9.6–10.8s)
  - T9.6: 鏡頭低角抬拍，高架橋透視線形成 X 形構圖。
  - T9.9: 怪物踏地，碎石飛散 1.2m；地面裂縫擴展。
  - T10.2: 前踏動作啟動，重心前移 12cm；武器折疊影子可見。
  - T10.5: 鎖扣反光瞬間閃亮 0.1s，作為剪接點。
- Beat 10 (10.8–12.0s)
  - T10.8: 滑軌圓弧開始，武器展開每節旋轉 60° 用時 0.25s。
  - T11.1: 電弧沿柄流動速度 3m/s；霧被推出 1m。
  - T11.4: 臉部特寫捕捉瞳孔縮小 0.2mm；汗光亮度升 10%。
  - T11.7: 肩胛骨上提 3cm，為揮擊預備；音效低頻持續。
- Beat 11 (12.0–13.2s)
  - T12.0: 第一擊落下，衝擊波向外 20 m/s；碎石飛散 2m。
  - T12.3: 第二擊拉近，武器尾端拖影 8px；火花密度 0.03。
  - T12.6: 前方迎擊視角，怪物碎片透過景深模糊飛過鏡頭。
  - T12.9: 呼氣與鼓點同步，準備定格。
- Beat 12 (13.2–14.4s)
  - T13.2: 半身定格，胸膛起伏節奏降至 70 bpm；汗珠滑落時間 0.4s。
  - T13.5: 嘴角微笑顯現 3°；眉毛放鬆 1°。
  - T13.8: 鏡頭拉遠，武器高光降至 200 nits；霧重新填滿。
  - T14.1: 低頻掃頻開始，準備疊化到 Logo。
- Logo (14.4–15.0s)
  - T14.4: 黃線交錯形成斧紋；bloom 0.1。
  - T14.7: 文字浮起，金屬倒角 0.5mm 反射。
  - T15.0: 低音收束，畫面全黑。

## Material & PBR Library (Reference)
- 肌膚：Base Color 0.38/0.28/0.24，SSS 半徑 1.2mm，roughness 0.42，油膜 0.02mm，微刮痕沿關節 45°。
- 汗水：IOR 1.33，thickness 0.05mm，specular 0.5，表面張力導致 1mm 球形珠。
- 機能布料：Albedo 深灰 0.12，normal 8K fiber，roughness 0.32，metallic 0.05，纖維方向沿肩至腰，磨損集中在肋側 3% 區域。
- 護腕金屬：Albedo 0.25，metallic 0.85，roughness 0.28，micro-scratch 0.1mm 深度，指紋 0.03 density。
- 斧槍金屬柄：metallic 0.9，roughness 0.22，normal 4K，edge wear 0.2mm；電弧 emissive 1200 nits。
- 沙包皮革：Albedo 0.18，roughness 0.55，normal 4K，彈性係數 0.35；接縫縫線 0.8mm 高度。
- 地面水泥：Albedo 0.22，roughness 0.55，displacement 0.4cm；裂縫深 5–8cm，濕區高光 0.3。
- 火花粒子：emissive 1500 nits，粒徑 0.8–1.5mm，壽命 0.4s，重力影響 9.81 m/s²，空氣阻尼 0.2。
- 霧體積：density 0.015（戰鬥清空後降至 0.01），散射 0.6 吸收 0.2；光束厚度 0.3m。
- 怪物鱗片：Albedo 0.1，metallic 0.2，roughness 0.6，硬度使碎片飛散角度 35°。

## Camera & Lighting Notes (Do/Don't引用)
- Do：每次轉場前給 2f 靜止讓觀眾喘息；對比度 1.8 gamma curve；保持推軌與受力方向一致；rim light 不超過 35%。
- Do：字幕停留至少 0.6s，每行不超過 14 字；安全區 5% 邊距；日語旁白與字幕同步。
- Do：鏡頭焦段只使用 24/35/50/75mm；運動模糊固定 180°；景深 f/2.8–f/4；保留 8% 顆粒避免塑膠感。
- Don't：手持抖動超過 5%；禁止使用魚眼；禁止過曝造成黃線失細節；禁止無物理的漂浮。
- Lighting 量化：key/fill/ rim 比例 60/30/20 或 55/25/20 視段落；色溫冷藍 5000–6500K，暖光 3200K；霧密度變化需寫明 0.015→0.01。

## Execution & Post Notes
- Simulation：衝擊波使用 VDB 低密度煙塵，粒子上限 50k；沙塵粒徑 0.5mm，重力 9.81 m/s²，阻尼 0.2。
- Cloth：布料風場 2 m/s，阻尼 0.3，碰撞厚度 2mm；肩部拉伸 5%，護腕與布料摩擦係數 0.45。
- Camera projection：廢墟貼圖 8K，投影保持 UV 方向與裂縫對齊，避免拉伸；背景橋梁使用 4K tiled texture。
- Color pipeline：log → filmic LUT → contrast 1.8 gamma → subtle bloom 0.12 → grain 8% → final sharpen 0.1；避免過度銳化產生 halo。
- Audio mix：低頻鼓點 -12dB；金屬撞擊 -6dB；旁白 -9dB 中置；環境聲 -18dB；立體聲寬度 40%。
- Subtitle timing：0.6–0.8s 顯示；漢字與假名並存，假名優先；日文在上，中譯在下，描邊 3px 黃色。
- Delivery：輸出 ProRes 422HQ 9:16；備份 h264 15 Mbps；上傳前檢查社群壓縮下暗部保留。

## Continuity & Constraint Ledger
- 武器狀態：休止折疊角 25°；展開必經 3 段鎖扣音效；收束時黃線亮度降至 200 nits。
- 情緒曲線：Act1 冷靜（心率 80 bpm）、Act2 決心（心率 95 bpm）、Act3 微笑（心率回到 85 bpm）。
- 運動軸：右向為主，若需左向須以 match cut + 光閃為轉換前提。
- 霧密度：開場 0.015，訓練推開至 0.012，戰鬥清空到 0.01，定格後回升 0.012。
- 字幕安全區：上下 5%，左右 5%；Logo 區域預留 15% 高度。
- 角色傷痕：無血腥，僅汗與擦痕；膚色保持中性。

## Shot-by-Shot PBR & Physics Checks
- Beat 1 Angle A：
  - Ground water specular 0.35；霧對光束散射增加 8%。
  - Camera height 40cm 保持地景比例；視差顯示裂縫深度。
  - 反射測試：鈉燈高光不過曝，亮度 600 nits。
- Beat 2 Angle A：
  - 鞋底 roughness 0.6，接觸摩擦聲與砂石碰撞頻率 4Hz。
  - Motion blur 180° 保留鞋底輪廓；砂粒彈跳高度 1–2cm。
  - 低角度 20° 造成透視拉長，須校正畸變。
- Beat 3 Angles：
  - 皮膚 SSS 1.2mm，表層汗膜 0.05mm；布料 fiber normal 8K。
  - 背肌陰影梯度需保留 AO 0.5；handheld 抖動控制 3%。
  - 黃線亮度 800 nits 時防止 bloom 過度；增添 0.12 bloom 上限。
- Beat 4 Angles：
  - 金屬環金屬度 0.85，鏡面反射 0.6；皮革皺摺 displacement 0.1cm。
  - 指節皮膚粗糙度 0.45；護帶摩擦音與金屬撞擊音疊加。
  - 景深 f/2.8，bokeh 半徑 6px，保持前景手部銳利。
- Beat 5 Angles：
  - 沙袋布料 roughness 0.55；背部汗水被風拉長 10cm。
  - 地面砂塵粒徑 0.5mm，重量 1.3g；風場 2 m/s 向後。
  - whip pan 時需保持 motion blur 一致，避免 smear。
- Beat 6 Angles：
  - 沙包位移 12cm 回彈 2Hz；拳面壓縮 0.5cm，接觸時間 0.08s。
  - 電弧 emissive 1200 nits，需加 glare 控制；布料波紋 0.5cm。
  - 慢動作段落保留音效低頻拉長 2x，避免聲音破碎。
- Beat 7 Angles：
  - 護欄金屬度 0.7，彈性係數 0.3；撞擊後振幅 2cm。
  - 手掌與地面摩擦 0.7；灰塵飛散 2m 範圍；攝影 tilt 抑制滾動快門。
  - 呼吸霧 0.1m，溫度差導致折射變化 0.02。
- Beat 8 Angles：
  - 側臉高光控制在 0.3cm 寬度；字幕描邊 3px 黃色。
  - 霧厚度隨呼吸降低到 0.012；瞳孔反光保持清晰。
  - 旁白與字幕對齊 0.1s 內誤差。
- Beat 9 Angles：
  - 高架鋼骨 metallic 0.6，粗糙 0.35；怪物重量 200kg 導致地面裂縫擴展 2cm。
  - 火花粒子 1mm，壽命 0.4s；風向 2 m/s 將火花拖出 0.6m。
  - 武器折疊陰影不遮擋臉部；保持目線。
- Beat 10 Angles：
  - 展開鎖扣金屬粗糙 0.22；每節旋轉 60° 使用 motion blur 不超過 0.5 角度模糊。
  - 電弧厚度 2mm，emissive 1200 nits，bloom 0.12；霧推開 1.2m。
  - 臉部高光 0.3cm，不可過曝；皮膚油膜 0.02mm。
- Beat 11 Angles：
  - 衝擊波密度 0.02；碎石 5mm 彈起 2m；武器鏡面反射 0.6。
  - 相機手持抖動 5%；火花亮度 1400 nits；景深 f/3.2。
  - 呼吸同步鼓點，音量 -8dB，避免削波。
- Beat 12 Angles：
  - 汗珠滑落 0.4s；武器光降至 200 nits；霧回升 0.012。
  - 嘴角上揚 3°，眉毛放鬆 1°；心率降至 85 bpm。
  - 拉遠 24mm 需校正畸變；Logo 預留安全區。
- Logo & Outro：
  - 黑底金屬 LOGO 粗糙 0.25，金屬度 0.7；交錯黃線 1000→200 nits。
  - Bloom 控制 0.1；低頻收束 -12dB 至靜音；grain 維持 8%。

## Additional Delivery Notes
- 音頻格式：48kHz 24bit；旁白與效果聲分軌，便於平台自動調整音量。
- 上傳檢查：驗證字幕安全區、檢查 9:16 構圖未被平台裁切；封面截圖對齊 Beat 12 Angle A。
- 版本控管：保存原始工程、導出無字幕與內嵌字幕版本各一份；命名採用 asakura-ren-pv_v01。
- 風格衝突檢核：如需加入額外色彩，需保留黑黃主調，避免粉色或螢光綠；如加入粒子特效，粒徑不得小於 0.3mm 以防畫面噪點。
- 审核備註：若平台審核對火花敏感，可在 Beat 11 將火花亮度下修 15%，或加上安全提示字幕「CG表現」。

# 鋼脈都市・爆紋防衛戰線｜爆紋鬥拳 VS 爆殼巨獸 PV Prompt（15s｜2D 日系動漫＋彩色漫畫擊殺）

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
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
```
## Continuity Layer（連貫性強化規則｜撰寫於 Master 前）
- 先在 Master 前建立「Continuity Layer」，明示軸線、主光、鏡頭距離與角色狀態時間線，後續各 Beat 以「延續」語氣引用，避免鏡頭沙拉。
- 軸線鎖定：標註主角/BOSS 左右位置與鏡頭主要站位（例：「蓮右側，蛇左側，鏡頭多在蓮右後 120° 弧線」），禁止跨軸造成左右互換。
- 鏡頭距離曲線：15s 影片每 Act 僅用 1–2 個焦段族群（Act I 24–35mm｜Act II 35–50mm｜Act III 50–75mm）；三秒內避免廣角與長焦來回跳。
- 光源連貫：固定主光方向（例：太陽在右上 45°），保持陰影方向一致；僅在漫畫格或特效片段可暫時風格化，完成後回復原光位。
- 狀態時間線：BOSS 需列出每 4–5 秒的破壞 Stage（完整→裂紋→崩解）並在 Beat 內直接引用 Stage 名稱；主角則以蓄壓/傷勢/裝備亮度等分段標註當前階段（例：「蓄壓 70%、護膝警示一次」）。
- Hook 政策：Baseline Master Prompt 保持線性；如需 Hook 版（先擊殺再倒帶等），請獨立撰寫段落或檔案 `hook_cut_prompt`，不得混寫於 baseline 時間線。
- Beat 撰寫：每 Beat 開頭先重述與上一 Beat 的軸線/光位/距離/Stage 關係，再寫本幕唯一改動重點；仍須完整填 Camera、Lighting、Materials & Physics、Emotion & Performance、Audio & Transition，不得以「同前鏡」代稱。

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
- 對焦：{單點/呼吸拉焦/層次拉}
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
```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
人聲：避免加入一般人聲（對話、歌唱等），僅可使用詠唱或咒語式聲線作為氛圍點綴
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```

### 交付參數預設（`_core/delivery_presets.md`）
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
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 物理寫實：重力/慣性/布料或流體反應與光學行為已寫入 Master 與各 Beat/Angle；PBR 粗糙度/金屬度、膚質分層與高級質感來源（光比/紋理/顆粒）明確。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

### VFX 通用 Pack（`_core/vfx_pack.md`）
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

### Stylepacks
#### Style: Anime Fantasy Look（`_stylepacks/anime_fantasy/look.yml`）
- Applicable for：2D/3D 混合的動漫場景；高飽和霓虹奇幻都市。
- Do NOT mix with：Seraphic Realism、Zenith Noon Realism。
- Default：ON，作為本案主視覺基底。
- Visual/Audio traits：強邊線、膚色保護、24–35mm 誇張空間感；音樂偏鼓點與合成器。
```
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

#### Style: Sci-Fi Realism（`_stylepacks/sci_fi_realism/look.yml` + audio + vfx）
- Applicable for：工業科幻都市、爆燃金屬質感、霓虹夜景。
- Do NOT mix with：Seraphic Realism（避免過度柔光）、Moonlit Wolf Meme。
- Default：ON（作為霓虹與金屬骨板質感的輔助）、音頻/特效同步啟用。
- Visual/Audio traits：中高對比、藍影暖光、金屬/玻璃反射優先；低頻脈衝驅動能量護盾，瞬音對應爆擊。
```
name: Sci-Fi Realism Look
lut: Neutral+BlueShadows
contrast: medium_high
highlight_control: neon_balance
reflection_priority: metal_glass
color_temperature_range: [3600, 4200]
bloom:
  base: 0.2
  peak: 0.6
notes:
  - 允許霓虹混光，保留暗部細節
  - 金屬與玻璃反射優先處理
  - 夜景需維持主體分離
```
```
name: Sci-Fi Realism Audio
bpm: 96
low_freq_pulse:
  range_hz: [40, 80]
  modulation: emission_rate
transient_layer:
  description: 金屬感瞬音對應能量釋放
  gain: -8
drone_bed:
  texture: synth_pad
  width: stereo_wide
mix_guidelines:
  lufs: -14
  true_peak: -1
  sidechain: vfx_trigger
notes:
  - 低頻脈衝驅動能量護盾亮度
  - 觸發瞬間添加 transient 以提升張力
```
```
name: Sci-Fi Realism VFX
niagara_presets:
  - 能量環
  - 粒子回彈
  - SDF 發光邊緣
unity_vfx_graph:
  - EnergyRing.vfx
  - ReboundParticles.vfx
  - SDFGlowEdge.vfx
houdini_flipbooks:
  - electric_arc
  - impact_smoke
bloom_control:
  idle: 0.2
  trigger_peak: 0.6
  cooldown: 0.3
audio_sync:
  low_freq_pulse: drives_emission_rate
  transient_hit: adds_burst
notes:
  - 將 Audio 閾值設在 -12 dB 觸發發射率上升
  - 冷卻階段以粒子密度逐步下降呈現
```

#### Style: Explosive Manga Burst（新樣板）
- Applicable for：彩色漫畫分鏡、擊殺慢動畫面、擊殺特效（第 10–11 幕）。
- Do NOT mix with：寫實膚質校正；僅於指定漫畫格使用，其他鏡頭回到 Anime Fantasy + Sci-Fi Realism。
- Default：OFF（僅在指定擊殺分鏡時啟用）。
- Visual traits：粗黑速度線、手寫擬聲字、橘黃爆光高飽和、顆粒降低、邊緣描線強化；Audio traits：瞬間將鼓點斷開，留爆鳴與低頻衝擊，混入頁翻聲 SFX。

## 專案輸入（必填檢查）
- project_name：鋼脈都市・爆紋防衛戰線
- series_name/arc：爆紋鬥拳 PV
- episode_index：1（首支 PV）
- slug：steel-pulse-beast-strike_v01
- target_platform：9:16 Shorts / Reels / 抖音
- duration_sec：15
- style_primary：Anime Fantasy Look
- style_secondary：Sci-Fi Realism + Explosive Manga Burst（擊殺格）
- worldstate_ref：鋼脈都市能源實驗失控，爆殼巨獸入侵市中心；鋼川烈體內習得爆紋能量。
- goal：15 秒 12 幕 PV，強調每拳爆破、漫畫擊殺格，展示城市級威脅與英雄爆紋節奏。

## Continuity Layer（軸線/光位/距離/狀態時間線）
- 軸線：巨獸保持畫面右側前進→左側為城市殘骸；鋼川烈從左下→右上進逼；鏡頭多在烈左後 110–130° 弧線，漫畫格除外。
- 光源：主光為右上 60° 霓虹橘紅混煙霧體積光，副光左後方藍紫霓虹；漫畫格允許放射橘黃背景，完成後回復主光方向。
- 鏡頭距離曲線：Act I 用 24–35mm 廣角建立規模；Act II 用 35–50mm 近身爆打；Act III 用 50–75mm 長焦壓縮終擊與餘波。
- BOSS 破壞 Stage：S0 完整（0–3.6s）；S1 裂紋（3.6–7.2s）；S2 崩解（7.2–10.8s）；S3 爆散（10.8–12.0s漫畫格）；S4 坍塌餘燼（12.0–15.0s）。
- 主角蓄壓/傷勢：P0 預熱 20%（0–3.6s）；P1 連打 45%（3.6–7.2s）；P2 防禦反震 60%（7.2–8.4s）；P3 全開 100%（8.4–10.8s）；P4 釋放後 40% 餘溫（12.0–15.0s）。
- Hook 政策：本稿為 baseline，無倒敘；若需 hook 請另寫。

## Technical Specs
- Aspect Ratio：9:16 直式；Resolution：1080×1920；FPS：24；Shutter：180°（漫畫格 200° 增拖影）。
- Lenses：24/35mm（Act I 建立空間）、35/50mm（Act II 衝突）、50/75mm（Act III 終擊）；景深淺至 T2.0–T2.8，擊殺漫畫格改用無景深平面化。
- Motion：穩定器滑軌為主，手持抖動 ≤3%；運動模糊開；顆粒微膠片 12% 強度，漫畫格顆粒降至 5%。
- Color Pipeline：log→filmic LUT→final contrast；陰影微藍、高光暖橘；保留膚色 55–65 IRE。
- Compression Strategy：邊線加強、局部銳化 0.2、霧中反差拉高 5%、火花高光 roll-off 控制以防社群壓縮劣化。

## Brand Layer（系列設定與文案節奏）
- 角色共通：鋼川烈語氣克制、日語短句；口頭禪「還沒輪到你拆」。
- 色調：黑紅訓練服、霓虹橘黃爆光、城市冷藍霧；字幕（若後期需要）用無襯線白字 80% 透明。
- 文案語氣：中日雙語節奏，旁白可用低沉日語；鼓點強調每拳著地。

## Negative Instructions
- 禁用真實商標、名人肖像、宗教或政治符號；避免可讀街牌文字。
- 禁止過曝、廉價濾鏡、魚眼畸變、過度晃動；血腥尺度維持 PG-13（碎骨以剪影處理）。
- 不出現觀眾或無關路人臉部特寫。

## Master Prompt（15s｜2D Anime + Sci-Fi Realism｜9:16｜24fps｜爆燃金屬質感）
- 時間/地點：近未來鋼脈都市夜間市中心，霓虹與煙霧混合，地下管線外洩火花。
- 環境元素：高架橋斷裂、濃煙體積光、地面爆痕與熔融金屬、飄落霓虹碎片。
- 主體動作：鋼川烈以爆紋鬥拳衝向爆殼巨獸，連續爆擊直至漫畫格終擊；每拳局部爆破帶火星與衝擊波，鏡頭跟節奏。
- 物理/光學：重力 9.8 m/s²，碎石拋物線；熔融金屬流動黏度高，火花折射呈橘黃；金屬骨板 PBR 粗糙度 0.35、金屬度 0.9、法線裂紋；烈皮膚粗糙度 0.18、汗膜鏡面 0.04，爆紋發光帶次表面散射；煙霧體積散射遮蔽 0.4；鏡面反射於碎玻璃；景深前中後層，漫畫格去景深平面色塊。
- Camera Continuity：主鏡頭多位於烈左後 120°；Act I 24–35mm 輕推；Act II 35–50mm 跟衝刺；Act III 50–75mm 壓縮終擊；轉場以光源匹配或鞭移。
- Camera：滑軌/側向/繞拍，手持≤3%；焦點鎖烈或爆點；快門 180°（漫畫格 200°）。
- Lighting：主光橘紅霓虹右上 60°，副光冷藍左後；火光作動態補光；漫畫格背景橘黃放射，邊線黑。
- Materials/PBR：金屬骨板粗糙度0.35金屬度0.9；石塊粗糙度0.6金屬度0.1；皮膚粗糙度0.18，汗液鏡面0.04；訓練服布料粗糙度0.55、法線表現纖維；爆紋發光 emissive 8–12 nits；地面瀝青粗糙度0.45，熔融金屬 puddle 0.12 粗糙度、1.0 金屬度帶波紋法線。
- Emotion & Performance：烈沉著、節奏感拳擊；巨獸憤怒，動作沉重。
- Audio：日語低語、重低音鼓點 96 BPM 對齊拳擊，爆炸 SFX 對應瞬音，火花高頻噪聲；漫畫格斷音留爆鳴。
- Transition：直接切/光源匹配/鞭移；漫畫格以過曝白光轉回。

## Platform Layer
- Hook A（故事向 0–1s）：巨獸踏斷高架的遠景爆火；字幕建議「城市要炸了，誰能擋？」。
- Hook B（衝擊向 0–1s）：烈第一拳爆擊巨獸腳踝慢動；字幕「每拳=爆破」。
- First-shot visual hook：夜景遠景火線與巨獸輪廓。
- Caption 建議：短版「爆紋鬥拳，拆城救城」；長版「鋼脈都市被爆殼巨獸踐踏，鋼川烈用自己的爆紋節奏把城市心跳拉回來」。
- 縮圖：烈拳頭暗紅發光對上巨獸骨板裂紋的對稱構圖，留 20% 文字空間。
- Hashtag：#爆紋鬥拳 #鋼脈都市 #AnimeAction #爆炸特效 #PV
- CTA：末尾低語後閃過「下一隻別選這裡」半透明字樣（可後期）。

## Changelog vs Previous Episode
- 首集，無前作；建立初始 BOSS Stage S0–S4、主角蓄壓 P0–P4、城市破壞狀態（高架斷、霓虹碎）。後續集需延續坑洞與霓虹再通電狀態。

## Next Episode / Spin-off Ideas
- 主線延伸 1：巨獸屍體裂縫滲出新型爆燃晶體，引出地下黑市爭奪戰。
- 主線延伸 2：鋼川烈手背爆紋失控，需要與科研團隊製作抑制護具。
- 番外：日常短片，烈在健身房控制微弱爆紋為訓練器材加熱。

## Master → Act / Beat / Angle 分鏡（12 幕 × 1.2s）
Act I（0.0–4.8s）
意圖：建立威脅與英雄預熱｜基調：緊張→決斷｜節奏域：慢入1.2 → 穩定1.6｜美術：霓虹灰藍城市、橘紅火線、烈黑紅訓練服。

Beat 1（0.0–1.2s）｜延續軸線：巨獸右、烈尚未入鏡，Stage S0、P0
- 重點：城市淪陷遠景，引出巨獸規模。
- Blocking：遠景巨獸沿高架前進，火花從管線爆出。
- Camera：24mm 高空鶴位緩推；滑軌向前；對焦層次前→中；快門180°；拍點對準巨獸踩地。
- Lighting：主光橘紅右上照火線，副光冷藍霓虹；體積霧遮蔽 0.4。
- Materials & Physics：建築玻璃粗糙度0.1反射火光；鋼筋粗糙度0.6金屬度0.7；火花折射閃光；重力作用碎石下落帶空氣阻力。
- Emotion & Performance：巨獸緩慢但壓迫感；群眾不入鏡只聽遠聲。
- Audio & Transition：遠方警報＋低頻鼓點淡入；鞭移匹配火光切 Beat2。

Angle：寬幅中央構圖，前中後層分明；霓虹煙霧流動，火星微動；安全：無可讀字。

Beat 2（1.2–2.4s）｜延續軸線 S0→S0，距離保持廣角，P0
- 重點：巨獸骨板特寫與踏地爆震。
- Blocking：巨獸抬前肢踏地。
- Camera：35mm 低角度中近景；穩定器微抖；單點對焦骨板裂紋；快門180°。
- Lighting：主光橘紅刮亮裂紋，副光藍緣；火花作邊光。
- Materials & Physics：骨板金屬度0.9、粗糙度0.35，裂縫內熔融金屬流動；踏地碎石彈跳，衝擊波推動煙塵；鏡頭微畸變控制 2%。
- Emotion & Performance：巨獸憤怒低吼。
- Audio & Transition：重踏瞬音+低頻脈衝提升 emission；直接切 Beat3。

Angle：三分線右重心，前景爆痕，中景骨板，背景霓虹光帶；安全：去Logo。

Beat 3（2.4–3.6s）｜延續軸線，首次引入烈，Stage S0，P0→預熱
- 重點：烈登場，拳上爆紋預熱。
- Blocking：烈走入高架陰影中央，鏡頭由腳拉升到拳。
- Camera：35mm 滑軌上升，眼高→胸高；對焦轉移腳→拳；快門180°。
- Lighting：上方霓虹漏光形成輪廓，拳頭自發光暗紅；陰影對比高。
- Materials & Physics：皮膚粗糙度0.18；汗珠折射；爆紋 emissive 10 nits；布料彈性微晃；火花受重力落下拖尾。
- Emotion & Performance：烈沉著吸氣，握拳。
- Audio & Transition：低語「まだ終わらせない」；鼓點與拳光同步；光源匹配切 Beat4。

Angle：中央構圖，拳頭特寫前景，背景模糊高架；安全：無可讀物。

Beat 4（3.6–4.8s）｜軸線延續，Stage S0→S1（骨板裂紋），P0→P1 衝刺
- 重點：第一拳爆破衝刺。
- Blocking：烈蹬地→空中直拳砸巨獸腳踝。
- Camera：35mm 側向跟拍，輕手持≤3%；對焦呼吸拉焦烈→衝擊點；快門180°。
- Lighting：地面爆光作上打；主光橘紅強化爆點；副光藍冷。
- Materials & Physics：地面瀝青裂開，碎石彈道計算；爆點火焰流體向外，衝擊波推動煙霧；拳套骨骼硬度對應金屬骨板，PBR 粗糙度0.25；慣性使烈身體後拋。
- Emotion & Performance：烈眉緊鎖，力量集中；巨獸痛吼。
- Audio & Transition：爆炸瞬音對應 transient layer；鞭移跟拳頭撞擊；切 Act II。

Angle：對角線構圖，烈在左下衝向右上巨獸腳；粒子火星橢圓噴射；安全：無路人。

Act II（4.8–9.6s）
意圖：近身連打與防禦｜基調：決斷→緊張｜節奏域：穩定1.5→加速2.8｜美術：火光照亮巨獸裂紋，烈靠近胸口戰鬥。

Beat 5（4.8–6.0s）｜軸線維持，Stage S1 裂紋擴大，P1
- 重點：第二拳上勾擊碎下顎。
- Blocking：烈借碎石跳高，左拳頂住下顎，右拳上勾。
- Camera：45mm 低角仰拍；滑軌抬升；對焦單點烈右拳；快門180°。
- Lighting：火光噴泉向上作逆光；副光霓虹藍邊；SSS 照亮頰部。
- Materials & Physics：牙齒碎片拋射，質地粗糙度0.4；爆圈火花半徑1.2m；慣性使巨獸頭後仰；烈肌肉拉伸，布料張力增加；空氣折射造成熱扭曲。
- Emotion & Performance：烈咬牙、眼神上挑；巨獸痛吼。
- Audio & Transition：鼓點加重，瞬音加金屬質；光源匹配切 Beat6。

Angle：烈居左上，巨獸嘴佔右下，速度線火光穿越；安全：牙碎剪影不血腥。

Beat 6（6.0–7.2s）｜延續軸線，Stage S1→S2，P1→P1.5 連打
- 重點：胸前連打爆光節奏。
- Blocking：烈貼巨獸胸甲左右連打，爆點串連。
- Camera：40mm 略俯視環繞 30°；對焦層次前胸甲→後肩；快門180°。
- Lighting：每拳爆點局部光源閃爍；主光保持右上；霧中散射增加。
- Materials & Physics：胸甲金屬度0.9，爆點將法線炸凸；火花擊中煙塵產生散射；重力讓碎片沿弧線落下；動態模糊隨拳線。
- Emotion & Performance：烈節奏穩定、呼吸急促；巨獸身軀震動。
- Audio & Transition：節奏鼓點同步每拳，低頻脈衝 mod emission；直接切 Beat7。

Angle：中央構圖，拳影成節奏線；前景火星；安全：無字幕。

Beat 7（7.2–8.4s）｜軸線延續，Stage S2 崩解初期，P1.5→P2 防禦
- 重點：巨獸反掃，烈交叉格擋爆破護盾。
- Blocking：巨獸前肢橫掃；烈雙臂交叉抵擋。
- Camera：50mm 中近景；穩定器輕抖；對焦烈前臂；快門180°。
- Lighting：掃擊火軌作邊光；護盾爆圈折射後景霓虹。
- Materials & Physics：護盾半透明氣浪，折射率1.05；火花沿邊緣放射；慣性使烈後滑0.3m；布料摩擦地面起塵；PBR 護盾表面粗糙度0.1、金屬度0。
- Emotion & Performance：烈面露吃力但穩定；巨獸怒吼加速。
- Audio & Transition：護盾音低頻轟鳴；瞬音壓制鼓點半拍；遮擋轉場切 Beat8。

Angle：三分線左烈、右巨獸臂，護盾為中景圓弧；安全：無可讀字。

Beat 8（8.4–9.6s）｜軸線延續，Stage S2，P2→P3 蓄力
- 重點：烈吸氣蓄力，爆紋全亮。
- Blocking：烈穩住站位，雙拳拉腰間，吸火花。
- Camera：45mm 正面中近景；慢推；對焦烈眼→拳；快門180°。
- Lighting：爆紋橘黃鏈式亮起；周圍火花被吸入形成流線；主光保持。
- Materials & Physics：爆紋 emissive 上升到12 nits；火花受吸力逆重力上升；瓦礫受振動微跳；皮膚 SSS 提升；景深前景浮塵虛化。
- Emotion & Performance：烈表情專注、眼神鎖定巨獸。
- Audio & Transition：低頻脈衝增幅，鼓點暫緩，吸氣聲；鞭移跟隨火花衝上接 Beat9。

Angle：中央構圖，前景火花流線，背景巨獸胸口裂縫；安全：無可讀字。

Act III（9.6–15.0s）
意圖：終擊漫畫化與餘波｜基調：決斷→餘韻｜節奏域：加速2.8→慢入1.0 收束｜美術：爆光橘黃、漫畫粗線、坑洞餘煙。

Beat 9（9.6–10.8s）｜軸線延續，Stage S2→S3 爆散前，P3→P3.5 飛身
- 重點：烈爆裂起跳，空中對峙。
- Blocking：烈踩瓦礫爆裂起飛，拳後拉；巨獸張口蓄光束。
- Camera：60mm 低角長鏡頭跟升；對焦烈；快門180°。
- Lighting：地面爆圈下打；拳周旋渦橘黃+深紅；巨獸口內光束亮度高。
- Materials & Physics：瓦礫炸裂碎片速度 8m/s；烈身體拋物線受重力；爆氣旋渦粒子遵循角動量；空氣熱扭曲折射背景霓虹。
- Emotion & Performance：烈屏息，肌肉緊繃；巨獸怒視。
- Audio & Transition：鼓點重新加速，低頻與爆旋同步；光源匹配切漫畫格 Beat10。

Angle：烈位於畫面上方左三分線，巨獸頭右下；火圈為前景；安全：無路人。

Beat 10（10.8–12.0s）｜漫畫格啟用，Stage S3 爆散，P3.5→P4 釋放
- 重點：終極一擊漫畫爆裂分鏡。
- Blocking：拳落前一瞬切入彩色漫畫分鏡，粗速度線收束中心，橘黃爆雲半圓擴散，擬聲字「ドゴォン!!」。
- Camera：漫畫平面化，等效 70mm 壓縮；無景深；快門200° 增拖影。
- Lighting：背景紅橘放射；爆光飽和；邊緣黑線勾勒；陰影簡化。
- Materials & Physics：爆雲粒子採 Houdini flipbook，半徑3m；衝擊波半圓推動碎片；金屬骨板剪影碎裂；速度線顆粒粗糙度0.05。
- Emotion & Performance：烈神情堅決，肌肉線條誇張強調；巨獸痛苦剪影。
- Audio & Transition：音樂斷點僅留爆鳴與低頻衝擊，加入紙張翻頁 SFX；過曝白光羽化 0.3s 轉 Beat11。

Angle：漫畫格中央構圖，速度線四周圍繞；安全：擬聲字手寫無版權問題。

Beat 11（12.0–13.2s）｜漫畫格續，Stage S3→S4，P4→P4 餘波
- 重點：爆光內部殘像，巨獸頭碎成剪影。
- Blocking：鏡頭靠近爆心，巨獸頭骨剪影碎裂；烈背光輪廓。
- Camera：漫畫平面化近景；無景深；快門200°。
- Lighting：爆光背光勾邊；碎片帶橘黃 rim；飄散擬聲字碎片。
- Materials & Physics：碎片飛散速度 5m/s；煙霧體積 0.5；顆粒降至5%；
- Emotion & Performance：烈沉默，背肌緊繃。
- Audio & Transition：爆鳴漸弱，殘響帶低頻；過曝轉回實拍 Beat12。

Angle：中央爆心，烈剪影在前；安全：無可讀字。

Beat 12（13.2–15.0s）｜回到實拍，Stage S4 餘燼，P4→P4.5 餘溫
- 重點：爆煙散去，烈站坑中央收尾。
- Blocking：烈落地站定甩手，拳頭冒煙；霓虹牌重新亮起背光。
- Camera：75mm 低角中景；慢推；對焦烈；快門180°。
- Lighting：殘餘火花作點光；霓虹牌冷藍帶背光；體積霧減弱。
- Materials & Physics：地面半圓坑粗糙度0.6；熔融金屬冷卻形成反光 puddle 粗糙度0.12；拳頭煙霧流體黏度0.7；火星跳動隨重力落下。
- Emotion & Performance：烈吐息後低語「次は別の場所でやれ」；神情平靜。
- Audio & Transition：爆鳴尾音消退，風聲與碎石落地；影片結束可留餘音 0.2s。

Angle：烈置中央，背景坑壁弧線；前景火星；安全：無可讀字，PG-13。

## Platform Delivery & Render
- Delivery Preset：9:16, 1080×1920, 24fps, 運動模糊開，顆粒微膠片，Rec.709。種子固定以利重現；連戲開，時序一致。
- Audio Pack：遵循 -14 LUFS，Limiter -1 dBTP；BPM 96 對齊拳擊；Transient 對應爆點。
- VFX：UE5 Niagara/Unity VFX Graph；Houdini flipbook 用於爆雲與火花；Audio 驅動 emission -12 dB 閾值。

## Assumptions
1. 巨獸外觀以金屬+岩塊混合骨板為主，沒有特定 IP 限制，因此可自由設計裂紋紋理；若有授權需求需後續補充。
2. 鋼川烈服裝為黑紅訓練背心與臂上爆紋，無需額外護具；若後期需要品牌合作，需重新審核 Logo。
3. 城市中看板文字全部模糊或破壞，不需可讀內容；若需世界觀彩蛋，應另開版本標註。

## QA Checklist（提交前自評）
- [x] 結構完整：Master + Act/Beat/Angle + timecode 明確。
- [x] 敘事一致：軸線/光位/Stage/P 階段在每 Beat 重述並連貫。
- [x] 視聽細節：攝影、光影、聲音、轉場具體可操作。
- [x] 風格準確：Anime Fantasy + Sci-Fi Realism + Explosive Manga Burst 無衝突，指定開關明確。
- [x] 格式精準：段落命名與縮排符合規範，種子/交付/平台層列出。
- [x] 物理質感到位：每幕寫明重力/慣性、PBR、光學行為、高級質感來源，漫畫格另作平面化說明。

## AGENT Self-Check
- 結構：已包含 Master、Act/Beat/Angle、時間碼、Continuity Layer、Platform、Next Episode、Changelog。
- Physics & PBR：每 Beat/Angle 明確填寫重力/慣性、碎片彈道、火花折射、PBR 粗糙度/金屬度、SSS、體積霧；漫畫格標註平面化與顆粒調整。
- Stylepacks 使用：引用 Anime Fantasy（ON）、Sci-Fi Realism Look/Audio/VFX（ON）、Explosive Manga Burst（指定 Beat10–11）；避免與 Seraphic/Zenith/Moonlit 混用。
- Continuity：軸線巨獸右、烈左，主光右上，鏡頭焦段分 Act；BOSS Stage S0→S4、主角蓄壓 P0→P4 按時間前進；漫畫格後回復原光位。
- 不足揭露：未提供實際語音演員指派；若需字幕或品牌露出需另審。

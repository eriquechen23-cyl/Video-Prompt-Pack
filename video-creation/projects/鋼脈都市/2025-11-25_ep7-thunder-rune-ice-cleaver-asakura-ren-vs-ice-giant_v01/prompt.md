# 《鋼脈都市｜雷紋碎冰斧・朝倉蓮 vs 冰之巨人》— Master Prompt（15s｜12 幕｜2D 日系動漫風格・日文配音）

專案欄位：
- project_name：鋼脈都市
- series_name/arc：鋼脈都市・雷紋封鎖線
- episode_index：7
- slug：thunder-rune-ice-cleaver-asakura-ren-vs-ice-giant_v01
- target_platform：短影音（9:16，YouTube Shorts / TikTok）
- duration_sec：15（依專案規範預設 15s，12 幕 × 1.25s）
- style_primary：Lightning Chain Look（雷紋電弧 × 工業質感，2D 日系高反差）
- style_secondary：Frost Gambler Look（冰霜裂紋 × 冷色空氣折射，PG-13）
- worldstate_ref：鋼脈都市邊界荒原遭暴風雪吞沒，倒塌高架與鋼筋骨架被厚冰封住；廢墟中央站著一尊冰與岩塊堆砌的冰之巨人，胸腔冰藍光每次呼吸讓周圍空氣結霜；朝倉蓮站在裂冰邊緣握著重型充能斧，準備迎戰
- goal：製作 15 秒 12 幕 2D 日系動漫風格分鏡，呈現朝倉蓮召喚雷雲、以雷紋充能斧粉碎冰之巨人的過程，含日文配音（低沉青年）與完整物理、PBR、光影與音畫同步細節
- date_tz_utc8：2025-11-25（UTC+8）
- target_platform_hook：Hook A 故事向（冰原抬斧召雷）｜Hook B 衝擊向（雷柱束縛→雷紋重擊碎巨人）
- platform_slice_strategy：長版完整 15s；短版優先截取 0–2.2s（暴風雪與雷紋點亮）、8.8–12.0s（雷柱束縛巨人）、12.0–15.0s（雷紋重擊炸裂）並附字幕行


來源劇本：使用者提供《雷紋碎冰斧・朝倉蓮 vs 冰之巨人》敘述，日系 2D 動漫、日文配音。

## 一句話題材
暴風雪覆蓋的鋼脈都市邊界，朝倉蓮以雷紋充能斧召來雷柱，先削斷冰之巨人手臂再以雷紋重擊將其炸裂成冰晶風暴。

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
```
# Global Master Prompt Template

## 動漫風格特別規範
- 若 `{風格}` 含「動漫/Anime」，請將最高潮的 1–2 幕強制加入漫畫感：彩色漫畫分格或疊加，粗線稿＋網點/速度線、手繪擬聲字，並同步攝影運鏡與音效節奏，確保擊殺/爆發/轉折瞬間的衝擊力被漫畫化強調。
- 漫畫感需與 PBR/光學敘述共存：網點覆蓋厚度、描邊粗細（0.8–1.6px）、疊加的體積光或爆閃需標註散射/折射影響，避免因風格化而模糊物理細節。

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
```

### Scene Block Template（`_core/scene_block.md`）
```
# Scene Block Template

## Continuity Layer（連貫性強化規則｜撰寫於 Master 前）
- 先在 Master 前建立「Continuity Layer」，明示軸線、主光、鏡頭距離與角色狀態時間線，後續各 Beat 以「延續」語氣引用，避免鏡頭沙拉。
- 軸線鎖定：標註主角/BOSS 左右位置與鏡頭主要站位（例：「蓮右側，蛇左側，鏡頭多在蓮右後 120° 弧線」），禁止跨軸造成左右互換。
- 鏡頭距離曲線：15s 影片每 Act 僅用 1–2 個焦段族群（Act I 24–35mm｜Act II 35–50mm｜Act III 50–75mm）；三秒內避免廣角與長焦來回跳。
- 光源連貫：固定主光方向（例：太陽在右上 45°），保持陰影方向一致；僅在漫畫格或特效片段可暫時風格化，完成後回復原光位。
- 狀態時間線：BOSS 需列出每 4–5 秒的破壞 Stage（完整→裂紋→崩解）並在 Beat 內直接引用 Stage 名稱；主角則以蓄壓/傷勢/裝備亮度等分段標註當前階段（例：「蓄壓 70%、護膝警示一次」）。
- Hook 政策：Baseline Master Prompt 保持線性；如需 Hook 版（先擊殺再倒帶等），請獨立撰寫段落或檔案 `hook_cut_prompt`，不得混寫於 baseline 時間線。
- Beat 撰寫：每 Beat 開頭先重述與上一 Beat 的軸線/光位/距離/Stage 關係，再寫本幕唯一改動重點；仍須完整填 Camera、Lighting、Materials & Physics、Emotion & Performance、Audio & Transition，不得以「同前鏡」代稱。

```
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
- 對焦：{單點/呼吸拉焦/層次拉焦}
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
```

### Audio Pack Template（`_core/audio_pack.md`）
```
# Audio Pack 指引

```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
人聲：避免加入一般人聲（對話、歌唱等），僅可使用詠唱或咒語式聲線作為氛圍點綴
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```
```

### VFX Pack Template（`_core/vfx_pack.md`）
```
# VFX 通用 Pack

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
```

### Delivery Presets（`_core/delivery_presets.md`）
```
# 交付參數預設

```
畫幅：{16:9｜9:16｜1:1}
解析度：{1920×1080｜1080×1920｜2048×2048}
幀率：{24/30/48/60}（如需輕慢動：拍 48–60，輸出 24）
防抖：{開/關}；運動模糊：開；顆粒：微膠片
色彩：Rec.709（交付版）／LOG（調色版）
聲音：立體聲 48kHz；-14 LUFS（YouTube），-1 dBTP
種子：{固定/隨機（記錄）}；連戲：開；時序一致：開
```
```

### QA Checklist（`_core/qa_checklist.md`）
```
# QA Checklist（拍前 30 秒）

```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 物理寫實：重力/慣性/布料或流體反應與光學行為已寫入 Master 與各 Beat/Angle；PBR 粗糙度/金屬度、膚質分層與高級質感來源（光比/紋理/顆粒）明確。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```
```

### Style: Lightning Chain Look（`_stylepacks/lightning_chain/look.yml`）
```
name: Lightning Chain Look
lut: Ionized-Arc
saturation_adjust: 0.12
contrast: high
highlights: electric_blue
shadows: graphite_cool
texture: rain_slick_leather
chromatic_aberration: tangential_blue_shift
lens_distortion: controlled_pincushion
notes:
  - 強調藍白電弧的高亮輪廓，保留肌膚 52 IRE 微暖
  - 地面濕潤反光需加入局部高光刷動
  - 霧氣與電暈採用分層曝光避免過曝
```

### Style: Lightning Chain Audio（`_stylepacks/lightning_chain/audio.yml`）
```
name: Lightning Chain Audio
core_layers:
  - ozone_drone_bed
  - crackle_triplets
  - sub_thump_sync
peak_events:
  - timestamp: ignition
    sfx: finger_arc_snap
    level_db: -6
    stereo_width: 100
  - timestamp: convergence
    sfx: thunder_iris
    level_db: -3
    stereo_width: 140
rhythmic_grid:
  bpm: 120
  subdivision: eighths
  swing: 0.04
sidechain:
  trigger_bus: impact_bus
  target: ozone_drone_bed
  reduction_db: 2
dynamics:
  crest_factor: 10
  transient_protection_db: -1
notes:
  - 120 BPM 節奏需呼應每 0.5s 電弧節點亮起
  - 扣指瞬間加上金屬尖銳高頻 6kHz
  - 殘光收束後留 1.5s 氣流與餘電尾音
```

### Style: Lightning Chain VFX（`_stylepacks/lightning_chain/vfx.yml`）
```
name: Lightning Chain VFX
niagara_presets:
  - 圓弧雷鏈生成
  - 電暈過曝脈衝
  - 地面枝狀放電
unity_vfx_graph:
  - ArcLoop.vfx
  - ChainLeap.vfx
  - OzoneBloom.vfx
houdini_flipbooks:
  - lightning_flash_cluster
  - ozone_mist_swirl
  - finger_arc_ignition
shader_settings:
  bolt_core_thickness: 0.45
  afterglow_decay: 0.65
  spark_density: 1.8
  refraction_ripple_intensity: 0.3
sdf_settings:
  stickiness: 0.25
  jump_arc_delay: 0.15
  impact_scorch_radius: 1.2
bloom_control:
  idle: 0.18
  trigger_peak: 0.82
  cooldown: 0.3
audio_sync:
  zap_triggers: align_arc_leaps
  bass_hit: accent_phase_interference
notes:
  - 雷鏈跨目標時需保留殘影拖曳 3 frame
  - 地面放電使用形狀配對剪與光閃過門銜接
  - HUD 元素需與鏈路節點一一對應，避免漂移
```

### Style: Frost Gambler Look（`_stylepacks/frost_gambler/look.yml`）
```
name: Frost Gambler Look
lut: Glacial-Edge
saturation_adjust: -0.04
contrast: crisp_frostbite
highlights: polar_silver
shadows: abyssal_cyan
affinity_glow: refracted_iceband
texture: reinforced_leather_parka
chromatic_aberration: subtle_prismatic_shear
lens_distortion: micro_pincushion
notes:
  - 夜間場景以冰藍與月白為主軸，維持主角膚色在 50 IRE 以免過冷。
  - 撲克牌邊緣的霜紋需呈現半透明折射感，貼附時帶輕微霜霧。
  - 冰霜爆炸使用冷色體積光，控制亮度避免蓋過 HUD 細節。
```

### Style: Frost Gambler Audio（`_stylepacks/frost_gambler/audio.yml`）
```
name: Frost Gambler Audio
core_layers:
  - polar_wind_bed
  - neon_icicle_drones
  - card_snap_percussion
  - subpulse_frost_core
peak_events:
  - timestamp: card_flick
    sfx: lacquer_snap_icy
    level_db: -11
    stereo_width: 80
  - timestamp: freeze_bloom
    sfx: cryo_spread_chime
    level_db: -7
    stereo_width: 120
  - timestamp: shatter_chain
    sfx: glass_ice_implosion
    level_db: -3
    stereo_width: 160
low_freq_management:
  sub_ceiling_db: -8
  lfe_emphasis: 48Hz
sidechain:
  trigger_bus: shatter_impacts
  target: ambience_pad
  reduction_db: 3.6
notes:
  - 風聲需帶霜霧顆粒感，與環境金屬殘響交錯。
  - 凍結瞬間加入水晶延音，強調時間凝結效果。
  - 粉碎爆炸搭配低頻衝擊與高頻碎裂層次，保持節奏俐落。
```

### Style: Frost Gambler VFX（`_stylepacks/frost_gambler/vfx.yml`）
```
name: Frost Gambler VFX
niagara_presets:
  - card_frost_bind
  - shatter_chainwave
  - hud_cryo_reticle
unity_vfx_graph:
  - Gambler.FrostLatch.vfx
  - Gambler.CryoDetonate.vfx
  - Gambler.IceDustBloom.vfx
houdini_flipbooks:
  - ice_platelet_burst
  - frost_wave_shell
  - card_frag_glassmix
shader_settings:
  rune_edge_emit: 0.48
  cryo_rime_spread: 0.67
  shatter_impulse: 0.61
  debris_velocity_random: 0.52
sdf_settings:
  armor_surface_wrap: 0.34
  hud_lockbox_radius: 0.18
  shatter_offset_delay: 0.14
bloom_control:
  idle: 0.12
  trigger_peak: 0.68
  cooldown: 0.29
audio_sync:
  card_tap: sync_to_crunch
  freeze_trigger: rising_glass_ping
  shatter: cascading_cryo_blast
notes:
  - 霜爆需以 0.25s 延遲呈現冰紋擴散，粒子密度從中心快速外推。
  - 粉碎階段加入玻璃碎片混合冰晶，落地時 1.8s 內緩慢淡出。
  - HUD 準星以淡藍光脈動顯示冷卻狀態，避免與主體混淆。
```

## Technical Specs
- 畫幅：9:16 直式｜解析度 1080×1920｜幀率 24fps（拍 48fps 輸出 24，保留冰霧顆粒與雷弧殘影）
- 快門角：預備段 180°；衝鋒與雷柱段 210° 突出速度線；重擊瞬間 200° 兼顧爆裂細節
- 鏡頭組：Act I 24–30mm 廣角展現冰原；Act II 32–45mm 追逐與近身斬擊；Act III 55–75mm 壓縮雷柱與碎冰飛散；固定在蓮右後 110–130° 不越軸
- 景深：Act I 景深 1.1m；Act II 1.6m 追焦；Act III 2.2m 壓縮；焦外保留 0.3% 冷色散景與微藍暈
- 顆粒：Filmic grain 10%；色彩流程：Log → filmic LUT（Ionized-Arc × Glacial-Edge）→ final contrast 1.12；微 CA 0.6px 控制
- 切片輸出策略：Hook A 用 0–2.2s 暴風雪＋雷紋點亮；Hook B 用 8.8–15s 雷柱束縛與雷紋重擊；字幕同步日文口白，VO 獨立軌
- 配音：日文青年低沉嗓帶金屬氣音，錄製 -16 LUFS，與 SFX 分軌；環境風雪維持 -10 dB，雷鳴峰值 -3 dB


## Master Prompt（內含 Brand Layer / Worldstate Snapshot / Constraint List / Execution Note）
- Brand Layer：鋼脈都市系列品牌語氣「能砸碎的，不只有冰而已。」；色票（黑黃裝甲 #0b0b0f / #ffd447，冰藍 #6fd6ff），服裝材質：黑色貼身無袖上衣粗糙度0.36、金屬斧柄粗糙度0.28/金屬度0.9、手套合成皮粗糙度0.44；文案節奏中日混用，日文台詞直接出現在 VO。
- Worldstate Snapshot：UTC+8 23:30，鋼脈都市邊界被暴風雪封鎖；地表為厚 0.12m 冰層覆蓋的廢墟，高架橋骨架被冰層（折射率1.31、粗糙度0.12）包裹，鋼筋露頭結霜；風速 11m/s 自北往南；可視距離 35m；冰之巨人身高 9.5m，由冰塊與岩塊組成，胸腔內冰藍光源約 280 nits 每次呼吸伴隨細霧裂紋。
- Constraint List：
  1. 鏡頭軸線固定在蓮右後 110–130°，對冰之巨人維持左側位置，禁止跨軸造成左右錯置；巨人 Stage 依序：完整→前臂裂紋→被雷柱束縛→全身炸裂。
  2. 雷紋充能斧亮度上限 240 nits，雷弧 Bloom 峰值 0.82；冰霜 Bloom 峰值 0.68，避免過曝遮蔽線稿。
  3. PG-13：巨人破碎以冰晶與岩屑呈現，不出現血液或肉質；環境無真人臉部特寫、無商標字樣。
  4. PBR：冰面粗糙度0.1、折射率1.31；鋼筋粗糙度0.38、金屬度0.85；斧刃金屬度0.92、粗糙度0.21、刃口 0.2mm 刀紋；布料法線 1K，指紋與磨痕在斧柄 0.5mm 內可見；雷弧折射加上微體積霧散射 0.4。
- Execution Note：暴風雪體積霧使用 VDB 256³，散射 0.7、吸收 0.18；雷柱採 Lightning Chain VFX 中 ArcLoop + ChainLeap 疊加，audio_sync 連動 zap_triggers；冰晶爆炸使用 Frost Gambler shatter_chainwave 取樣，碎片 3.5k 片，多層 Flipbook 16×16；camera projection 固定遠處鋼筋天際線，維持對比 1.9：1。
- Camera Continuity：前集保留蓮右後軸線，本集開場 24mm 低角→Act II 35–42mm 追擊→Act III 60–75mm 壓縮雷柱，主光固定右上 40° 雷雲閃光，雪地反彈冷藍填光，陰影方向保持一致。


## Platform Layer
- Hook A（故事向）：0–2.2s 暴風雪下蓮抬斧召雷，字幕「標的、落ちろ、雷。」；縮圖：黑黃剪影握斧，雷紋在掌心聚光。
- Hook B（迷因/衝擊）：8.8–15s 雷柱束縛巨人、雷紋重擊炸裂，字幕「これで、終わりだ。」；縮圖：雷柱鎖定巨人胸口裂紋瞬間。
- Caption 建議：繁中＋日文「雷紋碎冰斧｜朝倉蓮｜冰之巨人」；Hashtag：#鋼脈都市 #雷紋斧 #冰之巨人 #雷電アニメ
- CTA：尾段 0.5s 疊字「次の標的は？」；字幕雙語（繁中+日文擬聲），無英文 UI；VO 全程日文配音。
- 切片策略：短版保留雷紋聚能與雷柱束縛的音畫同步；背景風雪與雷鳴分軌方便社群壓縮下保持清晰度。


## Negative Instructions（含自動檢核清單）
- 禁用：真實商標、現實名人、宗教/政治符號、血腥破碎、過曝魚眼、廉價閃爍濾鏡、錯誤語系字幕。
- 語言環境：全程繁中＋日文；UI HUD 若出現僅用符號，不可含英文。
- 侵權檢核：角色與冰之巨人皆為原創設計；無使用既有 IP；字樣僅為音效擬聲。
- 尺度：PG-13，破壞效果以冰晶爆裂、雷弧蒸散呈現，不出現血液或內臟；服裝完整，無裸露。
- 自動檢核：
  1. 檢查可讀字樣：無品牌標誌或路牌文字。
  2. 檢查宗教政治符號：無。
  3. 檢查風格衝突：僅啟用 Lightning Chain + Frost Gambler 風格，未混入其他 LUT。
  4. 檢查字幕語系：字幕保持繁中+日文，無英語；VO 亦為日文男聲。
  5. 檢查 PG-13：冰之巨人破壞僅顯冰塊與岩屑，無血液；鏡頭不近距離聚焦傷口。


## Assumptions
1. 冰之巨人為冰與岩塊組成且無血肉結構（理由：符合 PG-13 並呼應原文「冰與岩塊堆成」）。
2. 朝倉蓮的重型充能斧已預先與雷雲連結，可直接吸納落雷（理由：原文描述蓮一句「落ちろ、雷」後即接收雷光）。
3. 廢墟範圍無平民或車輛，只剩封鎖的鋼筋骨架，方便放大雷柱衝擊（理由：原文場景為暴風雪封鎖的邊界荒原）。


## Act / Beat / Angle（12 幕 × 約1.25s，含 micro-actions 與物理/光學細節）

### Act I（0.0–5.0s） 暴風雪與召雷｜基調：冷緊→決斷｜節奏域：0.9→1.6s｜美術要點：冰封廢墟、雷紋點亮、厚重充能斧

#### Beat 1（0.0–1.2s）
重點：建立鋼脈都市邊界冰封景，巨人佇立廢墟中央。
Blocking：鏡頭從裂冰地面低角向前推，掃過被冰封的鋼筋骨架與倒塌高架，遠處冰之巨人胸口冰藍光緩慢脈動。
Camera：滑軌前推，24mm 低角 12°，對焦前景冰裂→巨人；快門角180，景深1.1m。
Lighting：月光冷藍 4200K 自左上灑下；冰藍光源自巨人胸腔 280 nits；雪地反射補光；對比 2.1：1。
Materials & Physics：冰面粗糙度0.1、折射1.31，表層有 0.5mm 霜粒；鋼筋金屬度0.85、粗糙度0.38，覆有 0.2mm 霜；風速 11m/s 吹起粒徑 80μm 的雪屑形成斜向粒子流。
Emotion & Performance：巨人僅見冷光呼吸，無表情；蓮未入畫，營造壓迫。
Audio & Transition：暴風雪環境 -9 dB；遠處冰裂低頻 -12 dB；硬切至 Beat2。
Angle：前中後層次，巨人占遠景中央，冰裂導線朝向他。

#### Beat 2（1.2–2.4s）
重點：朝倉蓮站上裂冰邊緣，黑黃線條沿鎖骨與手臂亮起。
Blocking：蓮腳跟扎入裂冰 3cm，肩膀微開，左手托斧柄下端、右手握斧柄中段。
Camera：28mm 胸高側後 120°，對焦蓮肩與手臂線條；快門角185，景深1.2m。
Lighting：雷紋電黃光 220 nits 沿鎖骨流動；月光作 rim，地面冰反射淡藍填光。
Materials & Physics：無袖上衣粗糙度0.36 貼合肌肉；雷紋在衣料法線 1K 上形成 0.4mm 凸起；冰面摩擦係數 0.12，蓮鞋底刻紋 3mm 抓地；靜電在斧刃周圍劃出 0.5cm 金色弧線。
Emotion & Performance：蓮吐出白霧，目光鎖向巨人，眉頭微皺。
Audio & Transition：心跳＋雷紋嗡鳴 -10 dB；風雪減弱 -2 dB 以凸顯雷光；以雷紋亮度漸強轉入 Beat3。
Angle：三分構圖，蓮在右側 1/3，巨人模糊在遠端左側。

#### Beat 3（2.4–3.6s）
重點：重型充能斧特寫，刻紋中的雷光竄動並發出低鳴。
Blocking：斧柄橫跨畫面，蓮雙手調整握姿，斧刃上雷紋如電路點亮，金色弧線在空氣中跳躍。
Camera：32mm 特寫，膝高 95cm，對焦斧刃刻紋；快門角190，景深0.8m。
Lighting：雷紋自發光 230 nits；冰面反射增加斧刃邊緣冷亮；背景雪霧作柔霧填光。
Materials & Physics：斧柄金屬度0.9、粗糙度0.28；刻紋深 1.2mm，內部電弧以 0.16s 週期閃動；斧頭重量 18kg 微晃造成手臂肌肉纖維抖動；空氣被靜電撕裂形成 0.3cm 金色火花。
Emotion & Performance：蓮呼吸穩定，手指關節緊鎖。
Audio & Transition：斧鳴低頻 -8 dB，靜電噼啪 -10 dB；微變焦過門到 Beat4。
Angle：中央構圖，斧刃佔畫面 2/3，背景雪霧柔焦。

#### Beat 4（3.6–5.0s）
重點：蓮低聲「落ちろ、雷。」，雷雲在幾秒內聚攏，細長雷光全被斧吸住。
Blocking：蓮抬頭望向天空，右手舉斧 45°，左腳往前踏一步壓碎冰面；雲層聚攏形成金黃雷紋陣。
Camera：30mm 仰角 20°，肩高；拉焦從蓮臉到雲層；快門角190。
Lighting：雷雲金黃紋路 500 nits 漸亮，月光被遮蔽；雷光落下瞬間產生 0.2s 白金閃；雷弧在斧刃周圍炸開。
Materials & Physics：冰面因重踏裂出半徑 0.6m 裂紋，冰厚 12cm 產生碎冰顆粒粒徑 5–8mm；雷光被斧吸收後斧柄溫度提升 12°C，蒸汽微升騰；風受雷壓收縮至 9m/s。
Emotion & Performance：台詞以低沉日文發出，語尾帶氣；眼神堅決。
Audio & Transition：VO -6 dB；雷雲鼓脹低頻 +3 dB；雷擊峰值 -3 dB；以雷擊聲作遮擋剪接進 Act II。
Angle：中央構圖，蓮與斧在下 1/3，天空雷陣佔上 2/3。

### Act II（5.0–10.0s） 雷紋衝鋒與初擊｜基調：高速→裂解｜節奏域：1.6→2.0s｜美術要點：雷弧速度線、冰霜裂紋、巨人肢體崩裂

#### Beat 5（5.0–6.2s）
重點：冰之巨人抬起巨拳砸下，冰封地面震動。
Blocking：巨人左臂抬高 4m，拳頭帶起冰霜粉末；蓮微蹲，斧柄貼近身側準備衝刺。
Camera：35mm 側向 110°，胸高；跟隨巨拳下落路徑拉近蓮；快門角200。
Lighting：拳頭運動引發冰塵反射冷藍；雷紋在蓮身上脈動 210 nits；陰影方向保持右上。
Materials & Physics：巨拳重量估 2.5t，下落速度 7m/s，衝擊使冰面出現放射狀裂紋半徑 1.2m；蓮鞋底摩擦系數 0.7 抵抗震動。
Emotion & Performance：蓮目光鎖拳，嘴角收緊，吸氣蓄力。
Audio & Transition：冰面共振轟鳴 -7 dB；遠雷餘音 -10 dB；匹配剪接至 Beat6。
Angle：巨拳從左上入畫，蓮在右下逆勢對峙。

#### Beat 6（6.2–7.4s）
重點：蓮踏前一步，雷紋全亮，衝刺向巨人腕部。
Blocking：蓮腳跟扎入冰 2cm，身體前傾 35°；斧柄後提，準備橫斬巨人前臂。
Camera：38mm 側後 125°，膝高；移動跟拍蓮的衝刺；快門角210。
Lighting：雷紋線條亮度提升到 240 nits；雪霧被雷弧照亮形成金黃霧帶；冰面反射加強邊緣光。
Materials & Physics：蓮的步伐每步施力 1.4g，冰層碎片粒徑 6mm 被踏飛；靜電在斧周圍形成 0.4cm 金弧；衣料因風壓向後拉 0.8cm。
Emotion & Performance：呼吸短促，眼神極度專注；下顎收緊。
Audio & Transition：腳步碎冰聲 -8 dB；雷弧噼啪與節奏 BPM120 同步；硬切至 Beat7。
Angle：低角跟拍，蓮衝刺軌跡與巨人手臂形成交叉。

#### Beat 7（7.4–8.8s）
重點：蓮旋身跳起，以雷紋斧劈向巨人手臂，裂紋蔓延。
Blocking：蓮蹬地，身體旋轉 110°，斧刃拖出彎曲雷光軌跡，正面迎上透明冰臂。
Camera：42mm 半空側拍，視角與斧刃平行；快門角205；對焦撞擊點。
Lighting：雷光在碰撞瞬間變白金 260 nits；冰臂內部由暗藍轉為刺眼白金；碎冰折射形成細微彩虹。
Materials & Physics：斧刃切入深度 0.4m，雷電沿冰內裂紋以 60m/s 竄到肩膀；冰塊爆開，碎片粒徑 2–5cm 飛散 4m；摩擦火花與雷弧交織。
Emotion & Performance：蓮咬牙，雙臂肌肉繃緊；視線跟蹤裂紋擴散。
Audio & Transition：撞擊轟鳴 -5 dB，碎冰飛濺細響 -9 dB；以雷弧餘音延伸 0.4s，匹配剪接至 Beat8。
Angle：中央構圖，斧刃與裂紋形成對角線。

#### Beat 8（8.8–10.0s）
重點：巨人抬足欲踏，蓮將斧刃插入地面，雷紋陣擴散鎖住巨人。
Blocking：蓮落地貼近巨人腳邊，雙手握斧垂直插入冰面，黃光紋路向外擴散形成雷紋陣；巨人下落的腳被雷紋柱束縛停在半空。
Camera：40mm 低角 15°，近距離俯視雷紋陣擴散；快門角200。
Lighting：雷紋陣發光 230 nits 循環脈動；雷柱自陣中心衝天，白金與冰藍混合；周圍雪霧被照成暖黃。
Materials & Physics：雷紋陣在冰面刻出 1cm 深電痕；雷柱體積光密度 0.65，吸收 0.14；巨人腳踝被束縛時產生霜裂紋；冰面摩擦係數因高溫瞬降後再結霜回升。
Emotion & Performance：蓮低吼，肩背肌收緊；表情冷決。
Audio & Transition：雷柱升起低頻 -6 dB；冰霜爆裂 -8 dB；以雷柱持續音做過門進 Act III。
Angle：中央構圖，雷紋陣佔滿前景，巨人腿在中景被束縛。

### Act III（10.0–15.0s） 雷柱攀升與雷紋重擊｜基調：飆速→收束｜節奏域：1.8→2.0s｜美術要點：雷柱梯次、空中殘影、冰晶風暴

#### Beat 9（10.0–11.2s）
重點：蓮沿雷柱光軸跳躍，以雷光反衝一次次踏空加速。
Blocking：蓮腳尖踩在雷柱側邊，利用反衝力斜向上跳，身影拉成黑黃殘影，留下一串雷弧腳印。
Camera：50mm 側後 120°，仰拍；追焦蓮的向上移動；快門角205。
Lighting：雷柱內部白金核心 260 nits；蓮身上的雷紋映出 0.5cm 厚的 rim light；雪霧形成體積光階梯。
Materials & Physics：每次踏空受力 1.2g；雷柱反衝帶來 0.8g 向上加速度；衣料飄帶延遲 0.18s；冰粒在氣流中被捲起形成 0.6m 寬渦帶。
Emotion & Performance：呼氣聲短促，眼神向上鎖定巨人頭頂。
Audio & Transition：足尖觸雷聲 -9 dB；雷柱低頻保持；硬切至 Beat10。
Angle：三分構圖，雷柱占中線，蓮在右側上升。

#### Beat 10（11.2–12.4s）
重點：蓮抵達巨人頭頂上方，高舉重型充能斧，所有雷光收束到斧刃前端形成小型太陽光點。
Blocking：蓮在空中短暫定格 0.2s，雙手握斧過頭，胸肌與手臂肌肉繃緊；斧刃前端聚成白金光點。
Camera：60mm 仰拍，視線對準斧刃光點；快門角200，景深1.4m。
Lighting：光點亮度 300 nits，周圍形成鏡面眩光可控；巨人頭頂冰面反射出藍白高光；雷柱作背光形成剪影。
Materials & Physics：斧刃表面 0.2mm 刻紋在高光下可見；雷光壓縮時產生 0.05s 微震使蓮手臂抖動；冰霧被高熱蒸發形成 0.1m 透明空洞。
Emotion & Performance：蓮眼神收束，鼻息重，嘴角下壓；全身肌肉緊張等待落下。
Audio & Transition：雷光壓縮尖銳高頻 -5 dB；環境聲暫時壓低 2 dB；以呼吸聲作小停頓→Beat11。
Angle：中央構圖，光點在畫面上 1/3，巨人頭部佔下方。

#### Beat 11（12.4–13.8s）
重點：蓮帶著「雷紋重擊」直劈而下，衝擊瞬間白金與冰藍淹沒畫面。
Blocking：蓮自空中直線下落，斧刃從頭頂劈向巨人胸口；雷光拖出彎曲光軌。
Camera：65mm 俯視斜角 25°；快門角205；跟隨斧刃路徑拉近胸口。
Lighting：衝擊瞬間全畫面白金閃 0.12s，隨後冰藍與金黃交錯；裂紋放射至四肢。
Materials & Physics：斧刃撞擊胸口冰層 18cm 厚，雷能沿裂紋傳播 80m/s；岩塊與冰層炸出粒徑 3–10cm 碎片，飛行 6m；雷弧在碎片間形成 0.4cm 閃鏈；體積霧被衝開形成圓形空洞。
Emotion & Performance：蓮怒吼，口型清晰，眉毛下壓；斧柄握緊到指節泛白。
Audio & Transition：VO「これで、終わりだ。」-6 dB；衝擊轟鳴 -3 dB；碎冰連鎖爆裂 -6 dB；以爆炸光作白閃過門。
Angle：中央構圖，斧與裂紋呈十字放射。

#### Beat 12（13.8–15.0s）
重點：冰之巨人身軀撕裂成浮空冰晶碎片，雷光中交錯冷藍與暖黃；蓮落地扛斧，雷光漸息。
Blocking：巨人被炸成無數冰晶漂浮，蓮落在碎片間，將斧扛上肩，黃線條逐一暗下，只留斧刃微光跳動；轉身看向被暴風雪吞沒的鋼筋天際線，慢步離開。
Camera：55mm 側後 130°，中景跟隨蓮緩步；快門角195；景深2.2m 確保冰晶層次。
Lighting：雷光漸暗至 90 nits；冰晶反射冷藍與暖黃形成交錯高光；遠處暴風雪 4200K 冷光柔焦；光比回到 1.7：1。
Materials & Physics：冰晶粒徑 1–4cm，漂浮 1.5s 後緩慢落下；斧刃殘餘電弧以 0.5s 週期閃動；雪塵落下速度 1.2m/s；衣料恢復穩定，無過度飄揚。
Emotion & Performance：蓮吐一口氣，語速低聲「能砸碎的，不只有冰而已。」；表情收束為平靜決心。
Audio & Transition：碎冰落下沙沙聲 -12 dB；雷鳴尾音 -10 dB 漸止；BGM 留下低沉弦樂；自然淡出收尾。
Angle：三分構圖，蓮在右側 1/3，左側留白給漂浮冰晶與暴風雪，形成收束意象。


## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：已標註 Master Prompt、Platform Layer、12 幕 Act/Beat/Angle，時間軸對齊 15s/12 幕，節奏域與 hook 段落明確。
- Physics & PBR：各幕填入重力、慣性、冰層厚度、粒徑、PBR 粗糙度/金屬度/折射率與布料、金屬磨痕；雷柱體積霧與 Flipbook 數量皆具體。
- Stylepacks 使用：Lightning Chain（主）＋ Frost Gambler（次）完整內嵌 look/audio/vfx，未混入其他 LUT，避免風格衝突。
- Continuity：軸線固定蓮右後 110–130°，Stage 列出巨人完整→裂紋→束縛→炸裂；延續系列黑黃配色與口頭禪，時間線單向無倒敘。
- Platform & Delivery：Technical Specs、切片策略、字幕語系、配音規格、PG-13 尺度皆列出；Negative Instructions 與假設完整揭露。
- 風險揭露：假設冰之巨人無血肉、場景無平民，如有不同設定需再確認；雷光亮度已限制但仍需注意生成器避免過曝。

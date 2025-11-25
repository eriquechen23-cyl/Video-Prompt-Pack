## Project Inputs
- project_name: 冰鏈跳彈・神谷隼人
- series_name/arc: 夕幕廢墟清掃篇
- episode_index: 2
- slug: one-shot-chain-iceburst
- target_platform: TikTok / Shorts / Reels 直式 9:16
- duration_sec: 15 (12 幕 × 1.2s)
- style_primary: 2D 動漫冰鏈跳彈控制
- style_secondary: 暮色廢墟寫實 + 電藍能量刻紋
- worldstate_ref: 傍晚廢墟高地，橙紫天空，坡道下湧出骨刺野獸群，限定一發冰核跳彈連鎖凍結
- goal: 製作 15 秒 2D 日系動漫，神谷隼人只扣一次扳機，以冰核跳彈的連鎖冰爆清空野獸群，保留日文低語與冰殼綻裂跳彈特寫。

## _core (Brand Bible & Worldstate)
- Brand Traits:
  - 主角神谷隼人：黑色貼身機能上衣（尼龍/氨綸混紡，粗糙度 0.32，金屬度 0.08），深藍導電紋路沿肩膀至前臂（發光 1100 nits，導電紋厚度 0.6mm），貼合的戰鬥手套內藏冷卻匣（鋁鎂合金，粗糙度 0.18，金屬度 0.75）。
  - 武器「冰核充能槍」：黑底冰藍刻線，核心艙六角冰晶旋轉，外殼 PBR：粗糙度 0.22、金屬度 0.84、法線 0.35；槍口附可分裂冰晶彈匣，單發初速 32m/s，彈體直徑 2.4cm。
  - 口頭禪：開戰前低語「……まとめて凍らせてやる」、射擊後「跳弾制御……上出来だな」。
  - 身體習慣：射擊前微微前傾，呼吸調整 0.6s，鎖定時左腳壓低重心；收槍後檢視彈匣並以拇指輕觸導電紋確認冷卻。
  - 場景色調：橙紫天空（#f6a46f 漸變 #5e4ba5），廢墟混凝土路面粗糙度 0.64，破護欄鏽蝕色 #7a4b3c，風速 3.1m/s 往坡下。
- Worldstate Snapshot (前置狀態):
  - 時間：傍晚 17:40，天空帶橙紫霞，斜射主光 4300–4700K 從右上灑下；環境亮度 12000 lux。
  - 地形：高地邊緣斷裂，道路坡度 12 度向下，破護欄間隙 0.4m；碎石顆粒 2–6cm，摩擦係數 0.62。
  - 敵方：野獸群 18–22 隻，肩背骨刺錯位突出 6–12cm，肌膚粗糙度 0.55，螢黃獸瞳 620 nm 發光；平均質量 85kg，衝刺初速 7m/s。
  - 天氣：風速 3.1m/s，捲起灰塵與枯葉；空氣體積霧密度 0.08，散射係數 0.07；溫度 9°C，濕度 48%。
- Constraints (不可變更):
  - 角色與武器必須以 2D cel shading 呈現，描邊 0.8–1.2px 隨景深調整，禁止全 3D 寫實陰影；必要 3D FX 需標註 2D overpaint。
  - 15 秒 12 幕固定，時間軸 0–14.4s 以 1.2s 切分；遵守 180 度軸，鏡頭不跨越坡道主軸。
  - 血腥尺度 PG-13：野獸被凍結、碎裂僅能出現冰塵與粉碎冰晶，不可出現血液；骨刺不得斷裂噴血。
  - 彈射鏈路需保持能量感：冰鏈透明度 70%，速度 28–34m/s，跳彈角度 25–75 度內；每跳需標註牽引痕跡與折射。
- Brand Do / Don't：
  - Do：使用 35–50mm 鏡頭描繪角色，漫畫化高潮加入網點 0.6mm、速度線 28 條/秒，對比度 1.9 gamma curve，冰鏈發光以 #7fd8ff。
  - Don't：禁用霓虹飽和濾鏡、禁止魚眼與 360° 繞拍、禁止過度景深散景造成寫實感、避免長時間全畫面爆閃。

## _core Templates (embedded)
### Global Master Prompt Template
# Global Master Prompt Template

## 動漫風格特別規範
- 若 `{風格}` 含「動漫/Anime」，請將最高潮的 1–2 幕強制加入漫畫感：彩色漫畫分格或疊加，粗線稿＋網點/速度線、手繪擬聲字，並同步攝影運鏡與音效節奏，確保擊殺/爆發/轉折瞬間的衝擊力被漫畫化強調。
- 漫畫感需與 PBR/光學敘述共存：網點覆蓋厚度、描邊粗細（0.8–1.6px）、疊加的體積光或爆閃需標註散射/折射影響，避免因風格化而模糊物理細節。
- 2D 日系動漫質感：每幕保持平面分層（前景/角色/背景最多 3–4 層，僅微量平移視差 2–6px），材質以「色塊＋漸層 1–2 級」表現，禁止 3D 立體感的強陰影或照片級置換；描邊依景深調整 0.6–1.2px，角色膚質以 cel shading 的 base color＋SSS 提示（0.05–0.12 強度）呈現，避免玻璃/金屬高光造成 3D 反射。
- 反 3D 風格檢核：背景禁止重度體積光或景深散景模擬；鏡頭運動以平移/推拉/上下移為主，避免 360° 繞拍或視差過大的滑軌；如需粒子或特效，優先使用 2D sprite/手繪筆刷並標註透明度 60–85%、速度 0.4–0.9m/s，避免 3D 粒子體積堆疊。

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

### Audio Pack 指引
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

### VFX 通用 Pack
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

### 交付參數預設
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

### QA Checklist（拍前 30 秒）
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

### Scene Block Template
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

## _stylepacks (embedded)
### Style: Frost Gambler (Look / Audio / VFX)
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

### Style: Lightning Chain (Look / Audio / VFX)
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

## Technical Specs
- Aspect Ratio: 9:16 直式；解析度 1080x1920。
- FPS: 24fps；Shutter: 180° (1/48s)；Motion blur 遵循實景速度，漫畫格時降低至 120°。
- Lens kit: Act I 使用 24–35mm 拉近，Act II 使用 35–50mm，Act III 使用 50–75mm；避免 3 秒內焦段跳躍。
- Depth of Field: 主體景深 0.7–0.9m，背景輕微散焦；漫畫格使用平面化 DOF 以防寫實散景。
- Grain & Color: Filmic LUT，對比度 1.9 gamma curve，飽和度 -3%，微顆粒 10%；色彩流程：line art → flat color → shadow (soft + hard) → FX pass (冰鏈/速度線) → LUT。
- Light: 傍晚主光 4500K 斜射，輔光 6200K 電藍 rim 勾勒導電紋；AO 0.55，體積霧 0.08；漫畫化鏡頭加入網點疊加 0.6mm。
- Simulation notes: 冰晶粒徑 0.3–1.2mm，冰霧散射係數 0.07；彈射冰鏈使用 2D sprite + 3D VDB 透明度 70%，粒子上限 45k；折射 index 1.31。
- Compression strategy: GOP 24、bitrate 20Mbps；保持線稿銳利，避免社群壓縮崩潰；字幕黑描邊 2px。

## Continuity Layer
- 軸線鎖定：神谷隼人位於高地右側，野獸群從坡道下方左側湧上；鏡頭保持在隼人右後 110–140° 弧線，絕不跨軸。
- 鏡頭距離曲線：Act1 24–35mm 建立環境與緊張；Act2 35–50mm 跟進跳彈；Act3 50–75mm 壓縮凍結結果與收槍特寫。
- 光源連貫：夕陽主光固定在右上 35°，色溫 4500K；藍色導電 rim 光從左後方 6200K；冰鏈爆閃暫時增加對比至 3:1 後回落 2:1。
- 狀態時間線：
  - 0–4.8s：蓄壓 60%，冰核穩定；
  - 4.8–9.6s：蓄壓 100%，冰鏈跳彈連鎖；
  - 9.6–14.4s：冷卻下降到 40%，野獸全凍結，收槍檢查。
- Hook 策略：保持基線時間線；Hook B 版在 Platform Layer 列出，無時間倒帶。

## Master Prompt
- Duration: 15s，分為 12 幕，每幕約 1.2s，時間軸 0–14.4s 標記。
- Scene Overview: 傍晚橙紫天空壓低的廢墟高地，斷裂混凝土路面延伸至坡道，破護欄縫隙捲入風沙與枯葉。神谷隼人站在高地邊，黑色機能上衣與電藍紋路反射夕光，手持冰核充能槍；坡道下方螢黃獸瞳成片亮起。
- Worldstate Snapshot: 延續 `_core`，風速 3.1m/s，體積霧 0.08，冰核旋轉速率 1.4 rps，彈匣滿載 6 發。
- Constraint List:
  - 角色與武器 2D cel shading，3D FX 僅用於冰霧/碎冰/粒子，並加 2D 漫畫線條 overlay。
  - 彈射鏈路透明度 70%，最大彈跳 9 次，跳彈角度 25–75 度；每跳計入折射與霧散射。
  - 鏡頭不跨 180 度軸，保持 9:16；運鏡以平移/推拉/上下移，避免旋轉。
  - 體感衝擊：冰鏈觸發時 bloom 控制在 0.8 以內，避免過曝；音畫同步 120 BPM 與 0.5s 節點。
- Execution Note:
  - Camera projection：背景廢墟以 2D projection + 輕 parallax 4px，避免 3D 視差；地面裂紋與碎冰使用 3D 粒子（冰晶 0.3–1.2mm）並在上層加 2D 描邊。
  - Volume & VFX：冰霧使用 3D VDB 透明度 70%，密度 0.08；冰鏈跳彈在接觸點加入 2D speed line 28 條/秒與漫畫擬聲「カチ」「シュン」。
  - Denoise 限制：保留顆粒，禁止過度降噪；線稿與網點保持銳利；Motion blur 僅限移動物體。
- Camera Continuity:
  - 開場承接肩後 35mm 左→右平移，向下坡道延伸；中段推近到 45mm 鎖定跳彈軌跡；高潮用 55–70mm 壓縮冰鏈陣列並插入漫畫分格。
  - 光比 2:1 常態，爆閃瞬間 3:1；眼神光保持單點 2mm 反射，避免失焦。
- High-end Look:
  - 膚質：base color #c9a992，SSS 半徑 1.1mm，specular 0.16，油膜 0.03；汗珠 0.05mm highlight。
  - 布料：尼龍織紋 110 條/cm，法線強度 0.32；磨損區域 0.1mm 刻痕；導電紋 emissive 1100 nits，顏色 #7fd8ff。
  - 冰晶：折射率 1.31，表面微刮痕 0.02mm，金屬度 0，粗糙度 0.12；碎裂時粒子散射 35°。
  - 光學：景深平滑，避免真實 bokeh；色差控制 0.3px；顆粒微膠片 10%。
- Assumptions:
  - 無其他隊友或敵方槍械干擾，僅野獸群與神谷隼人對峙。
  - 日文低語不需字幕顯示，只保留音效；環境鳥鳴可做遠景點綴。
  - 平台上傳保持 15s，不需要長版剪輯；音樂原創免授權問題。

## Negative Instructions
- 禁用：真實商標/名人/宗教政治符號、過度血腥或肢解、色情暗示、魚眼變形、手持劇烈晃動、霓虹賽博濾鏡、過曝白片、超寫實景深。
- 避免：角色崩壞比例、模糊線稿、錯誤語言字幕、版權音樂、煙霧遮蔽主體；冰鏈過度亮度造成信息丟失。
- 自動檢核清單：
  - [ ] 無侵權標誌；[ ] 無血腥；[ ] 無政治宗教符號；[ ] 無錯誤字幕；[ ] 光比穩定；[ ] 9:16 保持；[ ] 彈鏈透明度 70%；[ ] 粒子數 ≤45k；[ ] 180 度規則；[ ] PG-13 尺度。

## Platform Layer
- Hook A (故事向 0–1s): 「傍晚高地，獸瞳亮起，隼人低語鎖定」；視覺：肩後低角 35mm，夕光 rim 勾出冰藍紋路。
- Hook B (衝擊向 0–1s): 彈匣冰晶旋轉特寫，字幕疊「凍らせてやる」；鏡頭快速推近槍口藍光。
- First-shot visual hook: 24mm 背後仰拍，前景破護欄模糊，遠處獸瞳呈螢黃點。
- Captions: 日文配音搭配中日雙語字幕，白字黑描邊；Hook A 用「被獸群盯上？」、Hook B 用「冰鏈跳彈 ON」。
- Thumbnail: 隼人扣扳機瞬間，冰鏈在坡道上形成六角網，夕光染橙紫。
- Hashtags: #冰鏈跳彈 #神谷隼人 #2Dアニメ #廢墟坡道 #連鎖凍結
- CTA: 結尾疊字「次回、進軍森林？」鼓勵追蹤。
- Slicing Strategy: 15s 全版；短版 6s 可截取 Act2 Beat2-3 (跳彈鋪開)；長版維持 15s，全字幕同步；Hook B 版保留同時間軸。

## Act 1: 逼近與瞄準 (0.0–4.8s)
- Planned transitions: 承接平移 → 推近 → 匹配剪接；硬切維持軸線。
- Beats:
  - Beat 1 (0.0–1.2s): 環境建立，獸瞳聚焦坡下。
  - Beat 2 (1.2–2.4s): 野獸群爬坡逼近，骨刺顫動。
  - Beat 3 (2.4–3.6s): 隼人低語「……まとめて凍らせてやる」，冰核亮度升。
  - Beat 4 (3.6–4.8s): 扣扳機，第一發冰晶彈射出分裂。

### Angle A1-1 (Beat1 0.0–1.2s)
- Camera: 24mm，肩後低角度仰拍，左→右平移 0.9m；F/5.6，快門 1/48；景深 0.8m。
- Lighting: 夕陽 4500K 斜射，地面反射 4300K；電藍 rim 6200K 從左後方；體積霧 0.08。
- Materials & Physics: 混凝土粗糙 0.64，護欄鏽蝕 0.6 金屬度；風速 3.1m/s 吹動枯葉飄 0.5m；重力 9.81m/s²，碎石靜止。2D / 3D Layering：角色與槍=2D；背景護欄=2D projection；遠景塵霧=3D VDB；前景飄葉=3D 粒子加 2D 描邊。FX Solver & Budget：塵霧粒徑 30–80µm，粒子上限 20k，VDB 分辨率 0.02。
- Emotion & Performance: 隼人前傾 5 度，目光掃向坡下，表情冷靜 20%；呼吸均勻。
- Audio & Transition: 風聲 200Hz，遠鳥鳴 -18dB；無台詞；平移結束時硬切 Beat2。

### Angle A1-2 (Beat2 1.2–2.4s)
- Camera: 28mm 中景，滑軌向前 0.7m；F/4.5，景深 0.7m；保持 180 度軸。
- Lighting: 主光 4500K，獸群上方投下斜陰影；rim 光保持 6200K；暗部對比 2:1。
- Materials & Physics: 野獸皮膚粗糙 0.55，骨刺半透明角質折射 1.52；牠們踩碎石摩擦 0.6，滑行 0.2m；螢黃眼反射 620nm。2D / 3D Layering：獸群輪廓=2D；骨刺閃光=2D overlay；地面碎石=3D 粒子；塵霧=3D VDB；速度線=2D。FX Solver & Budget：碎石粒子 25k，碰撞彈性 0.25；塵霧散射係數 0.07。
- Emotion & Performance: 野獸咆哮，胸腔起伏 1.5cm；隼人眉微挑，握槍更緊 15%。
- Audio & Transition: 咆哮 1.2kHz，骨刺磨擦 2kHz；環境音壓降 2dB 為台詞鋪陳；硬切 Beat3。

### Angle A1-3 (Beat3 2.4–3.6s)
- Camera: 35mm 半身特寫，穩定器微推 0.4m；F/4，景深 0.6m；焦點鎖在隼人眼。
- Lighting: 主光橙紫過門，輔光電藍 rim 增強 10%；網點準備疊加 0.6mm。
- Materials & Physics: 上衣法線 0.32，導電紋 emissive 1100 nits；冰核轉速 1.4 rps；呼吸起伏帶動布料拉伸 1mm。2D / 3D Layering：角色=2D；槍=2D with 3D base overpaint；背景霧=3D VDB；粒子=2D speed lines。FX Solver & Budget：冰核內流體動畫 2D；無新增粒子。
- Emotion & Performance: 隼人低聲日文「……まとめて凍らせてやる」，嘴角收緊 10%，眼神聚焦。
- Audio & Transition: 台詞 -8dB，口型同步；背景風聲降至 -20dB；微推結束匹配剪接 Beat4。

### Angle A1-4 (Beat4 3.6–4.8s)
- Camera: 40mm 中近景，前推 0.5m 至槍口；F/4.5；快門 1/48；景深 0.5m。
- Lighting: 冰核內藍光提升至 1300 nits，主光維持；rim 光 6200K；冰鏈預閃 bloom 0.6。
- Materials & Physics: 冰晶彈粗糙度 0.12，折射 1.31；彈丸初速 32m/s；分裂預備 0.2s；槍身金屬粗糙 0.22。2D / 3D Layering：槍與手=2D；彈丸=3D 粒子 with 2D overpaint；背景霧=3D VDB；速度線=2D。FX Solver & Budget：彈丸粒子 5k，拖尾透明度 75%，粒徑 0.4cm；VDB 分辨率 0.018。
- Emotion & Performance: 扣扳機手指緊繃，前傾 7 度；眼神鎖定第一隻獸。
- Audio & Transition: 扳機聲 2.5kHz，伴冰晶裂音 -6dB；鞭移過門至 Act2。

## Act 2: 冰鏈跳彈連鎖 (4.8–9.6s)
- Planned transitions: 鞭移 → 硬切 → 漫畫化分格；保持節奏 120 BPM。
- Beats:
  - Beat 5 (4.8–6.0s): 第一發分裂彈擊中前排獸。
  - Beat 6 (6.0–7.2s): 冰鏈彈射到第二、三隻獸。
  - Beat 7 (7.2–8.4s): 冰鏈形成六角網覆蓋坡道，漫畫格疊加。
  - Beat 8 (8.4–9.6s): 後排獸試圖逃跑，冰面滑倒被補凍。

### Angle A2-1 (Beat5 4.8–6.0s)
- Camera: 45mm，中景跟蹤彈丸，滑軌向前 0.8m；快門 1/56 增加清晰度。
- Lighting: 冰鏈主光藍白 5200K，夕陽維持 4500K；bloom 0.75 控制。
- Materials & Physics: 彈丸分裂成 6 枚冰刃，粗糙度 0.14；首隻獸皮膚表面形成霜層厚 1.2mm，熱交換下降至 -5°C；重力導致冰刃彈道輕微下墜 1.5cm。2D / 3D Layering：角色與獸=2D；冰刃=3D 粒子 overpaint；霜霧=3D VDB；速度線=2D。FX Solver & Budget：粒子 30k，彈道透明度 70%，折射 ripple 0.3；VDB 密度 0.08。
- Emotion & Performance: 隼人眼神微縮，肩膀穩定；獸驚恐張口，肌肉僵硬。
- Audio & Transition: 冰刃破空聲 8kHz，獸吼被冰封截止；鞭移接到 Beat6。

### Angle A2-2 (Beat6 6.0–7.2s)
- Camera: 50mm 側向平移 1m，保持眼高；景深 0.6m；對焦在彈射點。
- Lighting: 冰鏈反射夕光，藍白高光與橙紫混色；rim 光保持 6200K。
- Materials & Physics: 冰鏈跳彈角度 32→58→41 度，速度 30m/s；每次撞擊釋放冰塵粒徑 0.5mm；獸毛被霜覆蓋粗糙度降至 0.2。2D / 3D Layering：獸=2D；冰鏈=3D sprite+VDB；地面碎石=3D 粒子；漫畫速度線=2D。FX Solver & Budget：冰塵粒子 18k，彈跳黏滯係數 0.3，碰撞阻尼 0.2；VDB 透明度 70%。
- Emotion & Performance: 第二隻獸被鎖足，第三隻獸抬頭欲逃；隼人保持鎖定姿勢。
- Audio & Transition: 連鎖冰裂聲 1–4kHz 漸強；環境音壓縮 2dB；硬切 Beat7。

### Angle A2-3 (Beat7 7.2–8.4s)
- Camera: 55mm 壓縮坡道，中央構圖；插入漫畫分格（對角 2 分格）0.4s；景深 0.7m。
- Lighting: 漫畫格使用平面光，描邊 1.1px；主畫面保持 4500K 主光 + 6200K rim；冰鏈 bloom 0.8。
- Materials & Physics: 冰鏈在坡面形成六角網，厚度 1.5cm，表面粗糙 0.18；地面摩擦降至 0.2 導致獸滑倒；折射形成光暈半徑 0.4m。2D / 3D Layering：主畫面角色/獸=2D；冰網=3D VDB + 2D overpaint；分格網點=2D；碎冰=3D 粒子。FX Solver & Budget：冰網 VDB 0.015；粒子 20k；漫畫格速度線 28 條/秒。
- Emotion & Performance: 隼人表情淡定，嘴角微抬 5%；獸動作定格在滑倒姿勢。
- Audio & Transition: 漫畫格疊紙張摩擦 600Hz；冰網共鳴 -6dB；硬切 Beat8。

### Angle A2-4 (Beat8 8.4–9.6s)
- Camera: 50mm 俯拍 20°，平移 0.6m；F/4.8；景深 0.6m。
- Lighting: 夕光與冰霧反射形成紫藍混光；rim 光加強 10% 強調凍結雕像。
- Materials & Physics: 後排獸嘗試奔跑但因冰面摩擦 0.2 滑倒，動能轉為滑行 1.1m；追加冰鏈補鎖透明度 70%，冰層厚度增加到 2.2cm。2D / 3D Layering：獸=2D；冰層=3D VDB + 2D 描邊；霜霧=3D；漫畫速度線=2D。FX Solver & Budget：粒子 22k；VDB 0.018；碰撞阻尼 0.25。
- Emotion & Performance: 野獸表情僵硬，舌頭被冰封；隼人肩膀放鬆。
- Audio & Transition: 滑倒聲 500Hz，冰面摩擦 1.5kHz；尾端硬切 Act3。

## Act 3: 收束與檢查 (9.6–14.4s)
- Planned transitions: 硬切 → 平移 → 收近；最後淡入黑。
- Beats:
  - Beat 9 (9.6–10.8s): 坡道全凍，冰霧瀰漫。
  - Beat 10 (10.8–12.0s): 隼人俯瞰冰雕獸群，槍身降溫。
  - Beat 11 (12.0–13.2s): 收槍，導電紋熄滅，台詞「跳弾制御……上出来だな」。
  - Beat 12 (13.2–14.4s): 拉遠展現坡道魔法陣般冰鏈，風聲與鳥鳴恢復。

### Angle A3-1 (Beat9 9.6–10.8s)
- Camera: 60mm 壓縮全景，平移 0.7m；F/5；景深 0.8m。
- Lighting: 主光 4500K 低角度拉長陰影；冰面反光偏藍 5200K；霧密度 0.08。
- Materials & Physics: 冰層厚 2.2cm，表面霜花 0.4mm；獸被定格，骨刺內含冰晶折射；冰霧粒徑 0.6µm。2D / 3D Layering：角色=2D；冰面=3D VDB + 2D 描邊；霧=3D；速度線關閉。FX Solver & Budget：粒子 18k，VDB 0.016。
- Emotion & Performance: 隼人站穩，微微抬槍檢視成果，表情冷靜。
- Audio & Transition: 冰裂餘音 -10dB，風聲回升至 -12dB；平移結束硬切 Beat10。

### Angle A3-2 (Beat10 10.8–12.0s)
- Camera: 65mm 中景過肩，對準冰雕獸群；F/4.5；景深 0.7m。
- Lighting: rim 光 6200K 勾勒肩線；主光維持；冰面反射輔助填光。
- Materials & Physics: 槍身開始降溫，導電紋亮度降至 400 nits；冰面微霧蒸氣 0.03；冰雕表層粗糙 0.18。2D / 3D Layering：隼人=2D；槍=2D with 3D base；冰雕=3D VDB + 2D line；霧=3D。FX Solver & Budget：霧粒子 15k；無新增粒子。
- Emotion & Performance: 隼人深呼吸，視線掃過每個凍結姿勢，眉頭微挑表示確認。
- Audio & Transition: 呼吸聲 -12dB，冰面滴水細聲 2kHz；平滑推近匹配剪接 Beat11。

### Angle A3-3 (Beat11 12.0–13.2s)
- Camera: 70mm 近景胸像，微推 0.3m；F/4；景深 0.5m。
- Lighting: 主光柔化 2.2:1；rim 光減 5%；漫畫網點疊加 0.6mm。
- Materials & Physics: 導電紋熄滅至 150 nits；槍身金屬冷凝 0.02mm 水珠；膚質 SSS 1.1mm。2D / 3D Layering：角色=2D；槍=2D；背景=2D projection；霧=3D。FX Solver & Budget：水珠粒子 5k；無 VDB 變更。
- Emotion & Performance: 隼人低聲「跳弾制御……上出来だな」，嘴角放鬆；肩膀下降。
- Audio & Transition: 台詞 -8dB，附帶輕微霜裂聲；尾端硬切 Beat12。

### Angle A3-4 (Beat12 13.2–14.4s)
- Camera: 35mm 拉遠至 24mm，俯視 25°，穩定器後退 1.5m；景深 0.9m。
- Lighting: 夕陽最後一抹光落在冰藍刻紋，環境轉暗 5%；rim 光淡出。
- Materials & Physics: 冰鏈網呈魔法陣圖樣，透明度 70%，折射形成六角虹彩；風速 3.1m/s 吹過冰面，碎冰顫動 1–2mm；冰霧逐漸散去至密度 0.03。2D / 3D Layering：冰網=3D VDB + 2D 描邊；角色=2D；環境=2D projection；飄塵=3D 粒子。FX Solver & Budget：粒子 12k；VDB 0.015。
- Emotion & Performance: 隼人背影站定，槍垂於身側，放鬆；畫面靜謐。
- Audio & Transition: 風聲與遠方鳥鳴恢復，音樂淡出；結尾 0.3s 黑場。

## AGENT Self-Check
- 結構完整度：已含 `_core`、`_stylepacks` 模板全文、Technical Specs、Master Prompt、Continuity Layer、Acts/Beats/Angles、Platform Layer、Negative Instructions、Assumptions、Self-Check，時間軸 12 幕 × 1.2s 明確。
- 敘事一致性：三 Act 從瞄準→跳彈→收束，軸線固定坡道右後 110–140°，台詞與動作連貫，無世界觀矛盾。
- 視聽細節：每 Angle 填入 Camera/Lighting/Materials & Physics/Emotion & Performance/Audio & Transition，含焦段、光色、聲音頻段與轉場。
- 風格準確性：主風格 2D 動漫冰鏈，嵌入 Frost Gambler + Lightning Chain stylepacks；高潮 Beat7 漫畫格遵守 Do/Don't；未混用衝突風格。
- 格式精準度：路徑 `projects/冰鏈跳彈・神谷隼人/2025-11-25_ep2-one-shot-chain-iceburst/prompt.md`，標題與縮排符合指引。
- 2D Anime Consistency vs 3D FX：角色與槍全程 2D；3D 僅用於冰霧/冰粒/碎石/冰網 VDB，皆加 2D 描邊；運鏡避免 360°；景深平面化，無寫實散景。
- 物理質感到位：重力、摩擦、折射、粒徑、冰層厚度、PBR 粗糙度/金屬度、SSS、光比均在各角落標註；冰鏈速度與角度量化。
- 量化標記度：時間、焦段、光溫、粒徑、速度、透明度、密度等皆有數值；T0 分段按 1.2s 節點列出。
- 可交付性：Platform Layer 有 Hook/Thumbnail/Hashtag/CTA/Slicing；Negative Instructions 列出禁用；自檢勾選點齊全；無 meta 檔案。
- 自動檢核：3D FX 為輔助並提供 2D 化方案（描邊、透明度、bloom 限制）；體積霧與景深已控制；爆閃不超 0.8 bloom；粒子未超 45k。

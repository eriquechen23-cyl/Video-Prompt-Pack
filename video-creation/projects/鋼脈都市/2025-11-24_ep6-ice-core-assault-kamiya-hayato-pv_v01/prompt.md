# 《鋼脈都市｜冰核衝線・神谷隼人 個人PV》— Master Prompt（15s｜12 幕｜2D 日系動漫風格・日文配音）

專案欄位：
- project_name：鋼脈都市
- series_name/arc：鋼脈都市・冰核衝線篇
- episode_index：6
- slug：ice-core-assault-kamiya-hayato-pv_v01
- target_platform：短影音（9:16，YouTube Shorts / TikTok）
- duration_sec：15（依專案規範預設 15s，12 幕 × 1.25s）
- style_primary：Light Glyph Anime Look（2D 日系線條＋霓虹 HUD 冰陣）
- style_secondary：Storm Boss Lock-On Look（電弧雷雨戰鬥對比，夜景冷藍高反差）
- worldstate_ref：鋼脈都市夜間高架鐵道與廢區交界，天橋 16m 高、橋面濕度 0.3mm，周遭廢車堆與霓虹反射混光；神谷隼人在欄杆邊啟動冰核陣式，俯衝獵殺黑霧鋼筋怪群
- goal：製作 15 秒 12 幕 2D 日系動漫風格分鏡，呈現神谷隼人以冰核充能槍鎖定、俯衝、全功率轟擊怪物群的過程，含日文配音（低沉青年）、完整物理與 PBR 細節
- date_tz_utc8：2025-11-24（UTC+8）
- target_platform_hook：Hook A 故事向（橋頂鎖定→冰核成槍）、Hook B 衝擊向（全功率冰束掃射廢區怪群）
- platform_slice_strategy：長版完整 15s；短版優先截取 0–2.5s（冰核陣式成槍）、12–15s（全功率冰束與殘光收束）並附對應字幕行

來源劇本：使用者提供《冰核衝線・神谷隼人 個人PV》敘述與 15 秒｜12 幕影片提示詞

## 一句話題材
深夜鋼脈都市的濕冷高架上，神谷隼人以電藍冰核陣式將掌心凝結成槍，俯衝掃蕩廢區黑霧鋼筋怪，最後以全功率冰束鎖鏈貫穿並凍結整片戰場。

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

### Audio Pack Template（`_core/audio_pack.md`）
```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
人聲：避免加入一般人聲（對話、歌唱等），僅可使用詠唱或咒語式聲線作為氛圍點綴
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```

### VFX Pack Template（`_core/vfx_pack.md`）
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

### Delivery Presets（`_core/delivery_presets.md`）
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

### Style: Light Glyph Anime Look（`_stylepacks/light_glyph_anime/look.yml`）
```
name: Light Glyph Anime Look
line_enhancement: crisp_vector_edge
noise_reduction: cel_plate_clean
saturation: dual_tone_split
contrast_profile: luminous_soft_mid
color_palette:
  primaries: [fog_blue, slate_gray, midnight_indigo]
  accents: [auric_gold, mint_glow]
  skin_tone: warm_amber
glow_layers:
  base_fill: cool_diffused
  rim_accents: HUD_edge_trace
  spell_core: emissive_gold_script
ui_overlay: parallax_glass_hud
bloom_intensity: 0.32
shadow_treatment: soft_multipass_cel
motion_blur_shutter: 165
texture_pass: layered_papergrain_subtle
notes:
  - 2D 線條需保持乾淨俐落，適度加粗邊緣讓 HUD 光軌不吞線。
  - 城市環境以冷灰與霧藍主調，透過金色與薄荷藍魔法光強化高對比。
  - HUD 與程式碼浮層採半透明玻璃質感，確保角色臉部仍清晰可見。
  - 施法時增加眼睛與衣內銀線的同步脈動光，營造「發光程式」感。
```

### Style: Light Glyph Anime VFX（`_stylepacks/light_glyph_anime/vfx.yml`）
```
name: Light Glyph Anime VFX
layer_stack:
  - background_mist_scroll
  - hud_symbol_plane
  - spell_vector_trail
  - glow_dust_overlay
spell_trail:
  color_mix: [auric_gold, mint_glow]
  taper: 0.42
  flicker_speed: 0.28
hud_widgets:
  panel_opacity: 0.65
  glyph_refresh_rate: 14
  debug_log_spacing: 18
error_feedback:
  color: crimson_error
  glitch_amount: 0.36
  frame_freeze: 0.08
particle_settings:
  glyph_sparks: 0.54
  light_dust: 0.32
  cat_starflare: 0.41
disintegration_fx:
  hexshield_tile_break: 0.57
  light_code_dissolve: 0.49
notes:
  - HUD 浮層需與角色動作略帶遲滯，營造空中投影被拉扯的感覺。
  - 能量彎射路徑依角色揮手軌跡生成弧形光帶，符文沿光帶流動。
  - 蜂巢六角盾破碎後應立即重排，碎片化為細小光粒回收至掌心。
  - 米漿星火充能時，尾端粒子需向胸口光晶形成柔和渦流。
```

### Style: Light Glyph Anime Audio（`_stylepacks/light_glyph_anime/audio.yml`）
```
name: Light Glyph Anime Audio
time_signature: 4/4
bpm_range: [92, 108]
ambient_beds:
  - soft_city_air_hum
  - crystalline_aether_pad
rhythmic_layers:
  percussive_clicks: holo_keyboard_taps
  sub_pulse: low_orbital_throb
ui_fx:
  glyph_expand: airy_chime_hi
  compile_ping: glassy_beep_mid
  error_flag: clipped_square_red
spell_sweeteners:
  curve_bolt_release: arc_bow_sheen
  hexshield_reform: hex_shingle_swirl
  cat_starflare: purr_riser_glow
mix_notes:
  - 對話維持 -6 dB 峰值，HUD 音效壓在 -12 dB 以下避免干擾詠唱。
  - 程式碼浮現時加入細緻鍵擊聲，與主角手指敲擊空氣同步。
  - 米漿心電音色偏低沉慵懶，情緒激動時可疊加高頻毛髮靜電。
  - 戰鬥高潮加強 4kHz 以上空氣感，讓光線爆閃更具穿透力。
```

### Style: Storm Boss Lock-On Look（`_stylepacks/storm_boss_lockon/look.yml`）
```
name: Storm Boss Lock-On Look
lut: Tempest-Rain
saturation_adjust: -0.02
contrast: high_dynamic
highlights: electric_blue
shadows: deep_charcoal
texture: rain_slick_armor
chromatic_aberration: restrained_blue_fringe
lens_distortion: micro_barrel
notes:
  - 夜雨環境保留冷藍閃電反光，膚色維持 58 IRE
  - 地面水漬需加入鏡面高光與波紋疊層
  - HUD 螢光元素亮度限制在 120 nits，避免壓過雷弓電弧
```

### Style: Storm Boss Lock-On VFX（`_stylepacks/storm_boss_lockon/vfx.yml`）
```
name: Storm Boss Lock-On VFX
niagara_presets:
  - electromagnetic_bowstring
  - shield_shatter_ring
  - serpent_ground_arcs
unity_vfx_graph:
  - StormBow.DrawPulse.vfx
  - BossShield.Fragment.vfx
  - CoreImplode.Cascade.vfx
houdini_flipbooks:
  - rain_sheet_hit_sparks
  - mech_plating_shatter
  - plasma_core_bloom
shader_settings:
  bolt_core_thickness: 0.38
  shield_crystalize_speed: 0.55
  arrow_trail_decay: 0.42
  hud_glow_intensity: 0.28
sdf_settings:
  boss_surface_wrap: 0.32
  weakpoint_lock_radius: 0.18
  debris_spawn_delay: 0.2
bloom_control:
  idle: 0.16
  trigger_peak: 0.88
  cooldown: 0.35
audio_sync:
  bow_draw_resonance: align_to_heartbeat
  release_flash: accent_thunderstring
  core_blast: sync_mech_implode
notes:
  - 拉弦期間 HUD 粒子需遵循電弧張力曲線，避免穿幀
  - 護盾破裂採用多層玻璃碎片與能量薄膜交錯，1 frame 延遲切換發光貼圖
  - 核心爆閃後地面殘留蛇型電光需沿裂縫動態遮罩延長 3 frame
```

### Style: Storm Boss Lock-On Audio（`_stylepacks/storm_boss_lockon/audio.yml`）
```
name: Storm Boss Lock-On Audio
core_layers:
  - torrential_rain_bed
  - bowed_metal_tension
  - subpulse_heartbeat
  - arc_flash_whoosh
peak_events:
  - timestamp: lock_confirm
    sfx: hud_pulse_ping
    level_db: -8
    stereo_width: 90
  - timestamp: arrow_release
    sfx: thunderstring_snap
    level_db: -3
    stereo_width: 140
  - timestamp: core_detonation
    sfx: mech_beast_implode
    level_db: -2
    stereo_width: 160
low_freq_management:
  sub_ceiling_db: -5
  lfe_emphasis: 48Hz
sidechain:
  trigger_bus: impact_bus
  target: subpulse_heartbeat
  reduction_db: 2.5
notes:
  - 雨聲需隨鏡頭切換維持連續，避免跳變
  - 雷弓拉弦時加入靜電細沙聲作粒子提示
  - 爆炸後殘留電弧使用反向混響緩慢衰減 1.2s
```
## Technical Specs
- 畫幅：9:16 直式｜解析度 1080×1920｜幀率 24fps（拍 48fps 輸出 24 以保留冰霧顆粒與殘影）
- 快門角：橋頂鎖定段 180°；俯衝段 210° 拉出速度線；全功率冰束段 170° 保持輪廓清晰
- 鏡頭組：Act I 24–28mm 建立高度與霓虹；Act II 32–45mm 追擊滑移；Act III 55–75mm 壓縮光束與殘骸；維持 180° 軸線右側視角
- 景深：Act I 淺景深 1.0m，Act II 中景深 1.4m，Act III 2.1m 壓縮；焦外加入 0.3% 冷色散景
- 顆粒：Filmic grain 11%；色彩流程：Log → filmic LUT（Glacial-Edge）→ final contrast
- 光學畸變：微樽形 0.7%，Chromatic aberration 藍邊限制 0.5px
- 切片輸出策略：0–2.5s Hook A 冰核成槍；12–15s Hook B 冰束貫穿；字幕行同步
- 配音：日文青年低沉嗓，收口帶氣音；錄製 -16 LUFS，與 SFX 分離輸出

## Master Prompt（內含 Brand Layer / Worldstate Snapshot / Constraint List / Execution Note）
- Brand Layer：鋼脈都市系列口頭禪「凍結路徑，鎖定標的」，色票（主體黑藍 #0a1624、冰脈電藍 #22e0ff、警示紅 #ff2f40），服裝材質（啞光 techwear 粗糙度0.34、手套合成皮粗糙度0.42、鋼質護甲金屬度0.78）。
- Worldstate Snapshot：夜間 23:50，鋼脈都市高架廢鐵道 16m 高，橋面 0.3mm 水膜反射霓虹（色溫 3600K–4100K）；空氣濕度 82%，風速 6.5m/s 自東向西帶鹽霧；下方廢車堆與扭曲鋼筋散發黑霧，霧密度 0.42 kg/m³。
- Constraint List：
  1. 鏡頭軸線固定在隼人右後 100–120°，俯衝時不可越軸；保持遠景霓虹水平線不傾斜超過 2°。
  2. 冰核紋路亮度上限 230 nits，保持眼神光 55–60 IRE；黑霧與綠光限制在 80–100 nits 避免過曝。
  3. 怪物以鋼筋＋黑霧觸手表現，PG-13，以霧散與冰裂方式解決；不得出現血液或擬真內臟。
  4. PBR：橋面柏油粗糙度0.56、金屬度0.08、濕膜折射 1.33；護欄鋼材粗糙度0.36、金屬度0.82；冰晶粗糙度0.08、折射率1.31、微刮痕法線 1K；服裝縫線置換 0.45mm。
- Execution Note：遠景霓虹與橋體採 camera projection 固定；黑霧用 VDB 192³，粒徑 20–35μm，吸收係數 0.12；冰核射擊採 Flip 粒子 140k 轉 spritesheet，冰束體積光使用 0.9 可見度並限制 Bloom 0.62；音畫同步使用 Storm Boss Lock-On Audio peak_events 觸發拉弦、射擊與核心爆閃。
- Camera Continuity：延續前集右後軸線，本集開場 24mm 低角鎖定→Act II 35–40mm 俯衝跟拍→Act III 60–75mm 近身壓縮冰束，主光保持右上 30° 霓虹混光與橋下反彈冷光。

## Platform Layer
- Hook A（故事向）：0–2.5s 隼人在橋邊抬手、冰核陣式旋轉成槍，字幕「標的、ロックした。」；縮圖：電藍六角陣與掌心冰晶聚合特寫。
- Hook B（迷因/衝擊）：12–15s 全功率冰束掃過廢區，怪物群瞬間凍結，字幕「これで、終わりだ。」；縮圖：冰束劃出的冰鎖軌跡與爆裂。
- Caption 建議：日中混用「冰核衝線｜神谷隼人｜霧藍俯衝」；Hashtag：#鋼脈都市 #冰核衝線 #神谷隼人
- CTA：結尾 0.5s 疊字「ターゲットは？」；字幕語言：繁中＋日文，無英文 UI；VO 全程日文配音。
- 切片策略：保留冰晶破裂與金屬擦動聲，音樂降到 -16 LUFS；VO 軌道獨立輸出方便字幕對齊。

## Negative Instructions（含自動檢核清單）
- 禁用：真實商標、政治/宗教符號、現實名人肖像、血腥破裂、過曝魚眼、廉價閃爍濾鏡。
- 語言環境：全程繁中＋日文擬聲，不得出現英文 UI 或看得懂的標語。
- 侵權檢核：角色造型與怪物為原創，無使用已知 IP；字幕大小 8% 畫幅以下。
- 尺度：PG-13，以冰裂與霧解離方式呈現受擊，不出現肉塊與紅液。
- 自動檢核：
  1. 檢查畫面可讀字樣：無。
  2. 檢查商標與路牌：全部模糊或替換為抽象霓虹條。
  3. 檢查宗教政治符號：無。
  4. 檢查風格衝突：Light Glyph Anime（主）＋ Storm Boss Lock-On（次）均 ON，未混用其他 LUT。
  5. 檢查字幕語系：僅繁中+日文擬聲。
  6. 檢查配音語系：VO 僅日文男聲，無英文旁白或 UI 口播。

## Assumptions
1. 怪物由扭曲鋼筋與黑霧構成、無器官與臉部，受擊以霧散＋冰裂呈現（理由：維持 PG-13 並符合原文「扭曲鋼筋與黑霧」）。
2. 高架路段已封鎖，無平民或車流，方便俯衝與掃射（理由：原文描述廢棄鐵道與廢區）。
3. 隼人已事先習得冰核陣式，無需解說，直接進入鎖定與射擊（理由：原文聚焦動作與台詞）。

## Act / Beat / Angle（12 幕 × 約1.25s，含 micro-actions 與物理/光學細節）

### Act I（0.0–5.0s） 橋頂鎖定｜基調：冷緊→凝結｜節奏域：慢入0.8→穩定1.5s｜美術要點：霧藍霓虹、濕冷橋面、冰核陣式亮起

#### Beat 1（0.0–1.2s）
重點：建立鋼脈都市夜間高架，濕冷金屬與霓虹交錯，黑霧在下方蠕動。
Blocking：由橋面水膜低角推向護欄，遠處鐵橋骨架與霓虹光帶，隼人身影模糊站在右側。
Camera：滑軌前推，24mm 眼高，對焦前景水滴→中景護欄→遠景霓虹；快門角180。
Lighting：上方路燈 3600K 冷白線條；遠霓虹 4100K 混合；霧氣折射藍光；對比 1.9：1。
Materials & Physics：柏油粗糙度0.56、金屬度0.08；0.3mm 水膜折射形成冷白亮點；鹽霧粒徑 20–35μm 受 6.5m/s 風自東推向西；遠處黑霧密度 0.42 kg/m³。
Emotion & Performance：無明顯表情，僅以剪影營造壓迫感。
Audio & Transition：環境風＋遠鐵橋嗡鳴 -10 dB；黑霧蠢動低頻 -12 dB；硬切入 Beat2。
Angle：前中後層次，橋面線條引導視線至隼人剪影。

#### Beat 2（1.2–2.5s）
重點：隼人站在護欄邊，右手抬起，掌心開始浮出六角冰核陣式。
Blocking：半身側背，右肩朝鏡頭，左腳踩橋面、右腳踏欄杆邊緣保持平衡。
Camera：28mm 微低角 15°，膝高；單點對焦掌心；快門角180。
Lighting：路燈勾邊，冰核陣自發光 4800K 電藍；霓虹反射作補光。
Materials & Physics：手套合成皮粗糙度0.42；掌心冰晶折射率1.31，微霜顆粒粒徑 40μm；欄杆鋼材摩擦係數0.58，水膜使靜摩擦降至0.5，隼人小腿肌肉微抖補償 0.3g。
Emotion & Performance：視線向前俯瞰，下顎緊鎖；肌肉緊繃。
Audio & Transition：冰核陣旋轉音 -8 dB，HUD 嗶聲 -14 dB；微光拉焦過渡。
Angle：三分構圖，掌心位於上右 1/3，前景欄杆模糊。

#### Beat 3（2.5–3.8s）
重點：電藍紋路沿鎖骨與手臂亮起，冰核碎片聚合成槍形。
Blocking：隼人右臂前伸，手指微張，掌心陣式旋轉，冰晶碎片由肩至前臂沿線排列。
Camera：35mm 側後 110°，胸高；追焦手臂；快門角190。
Lighting：冰核自發光 22e0ff 色，亮度 220 nits；路燈冷白作 rim light；霓虹 4100K 填光。
Materials & Physics：冰晶粗糙度0.08，邊緣有 0.4mm 微刮痕；電藍紋路在衣料置換 0.45mm 內發光；粒子以 0.3s 延遲鎖定骨架，慣性沿手臂震動 18Hz。
Emotion & Performance：深吸氣，肩膀穩定；眼神微瞇。
Audio & Transition：冰晶聚合叮鳴 -9 dB；subpulse_frost_core 與心跳同步；硬切至 Beat4。
Angle：前中後構圖，手臂佔中景，遠方霓虹做背景線。

#### Beat 4（3.8–5.0s）
重點：冰核充能槍成形，槍身貼著前臂，光脈動如心跳；隼人低聲報上名字與鎖定。
Blocking：隼人微抬槍口，左手穩住槍體側面，頭微低，嘴型吐出「神谷隼人」「標的、ロックした。」
Camera：35mm 半身側拍，視線與槍平行；呼吸拉焦臉→槍口；快門角185。
Lighting：槍身電藍能量管線亮度 210 nits；眼神光 60 IRE；橋下霧氣反光作 fill。
Materials & Physics：槍身金屬粗糙度0.35、金屬度0.83；能量管線玻璃折射 1.5，內有 1.8mm 冰核流動；手套摩擦系數0.72，保持槍體穩定。
Emotion & Performance：聲線低沉，語速 0.8s；眉頭下壓，眼神鎖定下方。
Audio & Transition：VO -6 dB；冰脈脈動低頻 -12 dB；以 VO 尾音作遮擋剪接至 Act II。
Angle：中央構圖，槍與眼睛形成對角線，背景霓虹模糊。

### Act II（5.0–10.0s） 俯衝掃射｜基調：高速→碎冰衝擊｜節奏域：1.6→2.0s｜美術要點：電藍速度線、冰藍彈丸、黑霧與鋼筋碎裂

#### Beat 5（5.0–6.2s）
重點：隼人腳尖點護欄，一躍而下，身後拖出電藍殘影。
Blocking：起跳瞬間，右腳蹬欄杆、左腳收起；身體前傾 30°，槍沿前臂指向下方。
Camera：32mm 後撤＋俯視，跟隨隼人下落軌跡；快門角210，創造速度線。
Lighting：路燈與霓虹在水膜上拉成冷色光帶；冰紋自發光補 rim；霧氣散射 0.45，形成光束。
Materials & Physics：重力 9.8m/s²，自由落體 1.2s；風壓 6.5m/s 使衣料向後拉，布料粗糙度0.34；冰紋粒子 120k 以 0.6g 慣性延遲。
Emotion & Performance：口型微張呼氣；眼神向下鎖定。
Audio & Transition：衣料破風聲 -9 dB；冰脈嗡鳴同步加強；匹配剪接至 Beat6。
Angle：隼人對角線貫穿畫面，速度線放射。

#### Beat 6（6.2–7.4s）
重點：第一發冰藍彈丸貫穿黑霧怪，瞬間凍結成晶體。
Blocking：半空側身，右臂伸直射擊，下方怪物被擊中停滯。
Camera：40mm 追隨，從上往下 30° 角度；單點對焦彈丸擊中點；快門角200。
Lighting：槍口冰晶閃光 0.1s，亮度 230 nits；黑霧被照亮後散射藍光；地面水漬反射。
Materials & Physics：冰彈直徑 4cm，金屬管線導出 1.5kN 推力；撞擊後 VDB 冰霧擴散 0.25s，晶體粗糙度0.09；鋼筋碎片金屬度0.78 飛散 3m。
Emotion & Performance：表情冷靜，手腕穩定無抖動。
Audio & Transition：彈道破風聲 -7 dB；凍結晶響 -6 dB；用碎冰聲遮擋切至 Beat7。
Angle：低空俯視，彈道與霓虹形成交叉線。

#### Beat 7（7.4–8.6s）
重點：隼人在半空鎖定其他怪物，換肩連射，冰核彈在怪群間引爆碎冰波。
Blocking：身體在空中滾身 40°，左肩向前，右手連扣扳機三次。
Camera：38mm 側向跟拍，圍繞 35° 弧線平移；快門角205。
Lighting：每發彈丸產生 0.2s 冰藍爆光；霧中帶綠眼的怪被冷光照亮；橋下反光作 fill。
Materials & Physics：連射間隔 0.18s；碎冰波厚度 6cm，向外擴散速度 22m/s；地面裂冰粗糙度0.22；黑霧吸收係數 0.12 使邊緣發藍光。
Emotion & Performance：下顎繃緊，呼吸短促，瞄準連續。
Audio & Transition：連射聲節奏 0.18s，與 card_snap_percussion 同步；玻璃碎裂層次 -5 dB；動態遮擋切至 Beat8。
Angle：三分構圖，彈道放射填滿畫面。

#### Beat 8（8.6–10.0s）
重點：隼人落地滑步，冰紋拖出長尾，怪物嘗試以黑霧觸手反撲。
Blocking：右腳先著地，膝蓋彎曲吸收衝擊 1.1g，身體向後滑 1.2m；左手撐槍平衡。
Camera：45mm 低角平移，跟隨滑步方向；快門角195。
Lighting：地面濺起冰晶反射路燈；黑霧觸手以 0.6s 從右側衝出，帶病態綠光 3800K；藍光 rim 勾出輪廓。
Materials & Physics：鞋底摩擦係數0.62 在水膜上滑行，因 0.3mm 水膜有效摩擦降至0.54；冰晶尾長 3.5m，顆粒 90μm；觸手質量 8kg，慣性推動碎冰向後散。
Emotion & Performance：嘴角冷硬，眼神向左下掃描威脅。
Audio & Transition：鞋底摩擦尖嘯 -8 dB；霧觸手轟鳴 -10 dB；遮擋切至 Act III。
Angle：前景冰晶尾線帶出動勢，背景怪影模糊。

### Act III（10.0–15.0s） 全功率終結｜基調：壓縮→爆閃｜節奏域：2.2→2.5s｜美術要點：冰束鎖鏈、體積爆光、廢區凍結

#### Beat 9（10.0–11.2s）
重點：隼人踏入裂冰中心，左手貼槍側，黑藍紋路全亮，準備全功率充能。
Blocking：站姿開肩，雙腳踩在裂冰上，膝微彎；左手按在能量管線上，吸氣。
Camera：55mm 半身側後 100°，穩定器微推；快門角180。
Lighting：冰紋全亮 230 nits；路燈與霓虹形成背光；霧氣 0.42 kg/m³ 使體積光呈淡藍。
Materials & Physics：裂冰厚度 4cm、粗糙度0.22；能量管線內液體流速 2.5m/s，壓力上升至 1.4kPa；布料因熱量交換出現 0.2mm 霜霧。
Emotion & Performance：深吸氣，眼中藍光閃；嘴型吐出「フルチャージ——」。
Audio & Transition：VO -6 dB；subpulse_frost_core 上升；以聲音做延遲拉焦進 Beat10。
Angle：中景三分構圖，槍與臉形成對角線。

#### Beat 10（11.2–12.4s）
重點：槍口冰晶收縮、脈動，體積光在槍口聚集；黑霧怪開始集體衝向中心。
Blocking：隼人微蹲，槍口下壓再抬；怪物從左右同時撲近，觸手攀爬裂冰。
Camera：60mm 前側 80°，拉近 0.4m；快門角175 保持清晰。
Lighting：槍口亮度峰值 240 nits；體積光圓錐半徑 0.6m；黑霧遮光形成剪影；地面冰晶反射。
Materials & Physics：冰晶收縮頻率 6Hz，表面出現 0.1mm 裂紋；觸手摩擦係數0.48 在冰面上滑行；霧粒在體積光下折射出藍白光斑。
Emotion & Performance：下顎緊咬，視線前方；呼吸短促。
Audio & Transition：冰晶收縮脈動聲 -7 dB；黑霧低吼 -11 dB；匹配剪接至 Beat11。
Angle：壓縮構圖，槍口居中，怪物在左右側翼。

#### Beat 11（12.4–13.6s）
重點：隼人扣下扳機，一道巨大冰藍光束轟出，沿地面劃出冰鎖軌跡。
Blocking：右手扣扳機，槍口反衝 0.3m；光束掃過地面呈 S 形，鎖鏈冰紋一路凍結怪物。
Camera：65mm 低角跟隨光束，向前滑行 2m；快門角170。
Lighting：光束亮度 260 nits，體積光穿透霧；冰鎖發出 4300K 冷光；碎片反射霓虹。
Materials & Physics：光束能量推力 2.1kN，反作用力使隼人後移 0.4m；冰鎖厚 7cm，折射率1.31，表面粗糙度0.12；怪物霧化並在 0.5s 內凍結。
Emotion & Performance：目光專注，肩膀穩定抵抗反衝；口型吐出「これで、終わりだ。」
Audio & Transition：主光束低頻 -4 dB，冰鎖裂紋聲 -6 dB；匹配剪接到 Beat12。
Angle：前景光束帶動視線，背景怪物凍結成晶。

#### Beat 12（13.6–15.0s）
重點：冰束在廢區中心炸裂，多層冰晶衝擊波掃過，黑霧被撕碎；光慢慢收斂，隼人扛槍離開。
Blocking：光束末端爆閃，衝擊波三層向外推；怪物化為碎裂冰晶，定格；隼人單手把槍扛回肩上，轉身走向鋼梁深處。
Camera：75mm 追隨，先定格爆閃再慢速推近背影；快門角172。
Lighting：爆閃峰值 280 nits 後衰減至 90 nits；碎冰反光填滿畫面；橋下霧光包裹背影。
Materials & Physics：冰晶碎片粒徑 1–5mm，1.6s 內受重力落下；鋼筋殘骸粗糙度0.6，覆蓋霜層厚 1mm；衣料微動受風 0.4m/s，紋路漸暗。
Emotion & Performance：眼底最後一點藍光熄滅，步伐平穩；低聲自語「次のターゲットは……どこだ？」
Audio & Transition：爆閃低頻轟鳴 -5 dB；碎冰落地鈴音 -9 dB；VO -7 dB；以冰霧淡出收尾。
Angle：背影居中，冰晶碎片形成前景散景，畫面在黑藍殘光中淡出。

## 音效 / 音樂 / 配音規劃（依 `_core/audio_pack.md` 展開）
- 音樂：Hybrid electronic + icy percussion，80 BPM，重低頻 pulse 配合冰脈脈動；副層加入 glassy pluck；高潮段 12.4–15s 疊加合成銅管。
- 環境：橋上風床、霓虹電流嗡鳴、遠處廢車金屬碰撞；俯衝時風噪加至 -8 dB。
- 人聲：日文低沉青年，短句，帶氣音；VO 分離錄製，保持 -16 LUFS。
- 音效：冰核聚合、水晶脈動、彈道破風、凍結爆裂、黑霧低吼、碎冰落地；HUD 嗶聲與鎖定提示。
- 混音：動態範圍 14 LU；主光束段 sidechain 音樂降低 4 dB 讓冰束突出；立體聲寬度保持 110–140。
- 定位：彈道與光束由右上→左下移動；環境風環繞；VO 居中。

## VFX / 粒子 / 體積規劃（依 `_core/vfx_pack.md` 展開）
- 粒子：冰晶粒徑 40–120μm，Flip 粒子 140k，重力影響 0.9；黑霧粒徑 20–35μm，風場自東向西；碎冰碰撞使用 Niagara shatter_chainwave。
- 體積：橋下霧密度 0.42 kg/m³，吸收係數 0.12，散射 0.18；冰束體積光錐 0.6m 半徑，衰減 0.45。
- HUD/介面：淡藍鎖定準星，透明度 0.32，動畫曲線 ease-in-out；冰核陣式旋轉 180°/s。
- 特殊效果：槍口折射 +0.16，色散 0.08；冰束邊緣菲涅耳 0.65；爆閃加微弱暈光 0.28。

## Delivery Presets（重申）
- 影片：9:16｜1080×1920｜24fps｜ProRes 422 LT，帶 2 秒前置黑場。
- 字幕：SRT 與內嵌版本各一，8% 畫幅高度，位置固定底部安全區。
- 音軌：立體聲，-14 至 -16 LUFS，VO、音效、音樂分軌。
- 備註：提供 LUT（Glacial-Edge）與顆粒參數，方便後期微調。

## AGENT Self-Check
- 結構（Master/Act/Beat/Angle/timecode）：已涵蓋 Master Prompt、Platform Layer、12 幕 Act/Beat/Angle，時間軸標註完整，符合 15s/12 幕需求。
- Physics & PBR：各幕寫明重力、慣性、摩擦、流體/霧密度，材質粗糙度/金屬度/折射率及高級質感來源（光比、體積光、顆粒）均有交代。
- Stylepacks 使用與衝突：Style Primary Light Glyph Anime + Style Secondary Storm Boss Lock-On，明確標註不可混用其他 LUT；Bloom/色散控制列出，無衝突。
- Continuity：延續前集右後軸線與夜間霓虹色溫；Worldstate Snapshot 記錄橋面濕度與霧密度，後續可沿用；無前集遺留道具需維持。
- Negative/安全檢核：列出禁用元素、PG-13 限制、字幕語系檢核；Assumptions 概述怪物與場景封鎖前提。
- 可能不足：未指定具體 BGM 樣本名稱，需後續音樂選曲時補齊；怪物數量未列具體數字，依後製需求可補 6–10 隻範圍。


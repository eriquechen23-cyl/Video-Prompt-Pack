# 鋼脈都市・爆紋防衛戰線｜爆紋鬥拳・鋼川烈 vs 巨人冰石像 PV Prompt（15s｜2D 日系動漫＋漫畫終擊｜特效滿載版）

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
```
# Global Master Prompt Template

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

### Audio Pack（`_core/audio_pack.md`）
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

### VFX Pack（`_core/vfx_pack.md`）
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

### Stylepack：Light Glyph Anime Look/VFX/Audio（`_stylepacks/light_glyph_anime`）
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

### Stylepack：Urban Switch FX Look（`_stylepacks/urban_switch_fx/look.yml`）
```
name: Urban Switch FX Look
noise_reduction: balanced_motion
saturation: neutral_skin_pop
line_enhancement: motion_defined
color_palette:
  primaries: [charcoal, neon_lime, crimson]
  accents: [steel_blue, tungsten_warm]
  skin_tone: preserved
motion_blur_shutter: 170
exposure_bias: +0.2
notes:
  - 保留夜間城市對比，皮膚自然略暖
  - 動作拖影需兼顧服裝切換殘影
  - 配合雨霧與火星可用 Fresnel rim light
  - 建議同場景多機位以利無縫隱剪
```

## 填寫完畢的輸入欄位（必填）
- project_name：鋼脈都市・爆紋防衛戰線
- series_name/arc：爆紋鬥拳師篇
- episode_index：2
- slug：explosive-vein-fist-vs-ice-colossus_v02
- target_platform：YouTube Shorts / TikTok（同版 9:16）
- duration_sec：15
- style_primary：Light Glyph Anime Look＋Light Glyph Anime VFX
- style_secondary：Urban Switch FX Look（加速殘影＆城市冷色對比）
- worldstate_ref：鋼川烈延續前一集膝擊破壞巨人左膝後，巨人仍有右腿與上半身完好；冰封廣場與冷卻塔保持寒霧
- goal：在 15 秒內用特效極致堆疊的近身連擊，把巨人冰石像從膝到頭貫穿並收束漫畫終擊

## Technical Specs（固定）
- Aspect Ratio：9:16 直式；解析度 1080×1920；FPS：24（以 48 拍攝、24 交付，保留輕慢動）；快門角 180° 主，撞擊瞬間 200–220°；運動模糊開。
- 鏡頭組：Act I 24–28mm 廣角建立空間；Act II 35–50mm 伴跑與衝擊；Act III 50–75mm 近身與漫畫格；景深 F2.2–F4，撞擊點縮至 F4–F5.6 讓碎冰清楚。
- 色彩流程：Log 拍攝→Filmic LUT（陰影微藍 + 高光暖 + 去飽和 8%）→微膠片顆粒（0.18 強度）；Rec.709 交付。
- 顆粒/降噪：細膠片粒，保留高頻冰霧顆粒；降噪僅在暗部 0.2 強度，避免吞線。
- 物理參數：地面冰層摩擦係數 0.12；巨人冰甲彈性 0.2，岩石核心 0.35；烈的鞋底與冰面動摩擦 0.28 但因爆紋熱量，局部融化形成薄水膜折射。
- 光源：主光為冷月色 4300K 從左上 55°；環境反射藍白 5200K；爆紋自發光紅橘 2800K，與冰面反射混色；漫畫格可短暫過曝到 105 IRE 後回落。
- 交付：立體聲 48kHz，-14 LUFS；無字幕、無商標；隨機種子記錄於 metadata，連戲開啟。

## _core Do/Don't
- Do：在 Master 與各 Beat/Angle 寫清 PBR（粗糙度/金屬度/法線）、重力/慣性、光學行為（折射/SSS/鏡面/體積霧）。
- Do：保持軸線與光位一致，標註 Stage 名稱與蓄力百分比。
- Do：每幕提供時間節點 T0/T0+0.3s/T0+0.6s micro-actions，並描述粒子尺寸與速度。
- Don't：省略材質或僅以「高質感」描述；不要用「同前鏡」。

## _stylepacks Do/Don't
- Light Glyph Anime：Do 用 HUD 線條與符文流光包裹爆紋；Don't 混入寫實鏡頭顆粒過重導致線條崩解。
- Urban Switch FX：Do 利用速度線與色差營造動態殘影；Don't 引入過度手持晃動或魚眼畸變。

## Continuity Layer（本集使用）
- 軸線：烈在畫面右側起跑，巨人面向鏡頭略左；鏡頭多在烈右後 110°–150° 弧線，避免跨軸。
- 光位：主光固定左上，爆紋紅橘做補光；漫畫格後回復同主光方向。
- 距離曲線：Act I 使用 24–28mm 建立舞台；Act II 35–45mm 伴跑；Act III 50–65mm 集中終擊；三秒內不跨焦段族群。
- Stage 標註：巨人 Stage A（完整）→ Stage B（左腿爆裂、藍紋外露）→ Stage C（胸甲破、核心露出）→ Stage D（垂直爆線崩塌）。烈蓄力：Lv1（預熱）→ Lv2（戰鬥）→ Lv3（終擊）。
- Hook：保持線性敘事，漫畫格僅在終擊段使用並回到全彩。

## Master Prompt（15s｜2D 日系戰鬥番＋漫畫終擊｜9:16｜骨頭社×MAPPA 動態感）
「午夜 02:10，冰封的鋼脈都市邊緣廣場，冷卻塔與鋼梁半埋於雪，地面結冰厚度 6–8cm，表面粗糙度 0.18，有霜晶與裂縫。中央屹立 18m 高的巨人冰石像（Stage A→D），岩石肌理粗糙度 0.35、冰甲粗糙度 0.12、金屬度 0.05，內部淡藍能量紋折射率 1.33，透光如冰川。黑紅爆紋鬥拳師鋼川烈（東亞短髮、低體脂、肩寬背厚），穿黑色貼身機能衣（尼龍彈性布料粗糙度 0.28、金屬度 0.08、縫線 2mm 步距）、深色戰鬥長褲、黑紅戰鬥鞋（鞋底刻紋 3mm，抗滑橡膠粗糙度 0.65），手套與護腕覆細緻紅色能量線。爆紋 Lv1–Lv3：皮下深紅裂紋發光，熔岩粒子 0.6–1.2mm 直徑外逸，拳頭外圈氣壓罩折射冰霧，邊緣電弧 0.4–0.8cm。鏡頭 24–65mm 穩定滑軌/側移/繞拍，手持抖動 <3%。構圖遵守三分線與前中後景，留白 15% 給能量殘影。光：主光冷藍 4300K 左上 55°，輔光為爆紋紅橘 2800K；體積霧密度 0.08，散射係數 0.14，冰面反射形成冷藍 vs 熱紅對比。色調：膚色優先，陰影微藍、高光暖、去飽和 8%，膚質 base color + SSS 1.2mm + specular 0.28 控油，指節汗液微光。聲音：環境寒風 -14 dB、冰屑摩擦 -16 dB、爆紋衝擊 -6 dB 峰值；音樂 100 BPM 電弦 + 鼓點疊合爆點。轉場多用白閃、光源匹配與鞭移；命中幀加入 1–2 格抽幀與色差抖動。安全：無商標、無可讀字、PG-13，血液以冰碎與光粒替代。」

## Platform Layer（Hook＆交付策略）
- Hook A（故事向 0–1s）：高空俯視冷藍廣場＋巨人甦醒藍光點亮，字幕建議「冰封巨人甦醒」。
- Hook B（衝擊向 12–13s）：子彈時間俯衝準備＋漫畫格終擊，字幕建議「一拳貫穿」。
- 短版可截取 11–15s 終擊段；長版保持全 15s。縮圖：烈拳頭特寫＋紅橘爆紋＋巨人頭裂縫；Hashtag：#爆紋鬥拳 #冰石像 #AnimeVFX。

## Negative Instructions
- 禁用：真實商標/Logo/政治宗教符號/可讀文字；避免血腥內臟，以冰碎與能量光代替。
- 規避：過曝（>105 IRE 持續超 0.2s）、過度手持晃動、魚眼畸變、過度濾鏡；避免漫畫格出現在非終擊段。
- 自動檢核：字幕/商標檢查、角色造型一致、冰塵粒徑 0.2–2mm、音畫同步門檻 -12 dB 觸發、PG-13 尺度確認。

## Act/Beat/Angle 分鏡（12 幕 × 1.2s，總長 <15s）

### Act I（0.0–4.8s）｜建立舞台與爆紋點火
意圖：建立環境與力量對比；基調：冷靜中的爆燃；節奏域：慢入 1.0–1.5s；美術：冰封廣場霧藍、巨人冰甲透光、烈黑紅能量線。

#### Beat 1（0.0–1.2s）｜俯視舞台（Stage A）
重點：冰封廣場與巨人全貌，預留反射面。Blocking：烈尚未入畫，巨人居中站立不動。
- Camera：滑軌下壓俯視，24mm，俯拍 65°；對焦層次由中心巨人→周邊鋼梁；快門角 180°，拍點在冰霜粒子飄落。
- Lighting：冷藍主光 4300K 左上 55°，冰面鏡面反射冷光；對比中等偏柔，眼神光無需。
- Materials & Physics：冰面粗糙度 0.18，反射帶 Fresnel 0.9；冰霜粒徑 0.2–0.6mm，下落速度 0.4 m/s；風速 1.2 m/s 往左。
- Emotion & Performance：無角色表情，氛圍冷清；空拍強調孤寂。
- Audio & Transition：環境寒風 -14 dB，遠處金屬結構吱聲；下一段光源匹配切。
Angle A1
構圖：三分線，巨人置中，前景鋼梁破口；留白 15% 給後續反射。
內容：環境建立特寫，冰裂紋呈輻射狀。
補充：冰霧薄層漂浮 0.3m 高；畫面邊緣微顆粒。
安全：去Logo。

#### Beat 2（1.2–2.4s）｜巨人甦醒（Stage A→B）
重點：眼窩藍光點亮、冰甲裂紋。Blocking：巨人保持原位，肩膀微震。
- Camera：仰角 30° 望向上半身，28mm；對焦單點眼窩；快門角 200° 突顯震動。
- Lighting：主光同前；裂縫內藍光 5200K 突刺，體積霧受激發光；對比提高。
- Materials & Physics：冰甲內部能量紋折射率 1.33，亮度 6000 cd/m²；裂紋擴張速度 0.8 m/s；冰屑爆破粒徑 1–3mm，出速 6 m/s，重力 9.8 m/s² 下墜。
- Emotion & Performance：巨人無表情但力量甦醒；鏡頭微手持 2% 落在肩震時。
- Audio & Transition：冰裂聲 -10 dB，低頻共鳴；轉場白閃 1 幀接下一段。
Angle A2
構圖：中央構圖，上半身充滿畫面；前景飄雪交代空間深度。
內容：眼窩藍光一格格點亮，肩鎧脈動。
補充：色差抖動 1 幀；HUD 無。
安全：去Logo。

#### Beat 3（2.4–3.6s）｜烈入畫・爆紋預熱（Lv1）
重點：烈握拳點亮爆紋。Blocking：烈站右側三分線，面向巨人左腿。
- Camera：低角 20°，35mm，胸高；對焦烈拳；快門 180°。
- Lighting：主光冷藍逆光，爆紋暗紅自發光 2800K；對比高，臉部保留眼神光。
- Materials & Physics：機能衣粗糙度 0.28，金屬度 0.08；膚質 base+SSS，汗珠 0.5mm；爆紋顆粒 0.6mm，速度 2 m/s；冰面摩擦 0.12，烈腳下微裂。
- Emotion & Performance：烈表情冷靜，視線鎖定膝關節；肩背緊繃。
- Audio & Transition：拳套摩擦聲 -12 dB，低頻鼓點進入；轉場鞭移跟跑。
Angle A3
構圖：三分線，烈佔右側，巨人腿在後景左側；前景冰裂紋。
內容：爆紋由內向外亮起，火花 0.3–0.5cm 外散。
補充：氣息白霧被熱推開，冰霧折射紅光。
安全：去Logo。

#### Beat 4（3.6–4.8s）｜滑步衝刺・膝爆點（Lv2）
重點：烈滑步躲踏擊，首拳打膝。Blocking：烈右向左滑步繞前，拳擊膝關節。
- Camera：側向跟拍，45mm；運鏡平移+輕繞拍，手持 3%；快門角 220° 增速度拖影。
- Lighting：主光同向，紅橘爆光補前景；撞擊幀白閃 1 幀。
- Materials & Physics：滑步摩擦生火花 1–2mm，速度 7 m/s；拳頭氣壓罩厚 1cm，壓縮冰霧產生水珠 0.2mm；膝關節冰甲凹陷 3cm 後內爆外爆，碎片 2–8cm 飛出 10 m/s。
- Emotion & Performance：烈牙關緊咬，眉峰下壓；身體低伏重心前移。
- Audio & Transition：爆點低頻 -6 dB，冰碎高頻 -8 dB；抽幀 2 格後直接切 Act II。
Angle A4
構圖：中央對決，烈在近景右前，膝在中景左；速度線沿背景鋼梁。
內容：紅橘衝擊環爆出，藍光被染成橘紅亂流。
補充：色差抖動+局部縮放 1.05x。
安全：去Logo。

### Act II（4.8–10.8s）｜拆腿與胸口核心暴露
意圖：連擊拆解與能量污染；基調：決斷；節奏域：穩定 1.6–2.3s；美術：紅橘光蛇沿冰腿，冰塵反射。

#### Beat 5（4.8–6.0s）｜沿腿連打（Stage B，Lv2）
重點：沿裂縫往上打，光蛇形成。Blocking：烈踩裂縫往上跑，拳拳命中。
- Camera：半環繞 35–40mm，胸高，穩定器；快門 200° 保留殘影。
- Lighting：冷藍主光+紅橘反射在冰面形成條紋；光比高。
- Materials & Physics：每拳產生凹坑 4–6cm，內爆後粒子 0.5–3mm 往外 8–12 m/s；跑步時碎冰受力彈飛，慣性沿腿面滑落；爆紋光蛇亮度 7000 cd/m²。
- Emotion & Performance：烈專注，呼吸急促可見白霧；身體前傾 20°。
- Audio & Transition：連擊鼓點 100 BPM 對齊；轉場光源匹配到腳踏地震。
Angle A5
構圖：前中後景分明，腿為中景斜線，烈在前景下方爬升；留白給粒子。
內容：每拳殘影 Smear 1–2 格，拳輪廓清楚。
補充：HUD 符文薄層貼在光蛇邊緣，刷新率 14Hz。
安全：去Logo。

#### Beat 6（6.0–7.2s）｜巨人右腳踏震（Stage B）
重點：冷藍震波與冰柱爆破。Blocking：巨人抬右腳踏地，烈被震退。
- Camera：中遠景側拍，32mm，膝高；對焦巨人腳→烈滑退；快門 180°。
- Lighting：震波藍光 5200K 放射；主光同向，陰影被震波模糊。
- Materials & Physics：震波環 3 層：冰塵霧層密度 0.06，冰柱 10–30cm 高以 15 m/s 爆出，大塊碎冰 8–15cm；地面裂紋寬 2–4cm 擴散速度 18 m/s。
- Emotion & Performance：烈眉頭一皺，腳步滑行 4m，拉出冰霜長痕與紅光殘影。
- Audio & Transition：低頻轟鳴 -8 dB，冰柱破裂高頻 -10 dB；轉場遮擋切到格擋。
Angle A6
構圖：巨人腿佔左側，烈在右側滑退；地面裂紋成放射狀。
內容：冰震波如水紋，撞擊點爆出冰柱。
補充：輕微色差抖動；鏡頭 jolt 2%。
安全：去Logo。

#### Beat 7（7.2–8.4s）｜交叉格擋（Stage B，Lv2）
重點：氣壓罩抵禦冰震波。Blocking：烈雙臂交叉胸前站穩。
- Camera：正面中近景，45mm；對焦烈臉與前臂；快門 200°。
- Lighting：爆紋升級全臂發亮，紅橘 rim 光；主光依舊冷藍側逆。
- Materials & Physics：氣壓罩厚 1.5cm 折射率 1.02，外圈混色能量扭曲空氣，形成密度梯度；碎冰撞上被偏折 20–30°；袖口布料受風飄動 0.5cm。
- Emotion & Performance：烈咬牙，眼神堅定，肌肉緊繃可見；呼吸霧被氣壓罩帶出旋渦。
- Audio & Transition：混色能量嘶鳴 -9 dB，鼓點升強；轉場呼吸拉焦到胸口。
Angle A7
構圖：中央居中，肩膀占畫面寬度 70%，背景模糊；前景碎冰飛向鏡頭。
內容：慢動作 0.3s，碎冰在氣壓罩表面彈開。
補充：紅橘粒子漂浮 0.5–1mm，密度 0.4。
安全：去Logo。

#### Beat 8（8.4–9.6s）｜胸口爆破核心露出（Stage C，Lv2→3預熱）
重點：胸甲破裂，藍白核心被污染。Blocking：烈跳到胸口擊穿一塊冰甲。
- Camera：背後仰視 40mm，胸高；對焦拳頭落點；快門 200°。
- Lighting：爆點紅橘光強烈，體積霧被染色；主光仍冷藍，形成冷暖撞色。
- Materials & Physics：冰甲厚 8cm，粗糙度 0.1；裂開如玻璃，碎片 3–10cm 飛散 12 m/s；核心能量流體黏度 0.9 Pa·s，顏色由藍變橙形成湍流；拳頭氣壓罩擠出冰霧成水珠，折射光虹。
- Emotion & Performance：烈落地時膝微彎吸震，拳砸下瞬間肌群線條突顯，眼神銳利。
- Audio & Transition：玻璃裂聲 -8 dB，能量嗡鳴 -10 dB；轉場拉焦到落地滑行。
Angle A8
構圖：斜三分構圖，烈拳在上三分交點，核心露出位於中央。
內容：紅橘爆紋包圍藍白核心，顏色混濁。
補充：HUD 符文沿裂縫環繞，刷新率 14Hz；碎片帶動空氣扭曲。
安全：去Logo。

#### Beat 9（9.6–10.8s）｜落地滑行蓄力（Stage C，Lv3 充能）
重點：能量回收到雙拳，地面光軌。Blocking：烈從胸口落地滑行後穩住，雙拳收腰。
- Camera：斜俯視 35mm 跟拍，機位略前；快門 200°。
- Lighting：紅橘光軌沿地面反射，霧氣受熱形成高光條；主光冷藍仍在左上。
- Materials & Physics：滑行摩擦融冰形成水膜厚 1mm，折射光軌；光軌粒子 0.8–1.5mm，速度 6 m/s 往烈身體回收；衣料受風貼體，護腕金屬度 0.2 反射爆光。
- Emotion & Performance：烈吐出白霧，眉心收緊，蓄力時脊柱微拱，臀腿連動表現發力路徑。
- Audio & Transition：光軌回收發出吸氣聲 -12 dB；轉場匹配拳頭特寫。
Angle A9
構圖：烈在右下三分，光軌呈 S 形導向身體；背景巨人胸口裂縫可見。
內容：光粒子沿腳印回流，霧氣中漂浮。
補充：速度線在畫面邊緣淡入淡出；顆粒保持。
安全：去Logo。

### Act III（10.8–15.0s）｜終極爆紋砸擊與漫畫格收束
意圖：蓄力滿載、子彈時間、漫畫終擊；基調：決勝；節奏域：加速 2.6–3.0s；美術：紅橘熔岩光、漫畫分格、垂直爆線。

#### Beat 10（10.8–12.0s）｜爆紋滿載特寫（Stage C→D，Lv3）
重點：拳頭與手臂熔岩狀，空間震動。Blocking：烈定點蓄力。
- Camera：特寫 60mm，胸高；對焦拳頭；快門 180° 主，局部熱浪以鏡頭畸變表現。
- Lighting：爆紋亮度接近雷光，邊緣 Bloom 0.32；主光仍在左上但被紅光壓制。
- Materials & Physics：皮膚 SSS 1.2mm，汗珠 0.5mm 蒸發成霧；氣壓罩厚 2cm 折射率 1.02，冰霧在表面凝結成水珠再被甩開；漂浮冰粒 1–3mm 被熱浪提前震離，懸浮 0.4s；拳頭法線凸起清晰，粗糙度 0.35。
- Emotion & Performance：烈低吼，眼神聚焦，肩胸擴張；手指微顫顯蓄壓臨界。
- Audio & Transition：低頻脈動 -7 dB，電弧噼啪 -10 dB；轉場手持小幅前推到跳躍。
Angle A10
構圖：中央拳頭佔畫面 40%，背景模糊出巨人頭部輪廓。
內容：熔岩紋流動，輪廓發光；氣壓罩扭曲背景。
補充：紅橘粒子密度 0.6，向上飄；色差閃 1 幀。
安全：去Logo。

#### Beat 11（12.0–13.2s）｜跳上頭頂・子彈時間（Stage C→D，Lv3）
重點：長殘影跳躍，時間放慢。
- Camera：先跟拍 45mm 往前，再抬升到頭頂俯視 55mm；對焦烈；快門 200° → 144° 在子彈時間段。
- Lighting：紅橘殘影拖尾，主光冷藍；背景冰塵幾乎靜止，粒子反射混色。
- Materials & Physics：跳躍初速 11 m/s，身後殘影 Smear 3–4 幀；碎冰被踢起 5–8cm 停滯；氣壓罩厚 2.2cm；重力 9.8 m/s²，子彈時間段將背景運動縮至 20%。
- Emotion & Performance：烈嘴角上抬，戰意上揚；雙拳合於胸前，核心收束；身體前傾瞄準。
- Audio & Transition：音樂濾掉中高頻進入慢動；氣流聲長尾；轉場硬切至終擊。
Angle A11
構圖：烈殘影形成弧線帶向巨人頭頂中央，俯視畫面留白 20% 給落點。
內容：背景冰塵停頓，爆紋光唯一動態。
補充：速度線收斂到落點；HUD 文字微閃。
安全：去Logo。

#### Beat 12（13.2–15.0s）｜漫畫格終極爆破（Stage D，Lv3）
重點：垂直貫穿、漫畫分格、回彩收束。
- Camera：正上方俯視 60mm，快門 180°；白閃一格後切入漫畫分格；分格內主畫面 50mm 斜側；最後回到全彩 50mm 側臉特寫。
- Lighting：爆點紅橘光球 9000 cd/m²，Bloom 0.35；漫畫格中線稿黑白 + 彩色 SFX；回彩後主光與爆光重合，光比高。
- Materials & Physics：垂直爆線從頭頂貫穿到地面，裂縫寬 0.5–1m；碎片分三尺寸：大塊 20–60cm（有面反射），中塊 5–15cm（邊緣光），粉末 0.1–1mm（粒子）；內部藍光被紅橘覆蓋成亂流；坑洞深 3m，邊緣冰面粗糙度 0.22；烈拳頭指節冒煙，粗糙度 0.4，溫度視覺化為熱浪。
- Emotion & Performance：終擊時烈怒吼，表情極致；收束後吐白霧，眼神冷靜。
- Audio & Transition：前 0.2s 白閃靜音→爆炸「ドガァァン!!」 SFX 疊低頻；漫畫格期間加入紙張翻頁聲 -14 dB；回彩時音樂收束，尾端殘響 -12 dB 內。
Angle A12-1（起爆）
構圖：俯視中央，拳頭嵌入頭頂；留白給爆光。
內容：白閃後紅橘光球爆出，裂紋垂直向下。
補充：色差抖動 1 幀；粒子爆散。
安全：去Logo。
Angle A12-2（漫畫格主畫面）
構圖：斜側上方，烈與巨人頭佔大格；中央垂直爆線。
內容：眼窩、胸口、腹部、膝同時噴光與碎冰；巨大彩色 SFX「ドガァァン!!」。
補充：側邊小格黑白線稿碎裂；底部長條格顯示貫穿坑洞與烈半跪背影。
安全：去Logo。
Angle A12-3（回彩收束）
構圖：烈側臉近景，背景坑洞冒霧；三分構圖。
內容：巨人崩解後只剩碎塊山；烈站起吐白霧，護腕冒煙。
補充：顆粒收斂，光線回穩；定格 0.2s 淡出。
安全：去Logo。

## Assumptions
- 巨人為無語音的魔像，不需配音；可用低頻震鳴代表能量。
- 爆紋顏色維持紅橘，不切換其他色盤，以保持冷暖對比。
- 舞台保持夜間冰霧環境，不加入額外 NPC 或建物破壞，以凸顯主角對決。

## Next Episode / Spin-off Ideas
- 延伸 1：巨人碎片吸收爆紋成為多頭碎塊獸，需空中連擊。
- 延伸 2：烈的爆紋超載導致雙臂需要臨時冷卻裝置，加入科技支援隊。
- 番外：廣場白天維修日常，烈練習控制爆紋做冰雕。

## Changelog vs Previous Episode
- 造型：烈服裝與顏色同前，爆紋亮度上限提升；護腕有燒焦痕。
- 場景：廣場破壞新增膝部裂縫、胸口破洞，最終形成垂直坑洞。
- 招式：新增漫畫格終擊、氣壓罩厚度提升。

## AGENT Self-Check
- 結構：Master / Act / Beat / Angle / timecode 皆列出，12 幕×1.2s，符合 15s。
- Physics & PBR：每 Beat/Angle 填寫重力、慣性、摩擦、粒徑、PBR 粗糙度/金屬度、光學行為（折射/SSS/體積霧）。
- Stylepacks：引用並內嵌 Light Glyph Anime + Urban Switch FX 全文，無衝突，遵守 Do/Don't。
- Continuity：軸線、光位、Stage、蓄力曲線明確，漫畫格僅終擊使用。
- Platform/Delivery：標註 9:16、1080×1920、24fps、音頻規格、Hook A/B、縮圖建議。
- Negative Instructions：商標/文字/血腥限制、抽幀與白閃控制皆列，PG-13。
- QA：引用 QA Checklist，提交前確認 10/10；揭露假設（巨人無語音、色盤固定、無 NPC）。

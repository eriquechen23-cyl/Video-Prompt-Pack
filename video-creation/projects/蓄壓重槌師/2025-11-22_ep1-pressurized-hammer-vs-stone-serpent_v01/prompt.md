# 蓄壓重槌師 EP01 — 朝倉蓮 vs 石甲巨蛇 BOSS PV Prompt（15s｜12 幕｜9:16 直式）

來源劇本：scripts/2025-11-22_pressurized-hammer-vs-stone-serpent_v01/script.md

## Input Registry
- project_name: 蓄壓重槌師
- series_name/arc: 蓄壓重槌師・白日神殿線
- episode_index: 1
- slug: pressurized-hammer-vs-stone-serpent_v01
- target_platform: TikTok / Reels / Shorts
- duration_sec: 15
- style_primary: Light Glyph Anime Look（黑＋黃正午漫畫化強化）
- style_secondary: Zenith Noon Real Look（壓力感過曝光比，用於黑黃衝擊波曝光）
- worldstate_ref: 廢棄石造神殿、正午強光、石甲巨蛇已盤踞於破柱之間
- goal: 以蓄壓節奏＋黑黃衝擊波呈現訓練組數感的 BOSS PV，收尾以漫畫格擊殺

## 一句話題材
正午岩地的廢棄神殿前，蓄壓重槌師朝倉蓮穩步點亮黑黃戰紋，頂著毒霧與熱浪蓄力，最後以漫畫格的重槌衝擊波把石甲巨蛇擊倒。

## 引用模板原文
### Global Master Prompt Template（`_core/global_prompt.md`）
```
Master({時長}s｜{風格}｜{畫幅}｜{fps}｜{質感})
「{時間/地點}；{環境元素1/2/3}；{主體＆動作一句話}。
鏡頭：{滑軌/側向/繞拍/手持≤3%/穩定器}。
表演：{情緒/肢體/視線}。
臉型/髮型：{依上傳五官特徵}。
構圖：{三分線/中央/前中後/留白10–20%}；動態：{風/水/人群/道具}。
寫實細節：{服裝/材質/肌理/光影過門}。
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

### QA Checklist（`_core/qa_checklist.md`）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

## Stylepacks

### 引用 Style Pack：Light Glyph Anime（全量內嵌）
```yaml
# _stylepacks/light_glyph_anime/look.yml
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

# _stylepacks/light_glyph_anime/audio.yml
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

# _stylepacks/light_glyph_anime/vfx.yml
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

### Style: Hammered Noon Manga Burst（新樣板｜本案 Default ON）
- Applicable for: 正午白日、黑黃重槌、漫畫格收尾的 2D 動漫 PV；支援 9:16 直式 BOSS 戰、蓄力節奏演出。
- Do NOT mix with: 霓虹夜景膠片感、高霧體積光的冷夜場、寫實血腥破皮特寫。
- Default: ON
- Visual traits:
  - 用高對比黑線勾邊，金黃高光在槌頭與戰紋處溢出，邊緣帶 0.3px 漫畫網點。
  - 正午 5500–5800K 高色溫，硬陰影鋪在岩地；熱浪造成輕微折射失真與邊緣漂移。
  - 漫畫格模式：切換時背景改為黑白速度線，保留武器與衝擊中心彩色；擬聲字以粗黑邊＋金黃內發光處理。
  - PBR 參數：石甲粗糙度 0.75、金屬度 0、法線強度 1.0；戰槌金屬度 0.8、粗糙度 0.18、刮痕置換 0.06 cm；戰甲碳纖維法線 0.35、護膝橡膠粗糙度 0.42。
- Audio traits:
  - 4/4 重鼓對齊步伐與揮槌，鼓擊取 60–80 Hz 深低頻；毒霧用 3–5 kHz 帶噪尖嘯。
  - 漫畫格瞬間加入 0.2s high-shelf 滤波壓制低頻，保留短暫耳鳴；重回正常畫面時以 sub drop 強調衝擊恢復。
  - 打擊 UI：蓄力時節拍疊加連續金屬軋聲，滿格瞬間觸發金黃閃鈴。

## Technical Specs
- Aspect Ratio: 9:16 直式；Resolution Target: 1080x1920；Color Space: Rec.709 gamma 2.4；FPS: 24；快門角 180°；動態模糊依 Stylepack 指定 165–180°。
- Lenses: Act I 24–35mm（環境與熱浪折射），Act II 35–50mm（節奏中景），Act III 50–75mm（蓄力特寫與漫畫格衝擊）；景深中等，近景 f/2.2 保留背景熱扭曲，三秒內避免焦段跳換。
- Camera Continuity: 軸線固定「蓮右、蛇左」，鏡頭沿蓮右後 120° 弧線滑軌/穩定器移動；Act I 平穩建立位置，Act II 保持側向與 3/4 角跟隨節奏，Act III 收縮到 50–75mm 近景與漫畫格後回到 55mm 收尾；手持不超過 3%。
- Color Pipeline: log → filmic LUT → final contrast；保留黑線與金黃高光，不可過度去飽和；抗社群壓縮：邊緣加粗、粒子對比提升 8%、高光加 2% bloom。
- Grain & Compression: 紙感細紋 0.12、膠片顆粒 0.08 混合；避免過度去噪，保留石面微粗糙。
- Physics Hooks: 重力 9.81 m/s²，碎石拋物線需帶出落點粉塵；熱浪折射 index 1.02–1.05；毒霧流體阻尼 0.35；戰槌回彈與肩膀慣性需遵守。

## Brand / Worldstate Layer
- Brand Tone: 半教練式口吻，日語擬聲＋中文訓練用語混用；黑＋黃為品牌主色，象徵警示與力量儲存。
- Character Bible — 朝倉蓮：黑髮束後、銳利眼型；黑色無袖戰甲、碳纖維護胸、黃色護膝與護具；口頭禪「最後一組就好」。
- Weapon: 黑黃戰槌，槌頭金屬邊緣帶刻度，柄部包紋路橡膠握帶；蓄力紋會逐格亮起如 UI 條。
- Environment: 廢棄石造神殿，石階與柱面粗糙 0.7，塵土乾燥，陽光直射形成硬陰影與白色邊光；熱浪造成空氣抖動。
- Persistent Elements: 黑黃蓄力條 UI、訓練組數鼓點、護膝舊傷提醒（紅黃閃）。

## Assumptions
- 巨蛇體型設定為蓮身長 4 倍、石甲鱗片厚度 4 cm，避免過度巨型導致鏡頭塞滿；若需放大，請同步調整焦段與遠景留白。
- 聲音不含旁白台詞，最後近景台詞交由後期配音填入；當前僅留口型與呼吸。
- 無外部 NPC 或其他角色登場，畫面集中在蓮與巨蛇的對峙；如需加入觀眾，需另做版本。

## Platform Layer
- Hook A（故事向 0–1s）：蛇尾拍地與熱浪扭曲，單一下沉重鼓「ドン」，字幕提要「正午訓練，遇上石甲巨蛇」。
- Hook B（衝擊向 0–1s，獨立 `hook_cut_prompt`）：取 Beat 11 漫畫格擊殺 0.8s 作鉤子，再硬切回 baseline 0.0s；不得在 baseline 內混用倒敘指示。
- Caption 建議：短版「把力量存滿，只為那一槌。」｜長版「正午石殿對決，朝倉蓮用訓練節奏擊碎石甲巨蛇。」
- Thumbnail: 斜前方蓄力姿勢，黑黃蓄壓紋全亮，背景石殿與巨蛇頭部半入畫；粗黑外框＋金黃標題條。
- Hashtag: #蓄壓重槌師 #BossFight #Anime #BlackGold #15sPV
- CTA: 影片收尾淡出時加「Follow for next drill」字幕，0.6s 內完成。

## Continuity Layer（軸線 / 距離 / 光源 / 狀態時間線）
- Axis Lock：神殿位畫面上方、岩地向下延伸；朝倉蓮保持畫面右側，石甲巨蛇偏左；鏡頭多沿蓮右後 120° 弧線移動，不跨軸讓左右對調。
- Camera Distance Curve：Act I 24–35mm 建立環境；Act II 35–50mm 維持中近景與節奏；Act III 50–75mm 聚焦蓄力與漫畫格擊殺，收尾回 55mm 中景，三秒內避免廣角/長焦反跳。
- Light Direction Lock：太陽固定右上 45°，光溫 5600–5800K；蓮右肩持續白金 rim，地面陰影朝左下；漫畫格可暫轉黑白速度線後回復同光位。
- Boss State Timeline：Stage 1（0–4s）石甲完整僅舊刮痕；Stage 2（4–8s）第一槌後局部裂、第二槌後大裂紋；Stage 3（8–15s）裂紋發光待崩解、擊殺後碎裂成核。
- Ren State Timeline：蓄壓條 0–4s 僅 1 格微光；4–8s 逐格亮至 70% 並隨揮槌消耗；8–12s 滿格閃爍，最終槌後瞬間清零；護膝 0–6s 無警示、6–9s 紅黃閃一次、9–15s 再提醒但站穩。
- Beat Writing Rule：每 Beat 先標註「延續 Axis/Light/Stage/Lens 群組」再寫唯一新重點；各 Angle 仍需完整 Camera / Lighting / Materials & Physics / Emotion & Performance / Audio & Transition 欄位。

## Master Prompt（含物理與質感）
Master(15s｜2D 日系動漫＋黑黃漫畫格｜9:16｜24fps｜高對比熱浪質感)
「正午白日的廢棄石造神殿前，熱浪扭曲空氣、石階被曬白，覆滿石甲鱗片的巨蛇盤在破柱間；蓄壓重槌師朝倉蓮扛著黑黃戰槌，穩步前進、蓄力到滿格後以漫畫格重槌擊碎蛇頭。
鏡頭：滑軌與穩定器為主，近景偶帶 2% 手持晃動；24–35mm 建立環境，50–75mm 聚焦蓄力與衝擊，漫畫格瞬間用 75mm 壓縮。
表演：呼吸穩、步伐重，眼神從沉著轉為微笑挑釁；揮槌時肩背肌繃緊、護膝偶有抖動。
臉型/髮型：黑髮束後，稜角分明的下顎；汗珠沿鬢角滑落。
構圖：三分線維持前中後層，留白 12–18%；動態包含熱浪折射、碎石噴飛、毒霧飄散。
寫實細節：石甲粗糙 0.75、砂塵法線清晰；戰槌金屬邊緣鏡面 0.8 伴細刮痕，護膝橡膠磨損；陽光硬邊在肩線形成白金 rim；粒子衝擊波遵循圓形 UI 刻度。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35 空間｜50–75 親密｜75 壓縮漫畫格；光圈 T2.2–T4；快門角 165–200（漫畫格瞬間 200 強化殘影）；對焦單點眼＋衝擊瞬間層次拉焦。
光影：正午側逆光 5500–5800K，高對比；硬邊陰影與熱浪折射，衝擊瞬間有體積塵煙散射；眼神光保留。
色調/LUT：黑線清晰、金黃高光微過曝 3%、陰影留灰度紋理；去飽和 4% 避免螢光過亮。
聲音：環境風聲低頻 80 Hz、砂塵顆粒；節奏鼓點與揮槌同步；毒霧尖嘯在 4 kHz，擊殺後留 0.2s 耳鳴再回環境。
轉場：直接切＋衝擊匹配剪接；漫畫格切換用遮擋與粗框；羽化 0.5s 收尾至黑黃漸層。
安全：無品牌、無可讀文字、僅成人角色；時間序一致，熱浪方向連貫。

## Negative Instructions
- 禁用真實品牌商標、宗教與政治符號；無血腥破皮，石甲破碎以碎片與塵土呈現。
- 禁用過曝整片白、過度魚眼變形（除 Beat03 0.2s 內的細節）、過度手持晃動；避免廉價濾鏡或絢爛鏡頭光斑。
- 人物比例需保持寫實骨架，避免 Q 版或超變形；巨蛇口腔不露粘液細節。

## Act / Beat / Angle 詳稿（12 幕 × 1.2s）

### Act I — 正午對峙（0.0–3.6s）｜基調：決斷、炙熱｜節奏域：慢入 1.0–1.4
- 美術要點：曬白石階、破柱、石甲巨蛇、黑黃戰槌、硬邊日光、熱浪折射紋。

#### Beat 01（0.0–1.2s）｜白日神殿前的巨蛇｜意圖：建立場景＋節奏起點
- Blocking：蛇盤踞中心，尾巴緩慢拍地；鏡頭俯視拉遠。
- Continuity：Axis「蓮右蛇左」初始建立、主光右上 45°、Camera 24–35mm 群組；Boss Stage 1 石甲完整、Ren 蓄壓條 1 格微光。
- Angle A — 高俯中遠景建立
  - Camera：24mm 俯拍，滑軌升降，快門角 180，對焦前→中→後層次。
  - Lighting：正午直射 5600K，硬陰影；熱浪造成地面反射微抖動。
  - Materials & Physics：石地粗糙度 0.72，法線突出；蛇鱗石甲粗糙 0.78、金屬度 0；尾巴拍地帶出細粉塵粒子 0.2m/s 跳動，重力 9.81 m/s² 下落。
  - Emotion & Performance：巨蛇凝視遠方，張力蓄積；畫面冷靜。
  - Audio & Transition：環境風＋低頻「ドン」；直接切入下一幕。

#### Beat 02（1.2–2.4s）｜朝倉蓮登場｜意圖：引入主角、穩重氣場
- Blocking：蓮站在石階上方踏下一階。
- Continuity：延續 Axis Lock 與正午光位，維持 24–35mm 群組；Boss 仍 Stage 1，Ren 蓄壓仍低量，鏡頭位置略下移但不跨軸。
- Angle A — 低角度推近中景
  - Camera：35mm 低角度向上，穩定器前推，快門角 180；對焦單點在眼睛隨步伐微拉。
  - Lighting：背光 rim 5700K，肩線強烈白金邊；地面反光補光 0.25。
  - Materials & Physics：戰槌金屬邊鏡面反射；戰甲碳纖維粗糙 0.38；護膝橡膠磨痕可見；踏階引起細微塵霧 0.4m/s。
  - Emotion & Performance：蓮穩重無懼，呼吸穩；汗珠在上臂滑落。
  - Audio & Transition：第二下重鼓對齊踏步；石階輕震聲；硬切下一幕。

#### Beat 03（2.4–3.6s）｜巨蛇先發制人｜意圖：提升危險感
- Blocking：巨蛇抬頭噴毒霧，鏡頭貼近蛇口。
- Continuity：維持蓮右蛇左的軸線，鏡頭從蓮右後弧線貼近蛇頭但不跨線；仍屬 Act I 24–35mm 群組；Boss Stage 1、Ren 蓄壓條保持 1–2 格微光。
- Angle A — 蛇頭特寫魚眼
  - Camera：24mm 近距廣角帶輕微桶狀畸變，快門角 200 強化動感；對焦在牙尖，呼吸拉焦到毒霧前緣。
  - Lighting：陽光直射蛇鱗反白，高反差；毒霧邊緣逆光半透明。
  - Materials & Physics：毒霧流體阻尼 0.35，粒子半徑 0.6mm；牙齒濕潤粗糙 0.22 但不出血；石甲法線深度 1.0。
  - Emotion & Performance：蛇瞳收縮、張嘴發出威脅；背景略變形增壓迫。
  - Audio & Transition：尖銳「シューッ」＋第三下鼓；匹配切到側面步伐鏡。

### Act II — 蓄壓節奏（3.6–8.4s）｜基調：緊張與穩定混合｜節奏域：穩定 1.6–2.0
- 美術要點：黑線流光、蓄壓 UI、腳下裂紋、衝擊波刻度。

#### Beat 04（3.6–4.8s）｜穩步蓄壓起步｜意圖：建立節奏、啟動蓄力
- Blocking：蓮向前踏步，戰槌於身側，腳下輔助圓線閃現。
- Continuity：延續 Axis Lock（蓮右蛇左）、主光右上 45°、Act II 鏡頭 35–50mm 群組；Boss 仍 Stage 1，Ren 蓄壓條提升到 30%、步伐與鼓點同步。
- Angle A — 側面追蹤中景
  - Camera：35mm 側移滑軌，身體保持中景，快門角 180；對焦層次從腳步到戰槌。
  - Lighting：側逆光 5600K，高對比；地面反光填充 0.2；熱浪折射讓邊線微漂移。
  - Materials & Physics：腳步落地產生細裂紋 0.5 cm 深，碎片掉落；蓄壓線條暗黃流動速度 0.4；護膝橡膠壓縮回彈。
  - Emotion & Performance：臉沉著，嘴角微收；步伐穩定如數組數。
  - Audio & Transition：每步「ドン」對齊鼓；滑入下一幕。

#### Beat 05（4.8–6.0s）｜蓄壓槽點亮｜意圖：凸顯充能視覺
- Blocking：戰槌拉上肩，手臂與戰甲黑線逐格亮黃。
- Continuity：延續 Beat 04 軸線與光位，鏡頭上推但不跨線，保持 Act II 35–50mm 群組；Boss Stage 2 尚未開啟、Ren 蓄壓條升至 70% 閃動。
- Angle A — 上半身仰角特寫
  - Camera：50mm 仰角，穩定器微推，快門角 172；對焦在前臂紋路並呼吸拉到眼睛。
  - Lighting：背光邊緣 5700K，背景壓暗；肩線和槌頭邊緣有金黃 rim。
  - Materials & Physics：戰紋亮度分段增加；肌肉張力讓皮膚微隆起，汗珠折射點光；槌頭金屬反射出環境藍天。
  - Emotion & Performance：深吸氣，眼神鎖定巨蛇，表情專注。
  - Audio & Transition：低沉蓄力音與加速鼓擊；直接切第一槌。

#### Beat 06（6.0–7.2s）｜第一組・穩定起槌｜意圖：展示打擊節奏與衝擊波
- Blocking：橫向砸地，衝擊波擴散震開巨蛇。
- Continuity：沿同軸線往前半步，保持 Act II 焦段群組；Boss 進入 Stage 2（局部裂痕），Ren 蓄壓條從 70% 消耗一部分但保持亮度脈動。
- Angle A — 斜 3/4 中景
  - Camera：35mm 斜前方，快門角 190 增加殘影，穩定器弧形跟；對焦在槌頭落點，衝擊後拉到碎片。
  - Lighting：側逆硬光，衝擊瞬間塵埃體積散射；色溫 5600K。
  - Materials & Physics：衝擊波圓環以黑黃刻度向外 12 m/s，岩屑粒子 2–3 mm 隨重力弧線落下；石甲裂片厚 4 cm，破碎邊緣粗糙 0.82。
  - Emotion & Performance：肩背肌收緊，表情短促吐息。
  - Audio & Transition：重低音「ドゴン」＋碎石噴濺；匹配剪接到第二槌。

#### Beat 07（7.2–8.4s）｜第二組・深度壓縮｜意圖：升級力量、加速度
- Blocking：旋身斜砸巨蛇身軀，裂紋蔓延。
- Continuity：保持蓮右蛇左軸線，鏡頭近距旋繞但不跨線，依舊使用 35–50mm 群組；Boss Stage 2 裂紋擴散，Ren 蓄壓條回填到 80% 後再次消耗。
- Angle A — 近景跟拍
  - Camera：50mm 近景，穩定器繞身，快門角 200；對焦在槌頭擊點，2-frame 閃白後回復。
  - Lighting：強硬日光＋反光板 0.15 補臉；衝擊時高對比閃白。
  - Materials & Physics：黑紋再被黃光填滿，亮度 1.2 倍；護甲裂紋以法線貼圖顯示深度 0.9；石屑飛行受慣性方向性明確。
  - Emotion & Performance：牙關緊咬，下顎線突出；肩部旋轉慣性明顯。
  - Audio & Transition：連續兩下重鼓對齊旋身與落點；硬切到警示特寫。

### Act III — 最終組（8.4–15.0s）｜基調：決戰、釋放｜節奏域：加速 2.4–3.0
- 美術要點：護膝警示光、滿格戰紋、漫畫格粗框、黑黃衝擊圓形分格。

#### Beat 08（8.4–9.6s）｜舊傷警示｜意圖：增加張力、短暫停頓
- Blocking：蓮微蹲按護膝，護具紅黃閃一下。
- Continuity：維持軸線與光位，鏡頭收束到 Act III 50–75mm 群組；Boss 進入 Stage 3（裂紋發光待崩解），Ren 護膝警示首度亮起、蓄壓條回升至 80%。
- Angle A — 膝蓋與腰部中近景
  - Camera：75mm 近景，穩定器定機，快門角 180；對焦在護膝警示光後拉回臉部一瞥。
  - Lighting：側光 5600K，膝蓋金黃反光；背景略降曝光。
  - Materials & Physics：護膝橡膠粗糙 0.42，紅黃警示光散射 0.6；膝蓋微抖顯示肌肉緊繃。
  - Emotion & Performance：眉頭皺、呼吸重，但站姿仍穩；短暫停頓。
  - Audio & Transition：心跳加重，BGM 暫停半拍；羽化 0.4s 轉決心近景。

#### Beat 09（9.6–10.8s）｜最終組前的決心｜意圖：情緒提拉、滿格展示
- Blocking：抬頭微笑，雙手握槌，戰紋全亮。
- Continuity：延續 Beat 08 軸線與光位，鏡頭微推但保持 50–75mm 群組；Boss 仍 Stage 3 裂紋發光，Ren 蓄壓條滿格閃爍、護膝第二次短暫警示。
- Angle A — 胸像正面略仰
  - Camera：50mm 仰角，穩定器微推，快門角 180；對焦在眼神，背景過曝成白邊光。
  - Lighting：背光白金 rim，前方補光 0.2；高對比強調肌理。
  - Materials & Physics：黑黃戰紋亮度全開，光流速 0.8；汗水沿下巴形成細亮面；護甲反射陽光形成光斑。
  - Emotion & Performance：嘴角勾出「最後一組」微笑，眼神堅定。
  - Audio & Transition：鼓點重新踢入更大「ドン」，同步戰紋亮起；匹配剪接到慢動作蓄力。

#### Beat 10（10.8–12.0s）｜慢動作蓄力・總結重擊起手｜意圖：鋪陳終結槌
- Blocking：巨蛇撲下，蓮跨步旋身，槌軌畫光弧；進慢動作 0.5x。
- Continuity：延續 Beat 09 的軸線與光位，鏡頭收縮到 Act III 50–75mm 群組並環繞蓮右後；Boss Stage 3 裂紋發光，Ren 蓄壓條保持滿格閃爍、護膝未再警示。
 - Angle A — 環繞慢動作中景
  - Camera：55mm 弧形滑軌環繞，快門角 200 強化殘影；對焦在槌頭沿光弧移動，景深拉長；保持蓮右蛇左視覺方向不翻轉。
  - Lighting：陽光勾勒光弧邊緣，地面反光補充；體積塵埃在慢動作中漂浮。
  - Materials & Physics：光弧以黑黃雙層，粒子大小 1–2 mm，沿軌跡受慣性延遲；衣甲布料微動受風阻；熱浪折射 index 1.05 造成背景扭曲。
  - Emotion & Performance：肌肉線條張力被放大，表情專注。
  - Audio & Transition：BGM 拉長，低頻拉伸；蓄力條 UI 疊影跑到 100%；硬切漫畫格衝擊。

#### Beat 11（12.0–13.2s）｜漫畫格衝擊・擊殺瞬間｜意圖：高潮擊殺
- Blocking：槌頭砸中蛇頭，畫面切成漫畫格，速度線填滿背景；擬聲字「ドゴォン」。
- Continuity：保持軸線（蓮右蛇左）並延續 Act III 50–75mm 群組；Boss Stage 3 在此崩解，Ren 蓄壓條瞬間清零、護膝警示後熄滅；光位雖轉漫畫格但陰影方向一致。
- Angle A — 漫畫格特寫
  - Camera：75mm 壓縮特寫，畫面外框粗黑；快門角 200；對焦在槌頭與蛇頭交會點，背景速度線模糊。
  - Lighting：衝擊點爆出白金強光 1.15 倍，周圍黑白速度線；體積塵煙被光穿透形成射線。
  - Materials & Physics：石甲炸裂碎片尺寸 2–5 cm，向外 15 m/s；衝擊波以圓形分格擴散；漫畫網點附著在高光區。
  - Emotion & Performance：蓮表情凜然，動作定格在衝擊姿勢。
  - Audio & Transition：誇張重擊音＋0.2s 耳鳴，立即壓回正常環境；匹配切到落塵收尾。

#### Beat 12（13.2–15.0s）｜塵埃落定・訓練結束｜意圖：收束情緒、Brand Line
- Blocking：巨蛇倒地，蓮扶槌站直，吐氣，護膝微閃；0.5s 切胸像說收尾台詞再淡出。
- Continuity：維持 Axis Lock、主光方向與 Act III 焦段群組 50–75mm；Boss Stage 3 崩解後碎片落地，Ren 蓄壓條清零、護膝僅留餘光閃爍。
- Angle A — 中遠景拉遠後切胸像
  - Camera：55mm 中景推拉，快門角 180；對焦先在倒地巨蛇再拉到蓮；最後胸像保持 55mm 以維持焦段連續性。
  - Lighting：陽光穿雲形成光束，塵埃漂浮；光束溫度 5600K；背光 rim 勾勒蓮肩線。
  - Materials & Physics：碎片散落粗糙 0.8，塵埃粒子 0.3mm 慢速下沉；護膝黃光間歇閃爍 0.6Hz；戰槌重心微晃受慣性回彈。
  - Emotion & Performance：吐氣放鬆，嘴角微揚；胸像時口型可配「好了，訓練到這裡」。
  - Audio & Transition：環境風回歸，心跳漸弱；黑黃漸層淡出；疊字標語出現。

## Platform-safe Captions & Overlays
- 片尾標語疊字：右側豎排或下方橫排「蓄壓重槌師・朝倉蓮 —— 把力量存滿，只為那一槌定勝負。」黑底金字，描邊 2px。
- 漫畫格內的擬聲字需保持不可讀拉丁字，僅日文擬聲可留；無其他語言文字。

## Audio & VFX Implementation Notes
- 音畫同步：鼓擊對應腳步與槌落點；衝擊波 bloom 強度隨低頻包絡推升；耳鳴後 120ms 恢復環境。
- VFX：Niagara/Graph 以 Flowmap 控制衝擊波扭曲；Fresnel 邊緣光強調戰紋；破碎用 RBD flipbook 轉 sprite，Alpha 外擴 1px。
- 震動：衝擊瞬間畫面微抖 0.8 像素，符合漫畫感；UI 蓄力條在左上角小尺寸，隨時間填滿。

## Next Episode / Spin-off Ideas
- 續集 Hook：巨蛇倒地後露出石核，下一集探討「石核吸收」的副作用；或新敵人遠處監視。
- 番外：訓練室日常，蓮教導學員如何護膝拉伸；迷因向：把「ドゴォン」做成節奏遊戲短片。

## Changelog vs Previous Episode
- Episode 01 為開場集，無前集差異；建立 baseline：戰槌完好、護膝舊傷存在、蓄力條樣式定義為黑底黃填充。

## AGENT Self-Check
- 結構：已含 Master Prompt、Act/Beat/Angle（12 幕×1.2s）、時間軸標註、Technical Specs、Platform Layer、Negative Instructions。
- Physics & PBR：每幕明記重力、慣性、粗糙度/金屬度/法線與光學行為，熱浪折射、粒子尺寸、衝擊速度均寫明。
- Stylepacks：完整內嵌 `_core` 及 Light Glyph Anime，新增 Hammered Noon Manga Burst 並標註適用/衝突/Default；未混用禁用風格。
- Continuity：新增 Continuity Layer（軸線、光源、焦段曲線）、Boss/Ren 狀態時間線；各 Beat 以「延續」語氣標註 Stage 與焦段群組；Changelog 保持 baseline，Hook B 改為獨立 hook_cut_prompt。
- 風險揭露：假設蛇體型與無旁白台詞已列於 Assumptions；若需改變需人工確認。
- QA checklist：已內嵌，可供逐項勾選。

## Lighting & Material Matrix
- Key Light Map：
  - Beat 01–03：硬光直射 5600–5800K，光比 1:4，地面熱返光 5%；
  - Beat 04–07：側逆光 5600K，光比 1:3，衝擊瞬間加入塵埃體積散射；
  - Beat 08–09：側光 5600K，背光 rim 0.85；
  - Beat 10–12：背光＋光束穿雲，漫畫格時全局高對比黑白速度線，彩色僅保留衝擊與武器。
- Material Roughness / Metalness Quick Ref：
  - 石階：R 0.72 / M 0，粗法線 0.8；
  - 巨蛇石甲：R 0.78 / M 0，置換 0.4 cm；
  - 戰槌金屬：R 0.18 / M 0.8，刮痕置換 0.06 cm，邊緣 Fresnel 0.7；
  - 戰甲碳纖維：R 0.38 / M 0.15，法線 0.35；
  - 護膝橡膠：R 0.42 / M 0.05，磨損斑駁 0.12；
  - 衝擊波粒子：Emission 3.2，Bloom 0.28，邊緣硬度 0.65。
- Physics Hooks：
  - 踏步/揮槌地面回饋以 PhysX impulse 900N，碎石落地音量對應速度；
  - 熱浪折射層在地面 0.3–1.2m 間顫動，折射貼圖速率 1.6；
  - 毒霧粒子衰減時間 1.2s，重力影響 30%，擴散係數 0.8。

## Color & UI Notes
- 配色：黑（#0b0b0f）＋警示黃（#ffc400）為主；岩地中性色 #b8b1a5；毒霧綠灰 #6c7a6f；漫畫格速度線黑白。
- UI：左上角蓄力條黑底黃填，刻度 10 格，Beat 04–05 逐格亮；Beat 09 滿格閃；Beat 11 清零後隱藏。
- 擬聲字：使用粗邊黑框＋金黃內發光，置於畫面不遮擋主體；「ドゴォン」需有動態抖動 2px。

## Safety & Rating
- 分級：PG-13，無血腥、無斷肢；石屑與塵土替代血液效果。
- 服裝端正，無裸露；避免鏡頭穿透角色模型；無可讀文件或符號。
- 相機晃動限制在 3% 內，避免眩暈；漫畫格閃白不超過 2 frame，提供光敏安全。

## Delivery Checklist
- 解析度 1080x1920；立體聲 48kHz，-14 LUFS；保持字幕安全區 10% 內。
- 匯出同時保留無字幕版本；確認黑黃顏色在手機 SDR 不溢色。
- 檔名建議：pressurized-hammer-ep01_master.mp4；附 LUT 與粒子設定檔。

## Backup Shots（若主鏡失敗可替換）
- Beat 04 備用：腳步特寫 75mm，腳下裂紋與圓形 UI；
- Beat 06 備用：俯視 24mm 看到衝擊波圓環全貌；
- Beat 10 備用：側向長焦 85mm 窄景，只留槌軌與蛇頭。


## QA Runbook Notes
- 確認每幕時間碼：01 0.0–1.2、02 1.2–2.4、03 2.4–3.6、04 3.6–4.8、05 4.8–6.0、06 6.0–7.2、07 7.2–8.4、08 8.4–9.6、09 9.6–10.8、10 10.8–12.0、11 12.0–13.2、12 13.2–15.0。
- LUT/色調：應用 filmic LUT 後調整黑線銳度，避免去飽和超過 6%；高光裁切控制在 0.98 內。
- 粒子：衝擊波 sprite sheet 採 16x16，高速旋轉不得產生鍍膜條紋；塵埃粒子數限制 45k 以免壓縮噪點。
- 聲音：鼓點峰值 -4 dB，耳鳴部分 -12 dB；毒霧尖嘯收斂在 3–6 kHz，避免刺耳。
- 版控：保留 seed/參數表，列出攝影機焦段與快門角；存檔含 JSON 設定。
- 轉場：Beat 08 羽化轉 09，Beat 11 匹配剪接回 Beat 12；其他使用硬切或光源遮擋。


## Backup Audio Variations
- 若需迷因版：在 Beat 11 衝擊後加入 0.4s 低頻 sidechain pump，並把「ドゴォン」做 pitch down -2 semitone。
- 若需故事版：保留更長的尾聲風聲 1.5s，縮短耳鳴至 0.15s，讓收尾台詞更清晰。
- 若需訓練版：每組擊打前加入輕聲數拍「1、2」，音量 -18 dB，維持節奏感。


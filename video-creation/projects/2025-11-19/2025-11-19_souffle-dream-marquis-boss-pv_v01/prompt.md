# 異界編譯 EP10 — 織夢侯・瑟芙蕾 BOSS PV Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-19_souffle-dream-marquis-boss-pv_v01/script.md

## 一句話題材
階梯盡頭的浮空庭園裡，織夢侯・瑟芙蕾以夢層位移與夢境剪輯重排入侵者的記憶，展開安眠庭園與夢剪刀審判，最後在白金曝光的 Phase 3 中用一句「別急著醒」剪黑整場 BOSS PV。

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

### Style Pack：Dream Marquis Lucid Elegy Look（新樣板）
```yaml
name: Dream Marquis Lucid Elegy Look
line_enhancement: watercolor_silver_edge
noise_reduction: velvet_grain_soften
contrast_profile: low_mid_contrast_with_specular_spikes
color_palette:
  primaries: [moonstone_white, mist_blue, hush_lilac]
  accents: [pale_gold, prism_rose, opaline_teal]
skin_tone: cold_porcelain_with_pearl_sheen
lighting:
  key: volumetric_moonbeam (3000–3600K)
  fill: stairwell_reflective_pool (soft cyan bounce)
  rim: halo_fragment_light (pale gold 4200K)
materials:
  robe: semi_transparent_moire_silk
  mask: glass_shard_caustic
  floating_islands: moss_marble + micro lanterns
lens_treatment:
  bloom: dreamy 0.42 (sync to halo pulses)
  chromatic_aberration: 0.02 inward
  focus_breath: eased 220ms to mimic lucid breath
notes:
  - 所有高光以柔軟白金呈現，避免硬陰影；利用 slow shutter smear 表現夢境流動。
  - 反重力庭園與斷裂階梯光環需保持 15–20% 透明度並帶粒子拖尾。
  - 無血腥、無尖銳破皮；以 UI 紋理與光粒取代暴力細節。
```

### Style Pack：Dream Marquis Lucid Elegy VFX（新樣板）
```yaml
name: Dream Marquis Lucid Elegy VFX
niagara_presets:
  - dream_layer_pull (radial stretch + refraction)
  - somnolent_pollen_delay (slow particle fog)
  - halo_stair_fragment (floating ribbon stairs)
unity_vfx_graph:
  - Memory.Panel.Float.vfx
  - Garden.Fragment.Orbit.vfx
  - Scissor.Path.Cut.vfx
houdini_flipbooks:
  - glass_mask_reflect_loop
  - butterfly_ui_particle
  - timeline_slice_stutter
shader_controls:
  refract_strength: 0.35 (Phase 1) → 0.55 (Phase 3)
  pollen_lag_frames: 3
  scissor_cut_alpha: 0 → 1 within 4 frames
bloom_profile:
  idle: 0.22
  ability_peak: 0.58
  phase3_overexposed: 0.75
sync_hooks:
  layer_shift: sync_to_low_sub_boom
  montage_drag: sync_to_ui_clicks
  final_cut: sync_to_scissor_snap + silence
notes:
  - 夢境剪輯段需用 Memory.Panel.Float 疊出分割畫面並於角落顯示浮動時間軸。
  - Somnolent Garden 花粉會把前景拖影 1 frame，透過 pollen_lag_frames 控制延遲感。
  - 夢剪刀軌跡需以 Scissor.Path.Cut.vfx 讓畫面被橫向切裂並露出星光縫隙後熄滅。
```

### Style Pack：Dream Marquis Lucid Elegy Audio（新樣板）
```yaml
name: Dream Marquis Lucid Elegy Audio
bed_layers:
  - glass_wind_chime_pad
  - moonwater_subpulse
  - lucid_heartbeat_low
accent_fx:
  - ui_chime_drag (per tile move)
  - pollen_muffle_whoosh
  - scissor_crystal_snap
  - halo_orbit_gliss
vocal_elements:
  - androgynous_whisper (processed, bilingual murmur)
  - distant_choir_ah (no lyrics)
transient_rules:
  layer_shift: sub_boom + reverse_riser
  pollen_bloom: soft_brush + breathy_swell
  timeline_cut: click + muted_whoosh
  final_cut: crystal_snap + vacuum_drop
mix_notes:
  - 音樂使用 70 BPM 絲絨弦樂墊疊玻璃打擊，保持 -10 dB 峰值。
  - 人聲僅作氣音低語且置於 -14 dB，避免蓋過剪刀瞬音。
  - Phase 3 的白金曝光要加入 high shelf -2 dB，防止過曝同時保留氣音亮度。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Dream Marquis Lucid Elegy｜16:9｜24fps｜唯美夢境審判質感)
「月下夢境層階梯盡頭；斷裂階梯光環、反重力浮島庭園、光粒蝴蝶；織夢侯・瑟芙蕾以夢層位移拖拽闖入者、剪輯記憶並展開巨型夢剪刀的一場 BOSS 審判。」
鏡頭：Act1 24mm 低角滑軌→Beat2 85mm 眼部特寫→Beat3 35mm 穩定器繞拍→Beat4 主觀 28mm 俯衝；Act2 混用 32–50mm 跟隨 UI 片段→Beat7 45mm 微推→Beat8 55mm 對打；Act3 40mm 仰視夢剪刀→Beat10 24mm 拉遠平台→Beat11 32mm 推近白金曝光→Beat12 65mm 半身特寫，最後硬切黑。
表演：瑟芙蕾整程保持輕柔微笑與慢語，手勢像拖曳介面；玩家幻影焦躁衝刺卻逐格被剪除； Phase 3 笑意收斂為安靜審判。
臉型/髮型：中性柔和面龐、銀白髮帶粉藍漸層及肩微捲，左臉覆透明碎面面具反射夢片段；虹膜右金左湖藍並有微型幾何紋浮動。
構圖：斷裂階梯光環常位於後景 15% 留白；浮島庭園提供前中後層；夢剪刀與 UI 面板交錯形成 X 型導線；水面倒影偶爾佔下緣 10%。
寫實細節：長外袍半透明灰藍×乳白、袖口內側星圖刺繡；戒指層環施法時旋轉；足跡短暫泛出水面反光；夢剪刀材質似玻璃＋流動星雲。
無字幕、無商標/Logo/水印。」

鏡頭語法：空間建立 24–35mm、表情與手勢 50–75mm、夢剪刀壓迫使用 85–100mm；
光圈 {Act1 T3.5 保景深、Act2 T2.8 柔化記憶邊界、Act3 T2.2 放大高光拖尾}；快門角 {常規 180°、Layer Shift 144° 拉長流動、Final Cut 200° 製造拖影}；
對焦 {主視線為單點眼、夢層轉換採層次前→中→後漸切，Phase 3 呼吸拉焦在蝴蝶與剪刀上}。
光影：月光+體積霧逆光勾勒身形，浮島小燈作暖色補光；安眠庭園花粉讓空氣呈粉霧散射；白金 Phase 3 將色溫推至 4200K 並提高對比但保持柔焦。
色調/LUT：去飽和 5%，陰影保微藍，肌膚維持冷白珠光，高光偏暖以顯神性；UI 面板使用粉金線描避免螢光過強。
聲音：glass_wind_chime_pad 與 moonwater_subpulse 為底，ui_chime_drag 配合夢境剪輯，pollen_muffle_whoosh 作動作延遲，scissor_crystal_snap 作終止；低語 androgynous_whisper 貫穿。
轉場：星階光暈匹配切→玻璃碎光遮擋→水面反射鞭移→白金曝光羽化 0.5s→夢剪刀剪切硬切黑。
安全：無血腥、無可讀真實文字、光粒頻率低於安全閃爍。
```

### Camera Continuity
- EP9 結束於 DEBUGGER 黑場與燁程 HUD 崩潰，本集開場以同樣黑場拉出月光階梯，並將 HUD 殘餘幾何線條化為瑟芙蕾虹膜內的 UI 紋，維持介面語言一致性。
- 延續嘉年華王支線中「浮動光粒」視覺語言，將其在本集轉化為光粒蝴蝶，節奏與先前 72 BPM 燈光脈衝一致但亮度下降 15%，避免突兀。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–4.8s）
意圖：建立階梯盡頭與瑟芙蕾登場儀式感
基調：靜謐預兆
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：無盡階梯、斷裂光環、長袍、浮島剪影

#### Beat 1（0.0–1.2s）
重點：階梯盡頭剪影與光環初現
Blocking：鏡頭貼著階梯表面往上推，瑟芙蕾在遠端背對觀眾，長袍隨風漂浮。
Camera：
- 運鏡：24mm 低角滑軌向上推 6m
- 焦段/機位：24mm 腳下 0.3m，仰視 20°
- 對焦：層次前階→中階→人物
- 快門角：180；拍點：鐘聲敲擊
光影：月光斜切階梯，背光勾勒人物輪廓
色調/LUT：藍灰階梯＋白金高光
聲音：遠處鐘聲＋玻璃風鈴墊
轉場：鐘聲尾音匹配 → Angle 1

Angle 1（0.0–1.2s）
構圖：中央對稱，階梯引導線
內容：瑟芙蕾剪影與斷裂光環
補充：微弱光粒逆向飄移
安全：無可讀符號

#### Beat 2（1.2–2.4s）
重點：異色瞳與碎面面具特寫
Blocking：瑟芙蕾回眸，眼部特寫顯示 UI 紋，面具反射夢片段。
Camera：
- 運鏡：穩定器微推 85mm
- 焦段/機位：85mm 眼高
- 對焦：單點右眼再拉至左眼
- 快門角：180；拍點：低語登場
光影：側逆光營造虹膜折射
色調/LUT：膚色冷白、瞳孔金藍
聲音：androgynous_whisper：「你醒著，還是在做夢？」
轉場：面具反射閃光 → Angle 2

Angle 2（1.2–2.4s）
構圖：對角線分割，面具佔左側
內容：眼睛與 UI 紋浮動
補充：面具內映出陌生夢境
安全：僅抽象影像

#### Beat 3（2.4–3.6s）
重點：反重力庭園展開
Blocking：瑟芙蕾轉身，腰後浮島展開並緩慢環繞。
Camera：
- 運鏡：35mm 半圓繞拍
- 焦段/機位：35mm 胸高
- 對焦：單點人物，浮島以層次景深
- 快門角：180；拍點：浮島亮起
光影：浮島暖光與月光冷光混合
色調/LUT：灰藍袍＋粉金微光
聲音：halo_orbit_gliss + wind chime pad
轉場：浮島通過鏡頭遮擋 → Angle 3

Angle 3（2.4–3.6s）
構圖：三分線，人物偏右，浮島於左後
內容：路燈、樹、長椅漂浮
補充：光粒蝴蝶繞圈
安全：無額外角色

#### Beat 4（3.6–4.8s）
重點：夢層位移墜落 POV
Blocking：玩家視角被拉進瑟芙蕾掌心，景物拉伸後整個墜入下一層。
Camera：
- 運鏡：28mm 主觀俯衝
- 焦段/機位：28mm 頭部高度
- 對焦：層次前方手勢→遠景階梯
- 快門角：144；拍點：低頻轟鳴
光影：畫面被拉出拖影，中心亮點
色調/LUT：藍灰被拉成水波狀
聲音：sub_boom + reverse_riser，環境音抽離
轉場：液態變形匹配 → Angle 4

Angle 4（3.6–4.8s）
構圖：中央手勢向鏡頭伸出
內容：瑟芙蕾手掌拖曳 UI 線
補充：畫面四周拉伸成水流
安全：無外部物件

### Act 2（4.8–9.6s）
意圖：展示夢境剪輯與安眠庭園造成的延遲審判
基調：詭譎迷醉
節奏域：穩定1.5–2.4
美術要點：記憶面板、Somnolent Garden、UI 符號

#### Beat 5（4.8–6.0s）
重點：童年夢境破碎
Blocking：多個記憶場景化成浮動面板，逐塊碎裂。
Camera：
- 運鏡：32mm 廣角定鏡+快速變焦
- 焦段/機位：32mm 眼高
- 對焦：層次切換面板
- 快門角：180；拍點：面板破裂
光影：面板內自帶暖光，外部冷霧
色調/LUT：內暖外冷對比
聲音：拉長的兒童笑聲 + Memory.Panel UI click
轉場：碎片飛向右側 → Angle 5

Angle 5（4.8–6.0s）
構圖：前中後皆為漂浮面板
內容：教室、家裡、街道片段
補充：邊緣 glitch 線條
安全：文字模糊不可讀

#### Beat 6（6.0–7.2s）
重點：夢境剪輯手勢
Blocking：瑟芙蕾於中景捏起夢片段，拖曳放入新場景，背景跟著拼合。
Camera：
- 運鏡：40mm 微推
- 焦段/機位：40mm 胸高
- 對焦：單點手指，再拉到方塊
- 快門角：180；拍點：每次落點
光影：指尖有微亮 UI 光
色調/LUT：柔和粉藍
聲音：ui_chime_drag 對應操作
轉場：面板充滿畫面遮擋 → Angle 6

Angle 6（6.0–7.2s）
構圖：前景手指、背景重組城市
內容：面板像剪輯時間軸
補充：HUD 漂浮字元以符號顯示
安全：符號為虛構語言

#### Beat 7（7.2–8.4s）
重點：安眠庭園花粉延遲
Blocking：瑟芙蕾彈指，腳下花海盛開，粉霧擴散包覆鏡頭邊緣。
Camera：
- 運鏡：45mm 半身斜側
- 焦段/機位：45mm 眼高
- 對焦：呼吸拉焦腳下→粉霧
- 快門角：200；拍點：花粉爆
光影：下方暖色逆光，上方冷月
色調/LUT：粉金霧覆藍背景
聲音：pollen_muffle_whoosh + 加重呼吸
轉場：粉霧覆滿鏡頭 → Angle 7

Angle 7（7.2–8.4s）
構圖：中央瑟芙蕾，前景失焦花粉
內容：花瓣飄浮並拖影一格
補充：蝴蝶粒子變成 UI 符號再散開
安全：粉霧遮蔽周圍

#### Beat 8（8.4–9.6s）
重點：玩家動作被剪掉
Blocking：玩家幻影衝刺揮擊，但動作於半途中被剪斷停止。
Camera：
- 運鏡：55mm 第三人稱追隨
- 焦段/機位：55mm 胸高略仰
- 對焦：單點玩家，再跳至瑟芙蕾
- 快門角：180；拍點：剪刀聲
光影：前景粉霧造成拖影
色調/LUT：玩家輪廓被粉霧淡化
聲音：scissor_crystal_snap + 動作被抽空
轉場：畫面跳一格匹配 → Angle 8

Angle 8（8.4–9.6s）
構圖：玩家在左前景定格，瑟芙蕾於右後
內容：攻擊動作被剪掉僅剩殘影
補充：剪掉處出現細線破口
安全：無血腥

### Act 3（9.6–15.0s）
意圖：展示夢剪刀、記憶敵人與 Phase 3 白金反轉並以標語收束
基調：危險而唯美
節奏域：加速2.4–3.0
美術要點：巨型夢剪刀、浮島戰場、白金曝光

#### Beat 9（9.6–10.8s）
重點：夢剪刀全貌
Blocking：戒指展開成巨剪，瑟芙蕾優雅揮出弧線。
Camera：
- 運鏡：40mm 低角仰視
- 焦段/機位：40mm 膝高
- 對焦：呼吸拉焦戒指→剪刀刃
- 快門角：180；拍點：剪刀完全展開
光影：剪刀內有星雲反射
色調/LUT：玻璃白＋粉金
聲音：scissor_crystal_snap + halo_orbit_gliss
轉場：剪刀刃掃過畫面 → Angle 9

Angle 9（9.6–10.8s）
構圖：中央 X 型剪刀軌跡
內容：剪刀刃內流動星河
補充：鏡頭鏡面反射浮島
安全：無暴力

#### Beat 10（10.8–12.0s）
重點：記憶敵人召喚
Blocking：多層平台浮現，過往敵人幻影站位，瑟芙蕾如指揮家揮動。
Camera：
- 運鏡：24mm 拉遠 + 小幅上升
- 焦段/機位：24mm 高度 5m 俯視
- 對焦：層次平台
- 快門角：180；拍點：幻影成形
光影：平台邊緣月光勾勒
色調/LUT：粉藍主色，幻影以淡金描邊
聲音：弦樂鼓點加快，多重遠吼被壓扁
轉場：平台裂縫匹配 → Angle 10

Angle 10（10.8–12.0s）
構圖：前景平台指向中心人物
內容：不同記憶敵人以霧化身顯現
補充：HUD 符號漂浮於平台上方
安全：敵人輪廓模糊無血

#### Beat 11（12.0–13.2s）
重點：白金 Phase 3 反轉
Blocking：全畫面曝光翻轉成白金柔光，蝴蝶與光環漂浮，危險壓迫升高。
Camera：
- 運鏡：32mm 高速推近→白光→拉回
- 焦段/機位：32mm 眼高
- 對焦：呼吸拉焦蝴蝶→瑟芙蕾
- 快門角：200；拍點：曝光翻轉
光影：全場白金高亮+體積霧
色調/LUT：高曝光白金 + 粉色邊
聲音：distant_choir_ah + 音樂衝頂
轉場：白光羽化 0.5s → Angle 11

Angle 11（12.0–13.2s）
構圖：剪影置中，光環碎階漂浮
內容：蝴蝶粒子在曝光中慢動
補充：花粉成為 UI 符號再解構
安全：閃光速度低於安全值

#### Beat 12（13.2–15.0s）
重點：標語與最後一剪
Blocking：半身特寫，瑟芙蕾對鏡頭低語；畫面浮現字幕後被夢剪刀剪黑。
Camera：
- 運鏡：65mm 微推
- 焦段/機位：65mm 胸高
- 對焦：單點眼
- 快門角：180；拍點：剪刀下落
光影：臉部柔和前光，背光 halo
色調/LUT：冷白肌膚＋粉金反射
聲音：低語「別急著醒。」→ crystal snap + vacuum silence
轉場：剪刀沿畫面中心剪開 → 黑場

Angle 12（13.2–15.0s）
構圖：中央半身，字幕置下方
內容：字幕「織夢侯・瑟芙蕾 / Dreams are the blueprint.」
補充：剪刀從上向下剪斷畫面
安全：字幕為自家標語、無商標


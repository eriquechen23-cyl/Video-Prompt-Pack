# 異界編譯 EP9 — 錯紋獵王覺醒 PV Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-18_glitchbone-sovereign-transform_v01/script.md

## 一句話題材
邊境外的錯紋盆地化作巨型陣式，錯紋獵王從倒轉屍山中組裝完成，啟動 Format Field 並與遠在城牆上的燁程互鎖視線，HUD 被 DEBUGGER 警示佔滿後啪地落入黑場。

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

### Style Pack：Glitchbone Sovereign Cataclysm Look（新樣板）
```yaml
name: Glitchbone Sovereign Cataclysm Look
line_enhancement: razor_wire_outline
noise_reduction: glitchgrain_preserve
contrast_profile: oppressive_high_contrast
color_palette:
  primaries: [mud_black, storm_purple, ash_bone]
  accents: [neon_err_green, error_red, static_white]
  skin_tone: cold_sienna (for human inserts)
glitch_layers:
  chroma_shift: tri_offset_neon
  scanline_break: 0.36
  tile_offset_interval: 6 frames
material_calls:
  bone_surface: wet_shard_specular
  wireframe_sections: emissive_gridline
  mud_ground: reflective_clay_streaks
volumetric:
  basin_fog: low_lying_data_smog
  lightning: violet_sheet_flash
lens_treatment:
  warp_amount: 0.08 (beat-synced)
  rolling_shutter_drag: 2 frames during jumps
notes:
  - 大獸近身時啟用 chroma_shift 疊影，呈現 UI 破圖效果。
  - 線框半渲染部位保持透明度 45%，可見節點閃爍。
  - 人類角色僅佔數幕，膚色需保持冷暖對比並被 HUD 紅字反射。
  - 地面積水映出陣列電路，必要時以差分材質顯示時間回溯拖影。
```

### Style Pack：Glitchbone Sovereign Cataclysm VFX（新樣板）
```yaml
name: Glitchbone Sovereign Cataclysm VFX
niagara_presets:
  - corpse_rewind_reverse_flow
  - format_field_array_bloom
  - minion_unrender_drop
unity_vfx_graph:
  - Errormesh.GridTessellation.vfx
  - Sovereign.MultiSkull.Assemble.vfx
  - HUD.Overflow.Warn.vfx
houdini_flipbooks:
  - glitch_tile_slice
  - boneplate_duplicate_snap
  - neon_core_burst
shader_controls:
  error_line_overlap: 0.62
  wireframe_alpha: 0.45
  pupil_glow_intensity: 0.78
  hud_noise_mix: 0.55
bloom_profile:
  idle: 0.18
  anomaly_peak: 0.72
  blackcut_decay: 0.05
sync_hooks:
  rewind_suck: align_to_reverse_hits
  minion_drop: sync_to_percussion_triplet
  format_field: sync_to_sub_boom
notes:
  - Format Field 展開需將地面覆蓋 32×32 陣列光紋，並在 0.2s 內自中心向外點亮。
  - 背上半渲染獸掉落時，骨骼需在空中補齊缺肢後著地成型，殘留的線框粒子隨風散去。
  - DEBUGGER 文字出現前需先以 hud_noise_mix 注入雜訊閃爍，再瞬間切黑以保持震撼。
```

### Style Pack：Glitchbone Sovereign Cataclysm Audio（新樣板）
```yaml
name: Glitchbone Sovereign Cataclysm Audio
bed_layers:
  - basin_wind_modulated
  - corrupted_drive_spin
  - sub_drone_errpulse
accent_fx:
  - glitch_log_ping_hi
  - bone_grind_reverse
  - format_field_boom
  - hud_stack_warning
vocal_elements:
  - machine_chant_low (wordless processed choir)
  - debugger_whisper (stereo whisper at -16 dB)
transient_rules:
  rewind_event: reverse_whoosh + click
  minion_drop: impact_thud layered with buffer_skip
  format_field: infra_hit + rising_sine
  debugger_flash: digital_shutdown_beep
mix_notes:
  - 所有 HUD 警示維持 -10 dB 峰值以免蓋過低頻轟鳴。
  - 盆地風聲需帶顆粒雜訊，並依畫面跳幀輕微抽動音量。
  - 黑場切換時所有音層於 80ms 內抽離，僅留 debugger_flash 作收。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Glitchbone Sovereign Cataclysm｜2.39:1｜24fps｜錯紋盆地終極異常質感)
「午夜後的錯紋盆地；陣列裂谷、倒轉屍山、螢綠錯誤閃電；錯紋獵王從三層頭骨與半渲染軀體中完全展開，啟動 Format Field 並以 DEBUGGER 視線鎖定燁程。」
鏡頭：Act1 24mm 高空俯視→Beat2 側俯滑軌→Beat3 骨板特寫 75mm→Beat4 32mm 升降→Act2 35–50mm 交替、加入穩定器繞頭→Beat7 加入手持≤3% 模擬畫面抖動→Beat8 後上方俯視→Act3 40mm 低角仰視巨爪→Beat10 85mm 望遠鎖燁程→Beat11 主觀 HUD 35mm→Beat12 100mm 超近瞳孔後硬切黑。
表演：錯紋獵王像自動化程序，動作斷續卻極端精準；背上半成品獸跌落抽搐；燁程遠景中緊握軌跡指令，眼神震驚但鎮定；系統聲線冷靜播報 Error Log。
臉型/髮型：燁程黑髮被風雨貼後腦、臉頰沾泥；錯紋獵王三層頭骨露出螢綠矩形眼；背上小型獵骨獸骨板缺損露出電路線框。
構圖：前景常留 10–15% 陣列紋路作導線；中景為獵王軀體或 HUD；遠景保留紫藍錯紋天空；跳幀視覺搭配 UI 重影。
寫實細節：泥地濕亮反射電路；骨板表面重複貼圖可見 seam；線框節點在風中抖動；燁程 HUD 彈滿 Error Log 紅框與 DEBUGGER DETECTED 粗體字；終場黑場前瞳孔縮成細線。
無字幕、無商標/Logo/水印。」

鏡頭語法：開場 24–35mm 建立空間，變形段落 35–50mm 聚焦頭骨與環境崩壞，燁程反應用 75–100mm 壓縮距離；
光圈 {Act1 T4.0 保景深、Act2 T3.2 突出骨層、Act3 T2.2 讓 HUD 發光軌跡融入背景}；快門角 {倒轉與跳幀 144° 增強斷裂感，常規 180°，Format Field 衝擊 200° 拉長殘影}；
對焦 {層次對焦讓骨板→頭骨→線框依序銳利，Beat10 鎖燁程眼，Beat12 呼吸拉焦於瞳孔與 HUD 倒影}。
光影：紫藍錯誤雲發出脈衝頂光，地面由螢綠陣紋補光；燁程處於邊境火把微光；Format Field 爆開時全場轉冷綠；色溫 {天空4200K、地面綠光3800K、人像4300K}；
對比 {全程高對比，黑場前瞬間拉低背景亮度}；眼神光 {巨獸透過螢綠瞳孔自發，燁程由 HUD 反射提供}。
色調/LUT：環境去飽和 8%，僅螢綠錯誤線與紅色 WARNING 保持高亮；線框部位以冷灰+霧白顯示未渲染質地；燁程膚色保冷暖對比。
聲音：basin_wind_modulated 與 corrupted_drive_spin 疊加骨磨逆轉聲；Format Field 使用 infra_hit + rising_sine；HUD 疊加 hud_stack_warning、glitch_log_ping_hi；debugger_whisper 繞場低語；終場 digital_shutdown_beep 切黑。
轉場：骨泥拖影作匹配→錯誤閃電遮擋→線框閃白作鞭移→HUD 報錯作硬切→黑場直接關機聲淡出。
安全：HUD 文本採虛構代碼；血液以螢光流體替代；黑場前無突兀閃頻超過安全閃爍率。
```

### Camera Continuity
- EP8 結束時燁程右眼倒映 `/compiler_log` 與錯綠光點，本集 Act1 Beat1 承接該綠光在邊境天空延伸成錯紋盆地電路，維持 HUD 玻璃厚度與 auric gold→此處轉換成 neon_err_green 以示權限衝突。
- 錯紋獵王曾於 EP7 遠景出現螢綠瞳孔，此次特寫需維持同樣狹長瞳比例但增加 UI 重影；跳幀效果沿用上一集中 error_feedback.glitch_amount 0.36 的節奏，再疊加新的 chroma_shift。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立錯紋盆地與屍山倒轉的異常徵兆
基調：壓迫預兆
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：盆地陣列、屍山、紫藍錯誤雲、泥面反射

#### Beat 1（0.0–1.2s）
重點：錯紋盆地全景揭露
Blocking：高空俯視邊境外的盆地，地面出現規律卻扭曲的陣列裂縫，紫藍電路雲壓頂並閃出錯位方格。
Camera：
- 運鏡：24mm 無人機式俯角滑行 20m
- 焦段/機位：24mm 150m 高度俯拍
- 對焦：層次前→中→遠
- 快門角：180；拍點：遠處閃電
光影：體積光穿過雲層照射地面陣紋
色調/LUT：地表冷灰，陣紋螢綠高亮
聲音：basin_wind_modulated + distant beast echo
轉場：雲中閃電白光 → Angle 2

Angle 1（0.0–1.2s）
構圖：中央對稱，陣列裂縫形成棋盤
內容：邊境城牆在遠處，盆地佔畫面 80%
補充：空氣中細碎像素粒子飄浮
安全：無可讀符號

#### Beat 2（1.2–2.4s）
重點：屍山倒轉重組
Blocking：鏡頭下降至側俯角，看見骨獸屍山像被倒帶，肢體滑回中心，泥水拖出逆向痕。
Camera：
- 運鏡：28mm 側俯滑軌 8m
- 焦段/機位：28mm 高於骨山 6m
- 對焦：單點骨板再拉焦至中心能量核
- 快門角：144；拍點：骨頭啪合
光影：逆轉時產生逆向火花
色調/LUT：骨板灰白帶錯綠反光
聲音：bone_grind_reverse 疊 sub_drone
轉場：飛散泥水遮擋 → Angle 3

Angle 2（1.2–2.4s）
構圖：三分線，骨山位左下，中心開啟光洞
內容：屍體滑入光洞
補充：泥水線條向後拉形成拖影
安全：血漬改為暗色泥

#### Beat 3（2.4–3.6s）
重點：骨板複製貼上
Blocking：極近骨板表面，電路紋同一段重疊三層並閃動，骨板被磁力拉起。
Camera：
- 運鏡：75mm 特寫穩定器微推
- 焦段/機位：75mm 與骨板距離 0.5m
- 對焦：單點電路紋，轉至骨板邊緣
- 快門角：180；拍點：紋路亮度衝頂
光影：微光掃描骨面
色調/LUT：骨面灰藍，螢綠線條交疊
聲音：glitch_log_ping_hi + 靜電滋滋
轉場：骨板朝鏡頭翻轉 → Angle 4

Angle 3（2.4–3.6s）
構圖：中央大面積骨板
內容：複製貼圖錯位清晰可見
補充：小塊線框空洞穿透
安全：僅抽象紋路

#### Beat 4（3.6–5.0s）
重點：半渲染巨獸輪廓成形
Blocking：拉遠顯示大量骨板與線框節點飄浮組成四足輪廓，身體有一半為實體骨甲、另一半保持線框。
Camera：
- 運鏡：32mm 起重機式抬升 + 繞半圈
- 焦段/機位：32mm 與中心距離 12m
- 對焦：層次線框→實體骨甲
- 快門角：180；拍點：骨骼合攏聲
光影：線框區域僅由節點散光照明
色調/LUT：線框透明 45%，骨板濕亮
聲音：machine_chant_low 逐步增強
轉場：線框節點閃白 → Angle 5

Angle 4（3.6–5.0s）
構圖：中央巨獸、前景漂浮碎片
內容：半渲染身軀於盆地中央浮現
補充：背景錯位格線隨風扭曲
安全：無多餘角色

### Act 2（5.0–9.6s）
意圖：聚焦三層頭骨與環境當機，營造 BOSS 變身壓力
基調：高壓驚異
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：三層頭骨、螢綠矩形眼、環境格狀 BUG、背上半成品獸

#### Beat 5（5.0–6.0s）
重點：三層頭骨組裝
Blocking：鏡頭貼向頭部，外層獸頭骨閉合，中層類人頭骨旋轉，內層多邊形骨核脈動。
Camera：
- 運鏡：50mm 半圓繞拍
- 焦段/機位：50mm 與頭部距離 3m
- 對焦：層次切換三層頭骨
- 快門角：180；拍點：骨核亮起
光影：逆光勾邊，骨縫透光
色調/LUT：頭骨冷白＋螢綠
聲音：骨節喀喀 + iris-like ping
轉場：骨縫閃光 → Angle 6

Angle 5（5.0–6.0s）
構圖：三分線，頭骨佔右側
內容：外層獸頭向鏡頭合攏
補充：背景線框模糊
安全：無人像

#### Beat 6（6.0–7.2s）
重點：矩形眼刷新
Blocking：極近頭骨裂縫，螢綠矩形眼在裂縫間跳出又關閉，最終僅留中央巨眼盯向鏡頭。
Camera：
- 運鏡：100mm 定機
- 焦段/機位：100mm 與眼距 0.3m
- 對焦：單點刷新眼
- 快門角：200；拍點：眼齊亮瞬間
光影：眼孔內部自發光，周邊暗化
色調/LUT：螢綠高飽和對比暗骨
聲音：glassy UI blips + sub hit
轉場：眼睛放出綠光掃過 → Angle 7

Angle 6（6.0–7.2s）
構圖：極近中央，眼窩填滿畫面
內容：矩形眼在裂縫跳動
補充：UI 殘影 overlay
安全：文字為虛構

#### Beat 7（7.2–8.4s）
重點：環境 BUG 化
Blocking：鏡頭拉開顯示盆地邊緣樹木、岩石被切成格子並錯位，附近獵骨獸瞬間化為線框再貼回。
Camera：
- 運鏡：35mm 手持≤3% 左右掃動
- 焦段/機位：35mm 眼高
- 對焦：層次環境→線框獸
- 快門角：172；拍點：格子切割
光影：錯位區塊亮度跳動
色調/LUT：局部飽和錯位
聲音：environment glitch clicks + high whine
轉場：畫面被格線 wipe → Angle 8

Angle 7（7.2–8.4s）
構圖：前景樹幹被切割，中景獸體線框
內容：場景格子化清晰
補充：地面 UI tile 疊在泥上
安全：無人像

#### Beat 8（8.4–9.6s）
重點：背上半成品獸掉落
Blocking：從背部俯視，半渲染獵骨獸一隻隻扯出，邊掉邊補齊缺肢，落地後衝散。
Camera：
- 運鏡：40mm 後上方俯視下降 5m
- 焦段/機位：40mm 高於背脊 4m
- 對焦：層次背脊→掉落小獸
- 快門角：156；拍點：著地震動
光影：背脊內部螢綠脈動，掉落時拖尾
色調/LUT：半渲染部位線框透視
聲音：minion_drop 音效 + bone撞地
轉場：掉落獸衝向鏡頭作遮擋 → Angle 9

Angle 8（8.4–9.6s）
構圖：背脊居中央，掉落軌跡呈弧線
內容：半渲染獸轉成實體
補充：線框殘影飄散
安全：無人像

### Act 3（9.6–15.0s）
意圖：展示 Format Field、燁程反應與 DEBUGGER 黑場
基調：終局警告
節奏域：加速2.4–3.0 → 慢入0.8–1.5
美術要點：巨爪、陣列電路、邊境 HUD、Curve Bolt UI、螢綠瞳孔與黑場

#### Beat 9（9.6–10.8s）
重點：Format Field 啟動
Blocking：巨型前肢抬起，關節像進度條亮起，再猛然拍地，整個盆地浮現螢綠陣列，HUD 跳出 WARNING。
Camera：
- 運鏡：40mm 低角仰視前肢
- 焦段/機位：40mm 腳踝高度
- 對焦：單點巨爪→擴散陣紋
- 快門角：200；拍點：落地瞬間
光影：地面螢綠爆閃並沿裂縫延伸
色調/LUT：畫面轉為綠色主調
聲音：format_field_boom + sub boom
轉場：螢綠光掃向遠景匹配 → Angle 10

Angle 9（9.6–10.8s）
構圖：低角度中央巨爪
內容：地面陣紋如 UI 展開
補充：畫面邊緣浮現【WARNING：Format Field 12%】
安全：文字為虛構

#### Beat 10（10.8–12.0s）
重點：燁程遠景 HUD 崩潰
Blocking：切到邊境城牆，燁程站在柵欄上眺望，HUD 被 Error Log 淹沒。
Camera：
- 運鏡：85mm 長焦緩推
- 焦段/機位：85mm 站位胸高
- 對焦：燁程面部→HUD 文本
- 快門角：180；拍點：Log 疊滿
光影：前景火把暖光、HUD 紅光覆臉
色調/LUT：背景冷紫，HUD 紅綠互斥
聲音：hud_stack_warning 密集、燁程喘息
轉場：HUD 視覺撲滿畫面 → Angle 11

Angle 10（10.8–12.0s）
構圖：燁程居中央，HUD 半透明層包覆
內容：邊境視角與遠方螢綠光海
補充：HUD 顯示 `Error Log Overflow`、`Debugger Candidate: Ye-Cheng`
安全：僅虛構字串

#### Beat 11（12.0–13.2s）
重點：Curve Bolt 軌跡被改寫
Blocking：燁程伸手，Curve Bolt UI 圓環半邊被錯紋干擾成雜訊，軌跡線被強制彎向 BOSS 心核。
Camera：
- 運鏡：主觀視角穩定
- 焦段/機位：虛擬35mm
- 對焦：單點軌跡線
- 快門角：180；拍點：Override 問題彈窗
光影：HUD 金線與螢綠雜訊互相撕扯
色調/LUT：半邊 UI 失色，半邊仍為 auric gold
聲音：glitch squeal + curve bolt charge
轉場：Override? 提示閃光 → Angle 12

Angle 11（12.0–13.2s）
構圖：主觀 HUD 中央顯示 `Override Trajectory? Y/N`
內容：軌跡線被折成多段折線
補充：背景 BOSS 心核對準視線
安全：無真實資料

#### Beat 12（13.2–15.0s）
重點：螢綠瞳孔映出燁程並黑場
Blocking：回到獵王超近瞳孔，瞳孔放大映出燁程與彎曲光彈，HUD 疊影顯示【DEBUGGER DETECTED】，接著瞳孔關閉，畫面啪地黑掉。
Camera：
- 運鏡：100mm 極特寫定機
- 焦段/機位：100mm 對準瞳孔
- 對焦：單點虹膜電路紋
- 快門角：180；拍點：黑場瞬間
光影：螢綠光線收斂成細線後熄滅
色調/LUT：高飽和綠→瞬間全黑
聲音：debugger_whisper 聚集→digital_shutdown_beep 收束
轉場：瞳孔合閉硬切黑場結束

Angle 12（13.2–15.0s）
構圖：瞳孔填滿畫面
內容：燁程與光軌倒映於虹膜，最終只剩一道細線
補充：黑場後 0.2s 無聲
安全：無真實資訊

---

## QA 自檢
- [x] 結構完整度 10/10：Master Prompt、Camera Continuity、12 Beat Scene Blocks 與 QA 條列皆依規範標註時間。
- [x] 敘事一致性 10/10：承接 EP8 `/compiler_log` 眼部收尾，推進至錯紋盆地 BOSS 覺醒、Format Field 與 DEBUGGER 黑場。
- [x] 視聽細節 10/10：各幕包含運鏡、光影、色調、VFX、HUD 文本與音效指令，並記錄黑場切換節奏。
- [x] 風格準確性 10/10：全片套用新 Glitchbone Sovereign Cataclysm Look/VFX/Audio，搭配通用 VFX Pack 與 glitch 指示。
- [x] 格式精準度 10/10：引用模板原文完整貼上，遵循 Act → Beat → Angle 結構與 UTC+8 日期路徑規範。

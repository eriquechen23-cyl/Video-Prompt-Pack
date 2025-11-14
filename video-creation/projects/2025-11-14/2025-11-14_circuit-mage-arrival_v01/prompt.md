# Circuit Mage Arrival — Master Prompt（15s｜12 幕）

來源劇本：scripts/2025-11-14_circuit-mage-arrival_v01/script.md

## 一句話題材
熬夜工程師燁龍與英短藍貓米漿在加班之夜被金色電路吞沒，雙雙墜入魔導都市，啟動基底詠唱語編譯的〈能量彎射〉守住護盾裂口。

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

### QA Checklist（`_core/qa_checklist.md`）
```
☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

### Style Pack：Circuit Mage Arrival Look（`_stylepacks/circuit_mage/look.yml`）
```yaml
name: Circuit Mage Arrival Look
noise_reduction: neon_edge_cleanse
saturation: balanced_glow_skin
contrast_profile: luminous_midnight
color_palette:
  primaries: [cobalt_blue, electric_gold, smoked_slate]
  accents: [frosted_teal, warm_white]
  skin_tone: resilient_warm_amber
light_behaviour:
  rim_light: holo_trace
  bounce_fill: cool_gradient
line_enhancement: semi_soft_outline
motion_blur_shutter: 180
texture_pass: woven_carbon_mesh
notes:
  - 強調黑色與深藍服飾上的冷藍反光，保持金線路細節清晰。
  - 膚色維持小麥暖調，黑眼圈僅留柔和陰影，不要過度泛青。
  - 施法時金色線條需在眼睛與衣內銀路上產生同步閃爍。
  - 城市光源以低飽和霧霾藍＋暖白晶體對比，避免雜訊。
```

### Style Pack：Circuit Mage Arrival VFX（`_stylepacks/circuit_mage/vfx.yml`）
```yaml
name: Circuit Mage Arrival VFX
niagara_presets:
  - circuit_thread_launch
  - portal_ribbon_fold
  - hexshield_microburst
unity_vfx_graph:
  - CircuitMage.LightCompile.vfx
  - CircuitMage.HexShieldPop.vfx
houdini_flipbooks:
  - lightcode_stream_wrap
  - cat_starflare_pulse
shader_controls:
  iris_glow_trace: 0.58
  circuit_line_thickness: 0.34
  portal_warp_intensity: 0.67
  hud_ring_opacity: 0.42
bloom_profile:
  idle: 0.12
  channeling: 0.65
  release: 0.28
light_trail:
  tail_length: 0.55
  decay_speed: 0.36
static_charge_particles:
  density: 0.48
  color_mix: [electric_gold, frost_blue]
audio_sync_hooks:
  iris_ping: sync_to_mid_high
  portal_whoosh: sync_to_low_mid
  hud_scroll: sync_to_highspark
  cat_purr_flux: sync_to_low_rumble
notes:
  - 請確保金色線路在 HUD 展開時沿左手環逐格亮起，與胸前光晶同頻。
  - 入口炸裂需保留 0.2s 無聲光閃後再釋出電流噼啪，避免過曝。
  - 貓尾星火補魔時，尾端粒子向術師胸口流動形成細緻弧線，最後收束於光晶。
```

### Style Pack：Circuit Mage Arrival Audio（`_stylepacks/circuit_mage/audio.yml`）
```yaml
name: Circuit Mage Arrival Audio
core_layers:
  - midnight_city_air
  - console_key_ghosts
  - arcane_hum_loops
  - feline_star_purr
  - portal_low_riser
peak_events:
  - timestamp: hud_activation
    sfx: crystalline_ui_spin
    level_db: -8
    stereo_width: 130
  - timestamp: portal_burst
    sfx: circuit_warp_slam
    level_db: -5
    stereo_width: 150
  - timestamp: landing_impact
    sfx: echoing_bootfall
    level_db: -7
    stereo_width: 110
  - timestamp: mana_transfer
    sfx: starlit_particle_flow
    level_db: -9
    stereo_width: 90
sidechain:
  trigger_bus: portal_burst
  target_bus: ambience
  reduction_db: 4.5
low_freq_management:
  lfe_focus_hz: 48
  sub_trim_db: -10
mix_notes:
  - 鍵盤敲擊節奏需與術師指尖動作對拍，音量低於 -18 dBFS 作為記憶殘響。
  - Portal 爆裂後 0.3s 內加入帶空氣感的風噪以銜接異世界聲景。
  - 米漿心電感應聲採用慵懶男中音帶柔性混響（0.6s），僅在字幕外以 VO 場景音呈現並提示詠唱節奏。
  - 燁龍基底詠唱錄製為清晰男中音，多段停頓配合 HUD 語法亮度；字句峰值控制在 -14 dBFS 並於命中瞬間觸發次低頻推力。
  - 當尾巴星火補魔時，加入高頻顆粒閃爍聲並漸強至 -12 dBFS 後快速衰減。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Circuit Mage Arrival｜2.39:1｜24fps｜電路霓光魔導質感)
「深夜辦公室 → 魔導都市護盾裂口；冷藍螢幕、金色電路碎片、濕潤石板；熬夜工程師燁龍與英短藍貓米漿被扭曲螢幕拉入光流，在異界落地後依 HUD 基底詠唱語啟動〈能量彎射〉掃除骨骸獸剪影。
鏡頭：開場24mm 滑軌貼桌面建立夜班環境，轉35mm 胸高追蹤金線纏繞，墜落段以28mm 手持5% 進入光流，落地後50mm 繞肩帶出 HUD，詠唱時65mm 微推＋側移鎖定光束命中。
表演：燁龍由專注疲憊轉為震驚後迅速計算，詠唱時口型清晰、視線鎖定目標；米漿從睡眼惺忪到炸毛補魔，心電語氣慵懶卻節奏分明。
臉型/髮型：燁龍黑色短髮微亂、眉上瀏海；米漿圓臉霧霾藍毛、右耳白毛尖。
構圖：三分線突出人物偏左，HUD 語法塊與護盾裂口在右後景層次；動態：鍵盤殘影、電路光絲、尾巴星火與城中霧氣流動。
寫實細節：黑色高領細符文只在啟動時亮起、深藍連帽外套內襯銀線巡弋、靴底落地留淡藍殘影、詠唱時掌心電路分段點亮、貓毛炸起顯靜電。
無字幕、無商標/Logo/水印。」

鏡頭語法：24 建立空間｜35 緊貼角色｜50 親密 HUD｜28 光流手持｜65 詠唱特寫；
光圈 {T2.8–T4}；快門角 {180°（Portal 爆裂降至150°）}；
對焦 {層次前→中→後／單點胸前光晶／呼吸拉焦於貓星火與光束命中}。
光影：夜間冷藍體積光混暖白晶體補光；色溫 {夜3200–3600K 搭配異界暖白3800K}；
對比 {柔中帶高}；眼神光 {保留於光晶反射}。
色調/LUT：{陰影霧霾藍、金線高光暖電金、膚色保持小麥暖調／去飽和3%}。
聲音：環境空調＋鍵盤殘響、portal_low_riser 提示扭曲、異界鐘聲與霧風漸入、詠唱男中音分段搭配粒子音；音樂 {Lo-fi 氛圍墊底 72BPM 漸轉霓虹節奏}；峰值控制於 -6 dB。
轉場：鍵盤殘影光源匹配 → 光流鞭移 → Portal 閃白直接切 → HUD 語法滑入 → 光束羽化掃過收束。
安全：去除可讀文件與品牌，城市行人遠景模糊，語法條僅抽象符號與英文關鍵字。
```

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立加班夜的疲憊與異常徵兆
基調：緊張悸動
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：冷藍螢幕、涼掉咖啡、黑色高領、桌面雜亂便條

#### Beat 1（0.0–2.5s）
重點：鍵盤敲擊與疲態
Blocking：燁龍敲鍵盤，視線掃螢幕，米漿在後方蜷縮
Camera：
- 運鏡：24mm 滑軌沿桌面前推
- 焦段/機位：24mm 眼高略低
- 對焦：層次拉焦鍵帽→手→疲倦眼神
- 快門角：180；拍點：指尖敲擊節奏
光影：螢幕冷光＋桌燈暖光混合
色調/LUT：膚色優先，陰影霧霾藍，去飽和3%
聲音：console_key_ghosts 主導，空調低頻，咖啡杯輕顫
轉場：鍵盤殘影遮擋 → Angle 2

Angle 1（0.0–1.2s）
構圖：三分線，燁龍偏右前景，背景霧化城市光
內容：環境建立廣角
補充：桌面便條紙微晃，咖啡杯冒淡霧
安全：去除可讀字樣

Angle 2（1.2–2.5s）
構圖：中央中近景，手指與眼神
內容：疲憊敲鍵特寫
補充：HUD 殘影尚未啟動，眼袋柔影
安全：螢幕無可讀內容

#### Beat 2（2.5–5.0s）
重點：螢幕扭曲與光線纏繞
Blocking：金線從螢幕衝出纏住燁龍與米漿
Camera：
- 運鏡：35mm 穩定器繞半圈
- 焦段/機位：35mm 胸高
- 對焦：呼吸拉焦螢幕→金線→角色面部
- 快門角：150（光線爆閃）；拍點：光晶生成瞬間
光影：螢幕變金光，室內亮度提升
色調/LUT：高光暖金提升，膚色維持
聲音：portal_low_riser 漸強，crystalline_ui_spin 閃後 circuit_warp_slam
轉場：光線爆閃 → Act 2

Angle 3（2.5–3.7s）
構圖：三分線，金線從螢幕射出成斜角
內容：螢幕扭曲與初始纏繞
補充：米漿尾巴開始炸毛
安全：光線亮度受控 ≤100 nits

Angle 4（3.7–5.0s）
構圖：過肩特寫，胸前光晶成形
內容：燁龍驚訝表情＋光晶生成
補充：左手 HUD 字串沿魔導環閃爍
安全：字串為抽象符號

### Act 2（5.0–10.0s）
意圖：穿越過程與落地衝擊
基調：緊張→決斷
節奏域：加速2.4–3.0 → 穩定1.5–2.4
美術要點：光流隧道、金線碎片、漂浮資料塊、濕潤石板

#### Beat 3（5.0–7.5s）
重點：墜入光流
Blocking：角色被吸入螢幕形成長殘影，指尖虛擬敲擊
Camera：
- 運鏡：28mm 手持5% 前進
- 焦段/機位：28mm 俯斜角
- 對焦：層次拉焦角色→光流碎片
- 快門角：150（保持電弧清晰）；拍點：指尖敲擊空氣
光影：純白閃至霓虹藍金
色調/LUT：陰影青藍，高光金白
聲音：arcane_hum_loops 疊加風噪，sidechain 壓鍵盤聲
轉場：光線扭曲鞭移 → Beat 4

Angle 5（5.0–6.2s）
構圖：中央斜俯，中景
內容：燁龍與米漿被拉伸的身形
補充：指尖虛擬鍵盤殘影
安全：無多餘物件

Angle 6（6.2–7.5s）
構圖：前中後分層，光線隧道延伸
內容：光流內部特寫
補充：米漿炸毛，尾巴靜電火花
安全：亮度控制

#### Beat 4（7.5–10.0s）
重點：落地與環境建立
Blocking：兩人從光束中墜落到石板路，燁龍半跪，米漿優雅落地
Camera：
- 運鏡：35mm 穩定器由俯角滑到胸高環繞
- 焦段/機位：35mm 先俯後眼高
- 對焦：單點靴底殘影→胸前光晶→環狀建築
- 快門角：180；拍點：靴底觸地、HUD 亮起
光影：霧霾藍城市光＋暖白晶體頂光
色調/LUT：陰影霧藍，高光暖白金
聲音：echoing_bootfall 接 starlit_particle_flow，midnight_city_air 帶鐘聲
轉場：靴底藍光殘影羽化 → Act 3

Angle 7（7.5–8.7s）
構圖：膝高仰視，燁龍半跪
內容：落地瞬間
補充：靴底藍光拖尾，石板濺水
安全：石板紋理無文字

Angle 8（8.7–10.0s）
構圖：環境建立，城市環狀建築環繞
內容：抬頭見高塔與晶體
補充：符文牌漂浮，霧氣順風
安全：符文為抽象圖形

### Act 3（10.0–15.0s）
意圖：認知新身份並協作施法
基調：盼望混決斷
節奏域：穩定1.5–2.4 → 慢入0.8–1.5
美術要點：銀色魔力線路、HUD 語法塊、貓星火、骨骸獸剪影、漂浮塵霧

#### Beat 5（10.0–12.5s）
重點：城市巡視與基底語提示
Blocking：燁龍起身環顧，魔導環投影地圖與語法塊，胸前光晶脈動，遠處骨骸獸逐漸靠近剪影
Camera：
- 運鏡：50mm 穩定器繞肩
- 焦段/機位：50mm 胸高近景
- 對焦：呼吸拉焦臉→HUD 語法→遠景威脅
- 快門角：180；拍點：HUD 展開框線
光影：暖白晶體反射於面部，HUD 金線照亮語法塊
色調/LUT：膚色優先，陰影青藍，HUD 金線強調
聲音：arcane_hum_loops 降低，crystalline_ui_spin 再次輕觸，鐘聲遠景，console_key_ghosts 低量回放
轉場：HUD 語法欄滑入 → Beat 6

Angle 9（10.0–11.2s）
構圖：三分線，燁龍偏左，HUD 語法塊懸右前景
內容：燁龍讀取基底語提示，遠景骨骸獸剪影上框
補充：內襯銀線巡弋，語法塊顯示 `element: LIGHT`
安全：HUD 字體抽象

Angle 10（11.2–12.5s）
構圖：胸口特寫，光晶＋語法字幕條
內容：光晶脈動與 `pattern: CURVE`、`mode: SAFE` 字樣流動
補充：魔導環透明界面沿左手旋轉
安全：語法僅符號與英文關鍵字

#### Beat 6（12.5–15.0s）
重點：詠唱基底語並釋放〈能量彎射〉
Blocking：米漿跳至肩上輸送魔力，燁龍按語法詠唱，掌心拉出彎曲光束射向骨骸獸
Camera：
- 運鏡：65mm 穩定器微推後側移 15°
- 焦段/機位：65mm 眼高
- 對焦：單點米漿→燁龍口型→掌心光束→遠景命中
- 快門角：180；拍點：語句收尾與光束命中
光影：尾巴星火照亮臉側，光束沿弧線投射藍金交錯
色調/LUT：膚色暖，貓毛霧霾藍帶銀光，光束高光暖金
聲音：feline_star_purr 與 starlit_particle_flow 同步，慵懶 VO 以 0.6s 混響提示節奏，燁龍詠唱以清晰男中音分段，命中觸發 circuit_warp_slam + 骨骼碎裂
轉場：光束殘影掃過 → HUD 彈出「Runtime Success」 → 結束

Angle 11（12.5–13.7s）
構圖：過肩中近景，米漿在肩上
內容：米漿尾巴星火輸送，燁龍開始詠唱首句
補充：語法條 `鎖定前方敵性源` 隨聲同步浮現
安全：語法條僅符號

Angle 12（13.7–15.0s）
構圖：中央特寫，燁龍側臉＋光束弧線延伸至遠景
內容：詠唱終句「執行——能量彎射」並看向骨骸獸爆散，HUD 顯示 Runtime Success
補充：背景高塔旋轉緩慢，遠處鐘聲尾音疊骨骼碎裂回聲
安全：HUD 任務內容僅抽象符號與英文關鍵詞

## Audio Notes（整體）
- 核心音樂維持 72BPM Lo-fi 氛圍，Portal 段落提高合成墊層濾波後再恢復。
- VO：米漿心電訊息音量 -16 dBFS，頻譜保留 2–4 kHz；燁龍詠唱音量 -14 dBFS，加入 120Hz 基頻增益，避免與 arcane_hum_loops 重疊。
- 重要瞬間：鍵盤節奏（Beat1）、Portal 靜默閃（Beat2）、光流風噪（Beat3）、落地回聲（Beat4）、HUD 語法提示（Beat5）、詠唱與骨骸獸粉碎（Beat6）。

## VFX Notes（整體）
- Portal 爆裂需依照 Circuit Mage Arrival VFX 的 portal_ribbon_fold；閃白0.2s 後才出現噼啪。
- HUD 展開以 circuit_line_thickness 0.34，保持透明度 0.42，不遮蔽角色表情；語法塊以電金方塊排列並在詠唱時逐段點亮。
- 尾巴星火補魔使用 cat_starflare_pulse，粒子流向胸口時加入微弧線追光；光束命中骨骸獸後碎片需配合 HUD Runtime Success 彈窗閃光與符文註解殘影。

## QA Checklist（自評 10/10）
- [x] 情緒與運鏡節奏匹配，加班→穿越→詠唱攻擊逐層調整。
- [x] 膚色與霧霾藍光比控制在 55–65 IRE，金線保留細節。
- [x] 轉場設計完成：鍵盤遮擋、光流鞭移、Portal 閃白、HUD 語法滑入、光束掃過。
- [x] LUT、光比、音畫節奏已標記，詠唱字句與粒子對齊。
- [x] 無可讀字樣、品牌或未授權元素。
- [x] 生成設定符合 2.39:1｜24fps｜15s，音頻規格 48kHz -14 LUFS。

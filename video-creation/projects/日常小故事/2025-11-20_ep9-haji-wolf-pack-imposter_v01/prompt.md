# 日常小故事 EP9 — 《哈幾誤入狼群》：月光雪林狼群 × 迷因哈士奇・15 秒 10 幕 Prompt（15s｜10 幕）

來源 brief：依使用者提供的「哈幾誤闖 2–3 隻狼群」情境，呈現外表狼王、內心二哈的反差，15 秒竪屏短片由史詩月夜到迷因破功再到默許陪跑。

## 一句話故事大綱
冬夜雪山月光下，小型灰狼群集結，一隻外表主角光環但內心心虛的哈士奇哈幾誤闖其中，模仿狼王坐姿與嚎叫卻在尾音破成「汪」，最後被默默接受，跟著狼群巡山成一夜限定的「同事」。

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

## `_stylepacks` 區塊
### Style Pack：Moonlit Wolf Meme Look（`_stylepacks/moonlit_wolf_meme/look.yml`）
```yaml
name: Moonlit Wolf Meme Look
lut: Silver-Moon-Cinema
white_balance_reference: 4200K_moonlit_snow
contrast: soft_highlight_rich
highlight_tone: moon_silver_with_warm_edge
shadow_tone: charcoal_blue
saturation_adjust: -0.03
skin_tone_ire: 52-58
grain_profile: micro_film_grain_with_soft_bloom
bloom: subtle_cold_glow
notes:
  - 以冷藍月光為基調，保留雪面與狼毛層次，避免過曝或純白剪影。
  - 高光邊緣略帶暖色，讓哈幾藍眼與金屬名牌在暗夜中仍有主角光感。
  - 對比維持柔和，讓幽默表情與尾巴小抖動清晰可見。
```

### Style Pack：Moonlit Wolf Meme Lighting（`_stylepacks/moonlit_wolf_meme/lighting.yml`）
```yaml
name: Moonlit Wolf Meme Lighting
key_light:
  source: high_full_moon
  color_temp: 4200K
  intensity_ratio: 1.0
fill:
  source: snowfield_bounce
  color_temp: 4300K
  intensity_ratio: 0.55
backlight:
  source: rim_from_moon_direction_or_far_campfire_glow
  color_temp: 4100K
  notes: 為狼毛與哈幾項圈名牌加邊光，維持分離度
atmosphere:
  haze_level: 0.04
  particles: light_snowflakes_with_visible_breath
notes:
  - 風向自山谷輕吹，狼毛和哈幾耳朵有細微流動。
  - 月光色溫保持冷，少量暖背光避免畫面死灰，仍符合深夜質感。
  - 地面雪反射作自然填光，避免額外器材感。
```

### Style Pack：Moonlit Wolf Meme Lens Set（`_stylepacks/moonlit_wolf_meme/lensset.yml`）
```yaml
name: Moonlit Wolf Meme Lens Set
primary_focals: [24, 35, 55, 85]
shutter_angle: 180
frame_support: gimbal_low_percent_with_slow_dolly
handheld_usage: 0.05
movement:
  dolly: slow_forward_push_and_side_follow
  note: 嚎叫與巡山段採緩慢推移，滑稽時刻可短暫手持感
focus_method: layered_pull_from_alpha_wolf_to_haji
usage_notes:
  - 24/35mm 建立雪林空地與狼群隊形，月光帶少量鏡頭 flare。
  - 55/85mm 用於哈幾表情、尾巴微抖與狼王嗅聞的親密特寫。
  - 嚎叫慢動作可提升快門角至 200–220 以保留冷霧粒子。
```

### Style Pack：Moonlit Wolf Meme Audio（`_stylepacks/moonlit_wolf_meme/audio.yml`）
```yaml
name: Moonlit Wolf Meme Audio
music:
  palette: cold_strings_with_subtle_taiko_then_meme_break
  bpm: 76
  progression: tense_minor_to_lighthearted_major
ambience:
  layers:
    - distant_wind_in_valley
    - snow_crunch_sparse_steps
    - faint_echoed_howl_far
foley:
  - collar_tag_clink
  - husky_tail_swish_on_snow
  - wolf_nose_sniff
  - paw_slide_on_ice
voice_fx:
  type: comedic_pitch_break_on_final_bark
  placement: 7.5-9.0s when howl turns "汪"
mix_targets:
  loudness: -14_LUFS
  peak: -1_dBTP
  dynamic_range: -18_to_-6_dBFS
notes:
  - 嚎叫段保持空靈殘響，哈幾破音時瞬間放大 + 降低底噪，凸顯迷因落差。
  - 巡山段留足雪踩聲與呼氣白霧聲，維持夜間臨場感。
```

## Master Prompt（15s｜月光雪林寫實 × 狼群迷因｜9:16｜24fps｜冷藍月光與雪反射質感）
「冬夜接近午夜的山腰雪林；稀疏針葉、滿月冷光、薄雪飄落、呼氣白霧；2–3 隻灰狼在月光下巡視領地時，黑白哈士奇哈幾追雪花誤闖，努力模仿狼群坐下與嚎叫，尾音破成『汪』後反被默許加入巡山。」
鏡頭：9:16 以滑軌與低比例穩定器為主，嚎叫段慢推＋極微手持感；特寫用 55–85mm 壓縮狼王嗅聞與哈幾尾巴小抖。
表演：哈幾外放帥氣但眼神緊張、尾端抖；狼王沉穩嗅聞，年輕狼戒備又好奇；嚎叫到「汪」時哈幾表情微崩。
構圖：前中後景分明，月光與雪紋理 15–20% 留白；狼群成弧線或列隊，哈幾置於中心偏後位置。
寫實細節：雪面腳印凌亂、名牌「HAJI」反光、狼毛粗糙與傷疤、可見呼吸霧與落雪粒子；無品牌、無血腥。
聲音：76 BPM 冷弦樂 + 微太鼓鋪張，嚎叫段殘響長尾；哈幾「汪」瞬間做 pitch break 迷因；雪踩聲、嗅聞聲、風聲。
安全：無可讀文字或 Logo，無暴力，犬狼距離安全、動作為模擬。

### Camera Continuity
- 全片沿用 24–55mm 為主的月夜雪林色調，嚎叫特寫與嗅聞用 55–85mm 親密距離；維持 4200–4300K 冷光，邊光勾毛流與名牌反光。
- 運鏡多為緩推與側向平移，僅在哈幾破功時加入 5% 手持微晃；快門角一般 180，嚎叫白霧段提升至 200–220。
- 轉場以直接切或月光遮擋匹配，保持隊形方向一致，巡山段改為跟隨側拍後收高空俯視。

## Scene Blocks（15s｜10 幕 × 約 1.5s）

### Act 1（0.0–7.5s）
意圖：建立月夜狼群氛圍與哈幾誤闖的緊張反差
基調：冷靜警戒中帶幽默
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：滿月冷光、針葉稀疏雪林、狼傷疤與粗毛、哈幾藍項圈

#### Beat 1（0.0–1.5s）
重點：雪山與狼影開場
Blocking：高空俯視推進，2–3 隻灰狼站成弧形在雪林空地上巡視。
Camera：
- 運鏡：滑軌式空拍緩推
- 焦段/機位：24mm 高俯視
- 對焦：層次前→中→後
- 快門角：180；拍點：月光落在狼背
光影：滿月主光＋雪面反射，對比柔冷
色調/LUT：陰影微藍、高光月銀，去飽和3%
聲音：遠風、遙遠狼嚎尾音，音樂前奏
轉場：直接切到哈幾奔跑

Angle 1
構圖：狼群成弧佔下三分，月亮在上方留白
內容：狼影明顯，雪地腳印雜亂
補充：飄雪與白霧前景
安全：無可讀字樣

#### Beat 2（1.5–3.0s）
重點：哈幾獨自在雪地穿梭
Blocking：哈幾從林緣小跑追雪花，項圈「HAJI」反光。
Camera：
- 運鏡：低角度手持 5% 微晃側跟
- 焦段/機位：35mm 膝高
- 對焦：單點眼→尾端抖
- 快門角：180；拍點：項圈晃動
光影：月光側逆，雪地 bounce 填光
色調/LUT：冷藍主調，高光帶暖 rim
聲音：雪踩聲、項圈叮噹、輕喘
轉場：遮擋切入誤闖空地

Angle 1
構圖：哈幾位於右三分線，前景雪枝模糊
內容：尾巴忍不住微翹，藍眼亮
補充：呼氣白霧清晰
安全：去品牌

#### Beat 3（3.0–4.5s）
重點：誤闖狼群瞬間對視
Blocking：哈幾衝入空地停下，狼群轉頭，僵持 0.5 秒。
Camera：
- 運鏡：中景前推後輕繞露雙方對視
- 焦段/機位：35mm 眼高
- 對焦：層次拉焦狼王→哈幾
- 快門角：180；拍點：耳朵「啵」立正
光影：月光正面+雪反射，對比柔
色調/LUT：陰影藍，眼神光保留
聲音：音樂張力拉高，雪地靜音感
轉場：直接切狼王靠近

Angle 1
構圖：哈幾與狼王各佔一側，弧形隊形形成前景線
內容：哈幾尾端偷偷抖
補充：遠處山谷淡回音
安全：無人類

#### Beat 4（4.5–6.0s）
重點：狼王繞圈嗅聞
Blocking：狼王緩步繞哈幾一圈，鼻尖嗅肩與側腹，哈幾僵硬吞口水。
Camera：
- 運鏡：55mm 環繞慢推
- 焦段/機位：55mm 胸高
- 對焦：單點狼王鼻尖→拉到哈幾眼
- 快門角：200；拍點：尾巴微抖
光影：月光勾邊，背光細節
色調/LUT：冷銀高光，去飽和3%
聲音：嗅聞聲、項圈金屬輕碰
轉場：匹配切到坐下

Angle 1
構圖：近距離雙犬半身，背景樹影模糊
內容：狼王傷疤可見，哈幾眼神放大
補充：呼氣霧形成小流
安全：保持距離

#### Beat 5（6.0–7.5s）
重點：同步坐下的 0.5 秒延遲
Blocking：狼王低吼坐下，年輕狼跟上；哈幾 lag 半拍重重坐下，雪炸開。
Camera：
- 運鏡：正面微前推
- 焦段/機位：35mm 眼高
- 對焦：層次狼王→哈幾
- 快門角：180；拍點：哈幾落地
光影：雪面反射填光，邊光勾耳朵
色調/LUT：陰影微藍，高光暖邊
聲音：低吼、坐下雪聲、音樂維持張力
轉場：直接切嚎叫

Angle 1
構圖：弧形隊形朝鏡頭，哈幾偏中間
內容：哈幾坐下微滑，裝成調姿
補充：尾巴在後方小拍子
安全：無可讀元素

### Act 2（7.5–15.0s）
意圖：嚎叫破功、狐疑與默許，再到巡山收束
基調：緊張轉喜感，最後溫暖接受
節奏域：穩定1.5–2.4 → 加速2.4–3.0 收束
美術要點：呼氣白霧、月光背 rim、雪粒反光、名牌亮點

#### Beat 6（7.5–9.0s）
重點：史詩嚎叫 vs 哈幾破功
Blocking：狼王率先仰頭長嚎，其他狼跟上；哈幾遲疑後抬頭「嗚——汪」。
Camera：
- 運鏡：仰角半身推近
- 焦段/機位：50mm 膝高仰
- 對焦：單點狼王→拉到哈幾嘴
- 快門角：200；拍點：尾音破音
光影：月光直射，呼氣白霧清楚
色調/LUT：冷銀高光，陰影藍
聲音：嚎叫殘響＋哈幾 pitch break，音樂短暫停頓
轉場：硬切到反應

Angle 1
構圖：仰拍狼口與月亮同框，哈幾在右側
內容：哈幾嘴型尷尬，眼睛睜大
補充：白霧上升成絲
安全：無文字

#### Beat 7（9.0–10.5s）
重點：狼群微妙反應
Blocking：嚎叫止，年輕狼歪頭看哈幾；哈幾假裝看遠方。
Camera：
- 運鏡：中近景切換
- 焦段/機位：55mm 眼高
- 對焦：單點歪頭狼→拉到哈幾側臉
- 快門角：180；拍點：耳朵抖
光影：月光側打，對比柔
色調/LUT：陰影藍，高光暖 rim
聲音：風聲回來，音樂轉輕鬆小調
轉場：遮擋切年長狼經過

Angle 1
構圖：歪頭狼在左三分，哈幾在右三分
內容：哈幾目光飄開，嘴角緊張
補充：雪粒落在鼻尖
安全：去可讀字

#### Beat 8（10.5–12.0s）
重點：被「半承認」的鼻子輕頂
Blocking：年長狼走過，鼻子輕頂哈幾肩膀；哈幾愣→放鬆。
Camera：
- 運鏡：低角度平移跟拍
- 焦段/機位：50mm 膝高
- 對焦：單點接觸點
- 快門角：180；拍點：鼻子碰觸
光影：背光 rim 勾出輪廓
色調/LUT：冷藍主調，名牌反光微暖
聲音：嗅聞聲、項圈輕敲，音樂回到溫暖弦樂
轉場：匹配切巡山行進

Angle 1
構圖：肩部特寫，兩個頭部半入畫
內容：哈幾耳朵先往後再放鬆
補充：呼氣白霧交疊
安全：距離安全

#### Beat 9（12.0–13.5s）
重點：一起巡山的小隊形
Blocking：狼群前後分散，哈幾走在中間略顯笨拙踩到雪洞又裝成加速。
Camera：
- 運鏡：側向平移滑行
- 焦段/機位：35mm 眼高
- 對焦：層次前狼→哈幾→後狼
- 快門角：180；拍點：腳踩雪洞
光影：月光斜照，雪面 bounce 填光
色調/LUT：冷藍，去飽和3%
聲音：雪踩聲節奏、輕喘、音樂漸收
轉場：上升拉遠

Angle 1
構圖：隊伍橫向佔中景，哈幾稍中央
內容：尾巴不小心翹高又壓低
補充：雪霧拖尾形成線條
安全：無品牌

#### Beat 10（13.5–15.0s）
重點：遠景收尾：今晚暫時是一隻狼
Blocking：鏡頭升高俯視，狼群與哈幾成小排影子在雪林前進，尾巴翹成顯眼亮點。
Camera：
- 運鏡：無人機視角緩升後拉
- 焦段/機位：24mm 高俯視
- 對焦：層次前→後，保持整隊清晰
- 快門角：180；拍點：定格收尾
光影：月亮與雪地同框，柔光
色調/LUT：冷銀收束，留白多
聲音：音樂收斂，留 0.2s 寂靜
轉場：定格停 0.2s 作片尾

Angle 1
構圖：隊形在下方三分線，月亮在上方
內容：哈幾尾巴亮點最醒目
補充：可淡出字幕「Tonight, he runs as one of them.」
安全：字幕為後製字卡

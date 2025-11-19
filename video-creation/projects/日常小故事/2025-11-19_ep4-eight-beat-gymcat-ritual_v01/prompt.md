# 日常小故事 EP4 — 臥蠶肌肉帥哥 × 深灰英短米漿・15 秒 8 幕黃昏日常 Prompt（15s｜8 幕）

來源 brief：依據「臥蠶肌肉帥哥 × 深灰英短貓」角色設定，濃縮為 15 秒 8 幕回家後的黃昏 routine，覆蓋玄關迎接、伸展監工、浴室地墊攻防、沙發宵夜與睡前同步呼吸，供動畫分鏡與畫師製作使用。

## 一句話題材
健身完回家的陳序在 15 秒內與深灰英短「米漿」完成固定的迎接、伸展、洗澡前鬧劇與宵夜放鬆，最後並肩睡去的療癒節奏。

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
☐ 情緒→運鏡已選定；焦段/對比/轉場一致
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。
```

## `_stylepacks` 區塊
### Style Pack：Mijiang Warm Cinema Look（`_stylepacks/mijiang_warm_cinema/look.yml`）
```yaml
name: Mijiang Warm Cinema Look
lut: Ember-Soft-Negative
white_balance_reference: 3200K_lamp
contrast: gentle_low_mid
highlight_tone: honey_amber
shadow_tone: indigo_soft_cool
skin_tone_ire: 58-62
saturation_adjust: -0.03
grain_profile: fine_35mm_400T
bloom: localized_palm_glow
notes:
  - 夜間室內保留暖黃主光與藍冷陰影對比
  - 皮膚與貓毛維持柔亮層次，不可過曝
  - 適度保留顆粒感與光暈，塑造溫馨電影質感
```

### Style Pack：Mijiang Warm Cinema Lighting（`_stylepacks/mijiang_warm_cinema/lighting.yml`）
```yaml
name: Mijiang Warm Cinema Lighting
key_light:
  source: tungsten_table_lamp
  color_temp: 3000K
  modifier: opal_dome_diffuser
fill:
  source: bounced_practical
  color_temp: 4200K
  intensity_ratio: 0.35
backlight:
  source: hidden_led_strip
  color_temp: 4600K
  notes: 用於勾勒貓耳與掌心邊緣
practicals:
  - name: corridor_window_sunset
    description: 4300K 黃昏窗光切入走廊形成長陰影
  - name: tv_cool_edge
    description: 客廳電視提供微弱冷藍 rim 勾邊
atmosphere:
  haze_level: 0.04
  particles: suspended_dust_soft
notes:
  - 走廊階段維持夕陽逆光，入屋後轉為暖燈＋窗餘暈
  - 控制對比，保留臥蠶與貓毛細節
  - 冰水/浴室段加局部高光凸顯水珠
```

### Style Pack：Mijiang Warm Cinema Lens Set（`_stylepacks/mijiang_warm_cinema/lensset.yml`）
```yaml
name: Mijiang Warm Cinema Lens Set
primary_focals: [28, 35, 48, 75]
shutter_angle: 180
depth_of_field: shallow_T2.0-T2.8
dolly:
  move: slider_glide_in
  speed_ratio: 0.7
handheld_usage: 0.02
support: slider_or_tripod_breath
focus_method: layered_pull_subject_to_pet
usage_notes:
  - 28mm 捕捉走廊與客廳全貌，保持暖色空間層次
  - 35/48mm 讓人與貓貼近又留出呼吸感
  - 75mm 用於臥蠶、貓呼嚕、浴室地墊等細節特寫
```

### Style Pack：Mijiang Warm Cinema Audio（`_stylepacks/mijiang_warm_cinema/audio.yml`）
```yaml
name: Mijiang Warm Cinema Audio
music:
  palette: lo_fi_guitar_with_piano_voicing
  bpm: 72
  progression: tired_major_sus4_to_rest
ambience:
  layers:
    - corridor_evening_air
    - apartment_hvac_low_hum
    - distant_city_muffle
foley:
  - key_in_lock_click
  - sneaker_rubber_floor
  - gym_bag_drop_soft
  - yoga_mat_unfurl
  - ice_cubes_clink_glass
  - towel_swish
  - cat_purr_close_mic
  - cat_paw_tap
voice:
  type: soft_spoken_whisper
  treatment: close_mic_soft_reverb
mix_targets:
  loudness: -14_LUFS
  peak: -1_dBTP
  dynamic_range: -18_to_-6_dBFS
notes:
  - 前半保持鍵入與腳步，Beat3–4 加入墊子摩擦與呼吸
  - 浴室段加暖水蒸氣環境層，沙發段疊冷氣低頻
  - 結尾放大呼嚕並壓低音樂營造關機感
```

### Style Pack：Mijiang Warm Cinema Safety Checklist（`_stylepacks/mijiang_warm_cinema/safety.yml`）
```yaml
name: Mijiang Warm Cinema Safety Checklist
rules:
  - 貓咪衝刺與跳躍需控制高度，鏡頭距離≥50cm
  - 浴室地墊段保持地面乾燥避免滑倒
  - 宵夜段食物容器去除品牌標籤
  - 手機畫面亮度降至 10%，防可讀訊息
  - 收音時維持室溫 24°C，避免冷氣直吹貓
```

## Master Prompt（15s｜16:9｜24fps｜2D anime-inspired live-action hybrid）
Master(15s｜slice-of-life warm cinema｜16:9｜24fps｜soft-grain film)
「黃昏的公寓走廊到客廳；暖黃燈、冰水杯、深灰英短米漿；臥蠶肌肉帥哥陳序下班回家與貓完成迎接、伸展、浴室地墊談判與宵夜抱睡。
鏡頭：滑軌＋極低比例手持（≤2%）平移；
表演：剛練完的疲憊微笑、對貓自言自語、被貓監督時無奈；
臉型/髮型：依角色設定短黑髮＋明顯臥蠶；
構圖：前中後層次＋暖色留白 15%；動態：貓尾、窗簾、呼吸；
寫實細節：汗微光、棉質家居 T、貓毛貼身；
無字幕、無商標。」

Camera Continuity：
- Beat1–2 使用 28→35mm 低角穩定器銜接門縫逆光。
- Beat3–6 主用 35/48mm 胸高，特寫（Beat4、5、7）採 75mm。
- Beat8 以 24mm 俯仰混合拉遠，轉場羽化 0.5s 收尾。

Persistent Elements：
- 道具：黑灰運動包、瑜伽墊、浴室灰白腳踏墊、沙發扶手貓抓痕。
- 光源：玄關 3200K 小吊燈、客廳立燈、電視冷光 4300K。
- 聲音：Lo-fi 吉他 + piano loop，貓呼嚕貫穿 Beats 2、6–8。

## 分鏡（15 秒｜8 幕）
### Act 1（0.0–4.2s）
意圖：建立回家路徑與迎接儀式
基調：疲憊卻期待
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：夕陽走廊、單肩運動包、玄關地毯、小夜燈

#### Beat 1（0.0–2.1s）
重點：走廊回家預熱
Blocking：陳序單肩背包走向自家門，汗微亮，空手在空中晃，腳步沉穩。
Camera：
- 運鏡：28mm 背後穩定器推進
- 焦段/機位：28mm 胸高後跟
- 對焦：單點肩胛→鑰匙手
- 快門角：180；拍點：鑰匙掏出
光影：夕陽 4300K 逆光，走廊燈 3600K 勾線
色調：膚色優先、陰影帶靛
聲音：吉他前奏＋包帶摩擦
轉場：鑰匙遮擋切門內

Angle 1
構圖：走廊消失點導向門
內容：汗珠貼在脖頸
補充：門牌模糊
安全：無住戶字樣

#### Beat 2（2.1–4.2s）
重點：玄關迎接
Blocking：門開半暗，米漿從地墊衝出立馬撞腿，尾巴豎直抖動，陳序彎腰說「小隊長。」
Camera：
- 運鏡：35mm 地面低角朝門推
- 焦段/機位：35mm 低 25cm
- 對焦：層次門縫→貓→青年臉
- 快門角：200；拍點：頭撞
光影：逆光＋室內 3200K 暖燈
色調：高光暖金
聲音：門鎖、貓呼嚕起、呢喃問候
轉場：貓尾掃過鏡頭遮擋

Angle 2
構圖：貓置前景右三分線，青年膝蓋後景
內容：尾尖抖
補充：鞋帶垂落
安全：鞋無品牌

### Act 2（4.2–10.4s）
意圖：展現家中日常模組
基調：輕鬆幽默
節奏域：穩定1.5–2.4
美術要點：瑜伽墊、客廳暖光、浴室灰墊、宵夜小盒

#### Beat 3（4.2–5.8s）
重點：伸展熱身
Blocking：換上寬鬆背心，陳序在瑜伽墊上舉手伸展，背肌展開；米漿坐墊角盯著。
Camera：
- 運鏡：35mm 側滑 30cm
- 焦段/機位：35mm 胸高
- 對焦：單點背肌→拉到貓眼
- 快門角：180；拍點：呼氣
光影：窗餘暈 + 客廳 3000K 主燈
色調：暖冷平衡
聲音：墊摩擦、深呼吸
轉場：肩線帶動 wipe

Angle 3
構圖：青年站左二分，貓在右下
內容：臥蠶微擠
補充：汗滴沿手臂
安全：無Logo

#### Beat 4（5.8–7.3s）
重點：平板撐監工
Blocking：陳序做平板，米漿貼臉前蹲監視，偶拍垂下抽繩，他笑：「別盯啦。」
Camera：
- 運鏡：48mm 正面低角
- 焦段/機位：48mm 膝高
- 對焦：單點眼神→抽繩
- 快門角：180；拍點：笑出聲
光影：地燈逆勾
色調：膚色暖、背景去飽 5%
聲音：手肘碰墊、呼吸亂、貓呼嚕增
轉場：抽繩甩向右做鞭移

Angle 4
構圖：青年頭居右三分線，貓佔左
內容：臥蠶擠壓
補充：抽繩晃動殘影
安全：無字樣

#### Beat 5（7.3–8.9s）
重點：浴室地墊攻防
Blocking：他拿著毛巾要進浴室，發現米漿攤平在腳踏墊；他用腳輕推求讓位。
Camera：
- 運鏡：75mm 俯拍 20°
- 焦段/機位：75mm 腰高
- 對焦：單點貓背→青年腳
- 快門角：180；拍點：尾巴甩兩下
光影：浴室 3500K 頂燈，走廊暖光洩入
色調：暖灰
聲音：毛巾摩擦、腳尖碰墊
轉場：他跨步帶遮擋

Angle 5
構圖：浴室門框前景，貓鋪滿中央
內容：腳尖勾墊
補充：水汽尚未開
安全：瓷磚無花紋

#### Beat 6（8.9–10.4s）
重點：宵夜審查
Blocking：洗完穿寬鬆 T 坐沙發，打開雞胸餐盒；米漿站沙發扶手，逐個聞。
Camera：
- 運鏡：48mm 半身穩定
- 焦段/機位：48mm 眼高
- 對焦：層次叉子→貓鼻
- 快門角：180；拍點：他說「這個太鹹。」
光影：立燈 3000K + TV 冷邊
色調：暖內冷邊
聲音：塑膠盒、叉子碰聲、輕聲提醒
轉場：零食拋向鏡頭上方做匹配剪

Angle 6
構圖：餐盒在前景，貓在右上
內容：他伸叉子誘惑
補充：手機在腿上 dim 無內容
安全：盒無商標

### Act 3（10.4–15.0s）
意圖：將情緒收束在親密呼吸
基調：沈靜療癒
節奏域：穩定1.5–2.4 → 慢出0.8–1.5
美術要點：沙發軟墊、暖黃小燈、被褥、窗外城市光

#### Beat 7（10.4–12.4s）
重點：胸口同步
Blocking：米漿窩在胸口，陳序半躺刷手機，空手順毛，臥蠶在微笑。
Camera：
- 運鏡：75mm 側面近景緩推
- 焦段/機位：75mm 胸高
- 對焦：單點貓背→拉到臥蠶
- 快門角：180；拍點：屏幕熄滅
光影：立燈主光+TV 殘光
色調：高光暖、背景柔化
聲音：呼嚕放大、指腹摩擦
轉場：手機暗屏羽化

Angle 7
構圖：胸口佔滿畫面，貓尾成弧
內容：手指與毛同頻
補充：臥蠶柔亮
安全：手機無內容

#### Beat 8（12.4–15.0s）
重點：全景收束
Blocking：鏡頭拉到窗外，客廳燈柔，兩人一貓靜止，冷氣吹動窗簾，字幕浮現「今天關機」。
Camera：
- 運鏡：24mm 從室內滑出窗外
- 焦段/機位：24mm 胸高→外推
- 對焦：層次青年→玻璃反射城市
- 快門角：144；拍點：尾巴最後晃
光影：室內 3000K vs 外部 3300K 餘暈
色調：外冷內暖、留 15% 窗框
聲音：音樂降、城市遠響、呼嚕淡出
轉場：淡出黑收尾

Angle 8
構圖：窗框包裹沙發與茶几
內容：白字「今天關機」淡入
補充：冷氣風揚起窗簾
安全：字卡僅此一句

## 聲音與音樂備註
- 音樂：Lo-fi fingerstyle 吉他 + Rhodes 鋪底，Beat6 後加入輕柔 pads，Beat8 只留低頻和弦與呼嚕。
- Foley：鑰匙、門軸、包帶、瑜伽墊、抽繩拍打、浴室墊摩擦、餐盒蓋、叉子點擊、零食掉落、手機熄滅觸控、窗簾吹動。
- Voice：陳序低聲台詞「小隊長」「別盯啦」「借我踩一下」「這個太鹹」「你才是放鬆指揮官」；錄音距離 30cm 內，Beat7 後轉耳語。

## 角色與場景設定節錄
### 陳序（Chen Xu）
- 25 歲健身行銷企劃，晚上是社區健身房常客。
- 黑色短髮兩側推短，上方自然亂翹；眼睛細長臥蠶明顯，嘴角常帶半笑。
- 身高 180±2 cm，寬肩、背厚、胸肌與手臂線條乾淨；回家換寬鬆 T + 運動短褲。
- 性格穩、慢半拍、私下對貓碎念多；健身為了保持心緒穩定，對細節和作息控。
- 小習慣：進門先摸貓；洗澡邊走邊吹頭髮，容易灑水；紀錄貓食量。

### 米漿（深灰英短）
- 2–3 歲，圓臉琥珀眼，下巴有淺色毛像奶泡，短腿結實。
- 招牌動作：玄關地墊等門，聽到鑰匙會小跑，尾巴豎直尾尖抖。
- 對外害羞，對陳序超黏；能分辨健身後的汗味並檢查；會用行為「管控」作息，如擋浴室、踩鍵盤。

### 場景模組對應
1. 玄關迎接（Beat1–2）
2. 客廳伸展＋平板監工（Beat3–4）
3. 浴室墊談判（Beat5）
4. 宵夜審查（Beat6）
5. 睡前呼吸（Beat7–8）

## QA Checklist（交付前自評）
- [ ] 焦段連戲：28→35→35/48→75→24mm 順序記錄於攝影表。
- [ ] 膚色 58–62 IRE、臥蠶與貓毛細節保留，汗光控制在 40 IRE。
- [ ] 轉場依序使用遮擋、肩線 wipe、鞭移、遮擋、匹配剪、羽化與淡出，無突兀硬切。
- [ ] 音樂 BPM 72 與運鏡 0.9× 同步；貓呼嚕層自 Beat2 起 -8 dB 遞增。
- [ ] 畫面無品牌、手機畫面僅灰色 UI；字卡僅顯示「今天關機」。
- [ ] 交付：4K 16:9、24fps、-14 LUFS 立體聲、無字幕。

# 日常小故事 EP1 — 吊嘎男 × 米漿英短貓・15 秒暖陽日常 Prompt（15s｜12 幕）

來源 brief：短髮吊嘎肌肉男與米漿英短貓的 15 秒寫實電影感日常 PV 分鏡

## 一句話題材
吊嘎男與米漿英短貓的一日晨練到夜晚 routine，以暖色自然光與貼身鏡位捕捉互動的幽默與溫度。

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
  - name: floor_reflection
    description: 木地板反射暖光形成淡光圈
  - name: sigil_glow
    description: 地面光陣散發淡金光補亮暗部
atmosphere:
  haze_level: 0.05
  particles: suspended_dust_soft
notes:
  - 暖黃實光搭配冷調背景，營造陰影安全感
  - 控制對比避免完全漆黑，保留細節可供追焦
  - 光陣亮度需可動畫控，與呢喃節奏同步
```

### Style Pack：Mijiang Warm Cinema Lens Set（`_stylepacks/mijiang_warm_cinema/lensset.yml`）
```yaml
name: Mijiang Warm Cinema Lens Set
primary_focals: [32, 48, 75]
shutter_angle: 180
depth_of_field: shallow_T2.0-T2.8
dolly:
  move: slider_glide_in
  speed_ratio: 0.75
handheld_usage: 0.02
support: slider_or_tripod_breath
focus_method: layered_pull_foreground_to_subject
usage_notes:
  - 32mm 建立環境光圈，保持前中後層次
  - 48mm 拍攝人與貓互動，視線貼近但穩定
  - 75mm 捕捉手部與毛髮細節，控制呼吸式拉焦
```

### Style Pack：Mijiang Warm Cinema Audio（`_stylepacks/mijiang_warm_cinema/audio.yml`）
```yaml
name: Mijiang Warm Cinema Audio
music:
  palette: lo_fi_strings_with_mallets
  bpm: 68
  progression: warm_minor_to_major_lift
ambience:
  layers:
    - hvac_low_hum
    - distant_city_muffle
    - soft_room_air
foley:
  - cloth_shift_subtle
  - finger_snap_resonant
  - cardboard_rustle
  - cat_paw_wood_taps
  - cat_purr_close_mic
voice:
  type: whispered_roll_call
  treatment: close_mic_soft_reverb
mix_targets:
  loudness: -14_LUFS
  peak: -1_dBTP
  dynamic_range: -18_to_-6_dBFS
notes:
  - 保留高頻空氣感避免房間過乾
  - 貓呼嚕聲後段可漸進成主導層
  - 音樂和光線變化需保持 0.9× 節奏同步
```

### Style Pack：Mijiang Warm Cinema Safety Checklist（`_stylepacks/mijiang_warm_cinema/safety.yml`）
```yaml
name: Mijiang Warm Cinema Safety Checklist
rules:
  - 避免實際火焰或高溫燈具接近動物
  - 所有道具紙箱貼紙需模糊或移除文字
  - 保持人類臉部低於 50% 曝光，主角為米漿
  - 記錄光陣亮度與動畫參數以利 QA 重製
  - 收音時預留貓咪舒適距離，避免驚嚇
```

## Master Prompt（15s｜寫實電影感暖光｜16:9｜23.98fps｜柔顆粒質感）
「早晨到夜晚的台北公寓；白床單、木地板、落地燈；短髮吊嘎肌肉男在米色英短貓的陪伴下完成晨練、遊戲與放鬆，以玩鬧互動收束於同頻入睡。
鏡頭：滑軌＋穩定器，僅 2% 手持。
表演：男主半睜惺忪、訓練時專注又被打斷、夜晚被貓療癒；米漿保持圓臉呆萌與突然爆衝。
構圖：多用前中後分層，陽光形成暖霧，保留 15% 留白顯示生活感。
寫實細節：白吊嘎帶汗色、灰運動短褲、木地板反光、英短毛蓬鬆、逗貓棒羽毛飄動、遊戲手把黑色霧面、落地燈亞麻罩。
聲音：Lo-fi 弦樂 68 BPM，疊加房間空調、遠處車聲、貓呼嚕與木地板踩踏；轉場以實體遮擋與匹配動作完成。
安全：無品牌、無手機螢幕內容、僅呈現成人角色，貓咪動作維持安全幅度。」

### Camera Continuity
- 以柔滑 slider 做晨間→午間→夜間的光感過門：早晨 5200K 日光、午間 5400K 伴有窗光帶塵粒、夜間 3000K 落地燈 + 4200K bounce。
- 男主與貓的視線交握採 48mm 親密焦段，所有特寫統一以 75mm + shallow DOF，確保米漿毛流一致。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立米漿當鬧鐘的幽默清晨
基調：溫柔被鬧醒
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：白床單、晨光、吊嘎、米色英短

#### Beat 1（0.0–1.2s）
重點：被米漿壓醒的瞬間
Blocking：男主仰躺，米漿趴在胸口，他半睜眼與貓對視。
Camera：
- 運鏡：32mm 俯視穩定器緩推
- 焦段/機位：32mm 床邊略俯 20°
- 對焦：層次拉焦從貓臉到男主眼睛
- 快門角：180；拍點：貓尾敲下巴
光影：5200K 柔日光從窗側灑入，床單高光柔化
色調/LUT：膚色優先，陰影帶淡藍，貓毛暖米
聲音：遠車聲＋貓輕喵＋柔呼吸
轉場：貓尾遮擋 → Angle 1

Angle 1（0.0–1.2s）
構圖：中央偏上的米漿，男主臉在畫面下半
內容：貓爪攤開，男主嘴角微笑
補充：床單有細皺紋，胸口起伏
安全：無文字

#### Beat 2（1.2–2.4s）
重點：肉墊鬧鐘敲臉
Blocking：米漿抬爪拍他臉頰，男主笑著閉眼
Camera：
- 運鏡：75mm 靜態
- 焦段/機位：75mm 側面微仰
- 對焦：單點貓爪觸碰瞬間
- 快門角：180；拍點：肉墊接觸
光影：晨光勾勒爪邊緣
色調/LUT：暖亮，膚色 60 IRE
聲音：近距離呼嚕＋布料摩擦
轉場：直接切至地板訓練

Angle 2（1.2–2.4s）
構圖：三分線，貓爪佔左側，男主嘴角在右
內容：肉墊壓軟臉頰
補充：鬍渣微動
安全：無可讀

#### Beat 3（2.4–3.6s）
重點：背上多一組重量
Blocking：男主做伏地挺身，米漿穩坐背上
Camera：
- 運鏡：40mm 側移跟
- 焦段/機位：40mm 胸高側面
- 對焦：層次從前景啞鈴→男主肩→貓
- 快門角：180；拍點：撐起瞬間
光影：窗光+木地板反射，形成 warm rim
色調/LUT：膚色暖，背景陰影略藍
聲音：呼吸重、木地板輕吱
轉場：男主上推至畫面頂部做遮擋

Angle 3（2.4–3.6s）
構圖：前景模糊啞鈴，中景男主，後景貓尾
內容：米漿隨推起晃動
補充：汗滴落至墊子
安全：無品牌

#### Beat 4（3.6–5.0s）
重點：啞鈴被貓爪拍偏
Blocking：男主坐姿舉啞鈴，貓突然拍金屬
Camera：
- 運鏡：48mm 膝高近景
- 焦段/機位：48mm 低角
- 對焦：單點啞鈴→呼吸拉至貓爪
- 快門角：180；拍點：金屬被拍
光影：陽光點亮啞鈴反光
色調/LUT：暖亮並帶金屬高光
聲音：金屬輕撞＋男主低笑
轉場：鞭移至同一房間陽光躺姿

Angle 4（3.6–5.0s）
構圖：中央啞鈴，貓爪從左入
內容：啞鈴稍微歪斜
補充：貓鬍鬚抖動
安全：無文字

### Act 2（5.0–10.0s）
意圖：午間陽光與逗貓互動
基調：玩心與默契
節奏域：穩定1.5–2.4
美術要點：窗邊陽光、逗貓棒、木地板動態

#### Beat 5（5.0–6.2s）
重點：陽光與毛絨貼靠
Blocking：男主靠窗拉伸，米漿貼臂而躺
Camera：
- 運鏡：32mm 靜態逆光
- 焦段/機位：32mm 眼高
- 對焦：單點貓背毛流
- 快門角：180；拍點：男主手指撫毛
光影：逆光 flare + floor bounce
色調/LUT：高光暖金，陰影柔藍
聲音：鳥鳴＋手掌摩毛聲
轉場：羽毛棒滑入畫面帶動

Angle 5（5.0–6.2s）
構圖：對角線，陽光切入
內容：男主手指沿著貓背
補充：塵粒漂浮
安全：無可讀

#### Beat 6（6.2–7.4s）
重點：伏擊位置就緒
Blocking：男主坐地雙腿成三角，逗貓棒晃；米漿蹲腿間
Camera：
- 運鏡：28mm 地面視角
- 焦段/機位：28mm 膝高
- 對焦：層次逗貓棒→貓眼
- 快門角：180；拍點：尾巴擺動
光影：側光形成陰影三角
色調/LUT：木地板暖 + 陰影冷
聲音：羽毛掠空＋男主低語「來，米漿，準備喔」
轉場：貓衝出造成動態遮擋

Angle 6（6.2–7.4s）
構圖：從雙腿間望向前方
內容：貓眼亮亮盯羽毛
補充：尾巴左右擺動
安全：無文字

#### Beat 7（7.4–8.6s）
重點：米色子彈衝出
Blocking：米漿爆衝撲逗貓棒，滑過地板再補一爪
Camera：
- 運鏡：手持 32mm 跟拍（限制 2%）
- 焦段/機位：32mm 低角
- 對焦：單點貓頭，略帶動態模糊
- 快門角：200；拍點：撞擊羽毛
光影：窗光在木地板形成拉絲高光
色調/LUT：地板高亮帶動軌跡
聲音：爪子滑行聲＋布料擦地
轉場：滑行尾巴掃過 → 遮擋

Angle 7（7.4–8.6s）
構圖：動態跟拍中央
內容：貓像彈丸向右撲
補充：木屑微飛
安全：無危險

#### Beat 8（8.6–9.8s）
重點：搶手把的霸主
Blocking：男主坐沙發，米漿趴在遊戲手把上睡
Camera：
- 運鏡：48mm 穩定器微推
- 焦段/機位：48mm 胸高
- 對焦：層次男主手→貓
- 快門角：180；拍點：男主聳肩
光影：客廳暖燈 + 窗外餘光
色調/LUT：暖黃主調
聲音：遊戲 BGM 小聲、男主嘆氣
轉場：男主掏手機拍攝帶入下一近景

Angle 8（8.6–9.8s）
構圖：男主置左，貓趴在中央手把
內容：男主攤手無奈
補充：貓尾蓋按鍵
安全：手把無 logo

#### Beat 9（9.8–11.0s）
重點：溫柔的側臉
Blocking：男主半跪拍照，眼神柔和，指節掃過貓額
Camera：
- 運鏡：75mm 靜態側面
- 焦段/機位：75mm 眼高
- 對焦：單點男主眼神→拉至貓額
- 快門角：180；拍點：指節滑過
光影：落地燈 rim 光
色調/LUT：暖金覆面
聲音：呼吸＋快門輕響
轉場：指節滑下帶動 wipe

Angle 9（9.8–11.0s）
構圖：三分線，男主臉在右，貓在左下
內容：男主笑得柔和
補充：短髮邊緣有光暈
安全：無可讀

### Act 3（11.0–15.0s）
意圖：夜間收束，同步呼吸
基調：療癒沈靜
節奏域：穩定1.5–2.4 → 慢出0.8–1.5
美術要點：落地燈、臂枕、沙發/地毯、窗景

#### Beat 10（11.0–12.2s）
重點：被揉捏的肌肉臂枕
Blocking：男主側躺，手臂成臂枕，米漿用前爪踩踏
Camera：
- 運鏡：75mm 特寫
- 焦段/機位：75mm 俯 15°
- 對焦：單點貓爪踩肌肉
- 快門角：180；拍點：踩踏節奏
光影：3000K 落地燈，局部 bloom 在臂彎
色調/LUT：暖橘＋陰影藍
聲音：貓呼嚕放大、布料細聲
轉場：呼嚕聲 crossfade 下一鏡

Angle 10（11.0–12.2s）
構圖：中央為手臂，貓爪佔畫面 60%
內容：肌肉跟著踩踏起伏
補充：貓閉眼享受
安全：無文字

#### Beat 11（12.2–13.6s）
重點：胸口上的小團子
Blocking：男主躺地毯刷手機，米漿圓成一球在胸口；他放下手機覆手於貓
Camera：
- 運鏡：35mm 俯視
- 焦段/機位：35mm 頂視
- 對焦：層次手機→貓
- 快門角：144；拍點：手機放下
光影：落地燈形成暖圈，背景夜色冷藍
色調/LUT：暖冷對比
聲音：鋼琴和弦＋同步呼吸
轉場：燈光漸暗 → 羽化

Angle 11（12.2–13.6s）
構圖：中央男主與貓，留白顯示落地燈
內容：手掌覆在貓肚上
補充：呼吸同步慢下
安全：手機螢幕關閉

#### Beat 12（13.6–15.0s）
重點：一天尾燈的靜止
Blocking：從窗外望進客廳，二者睡著，燈色暖
Camera：
- 運鏡：24mm 外景微拉遠
- 焦段/機位：24mm 窗外胸高
- 對焦：單點屋內光圈
- 快門角：144；拍點：米漿尾巴最後一晃
光影：室內暖光對比室外冷夜
色調/LUT：外冷內暖，玻璃微反射
聲音：音樂最後和弦延長，城市遠噪
轉場：淡出收尾

Angle 12（13.6–15.0s）
構圖：窗框當前景，室內人物於中央
內容：字幕「PEACEFUL ROUTINE / 米漿的一天」淡入
補充：尾巴輕晃後靜止
安全：字幕採無 serif 白字，無 logo

## 聲音與音樂備註
- 68 BPM Lo-fi 弦樂鋼琴交錯，早晨以 finger snap + soft brush，午間加木地板滑行 foley，夜晚疊加 cat purr close-mic 並漸成主旋律。
- Foley 層：床單皺摺、啞鈴金屬、木地板吱聲、逗貓棒羽毛刷氣、遊戲手把按鍵、手機快門。
- 氛圍：遠處車流與鳥鳴在早午段，夜間轉為空調低頻與城市遠噪。

## QA Checklist（交付前自評）
- [ ] 情緒與運鏡一致，晨練→遊戲→夜間採 32/48/75mm 連戲。
- [ ] 膚色 58–62 IRE，米漿毛保持暖米亮點。
- [ ] 轉場以遮擋與光源匹配實作，無突兀剪切。
- [ ] LUT、光比、音樂 BPM 68 記錄完畢，呼嚕聲與光衰同步。
- [ ] 物件無 logo、手機螢幕關閉、字幕僅顯示標題。
- [ ] 生成解析度 4K→16:9，交付 -14 LUFS 立體聲。

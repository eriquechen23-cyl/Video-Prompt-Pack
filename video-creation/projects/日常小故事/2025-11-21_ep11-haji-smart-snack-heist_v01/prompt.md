# 日常小故事 EP11 — 《自以為很聰明的偷吃計畫》：客廳監視器迷因 × 哈幾拉椅翻車・15 秒 10 幕 Prompt（15s｜10 幕）

來源 brief：依使用者提供的「客廳桌上零食誘餌，哈士奇哈幾裝作路過、偷偷拉椅子偷吃，結果椅子盤子一起翻車成監視器迷因」情境，直式 15 秒短片。

## 一句話故事大綱
客廳監視器定點拍下哈幾啟動自以為聰明的偷吃計畫，從裝無辜到拉椅子、最後失控把盤子掃落地，鼻子沾滿碎屑被逮個正著。

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
### Style Pack：Real Cinema Look（`_stylepacks/real_cinema/look.yml`）
```yaml
name: Real Cinema Look
lut: Skin-Priority
saturation_adjust: -0.05  # 去飽和 5–8%
skin_tone_ire: 60
contrast: soft
highlights: warm
shadows: cool_blue
texture: natural_grain
notes:
  - 膚色優先校正
  - 微膠片顆粒
  - 高光暖、陰影微藍
```

### Style Pack：Real Cinema Lens Set（`_stylepacks/real_cinema/lensset.yml`）
```yaml
name: Real Cinema Lens Set
primary_focals: [35, 50, 75]
shutter_angle: 180
dolly:
  move: glide_in
  speed_ratio: 0.8
handheld_usage: 0.03
support: slider_or_stabilizer
usage_notes:
  - 室內情緒戲採滑軌緩推
  - 側向平移保持視線連續
  - 聚焦於自然膚質呈現
```

### Style Pack：Real Cinema Safety Checklist（`_stylepacks/real_cinema/safety.yml`）
```yaml
name: Real Cinema Safety Checklist
rules:
  - 避免可讀字與商標曝光
  - 群眾不近特寫，維持隱私
  - 保持自然膚質與光比
  - 記錄 LUT 與種子以利 QA
```

### Style Pack：Home Surveillance Meme Lighting（新樣板）
```yaml
name: Home Surveillance Meme Lighting
applicable: indoor_living_room_meme; 監視器視角或CCTV復古回放
avoid: neon_club_mix; 戶外強烈陽光場景
key_light:
  source: ceiling_soft_box_or_window_bounce
  color_temp: 4300K
  intensity_ratio: 0.7
fill:
  source: wall_bounce_and_floor_reflect
  color_temp: 4800K
  intensity_ratio: 0.5
backlight:
  source: practical_lamp_rim
  color_temp: 4200K
  notes: 輕勾邊毛髮與零食碎屑，避免過曝
atmosphere:
  grain: mild_cctv_noise
  overlay: timestamp_top_left_and_record_dot
notes:
  - 適用客廳監視器或回放梗，保留輕微噪點與壓縮感。
  - 避免強飽和或戲劇性色片，保持中性色調以凸顯狗狗表情。
```

## Master Prompt（15s｜Real Cinema × Home Surveillance Meme｜9:16｜60fps｜膠片寫實）
Master(15s｜Real Cinema × Home Surveillance Meme｜9:16｜60fps｜膠片寫實)
「傍晚室內客廳；小餐桌擺零食、沙發與走道、角落監視器；哈士奇哈幾自以為聰明地拉椅偷吃，結果椅子盤子一起翻車成迷因。
鏡頭：監視器定點混合低角度側拍，少量滑軌補特寫，手持≤3%。
表演：哈幾從裝路過、偷瞄到小心拉椅，最後僵硬愣住鼻子沾碎屑；遠處主人的腳步聲逼近。
臉型/毛流：二哈黑白毛、藍眼、耳朵立起，毛蓬鬆且帶室內光反光。
構圖：監視器廣角疊時間碼，其他鏡頭用三分線與前中後層次呈桌子、椅子、哈幾。
寫實細節：木質椅子摩擦地板、金屬盤子滑動、零食碎屑散落、監視器壓縮與輕噪點。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35mm 建立客廳監視器視角；50–75mm 中景捕捉哈幾表情；快門角 180°，滑行失控段可 200° 帶拖影。
光影：Home Surveillance Meme Lighting；室內軟光為主，保留監視器陰影邊緣；色溫 4200–4800K；對比柔。
色調/LUT：Real Cinema Look；去飽和 5%；微膠片顆粒；輕微 CCTV 壓縮噪點。
聲音：環境底噪與時鐘聲；木頭椅腳摩擦、盤子「喀啦」滑行、零食掉地；BGM 由陰謀輕節奏 → 滑稽 → 爆點停頓，遠處主人呼喊「哈——幾——？」。
轉場：多用直接切與遮擋；失控段可鞭移；結尾監視器回放加「REPLAY ×4」疊字。
安全：遵循 Real Cinema Safety Checklist。

## Scene Blocks（15s｜10 幕｜Act→Beat→Angle）
Act 1（0.0–6.0s）
意圖：建立客廳誘餌與哈幾的「假裝無辜」鋪陳。
基調：療癒帶陰謀；節奏域：慢入 1.2s；美術要點：餐桌零食、沙發、監視器時間碼。

Beat 1（0.0–1.5s）
重點：觀眾先看見誘餌，哈幾未入畫。
Blocking：空景，桌上零食置中，走道空。
Camera：
- 運鏡：監視器定點。
- 焦段/機位：24mm｜俯拍高角度。
- 對焦：層次由桌到沙發清晰。
- 快門角：180；拍點：BGM 第一拍。
光影：室內軟光＋Home Surveillance overlay，對比柔。
色調/LUT：Real Cinema Look。
聲音：環境底噪＋輕微時鐘聲；BGM 陰謀輕節奏進。
轉場：直接切下一鏡。

Angle 1
構圖：廣角中央構圖；內容：環境建立；補充：左上角時間碼與 REC 紅點；安全：無可讀字。

Beat 2（1.5–3.0s）
重點：哈幾裝作路過、假裝聞沙發與牆。
Blocking：哈幾從右走道晃入，先在沙發角嗅一嗅再靠近桌邊。
Camera：
- 運鏡：監視器定點。
- 焦段/機位：24mm｜高角度。
- 對焦：單點跟隨哈幾移動。
- 快門角：180；拍點：尾巴晃動。
光影：同上一段，毛髮反光微亮。
色調/LUT：Real Cinema Look。
聲音：BGM 增加木魚/木琴節奏；爪子踩地輕聲。
轉場：直接切側面中景。

Angle 2
構圖：哈幾在三分線右側，桌子在左；補充：沙發纖維細節、空氣微塵；安全：去Logo。

Beat 3（3.0–4.5s）
重點：哈幾眼神計算、確認主人不在。
Blocking：站在桌邊，眼神盯零食再偷瞄主人方向。
Camera：
- 運鏡：側面滑軌微推。
- 焦段/機位：50mm｜桌面略下胸高。
- 對焦：單點在眼睛。
- 快門角：180；拍點：眼神來回。
光影：窗光柔和側光，眼神光保留。
色調/LUT：Real Cinema Look。
聲音：BGM 壓低疊 hi-hat；遠處環境靜。
轉場：直接切近景。

Angle 3
構圖：三分線左零食、右哈幾頭；內容：中景；補充：鼻息霧氣輕微；安全：無可讀字。

Beat 4（4.5–6.0s）
重點：裝無辜前置，鼻子慢靠近桌面。
Blocking：哈幾頭撇開聞椅背，耳朵抖、尾巴輕晃。
Camera：
- 運鏡：近景固定。
- 焦段/機位：75mm｜眼高。
- 對焦：單點在鼻尖。
- 快門角：180；拍點：耳朵抖動的小鼓點。
光影：側逆軟光，鼻子高光微亮。
色調/LUT：Real Cinema Look。
聲音：小「叮」提示將要出手。
轉場：遮擋切到低角度椅子。

Angle 4
構圖：中央偏右哈幾頭，前景桌腳虛焦；補充：鼻尖近桌面距離；安全：無可讀字。

Act 2（6.0–12.0s）
意圖：哈幾啟動偷吃計畫、拉椅子並失控。
基調：緊張滑稽；節奏域：穩定 1.8s → 加速 2.5s；美術要點：木椅、金屬盤、地板摩擦痕。

Beat 5（6.0–7.5s）
重點：前腳偷偷上椅子，動作像拆炸彈。
Blocking：哈幾一隻前腳慢慢搭上椅面，眼神偷瞄旁邊。
Camera：
- 運鏡：低角度側面微推。
- 焦段/機位：35mm｜膝高。
- 對焦：單點爪子，再呼吸拉焦到眼神。
- 快門角：180；拍點：爪子落椅瞬間。
光影：Home Surveillance Lighting，椅面反光明顯。
色調/LUT：Real Cinema Look。
聲音：木頭輕摩擦聲＋緊張拉弦。
轉場：直接切回監視器視角。

Angle 5
構圖：椅子前景大、哈幾後景；補充：椅腳投影；安全：去Logo。

Beat 6（7.5–9.0s）
重點：雙前腳上椅，開始拉動發出吱吱聲。
Blocking：哈幾重心前傾，椅子被拖動。
Camera：
- 運鏡：監視器高角度定點。
- 焦段/機位：24mm｜俯拍。
- 對焦：層次保持全清晰。
- 快門角：180；拍點：椅腳摩擦節拍。
光影：Home Surveillance Lighting，對比柔。
色調/LUT：Real Cinema Look。
聲音：椅腳「吱…吱…」突出，BGM 幾乎靜音。
轉場：鞭移帶出失控。

Angle 6
構圖：桌左、椅右、哈幾居中；補充：地板摩擦痕；安全：無可讀字。

Beat 7（9.0–10.5s）
重點：椅子失控側滑，盤子開始滑行。
Blocking：哈幾腳下一滑往前撲，盤子往桌邊衝。
Camera：
- 運鏡：中景正側面，快速跟隨滑行。
- 焦段/機位：50mm｜膝高。
- 對焦：呼吸拉焦哈幾 → 盤子 → 哈幾。
- 快門角：200；拍點：椅子急拉瞬間。
光影：保持軟光，桌面高光強化盤子滑動。
色調/LUT：Real Cinema Look。
聲音：長滑行音效，BGM 醞釀爆點。
轉場：直接切廣角暴露。

Angle 7
構圖：桌椅哈幾呈對角線；補充：鼻子接近桌邊；安全：去Logo。

Beat 8（10.5–12.0s）
重點：盤子撞擊、零食掉滿地，哈幾僵住。
Blocking：椅子撞桌腳，盤子「鏘！」彈起，碎屑飄落；哈幾四腳分開僵硬。
Camera：
- 運鏡：廣角稍拉遠。
- 焦段/機位：35mm｜眼高略上。
- 對焦：層次拉焦碎屑 → 哈幾眼神。
- 快門角：200；拍點：盤子落地聲。
光影：保持室內軟光，碎屑有高光閃點。
色調/LUT：Real Cinema Look。
聲音：盤子金屬撞擊、零食掉地聲；BGM 搞笑「啪」。
轉場：直接切中近景無辜臉。

Angle 8
構圖：中央哈幾，前景碎屑慢動作；補充：耳朵貼背；安全：無可讀字。

Act 3（12.0–15.0s）
意圖：被抓包與監視器回放梗收束。
基調：尷尬喜劇；節奏域：穩定 1.5s；美術要點：碎屑黏鼻頭、監視器回放疊字。

Beat 9（12.0–13.5s）
重點：哈幾裝無辜坐好，鼻頭沾碎屑。
Blocking：哈幾正對鏡頭坐下，眼睛睜大，遠處傳來主人腳步與呼喊。
Camera：
- 運鏡：中近景固定。
- 焦段/機位：75mm｜眼高。
- 對焦：單點在哈幾雙眼。
- 快門角：180；拍點：主人呼喊停 BGM。
光影：軟光，鼻頭碎屑反光。
色調/LUT：Real Cinema Look。
聲音：BGM 突然停留空白；遠處主人「哈——幾——？」回音。
轉場：直接切回放畫面。

Angle 9
構圖：中央頭像；補充：鼻頭碎屑、眼神呆住；安全：去Logo。

Beat 10（13.5–15.0s）
重點：監視器回放梗，定格迷因。
Blocking：黑白或綠夜視色調回播拉椅→碎屑災難，最後定格哈幾呆臉。
Camera：
- 運鏡：監視器定點，回放加「REPLAY ×4」。
- 焦段/機位：24mm｜俯拍。
- 對焦：全清晰。
- 快門角：180；拍點：字幕音效「噹——」。
光影：Home Surveillance Meme Lighting，帶微噪點。
色調/LUT：Real Cinema Look 基底疊回放黑白/綠色調。
聲音：網路迷因字幕音效，收尾輕快 BGM＋狗項圈鈴鐺聲。
轉場：羽化 0.5s 收尾。

Angle 10
構圖：監視器畫面分割，定格哈幾鼻子沾碎屑；補充：左上時間碼，右上 REPLAY；安全：無可讀字與商標。

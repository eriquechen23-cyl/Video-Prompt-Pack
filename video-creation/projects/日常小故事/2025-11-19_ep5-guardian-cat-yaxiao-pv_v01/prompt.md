# 日常小故事 EP5 — 《宵之守護》15 秒守護貓 PV Prompt（15s｜10 幕）

來源腳本：video-creation/scripts/2025-11-19_guardian-cat-yaxiao-pv_v01/script.md

## 一句話題材
現代客廳裡的懶貓小宵在項圈符文觸發後化身灰耳貓系獸人夜宵，於 15 秒內完成「察覺威脅 → 變身 → 斬除影子 → 裝睡」的守護循環。

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
### Style Pack：Guardian Cat Anime Look（新樣板）
```yaml
name: Guardian Cat Anime Look
line_enhancement: rounded_cel_edge
color_palette:
  primaries: [sofa_taupe, dusk_orange, slate_blue]
  accents: [auric_rune_gold, mint_pulse, blush_beige]
  skin_tone: warm_amber_with_soft_gradient
lighting:
  key: window_warm_shaft (4500K dusk)
  fill: lamp_soft_bounce (3800K)
  rim: rune_glow_edge (gold 5200K)
texture_pass:
  fur_detail: simplified_soft_shadow
  clothing_fabric: matte_knit
bloom: 0.28 limited to rune/eye highlights
shadow_treatment: velvety_low_contrast for cat form, sharper for beastman form
notes:
  - 維持 2D 平塗質感，毛髮以大片明暗塊表現不要寫實毛束。
  - 夜宵獸人時加入細緻金色 rim light 強調耳朵、尾端與護腕符文。
  - 居家背景保持模糊幾何塊，焦點集中在角色表演與符文光。
```

### Style Pack：Guardian Cat Anime Audio（新樣板）
```yaml
name: Guardian Cat Anime Audio
bpm: 96 lo-fi hop
ambient_layers:
  - dusk_window_air
  - faint_city_hum
melodic_layers:
  - nylon_guitar_pluck (soft arpeggio)
  - warm_pad_purr (sine with subtle vibrato)
impact_fx:
  collar_ping: small_metal_chime
  rune_flood: layered_purr_riser + low_sub_heartbeat
  claw_slash: airy_swipe_with_gold_particles
vocal_textures:
  - distant_ahh_pad (wordless, -14 dB)
  - processed_cat_purr (sidechain to rune glow)
notes:
  - 變身段加強低頻心跳並鋪上 processed_purr，戰鬥結束迅速淡出回日常環境聲。
  - 主人出聲僅為短疑問語氣，保持 -8 dB 並帶室內混響避免搶戲。
```

### Style Pack：Guardian Cat Anime VFX（新樣板）
```yaml
name: Guardian Cat Anime VFX
transformation_layers:
  - collar_rune_circle (gold thin line, 12 fps animation)
  - limb_stretch_glow (soft gradient, 2-frame offset)
particle_presets:
  tail_tip_static: 0.35 density, mint sparks
  paw_impact: 0.42 density, cat_paw glyph decals
shadow_enemy:
  shader: ink_smoke_cutout
  breakup: 0.55 noise with auric fracture core
trail_settings:
  claw_trail_color: [auric_rune_gold, soft_white]
  decay: 0.24s
  taper: 0.3 width falloff
impact_marks:
  - sofa_fabric_ripple subtle
  - floor_paw_glow fade 0.5s
notes:
  - 影步殘影以 2D 墨暈方式處理並保留貓爪輪廓。
  - 變身時的骨架拉伸保持剪影處理，僅在邊緣描繪金光，避免寫實肉感。
  - 影子怪破碎時改為煙墨裂開並被金光粒子掃除，禁用血霧。 
```

---

## Master Prompt 實際填寫
```
Master(15s｜Guardian Cat Anime Look｜16:9｜24fps｜2D 都市奇幻守護質感)
「黃昏室內客廳；布沙發、暖窗光、陰影爪印；懶貓小宵察覺異樣後變身成灰耳貓系獸人夜宵，踩牆斬裂影子再恢復成軟綿貓。」
鏡頭：Act1 28mm 室內穩定器慢推→Beat2 50mm 項圈特寫→Beat3 32mm 走廊俯視；Act2 45mm 眼特寫→24mm 低角剪影→32–40mm 半身揭示→28mm 跟跳；Act3 35mm 俯視戰鬥→45mm 主人視角→32mm 回到沙發。
表演：貓形態慵懶半睜眼、聽到威脅耳朵貼平；夜宵獸人時眼神銳利、嘴角帶獠牙笑並保持護主姿勢；最後恢復懶貓但用眼神阻止觀眾洩密。
臉型/髮型：獸人形態為 18–20 歲男性，圓潤臉型、墨灰短髮微翹、灰耳與金色豎瞳，貓形態為深灰英短圓臉貓。
構圖：客廳木地板與沙發成前中後層，黃昏光劃斜線；戰鬥段保留尾巴弧線作 S 型導線；收尾將主人與貓疊於三分線交點。
寫實細節：黑色無袖連帽＋淡金內裡、深灰 jogger 褲、皮質頸環符文會亮；護手繃帶在揮爪時產生光紋；沙發布料在衝刺時微皺。
無字幕、無商標/Logo/水印。」

鏡頭語法：空間建立以 24–35mm，獸人特寫使用 45–65mm；
光圈 {Act1 T2.8 暖窗柔焦、Act2 T2.4 加強光軌、Act3 T2.5 保柔亮點}；快門角 {日常 180°、變身 144° 拉出殘影、戰鬥 200° 突顯動感}；
對焦 {貓眼與符文單點，跳躍段呼吸拉焦貓→影子→主人}。
光影：黃昏窗光 + 室內暖燈形成雙色溫，符文金光提供 rim light，影子怪以冷藍 fill 構成對比。
色調/LUT：暖橘 + 冷藍互補，貓形態偏柔灰，獸人膚色暖琥珀，陰影加微藍以維持夜間異能感。
聲音：nylon_guitar_pluck 與 warm_pad_purr 為底，collar_ping 與 rune_flood 於變身點觸發，claw_slash 對應攻擊，processed_cat_purr 在結尾回歸靜態。
轉場：暖窗 flare 匹配切→符文光遮擋→動態爪印鞭移→影子碎煙硬切→窗光羽化 0.4s 回日常。
安全：室內道具不含可讀字，戰鬥為光影與煙霧表現，無血腥。
```

## Scene Blocks（10 Angles｜總長 15s）

### Act 1（0.0–4.5s）
意圖：建立家中黃昏氛圍與即將到來的異常
基調：療癒到緊張的過渡
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：布沙發、木地板、暖窗光、細黑項圈

#### Beat 1（0.0–1.5s）
重點：懶貓曬夕陽
Blocking：小宵窩在沙發上蜷縮，尾巴慢晃，主人路過摸頭。
Camera：
- 運鏡：28mm 穩定器慢推
- 焦段/機位：28mm 沙發高度略低視角
- 對焦：層次主人手→貓臉
- 快門角：180；拍點：主人手離開
光影：窗光斜切，毛皮柔光
色調/LUT：暖橘主色，陰影柔灰
聲音：環境 Lo-fi 鼓點 + 貓呼嚕
轉場：主人離框匹配 → Angle 1

Angle 1（0.0–1.5s）
構圖：三分線貓在右下
內容：沙發與貓，主人手穿越前景
補充：尾巴尾端輕點節拍
安全：居家擺件無字樣

#### Beat 2（1.5–3.0s）
重點：項圈符文啟動
Blocking：項圈特寫，金屬牌浮出「宵」字並延伸符文，耳朵抖動。
Camera：
- 運鏡：50mm 微推
- 焦段/機位：50mm 近胸高
- 對焦：單點項圈→跳至瞳孔倒影
- 快門角：144；拍點：符文亮起
光影：符文金光提升對比
色調/LUT：暖光+金色 rim
聲音：collar_ping + rune_flood
轉場：符文 flare 遮擋 → Angle 2

Angle 2（1.5–3.0s）
構圖：中央項圈，貓臉模糊背景
內容：符文沿皮質頸環流動
補充：細微火花向外飄
安全：僅抽象文字

#### Beat 3（3.0–4.5s）
重點：影子威脅逼近
Blocking：走廊俯視，牆面影子延伸貓爪，主人前景滑手機未察覺。
Camera：
- 運鏡：32mm 俯拍滑軌
- 焦段/機位：32mm 2.2m 高角
- 對焦：層次主人→影子爪
- 快門角：180；拍點：影子觸地
光影：冷藍陰影對比暖燈
色調/LUT：背景暖、影子冷
聲音：低頻 rumble + faint_city_hum
轉場：影子觸發光源遮擋 → Angle 3

Angle 3（3.0–4.5s）
構圖：S 型影子引導到主人
內容：影子爪從牆角探出
補充：地板顫動細線
安全：主人臉模糊避免識別

### Act 2（4.5–10.5s）
意圖：呈現小宵變身與獸人夜宵的敏捷戰鬥
基調：緊張決斷
節奏域：穩定1.5–2.4 → 加速2.4–3.0
美術要點：項圈符文、黑色連帽、長尾、金色爪印

#### Beat 4（4.5–6.0s）
重點：貓眼鎖定
Blocking：超近眼睛倒映影子與主人，瞳孔縮成線，耳朵貼平。
Camera：
- 運鏡：45mm 定鏡
- 焦段/機位：45mm 眼平
- 對焦：單點瞳孔
- 快門角：144；拍點：瞳孔收縮
光影：眼內反射暖光 + 冷影
色調/LUT：金眼與冷背景對比
聲音：低音心跳加速
轉場：眼內反射放大 → Angle 4

Angle 4（4.5–6.0s）
構圖：眼睛充滿畫面
內容：瞳孔反射主人背影與影子
補充：眼角毛炸起
安全：無額外元素

#### Beat 5（6.0–7.5s）
重點：變身啟動剪影
Blocking：貓落地，項圈符文成圓陣，金光沿四肢與尾巴擴散，影子拉成人形。
Camera：
- 運鏡：24mm 低角抬升
- 焦段/機位：24mm 地面 0.5m 仰視
- 對焦：層次項圈→四肢→剪影
- 快門角：144；拍點：符文爆光
光影：地面金環 + 背光剪影
色調/LUT：金 + 冷藍反差
聲音：rune_flood 漲潮 + processed_purr
轉場：金光遮擋 → Angle 5

Angle 5（6.0–7.5s）
構圖：剪影中央，金環包圍
內容：四肢拉長動畫化變形
補充：尾巴延伸出光弧
安全：剪影無血肉

#### Beat 6（7.5–9.0s）
重點：獸人夜宵登場
Blocking：獸人形態站定，撥動頸環，爪子彈出露出獠牙笑。
Camera：
- 運鏡：35mm 半身微繞
- 焦段/機位：35mm 胸高
- 對焦：單點臉部→護腕
- 快門角：180；拍點：爪子彈出
光影：窗光側逆 + 符文 rim
色調/LUT：灰黑服飾配金光
聲音：claw_slash 準備音 + lo-fi 節奏加強
轉場：爪子甩向牆面 → Angle 6

Angle 6（7.5–9.0s）
構圖：人物偏右，長尾 S 型佔左
內容：護腕亮起符文
補充：帽子被耳朵頂出兩個隆起
安全：無標誌

#### Beat 7（9.0–10.5s）
重點：牆面跳躍
Blocking：夜宵從地面爆衝踩牆兩次再朝鏡頭外衝，留下一連串金色貓爪光圈。
Camera：
- 運鏡：28mm 跟隨，帶動態模糊
- 焦段/機位：28mm 膝高
- 對焦：呼吸拉焦腳步→爪印
- 快門角：200；拍點：每次踩點
光影：暖室光 + 金色爪印
色調/LUT：背景模糊成暖灰
聲音：claw_slash + 低頻踩踏
轉場：最後一個爪印填滿畫面 → Angle 7

Angle 7（9.0–10.5s）
構圖：對角線動勢
內容：金色爪印在牆面延伸
補充：牆面布質微震
安全：家具無字樣

### Act 3（10.5–15.0s）
意圖：展示影子被擊碎與回歸日常
基調：決斷→療癒
節奏域：加速2.4–3.0 → 慢入0.8–1.5
美術要點：金色爪痕、煙墨影子、窗光粒子

#### Beat 8（10.5–12.0s）
重點：影子怪破碎
Blocking：夜宵從上方俯衝，爪痕在空中畫弧，影子怪被撕成煙墨碎片。
Camera：
- 運鏡：35mm 仰角跟隨
- 焦段/機位：35mm 胸高仰視
- 對焦：呼吸拉焦爪→煙墨
- 快門角：200；拍點：命中瞬間
光影：金色爆光 + 冷藍殘影
色調/LUT：金/藍撞色
聲音：claw_slash 強化 + airy_swipe_hit
轉場：煙霧羽化 → Angle 8

Angle 8（10.5–12.0s）
構圖：中央斜線爪痕
內容：煙墨裂縫被金光填滿
補充：爪痕殘影 0.3s 漸淡
安全：影子抽象無細節

#### Beat 9（12.0–13.5s）
重點：主人體感錯位
Blocking：主人視角回頭，只見金光粒子漂浮。
Camera：
- 運鏡：45mm 手持微晃
- 焦段/機位：45mm 眼高主觀
- 對焦：粒子→空沙發
- 快門角：180；拍點：主人輕聲疑問
光影：窗光 + 粒子反射
色調/LUT：暖中帶冷點
聲音：主人低語「…剛剛，是你嗎？」 + 背景音淡出
轉場：粒子飄到沙發 → Angle 9

Angle 9（12.0–13.5s）
構圖：中央留白，粒子漂浮
內容：沙發空著僅餘金粉
補充：窗簾輕晃
安全：對白以字幕避開（實際生成僅口型）

#### Beat 10（13.5–15.0s）
重點：恢復懶貓
Blocking：小宵縮回主人胸口睡覺，尾巴搭在主人手上，短暫睜眼示意保密後繼續呼嚕。
Camera：
- 運鏡：32mm 近景穩定
- 焦段/機位：32mm 胸高
- 對焦：單點貓臉
- 快門角：180；拍點：眨眼
光影：窗光柔和、符文全暗
色調/LUT：暖橘柔和
聲音：音樂回到 nylon_guitar_pluck，processed_purr 成主音
轉場：柔焦淡出 → Angle 10

Angle 10（13.5–15.0s）
構圖：三分線貓臉靠左
內容：貓與主人胸口重疊
補充：頸環金屬微亮但無符文
安全：畫面純日常

## QA 自檢（10/10）
- [x] 結構完整（Master + 3 Act × 10 Beat × 10 Angle），時間軸 1.5s ×10 = 15s。
- [x] 敘事由日常到戰鬥再回歸，無敘事斷點。
- [x] 光影、聲音、轉場皆對應 Style Pack，無互斥設定。
- [x] 所有道具與頸環符文僅以抽象字體顯示，無可讀字樣。
- [x] 變身與戰鬥僅用光、煙與剪影，零血腥；角色皆成年設定。

# 爆牌魔術師 × 精準爆破｜寫實遊戲風 Prompt（15s 動作戰鬥分鏡）

## 一句話題材
用撲克牌當導火線，將戰場變成可控的爆炸劇場。

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

### Audio Pack 指引（`_core/audio_pack.md`）
```
聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
音樂：{氛圍/絃樂/Lo-fi/節奏輕推}
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）
```

### Style Pack：Arcane Gambler Look（`_stylepacks/arcane_gambler/look.yml`）
```yaml
name: Arcane Gambler Look
lut: Ember-Neon
saturation_adjust: 0.08
contrast: high_dynamic
highlights: arcane_gold
shadows: obsidian_teal
affinity_glow: hud_crimson_thread
texture: wet_trench_coat
chromatic_aberration: restrained_dual_tint
lens_distortion: micro_barrel
notes:
  - 夜間霓虹反射需以紅金點亮撲克牌邊緣，膚色維持 55 IRE 微暖
  - 牌面符文採用細緻浮雕高光，避免過曝而看不清紋理
  - 背景雨霧與焦煙需分層處理，保留 HUD 介面清晰度
```

### Style Pack：Arcane Gambler VFX（`_stylepacks/arcane_gambler/vfx.yml`）
```yaml
name: Arcane Gambler VFX
niagara_presets:
  - card_sigils_attach
  - delayed_shrapnel_pop
  - hud_thread_reticle
unity_vfx_graph:
  - Gambler.CardLatch.vfx
  - Gambler.ChainDetonate.vfx
  - Gambler.ClusterImplode.vfx
houdini_flipbooks:
  - paper_sigil_ignite
  - micro_charge_bloom
  - debris_card_confetti
shader_settings:
  rune_edge_emit: 0.62
  delay_timer_glow: 0.34
  detonation_implode_strength: 0.58
  debris_velocity_random: 0.47
sdf_settings:
  armor_surface_wrap: 0.29
  hud_lockbox_radius: 0.22
  chain_trigger_offset: 0.18
bloom_control:
  idle: 0.14
  trigger_peak: 0.76
  cooldown: 0.33
audio_sync:
  card_tap: sync_to_heartbeat
  stick_confirm: ping_subtle_click
  detonate: staggered_implode
notes:
  - 撲克牌貼附需使用法陣紋理動畫，0.3 秒延遲內保留細緻脈動
  - 連鎖爆炸應採用節點延時 0.12s 的序列，突出節奏感
  - 爆炸後殘留紙屑粒子 1.6s 內漸進淡出，避免畫面太亂
```

### Style Pack：Arcane Gambler Audio（`_stylepacks/arcane_gambler/audio.yml`）
```yaml
name: Arcane Gambler Audio
core_layers:
  - wet_street_rain_bed
  - neon_hum_riser
  - card_flick_percussion
  - subpulse_suspense
peak_events:
  - timestamp: card_flick
    sfx: lacquer_snap
    level_db: -10
    stereo_width: 70
  - timestamp: card_stick
    sfx: sigil_whine
    level_db: -6
    stereo_width: 110
  - timestamp: detonate
    sfx: focused_implosion
    level_db: -2
    stereo_width: 150
low_freq_management:
  sub_ceiling_db: -7
  lfe_emphasis: 52Hz
sidechain:
  trigger_bus: explosion_hits
  target: ambience_pad
  reduction_db: 3.2
notes:
  - 彈牌聲須清脆且帶輕微金屬共鳴，襯托魔術師職業感
  - 延遲爆炸時加入升頻 whirr，與 HUD 倒數一致
  - 連鎖爆炸保持節奏如鼓點，最後集束爆破給 0.5s 淡出空間
```

---

## Master Prompt 實際填寫
```
Master(15s｜Arcane Gambler Look｜16:9｜24fps｜雨夜霓虹爆破)
「午夜雨中的廢墟街道；濕滑石板、水窪霓虹倒影、遠方焦煙；爆牌魔術師用撲克牌鎖定怪物群並引爆。」
鏡頭：穩定器半肩視角結合滑軌前推，爆破段加速鞭移。
表演：冷靜決斷、指尖靈巧、視線緊盯鎖定目標。
臉型/髮型：依上傳五官，黑髮微濕貼額，鬢角被風雨掀起。
構圖：前中後層次＋三分線，HUD 留白 15%；動態：雨絲、霓虹煙霧、撲克牌粒子。
寫實細節：黑色長外套紅內襯、皮手套水滴、撲克牌金紅符文、怪物金屬縫補肌理。
無字幕、無商標/Logo/水印。

鏡頭語法：24–35 空間｜50–75 親密｜100–135 壓縮；
光圈 {T2.0–T2.8}；快門角 {180°/200–240°}；
對焦 {單點眼/層次前→中→後}。
光影：{側逆/霓虹混光}；色溫 {夜3000–3800K}；
對比 {高}；眼神光 {保留}。
色調/LUT：{自然肌理/膚色優先/陰影微藍・高光暖/去飽和5–10%}。
聲音：環境/腳步/衣料/風/遠人聲（-6 dB 峰值）；音樂 {節奏輕推}。
轉場：{直接切/光源匹配/鞭移/羽化0.5s}。
安全：無品牌/無可讀文件/群眾臉不近特寫/連戲與時序一致。
```

## Scene Blocks

### Act 1（0.0–4.8s）
意圖：建立
基調：緊張
節奏域：慢入0.8–1.5
美術要點：夜色廢墟街道、水窪霓虹倒影、黑色長外套紅內襯、手中牌組與 HUD 細紋

#### Beat 1（0.0–1.2s）
重點：登場營造職業感
Blocking：主角背影由右側入畫，行進間指尖輕敲牌角
Camera：
- 運鏡：滑軌平推
- 焦段/機位：35mm 半肩後視
- 對焦：單點鎖定手部
- 快門角：200；拍點：指尖敲擊節奏
光影：側逆霓虹反射，雨滴形成細小光點
色調/LUT：陰影微藍6%，金紅高光強調牌邊
聲音：環境雨聲＋指尖「嗒嗒」，遠處怪物低吼
轉場：直接切至半身特寫

Angle A
構圖：三分線，主角佔左側，街道深邃消失點
內容：主角背影與手上牌組
補充：鏡頭前水滴滑落造成暫時模糊
安全：場景僅主角

#### Beat 2（1.2–2.4s）
重點：展示職業標誌特寫
Blocking：主角停步，手掌翻轉洗牌，眼神朝前方
Camera：
- 運鏡：穩定器微推近
- 焦段/機位：55mm 胸高
- 對焦：單點鎖定牌面符文
- 快門角：180；拍點：洗牌停住瞬間
光影：霓虹側逆光勾勒臉部輪廓
色調/LUT：膚色優先，HUD 暗紅 120 nits
聲音：指節摩擦牌面，雨水滴落衣襬
轉場：遮擋切，手勢帶動鏡頭轉向前方

Angle B
構圖：中央偏右，手部佔前景
內容：牌背符文流動
補充：雨水從袖口滴落
安全：無可讀字

#### Beat 3（2.4–3.6s）
重點：怪物群登場建立威脅
Blocking：鏡頭轉向街口，怪物群自陰影走出
Camera：
- 運鏡：滑軌後退並抬升
- 焦段/機位：28mm 眼高
- 對焦：層次拉焦 怪物前排→核心
- 快門角：200；拍點：能量核心脈動
光影：遠處燈光反射在濕地面
色調/LUT：去飽和7%，核心橘紅突顯
聲音：鐵鎖拖地與低吼混合
轉場：鐵鎖掠過鏡頭造成鞭移

Angle C
構圖：中央對稱，怪物佔據畫面
內容：半獸半異形怪物群
補充：玻璃碎屑掉落閃光
安全：僅怪物

#### Beat 4（3.6–4.8s）
重點：鎖定首個目標
Blocking：回到主角視角，準星框住最前方怪物
Camera：
- 運鏡：半肩視角微前推
- 焦段/機位：45mm 肩後
- 對焦：層次拉焦 手→HUD→怪物核心
- 快門角：180；拍點：準星收束
光影：HUD 細線淡紅映在雨霧
色調/LUT：HUD 金紅控制在 120 nits
聲音：背景壓低，只剩心跳與雨聲
轉場：羽化0.5s 進入慢動作

Angle D
構圖：中央準星對準怪物胸口
內容：HUD 細線準星、牌邊光紋
補充：雨滴拖尾線條
安全：HUD 無文字

### Act 2（4.8–8.4s）
意圖：敘事與轉折鋪陳
基調：決斷
節奏域：穩定1.5–2.4
美術要點：撲克牌金紅光紋、怪物裝甲金屬縫補、雨絲與霧氣層次

#### Beat 5（4.8–6.0s）
重點：第一次彈牌
Blocking：主角手指彈出第一張牌
Camera：
- 運鏡：子彈時間滑軌跟拍
- 焦段/機位：60mm 手部平行
- 對焦：呼吸拉焦 手→飛牌
- 快門角：200；拍點：牌離指瞬間
光影：牌邊金紅光暈拉出殘影
色調/LUT：高光暖5% 托起符文
聲音：輕微破風聲「咻」帶金屬共鳴
轉場：動態匹配跟進牌面

Angle E
構圖：過肩視角，牌飛向畫面中央
內容：牌邊發光與火花粒子
補充：雨滴被氣流切開
安全：畫面乾淨

#### Beat 6（6.0–7.2s）
重點：貼牌與延遲爆破預示
Blocking：牌貼在怪物胸口，符文亮起
Camera：
- 運鏡：穩定器快推至怪物胸口
- 焦段/機位：85mm 胸高
- 對焦：單點鎖定卡牌
- 快門角：180；拍點：符文啟動
光影：牌面陣紋脈動，裝甲反射金紅光
色調/LUT：陰影微藍7%，符文保持清晰
聲音：高頻「嗡——」與怪物低吼
轉場：符文脈動閃光

Angle F
構圖：中央特寫，卡牌貼附
內容：卡牌符文、裝甲細節
補充：HUD 倒數環環繞
安全：無文字

#### Beat 7（7.2–8.4s）
重點：第一次精準爆破
Blocking：延遲0.3秒後卡牌內縮爆炸
Camera：
- 運鏡：高速攝影輕微後退
- 焦段/機位：70mm 胸高
- 對焦：單點鎖爆炸點
- 快門角：200；拍點：爆炸瞬間
光影：定點爆破向內收束再外擴
色調/LUT：高對比，火花金紅照亮雨霧
聲音：悶爆「砰」＋碎片落地
轉場：爆炸衝擊波遮擋切

Angle G
構圖：中央爆點佔畫面
內容：裝甲碎片、紙屑飛散
補充：水霧被衝起濺向鏡頭
安全：僅怪物

### Act 3（8.4–12.0s）
意圖：情感推進與戰場掌控
基調：緊張
節奏域：加速2.4–3.0
美術要點：多張牌扇形軌跡、連鎖爆炸火花、半透明 HUD 扇區

#### Beat 8（8.4–9.6s）
重點：多目標投擲
Blocking：主角雙手甩出多張牌
Camera：
- 運鏡：穩定器斜上繞拍
- 焦段/機位：40mm 胸高
- 對焦：層次拉焦 手→牌群
- 快門角：200；拍點：牌散射
光影：扇形軌跡留下紅金光線
色調/LUT：去飽和6%，牌光增亮
聲音：連續彈牌聲與 HUD 連鎖提示
轉場：扇形光線導入下鏡頭

Angle H
構圖：前中後分層，主角居左，牌群往右上
內容：雙手各拋多張牌
補充：HUD 在空中描出扇形界面
安全：無文本

#### Beat 9（9.6–10.8s）
重點：連鎖爆炸掌控節奏
Blocking：多名怪物身上的牌依序引爆
Camera：
- 運鏡：長鏡掃描戰場，微鞭移
- 焦段/機位：32mm 眼高
- 對焦：層次拉焦 爆點→下一目標
- 快門角：200；拍點：每次爆炸
光影：交替爆閃照亮不同方向
色調/LUT：高對比，煙塵保留細節
聲音：節奏感爆炸聲如鼓點
轉場：最後爆閃白光

Angle I
構圖：中央偏右，連鎖爆破引導視線
內容：怪物被爆炸吞沒
補充：碎石與紙屑粒子在空中交錯
安全：僅怪物

#### Beat 10（10.8–12.0s）
重點：精英怪物集束前的牌圈
Blocking：精英怪衝向主角，牌從身上浮起形成旋轉圈
Camera：
- 運鏡：後退滑移保持距離
- 焦段/機位：48mm 胸高
- 對焦：呼吸拉焦 主角→牌圈→怪物
- 快門角：200；拍點：牌圈鎖定
光影：牌圈邊緣火花不斷噴出
色調/LUT：紅金光烘托焦土
聲音：升頻 whirr 與怪物怒吼重疊
轉場：牌圈合攏閃光

Angle J
構圖：中央主角，牌圈環繞怪物
內容：懸空牌組自轉
補充：空氣中紙屑與火花飄散
安全：無文字

### Act 4（12.0–15.0s）
意圖：收束
基調：決斷
節奏域：穩定1.5–2.4
美術要點：集束爆破白光、紙屑慢動作、主角收牌

#### Beat 11（12.0–13.5s）
重點：終結技引爆
Blocking：主角食指輕彈，牌聚合成能量球後爆炸
Camera：
- 運鏡：穩定器前推至半身
- 焦段/機位：65mm 胸高
- 對焦：單點鎖定能量球
- 快門角：200；拍點：白光爆開
光影：能量球內縮後爆閃，全畫面短暫過曝
色調/LUT：過曝後迅速恢復陰影微藍
聲音：低沉巨響後留下耳鳴空洞
轉場：爆炸白光作遮擋

Angle K
構圖：中央能量球，主角指尖置於三分線
內容：聚合能量球爆閃
補充：紙屑慢動作飛散
安全：僅主角與怪物

#### Beat 12（13.5–15.0s）
重點：收尾簽名動作
Blocking：怪物倒地遠景，主角收牌插回口袋
Camera：
- 運鏡：滑軌後退並略微升高
- 焦段/機位：45mm 背影視角
- 對焦：層次拉焦 主角→遠處殘骸
- 快門角：180；拍點：最後一張牌插入口袋
光影：夜風吹動外套，殘餘火星閃爍
色調/LUT：去飽和5%，金紅火星在陰影中跳動
聲音：雨聲恢復主導，紙屑落地輕響
轉場：淡入黑

Angle L
構圖：三分線，主角背對佔左側，遠方焦黑爆點在右
內容：主角收牌、紙屑飄落
補充：外套下襬被夜風掀動
安全：無品牌

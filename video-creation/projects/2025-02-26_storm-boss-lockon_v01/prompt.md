# 雷電弓箭 × BOSS戰｜寫實遊戲風題材 Prompt（15s BOSS戰 VFX 鏡頭）

## 一句話題材
在暴雨中的廢墟廣場，你拉滿雷電長弓，鎖定狂暴巨型 BOSS，一箭貫穿護盾與裝甲。

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

### Style Pack：Storm Boss Lock-On Look（`_stylepacks/storm_boss_lockon/look.yml`）
```yaml
name: Storm Boss Lock-On Look
lut: Tempest-Rain
saturation_adjust: -0.02
contrast: high_dynamic
highlights: electric_blue
shadows: deep_charcoal
texture: rain_slick_armor
chromatic_aberration: restrained_blue_fringe
lens_distortion: micro_barrel
notes:
  - 夜雨環境保留冷藍閃電反光，膚色維持 58 IRE
  - 地面水漬需加入鏡面高光與波紋疊層
  - HUD 螢光元素亮度限制在 120 nits，避免壓過雷弓電弧
```

### Style Pack：Storm Boss Lock-On VFX（`_stylepacks/storm_boss_lockon/vfx.yml`）
```yaml
name: Storm Boss Lock-On VFX
niagara_presets:
  - electromagnetic_bowstring
  - shield_shatter_ring
  - serpent_ground_arcs
unity_vfx_graph:
  - StormBow.DrawPulse.vfx
  - BossShield.Fragment.vfx
  - CoreImplode.Cascade.vfx
houdini_flipbooks:
  - rain_sheet_hit_sparks
  - mech_plating_shatter
  - plasma_core_bloom
shader_settings:
  bolt_core_thickness: 0.38
  shield_crystalize_speed: 0.55
  arrow_trail_decay: 0.42
  hud_glow_intensity: 0.28
sdf_settings:
  boss_surface_wrap: 0.32
  weakpoint_lock_radius: 0.18
  debris_spawn_delay: 0.2
bloom_control:
  idle: 0.16
  trigger_peak: 0.88
  cooldown: 0.35
audio_sync:
  bow_draw_resonance: align_to_heartbeat
  release_flash: accent_thunderstring
  core_blast: sync_mech_implode
notes:
  - 拉弦期間 HUD 粒子需遵循電弧張力曲線，避免穿幀
  - 護盾破裂採用多層玻璃碎片與能量薄膜交錯，1 frame 延遲切換發光貼圖
  - 核心爆閃後地面殘留蛇型電光需沿裂縫動態遮罩延長 3 frame
```

### Style Pack：Storm Boss Lock-On Audio（`_stylepacks/storm_boss_lockon/audio.yml`）
```yaml
name: Storm Boss Lock-On Audio
core_layers:
  - torrential_rain_bed
  - bowed_metal_tension
  - subpulse_heartbeat
  - arc_flash_whoosh
peak_events:
  - timestamp: lock_confirm
    sfx: hud_pulse_ping
    level_db: -8
    stereo_width: 90
  - timestamp: arrow_release
    sfx: thunderstring_snap
    level_db: -3
    stereo_width: 140
  - timestamp: core_detonation
    sfx: mech_beast_implode
    level_db: -2
    stereo_width: 160
low_freq_management:
  sub_ceiling_db: -5
  lfe_emphasis: 48Hz
sidechain:
  trigger_bus: impact_bus
  target: subpulse_heartbeat
  reduction_db: 2.5
notes:
  - 雨聲需隨鏡頭切換維持連續，避免跳變
  - 雷弓拉弦時加入靜電細沙聲作粒子提示
  - 爆炸後殘留電弧使用反向混響緩慢衰減 1.2s
```

---

## Master Prompt 實際填寫
```
Master(15s｜Storm Boss Lock-On Look｜16:9｜24fps｜雨夜鏡面閃光)
「暴雨夜的廢墟廣場；碎石殘骸、地面水窪、遠方雷雲；主角拉滿雷電長弓鎖定狂暴機械巨獸胸口核心。
鏡頭：滑軌平移＋半肩穩定器微繞。
表演：決斷緊繃、呼吸壓抑、視線鎖定弱點。
臉型/髮型：依上傳五官特徵，濕潤短髮貼額。
構圖：前中後層次＋三分線 HUD 留白10–20%；動態：雨水、電弧、HUD 粒子。
寫實細節：近未來輕裝甲金屬反光、雨水滑落、弓臂肌理繃緊、雷雲體積閃光。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35 空間｜50–75 親密｜100–135 壓縮；
光圈 {T2.0–T2.8}；快門角 {180°/200–240°}；
對焦 {單點眼/層次前→中→後}。
光影：{側逆/體積}；色溫 {夜3000–3800K}；
對比 {高}；眼神光 {保留}。
色調/LUT：{自然肌理/膚色優先/陰影微藍・高光暖/去飽和5–10%}。
聲音：環境/腳步/衣料/風/遠人聲（-6 dB 峰值）；音樂 {氛圍/節奏輕推}。
轉場：{直接切/光源匹配/鞭移}。
安全：無品牌/無可讀文件/群眾臉不近特寫/連戲與時序一致。
```

## Scene Blocks

### Act 1（0.0–3.0s）
意圖：建立
基調：緊張
節奏域：慢入0.8–1.5
美術要點：廢墟廣場碎石＋金屬殘骸、雨水水窪、遠方雷雲閃光、BOSS 破損裝甲蒸汽

#### Beat 1（0.0–1.5s）
重點：BOSS 咆哮、護盾閃耀，建立威脅
Blocking：BOSS 居中咆哮，胸口核心鼓脹閃紅光
Camera：
- 運鏡：滑軌前推
- 焦段/機位：35mm 胸高
- 對焦：層次拉焦 核心→獸頭
- 快門角：200；拍點：胸腔閃光
光影：側逆光＋雷光瞬閃，霧雨折射
色調/LUT：陰影微藍6%，高光暖4%
聲音：遠距咆哮＋雷鳴回蕩，雨聲濕重
轉場：鞭移→主角背後視角

Angle A
構圖：中央對稱，BOSS 充滿畫面
內容：BOSS 胸腔能量充填
補充：胸口護盾電紋擴張、地面水花跳動
安全：無文字

#### Beat 2（1.5–3.0s）
重點：鏡頭轉至主角肩後，鎖定框架展開
Blocking：主角左前景進入，拉弓預備；BOSS 在遠景正對
Camera：
- 運鏡：穩定器側移並抬升
- 焦段/機位：50mm 肩後半肩視角
- 對焦：層次拉焦 主角→HUD→弱點
- 快門角：180；拍點：鎖定框線閉合
光影：主角肩甲反光帶出雷光輪廓
色調/LUT：去飽和6%，HUD 電藍提亮
聲音：HUD 鎖定提示疊加心跳低頻
轉場：HUD 脈衝閃白

Angle B
構圖：三分線，主角背影佔左側，BOSS 弱點置於準星
內容：HUD 四框線滑入弱點
補充：雨滴掠過鏡頭，粒子受電場吸附
安全：無額外人物

### Act 2（3.0–7.0s）
意圖：情感蓄力
基調：決斷
節奏域：穩定1.5–2.4
美術要點：主角雷電弓、靜電揚起髮梢、弓身發光紋路、HUD 半透明層

#### Beat 3（3.0–5.0s）
重點：主角側臉與手部特寫，弓弦電弧蓄力
Blocking：主角右手拉弦至極限，肌肉繃緊，左手穩固弓身
Camera：
- 運鏡：穩定器微環繞
- 焦段/機位：75mm 眼高
- 對焦：單點鎖指節
- 快門角：180；拍點：電弧強度提升
光影：體積光掃過臉部，雨滴折射藍光
色調/LUT：膚色優先，陰影微藍7%
聲音：靜電噼啪＋弓弦嗡鳴，呼吸壓抑
轉場：雨滴擦鏡引導

Angle C
構圖：中近景三分線
內容：手指與電弧弓弦接觸處火花飛濺
補充：靜電扭曲空氣、衣角被吸起
安全：僅主角

#### Beat 4（5.0–7.0s）
重點：HUD 展示鎖定完成，能量蓄滿
Blocking：準星縮放呼吸同步心跳，核心亮度上升
Camera：
- 運鏡：半肩視角輕微前推
- 焦段/機位：60mm 肩後
- 對焦：層次拉焦 HUD→核心
- 快門角：180；拍點：「鎖定完成」脈衝
光影：HUD 淡藍光暈包覆 BOSS 核心
色調/LUT：HUD 電藍維持 120 nits，背景去飽和7%
聲音：HUD 脈衝 ping，心跳低頻側鏈壓縮
轉場：脈衝擴散切至子彈時間

Angle D
構圖：前中後分層，準星居中央
內容：鎖定框線呼吸縮放，粒子向外飄散
補充：四個細長矩形邊框滑入閉合
安全：無文本

### Act 3（7.0–10.0s）
意圖：轉折
基調：緊張
節奏域：加速2.4–3.0
美術要點：電弓發射殘影、箭矢能量體、雨滴被震開

#### Beat 5（7.0–8.5s）
重點：弓弦彈出瞬間，鏡頭震動
Blocking：主角放開弓弦，電弧斷裂成箭矢
Camera：
- 運鏡：半肩視角急速前推後急停
- 焦段/機位：50mm 肩後
- 對焦：呼吸拉焦 手→箭軌
- 快門角：200；拍點：箭矢離弦
光影：電弧爆閃照亮臉部與雨霧
色調/LUT：高光暖4%，陰影藍8%
聲音：雷弓「嗡」＋電流爆發，鏡頭震動
轉場：箭矢殘影引導動態切

Angle E
構圖：過肩視角
內容：箭矢主幹電弧延伸，外圍分支閃爍
補充：箭身殘影 0.5s 內漸逝
安全：僅主角與箭軌

#### Beat 6（8.5–10.0s）
重點：箭矢飛行子彈時間，BOSS 視角恐懼
Blocking：鏡頭切至 BOSS 視角，箭矢直衝核心
Camera：
- 運鏡：手持≤3% 前衝
- 焦段/機位：24mm 俯視核心
- 對焦：單點鎖定箭尖
- 快門角：180；拍點：護盾接觸
光影：護盾表面亮起晶化紋路
色調/LUT：去飽和5%，閃光提亮
聲音：低頻轟鳴拉長，箭矢尖嘯
轉場：護盾碎片閃白切入爆炸

Angle F
構圖：中央特寫
內容：護盾玻璃能量膜結晶再炸裂
補充：碎片飛散帶電火花
安全：僅 BOSS

### Act 4（10.0–15.0s）
意圖：收束
基調：決斷
節奏域：穩定1.5–2.4
美術要點：護盾破裂碎片、核心爆閃、地面電光爬行、塵霧

#### Beat 7（10.0–12.5s）
重點：護盾破裂與核心爆閃
Blocking：護盾碎裂→箭入核心→白藍閃光
Camera：
- 運鏡：滑軌前推接近核心
- 焦段/機位：65mm 胸高
- 對焦：層次拉焦 護盾→核心→碎片
- 快門角：200；拍點：核心內縮爆閃
光影：爆閃過曝 0.4s，周圍逆光邊緣
色調/LUT：高光暖2%，陰影藍9%
聲音：護盾破裂「咔嗒」＋高頻嘯聲，爆閃重擊
轉場：爆閃漸暗帶入跪地

Angle G
構圖：中央對稱
內容：核心爆閃噴出金屬碎片與能量火花
補充：粒子層次：金屬塊、電火花、灰塵、煙霧
安全：無其他人物

#### Beat 8（12.5–15.0s）
重點：BOSS 跪地熄火，主角收弓
Blocking：BOSS 膝軟跪倒，主角放下長弓，HUD 框線淡出
Camera：
- 運鏡：穩定器後退抬升
- 焦段/機位：45mm 背後
- 對焦：層次拉焦 BOSS→主角→前景塵霧
- 快門角：180；拍點：HUD 消退
光影：雨霧瀰漫，電光沿地面裂縫爬行
色調/LUT：去飽和6%，餘暉保持電藍邊緣光
聲音：金屬崩塌、電弧滋滋、雨聲回歸、音樂漸收
轉場：尾段雨聲長停

Angle H
構圖：前景塵霧作框，主角居左三分線
內容：BOSS 跪地，眼光熄滅，HUD 線條淡出
補充：蛇型電光沿裂縫延伸 3s 後熄滅
安全：無文字

## HUD / UI 特化說明
- 鏡頭維持第三人稱半肩視角時，HUD 以 70% 透明度疊加，避免遮擋主體。
- 鎖定框線由四個細長矩形自外向內滑入，0.8s 完成閉合，鎖定期間以 0.9–1.05 倍縮放循環模擬心跳。
- 成功鎖定瞬間觸發亮藍圓形脈衝，由核心向外擴散 1.2 倍畫面寬度並於 12 frame 內淡出。
- 螢幕邊緣 HUD 弧線保持微弱發光，左下血條僅顯示抽象格子，不出現文字或數字。

## VFX 技術細節
- 雷電弓弦採用 Niagara `electromagnetic_bowstring` 預設，弓弦電弧以粒子子系統驅動分支閃爍，觸點使用 GPU 粒子迸出微型雷球。
- 箭矢能量體使用 shader `bolt_core_thickness 0.38`，主幹電弧採 Flowmap 驅動，外層透明度根據箭速調整 `arrow_trail_decay 0.42`。
- 护盾破裂：先啟動 `shield_shatter_ring`，將護盾表面轉換為玻璃晶格材質並以 Houdini Flipbook `mech_plating_shatter` 投影，碎片帶電火花 2 frame 延遲加入。
- 核心爆閃以 `plasma_core_bloom` Flipbook 疊加，Bloom 於 0.2s 內衝至 0.88，隨後在 0.6s 下降至 0.2；同時驅動 serpent_ground_arcs 沿裂縫爬行 3s。
- HUD 粒子以 `hud_glow_intensity 0.28` 限制發光，並透過 Audio Sync `bow_draw_resonance` 與心跳層對齊，避免閃爍脫節。

## 粒子與模擬要點
- 雨滴採 GPU 粒子，撞擊地面時觸發 `rain_sheet_hit_sparks` 生成電火花；近鏡頭雨滴使用 Flipbook 8×8 確保景深暈染。
- 地面水窪使用 Flowmap 扭曲反射，雷光閃爍時提升 Roughness→Specular 對比，呈現鏡面反射閃動。
- 核心爆炸噴發的金屬碎片使用 RBD 模擬，並附帶 Trail 粒子造成帶電殘光；碎片飛近鏡頭時加啟 Motion Blur 25% 加乘。

## 音訊設計
- 依 Storm Boss Lock-On Audio 分層，雨床維持 -12 dBFS，心跳層以 45Hz LFE 突顯鎖定壓力。
- HUD 鎖定提示使用 `hud_pulse_ping`，脈衝與準星縮放對應；鬆弦瞬間 `thunderstring_snap` 與鏡頭震動同步。
- 核心爆閃觸發 `mech_beast_implode`，後接反向混響形成尾韻 1.2s，最後以環境雨聲收束回歸。

## 交付備註
- 解析度 3840×2160（16:9），24fps，EXR 或 ProRes 4444 with Alpha；保留 HUD 元素於獨立 Render Pass。
- 角色與 BOSS 使用 Unreal Engine 5 Sequencer 搭配 Niagara；HUD 於後期合成並鎖定螢幕空間。
- QA：確認無可讀文字、雷電亮度未過曝、HUD 與 BOSS 核心對齊；爆炸後殘留電光在 3s 內自然熄滅並避免循環感。

# 曲線光彈初啟 — Master Prompt（15s｜12 幕）

## 一句話題材
燁程在霧濕樹林遭異獸夾擊，背抵岩壁被逼入死角，手背的程式紋突然啟動，召喚出第一枚彎射光彈 Curve Bolt 逆轉危機。

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

### Style Pack：Light Glyph Anime Look（`_stylepacks/light_glyph_anime/look.yml`）
```yaml
name: Light Glyph Anime Look
line_enhancement: crisp_vector_edge
noise_reduction: cel_plate_clean
saturation: dual_tone_split
contrast_profile: luminous_soft_mid
color_palette:
  primaries: [fog_blue, slate_gray, midnight_indigo]
  accents: [auric_gold, mint_glow]
  skin_tone: warm_amber
glow_layers:
  base_fill: cool_diffused
  rim_accents: HUD_edge_trace
  spell_core: emissive_gold_script
ui_overlay: parallax_glass_hud
bloom_intensity: 0.32
shadow_treatment: soft_multipass_cel
motion_blur_shutter: 165
texture_pass: layered_papergrain_subtle
notes:
  - 2D 線條需保持乾淨俐落，適度加粗邊緣讓 HUD 光軌不吞線。
  - 城市環境以冷灰與霧藍主調，透過金色與薄荷藍魔法光強化高對比。
  - HUD 與程式碼浮層採半透明玻璃質感，確保角色臉部仍清晰可見。
  - 施法時增加眼睛與衣內銀線的同步脈動光，營造「發光程式」感。
```

### Style Pack：Light Glyph Anime VFX（`_stylepacks/light_glyph_anime/vfx.yml`）
```yaml
name: Light Glyph Anime VFX
layer_stack:
  - background_mist_scroll
  - hud_symbol_plane
  - spell_vector_trail
  - glow_dust_overlay
spell_trail:
  color_mix: [auric_gold, mint_glow]
  taper: 0.42
  flicker_speed: 0.28
hud_widgets:
  panel_opacity: 0.65
  glyph_refresh_rate: 14
  debug_log_spacing: 18
error_feedback:
  color: crimson_error
  glitch_amount: 0.36
  frame_freeze: 0.08
particle_settings:
  glyph_sparks: 0.54
  light_dust: 0.32
  cat_starflare: 0.41
disintegration_fx:
  hexshield_tile_break: 0.57
  light_code_dissolve: 0.49
notes:
  - HUD 浮層需與角色動作略帶遲滯，營造空中投影被拉扯的感覺。
  - 能量彎射路徑依角色揮手軌跡生成弧形光帶，符文沿光帶流動。
  - 蜂巢六角盾破碎後應立即重排，碎片化為細小光粒回收至掌心。
  - 米漿星火充能時，尾端粒子需向胸口光晶形成柔和渦流。
```

### Style Pack：Light Glyph Anime Audio（`_stylepacks/light_glyph_anime/audio.yml`）
```yaml
name: Light Glyph Anime Audio
time_signature: 4/4
bpm_range: [92, 108]
ambient_beds:
  - soft_city_air_hum
  - crystalline_aether_pad
rhythmic_layers:
  percussive_clicks: holo_keyboard_taps
  sub_pulse: low_orbital_throb
ui_fx:
  glyph_expand: airy_chime_hi
  compile_ping: glassy_beep_mid
  error_flag: clipped_square_red
spell_sweeteners:
  curve_bolt_release: arc_bow_sheen
  hexshield_reform: hex_shingle_swirl
  cat_starflare: purr_riser_glow
mix_notes:
  - 對話維持 -6 dB 峰值，HUD 音效壓在 -12 dB 以下避免干擾詠唱。
  - 程式碼浮現時加入細緻鍵擊聲，與主角手指敲擊空氣同步。
  - 米漿心電音色偏低沉慵懶，情緒激動時可疊加高頻毛髮靜電。
  - 戰鬥高潮加強 4kHz 以上空氣感，讓光線爆閃更具穿透力。
```

---

## Master Prompt 實際填寫
```
Master(15s｜Light Glyph Anime Glyph-Combat｜16:9｜24fps｜濕霧冷藍＋金線脈動質感)
「夜霧瀰漫的濕泥林道；倒伏樹幹、青苔岩壁、HUD 弧形追蹤視窗；燁程被獸群追逼至岩壁，驚慌間啟動手背光紋，釋放第一枚彎射 Curve Bolt 斜穿怪物肩甲。 
鏡頭：手持 26mm 側向追奔 → 32mm 後跟晃動 → 50mm 俯視怪物飛撲 → 35mm 正面撞壁定格 → 55mm 近距右手特寫 → 40mm 半身抬掌 → 28mm 掌心低角 → 60mm 追蹤光彈 → 75mm 長焦撞擊 → 45mm 橫搖落地 → 65mm 低角餘震 → 50mm 胸近景停留。 
表演：燁程喘息急促、眉頭緊皺；背貼岩壁時瞳孔急收，詠唱時下意識含糊念出咒語；光彈命中後手指顫抖，嘴角因震驚微開。 
臉型/髮型：黑色短髮被霧濡濕貼額，臉型帶尖下巴，額頭汗珠、頰側泥痕。 
構圖：奔跑段採三分線側後跟拍；岩壁段中央鎖定強化窘境；施法段讓掌心位於畫面左下黃金分割，光彈弧線跨越至右上；動態：雨霧飄動、泥水濺起、怪物骨甲振動、手背符紋逐段點亮。 
寫實細節：濕泥濺在襯衫下擺、背包背帶甩動；怪物骨甲夾帶水滴，撞擊時骨碎與焦黑肉屑帶蒸汽；HUD 曲面與 UI 文案改為抽象符號；岩壁苔蘚受衝擊掉落細粉被金光照亮。 
無字幕、無商標/Logo/水印。」

鏡頭語法：26–35 建立追擊 → 40–55 聚焦施法 → 60–75 強化擊中 → 50 收束；
光圈 {T2.4–T3.2} 奔跑段淺景深隔離背景，施法時收至 {T4} 兼顧手掌與面部，命中瞬間開至 {T2.0} 製造光暈；快門角 {165°} 奔跑拖影，施法與爆裂收斂至 {150°}。 
對焦 {手動層次前→中→後} 在追擊段從前景枝葉拉至燁程，再鎖定掌心單點，命中瞬間呼吸拉焦至肩甲縫隙爆點。 
光影：森林上方冷霧漫射＋側逆月光，怪物逼近時加入 HUD 青金補光；施法時掌心金光成主光並投射在臉部右側；色溫 夜 3600K 基底，Curve Bolt 核心升至 5200K。 
對比 {中高}，眼神光 {由掌心反射維持}。 
色調/LUT：背景維持霧藍與石灰，角色膚色暖琥珀，Curve Bolt 弧線帶薄荷藍外緣與金色核心；去飽和 4%。 
聲音：環境以 soft_city_air_hum 降頻處理成林中風聲，搭配濕泥腳踩聲、低頻骨甲撞擊；詠唱時導入 airy_chime_hi 與 glassy_beep_mid 疊加；Curve Bolt 放出伴隨 arc_bow_sheen，命中時爆出刺耳白光衝擊配 low_orbital_throb 下沉；音樂取 96BPM 氛圍弦樂交錯電子律動，高潮提升高頻粒子音。 
轉場：泥水濺幕遮擋切換 → 追擊視角甩鏡直切 → 飛撲怪物以前景掠過 wipe → 掌心亮起以光耀羽化 → 光彈沿弧線動態匹配 → 爆裂以骨片遮擋 → 結尾定格淡出。 
安全：怪物造型抽象化無現實物種，HUD 字串為符號矩陣，避免血腥露骨僅呈焦黑煙。 
```

---

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立追擊壓力與走投無路的絕境
基調：緊張、求生
節奏域：加速2.4–3.0
美術要點：濕泥林地、青苔岩壁、破損白襯衫、骨甲異獸

#### Beat 1（0.0–2.4s）
重點：燁程拼命逃竄，獸群緊追在側
Blocking：燁程急轉身衝向鏡頭左方森林→鏡頭側後手持跟拍→怪物低伏疾奔貼地
Camera：
- 運鏡：手持側向追拍帶 5% 抖動
- 焦段/機位：26mm 胸高側後→32mm 低角拉近
- 對焦：層次拉焦從前景枝葉到燁程，再滑向後方獸群
- 快門角：165；拍點：泥水濺起、燁程喘息停頓
光影：月光穿樹投射斑駁冷光，獸群伴有霧中青金 HUD 追蹤線
色調/LUT：背景霧藍，燁程膚色暖琥珀，泥水偏墨綠
聲音：濕泥腳踩、喘息、獸群低吼與骨甲咯噔
轉場：獸群貼近時以泥水濺鏡遮擋 → Angle 2

Angle 1（0.0–1.2s）
構圖：燁程位於右側三分線，左側前景樹幹帶動速度
內容：燁程回頭一瞥後猛力轉身奔跑
補充：泥水濺上鏡頭下緣形成流痕
安全：服飾無 Logo，背景無人工設施

Angle 2（1.2–2.4s）
構圖：中央透視延伸，怪物半遮燁程背後
內容：兩隻骨甲獸貼地狂奔，蹄帶火花
補充：骨甲互相碰撞火花呈金綠色
安全：怪物細節抽象符紋避免血腥

#### Beat 2（2.4–5.0s）
重點：前後夾擊，燁程被迫停在岩壁前
Blocking：怪物自樹幹飛撲越過→前方怪物落地封堵→燁程急煞背撞岩壁
Camera：
- 運鏡：肩扛手持前推→瞬間停住
- 焦段/機位：50mm 俯拍怪物飛越→35mm 眼高正面→40mm 胸高貼面
- 對焦：單點追蹤飛撲怪物→切換燁程面部
- 快門角：150；拍點：怪物落地、背撞岩壁
光影：飛撲怪物受月光輪廓光，岩壁處反射金色苔蘚微光
色調/LUT：岩壁灰青，怪物牙齒泛冷白
聲音：獸吼疊加低頻撞擊，燁程喘息加重
轉場：燁程背撞引發塵霧羽化 → Act 2

Angle 3（2.4–3.6s）
構圖：俯視角呈弧線，燁程居中，下方怪物掠過
內容：怪物沿樹幹翻越畫面上方
補充：殘影拉出薄荷藍尾跡
安全：無血腥殘肢

Angle 4（3.6–4.4s）
構圖：正面中央，前景岩壁佔滿畫面
內容：前方怪物低身張嘴封死出路
補充：牙縫間滴下黏稠唾液被月光映成銀線
安全：唾液透明無血絲

Angle 5（4.4–5.0s）
構圖：胸近景，燁程背貼岩壁
內容：燁程猛力煞停、背撞岩石，瞳孔放大
補充：衣料與岩壁摩擦掉落苔蘚粉
安全：岩壁紋理無可辨字樣

### Act 2（5.0–9.0s）
意圖：聚焦能力啟動與 Curve Bolt 構築
基調：驚懼中覺醒
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：掌心光紋、HUD 彈窗、光陣構築

#### Beat 3（5.0–7.2s）
重點：手背光紋啟動，UI 彈出提示
Blocking：燁程抬手護胸→光紋沿手背亮起→HUD 文字浮現，燁程小聲詠唱
Camera：
- 運鏡：微移定格
- 焦段/機位：55mm 右手特寫→40mm 半身
- 對焦：單點鎖定光紋→拉回臉部與 HUD
- 快門角：150；拍點：光紋點亮節點、UI 彈出
光影：掌心金光為主光，背景獸影保持低亮度
色調/LUT：掌心金色對比冷藍森林
聲音：airy_chime_hi、glassy_beep_mid 隨光紋節點同步；低語詠唱
轉場：HUD 彈窗邊框掃過 → Angle 7

Angle 6（5.0–6.0s）
構圖：極近特寫，手背佔據畫面中央
內容：淡金線條像電路亮起至指節
補充：皮膚汗水冒出細小蒸汽
安全：手部無刺青文字

Angle 7（6.0–7.2s）
構圖：半身偏左三分線，右側 HUD 透明懸浮
內容：燁程凝視 HUD，唇形輕動念咒
補充：HUD 顯示「【基礎模組載入：能量彎射 Curve Bolt】」採符號體
安全：字體抽象不可讀

#### Beat 4（7.2–9.0s）
重點：掌心光陣構築並發射彎射光彈
Blocking：掌心前浮出光陣→光彈沿弧線飛出繞開怪物
Camera：
- 運鏡：低角推進追隨光彈
- 焦段/機位：28mm 掌心→60mm 追蹤光彈→75mm 長焦壓縮怪物
- 對焦：掌心→光彈→怪物肩甲縫隙
- 快門角：155；拍點：光陣完成、光彈拐彎
光影：光陣照亮周遭霧氣形成薄金霧帶
色調/LUT：金色核心配薄荷藍外緣，背景保持霧藍
聲音：arc_bow_sheen 隨光彈飛行，低頻 sub_pulse 推動緊張感
轉場：光彈尾跡拉出動態 wipe → Act 3

Angle 8（7.2–8.4s）
構圖：掌心位於左下三分線，光陣環繞
內容：線條如微縮主機板繞行
補充：符文以 HUD_edge_trace 光邊閃爍
安全：符號抽象

Angle 9（8.4–9.0s）
構圖：光彈弧線佔畫面，怪物在右側前景
內容：光彈先往側邊再折向怪物肩部
補充：尾跡粒子順勢拖出符文殘影
安全：爆裂前無血花

### Act 3（9.0–15.0s）
意圖：展示命中爆裂與燁程震驚反應
基調：決斷、驚喜
節奏域：穩定1.5–2.4 → 慢入0.8–1.5
美術要點：肩甲爆裂光芒、泥坑濺起、掌心餘光

#### Beat 5（9.0–12.0s）
重點：怪物肩甲被穿透爆裂，撲擊被打斷
Blocking：光彈鑽入肩甲縫隙→白光爆出骨片與焦肉→怪物失衡墜地
Camera：
- 運鏡：長焦橫搖配爆點拉焦
- 焦段/機位：75mm 側面→45mm 跟落地
- 對焦：鎖定肩甲 → 拉至墜地泥坑
- 快門角：150；拍點：爆光、落地砸坑
光影：爆炸白光瞬間壓過月光，殘餘以金粉漂浮
色調/LUT：白光中夾少量青綠粒子，泥坑偏深褐
聲音：爆裂聲帶高頻尖嘯，接著低沉悶響與泥濺聲
轉場：泥濺遮擋 → Beat 6

Angle 10（9.0–10.8s）
構圖：長焦壓縮，怪物肩甲佔右側
內容：光彈鑽入縫隙爆出白光
補充：骨片與焦肉被光化為粒子
安全：避免血腥僅焦黑碎屑

Angle 11（10.8–12.0s）
構圖：低角斜視，怪物向左側翻落
內容：怪物半空失衡重摔，地面砸出泥坑
補充：泥水與光粉混合形成羽化霧
安全：無斷肢

#### Beat 6（12.0–15.0s）
重點：燁程確認初次反擊成功的震驚
Blocking：鏡頭回到燁程→他喘息望向顫抖右手→光紋漸暗
Camera：
- 運鏡：穩定器慢推定格
- 焦段/機位：65mm 低角→50mm 胸近景
- 對焦：臉部眼神→手掌餘光
- 快門角：160；拍點：呼吸調整、口型「成了？」
光影：掌心餘光逐漸暗去，月光重新主導
色調/LUT：恢復冷藍主調，掌心留微弱金色餘暉
聲音：呼吸聲疊 soft_city_air_hum 回落；遠處獸群低吼漸散；小聲呢喃錄為囁語
轉場：最後以呼吸停頓 freeze frame 收束

Angle 12（12.0–15.0s）
構圖：胸近景，燁程居中偏右，背後岩壁模糊
內容：燁程驚魂未定看著右手，小聲說「……成了？」
補充：掌心光紋逐段暗下，胸膛起伏明顯
安全：對白僅囁語無字幕

---

## 音訊層級與節奏指引
- 96BPM 混合弦樂與電子節拍；前 5s 使用低頻 drone 與 soft_city_air_hum 轉為森林夜風質感，中段加入 crystalline_aether_pad 疊加緊張弦樂顫音。
- 曲線光彈構築採 airy_chime_hi 分層，節點亮起時加入 holo_keyboard_taps 作為節奏提示；釋放瞬間堆疊 arc_bow_sheen 與低頻 sub_pulse。
- 爆裂時添加短促 white flash hit + 骨甲碎裂金屬聲，落地泥濺使用低頻拍擊配合輕微延遲。
- 尾段降低音量，留下喘息與遠處獸吼迴音，背景音樂僅保留高頻粒子聲點綴。

## 交付備註
- 影格速率 24fps，需保留 1% hand-held jitter 以維持緊張質感。
- HUD 文案採符號矩陣輸出，嚴禁出現可讀語言；怪物血液以能量粒子替代。
- Curve Bolt 尾跡顏色需符合 style pack 定義：金色核心＋薄荷藍邊緣。

## QA 自檢
- [x] 結構完整：Master、Scene Blocks、音訊與交付備註齊備。
- [x] 敘事一致：分鏡與曲線光彈首次釋放劇情一致。
- [x] 視聽細節：運鏡、光影、聲音與 VFX 參數具體明確。
- [x] 風格準確：完全引用 Light Glyph Anime 相關樣板。
- [x] 格式精準：時間軸、幕次、標題與符號符合規範。
- [x] 安全檢核：移除可讀文字與血腥元素，符合 QA Checklist。

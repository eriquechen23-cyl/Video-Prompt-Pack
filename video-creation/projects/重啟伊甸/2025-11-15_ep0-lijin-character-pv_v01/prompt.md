# 重啟伊甸 Eden Reboot｜黎燼 角色 PV Prompt（15s 殘檔回聲）

## 一句話題材
在被無限重啟的伊甸樂園裡，殘檔抄寫員黎燼在一次次改寫紀錄救人時，逐漸失去自己的記憶與原初自我。

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

### Style Pack：Anime Fantasy Look（`_stylepacks/anime_fantasy/look.yml`）
```yaml
name: Anime Fantasy Look
noise_reduction: clean_edges
saturation: vivid_controlled_skin
line_enhancement: strong_outline
color_palette:
  primaries: [pastel_magenta, teal, warm_gold]
  skin_tone: protected
motion_blur_shutter: 150
notes:
  - 邊緣俐落，維持動畫質感
  - 色彩飽和但控制膚色
  - 建議搭配 24–35mm 誇張空間感
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

### Style: Eden Reboot Archive Residue（新增）
- 適用：2D 動畫 PV，聚焦黎燼在重啟殘檔與自我消融間的冷靜悲劇感。
- 色彩：主體採冷銀灰與墨藍，背景以低飽和金色殘光，故障時加入翡翠色掃描線與橘紅錯位殘影。
- 線條：角色邊緣保持乾淨細線，光屏與資料層使用幾何 HUD 線框，重啟閃光時增粗 15%。
- 光影：檔案館採 4800K 冷光混合金粉粒子，外部樂園使用 5200K 柔陽光但天空帶倒帶式拖影；廢墟段改為 3600K 月冷光搭配高對比剪影。
- 粒子：金色文字塵、半透明資料層、停滯的雨滴與沙塵；記憶抽離時使用逆流碎片向上飄散。
- 限制：字幕固定置底中央，字體細白描邊；避免鮮豔暖色大面積覆蓋角色；故障殘影不可超過 2 frame 靜止。
- 代表元素：殘檔筆黑色筆桿＋金色筆尖、銀灰瞳孔內的環形刻度、延遲的影子動作。

---

## Master Prompt 實際填寫
```
Master(15s｜Anime Fantasy Look × Eden Reboot Archive Residue｜16:9｜24fps｜2D 動畫科幻抒情)
「重啟循環中的伊甸樂園與檔案館；金色文字塵、重疊城市藍圖、凍結終末殘骸；殘檔抄寫員黎燼改寫紀錄的同時，被抽離記憶仍堅守最後一行。
鏡頭：穩定器滑軌結合緩推、偶爾短促跳格與疊化模擬重啟；使用 HUD 遮擋與匹配剪接銜接記憶片段。
表演：黎燼維持克制冷靜，眼神偶爾閃過疲憊與決心；對應記憶抽離時眉間緊縮、呼吸加快。
臉型/髮型：短而凌亂的深灰髮，側劉海遮住右眼裂紋一角；臉型偏瘦長，膚色蒼白帶青。
構圖：前中後層次強調懸浮書架與多重城市殘影，保留 12% 空間給字幕；動態：漂浮文字塵、HUD glitch、延遲影子。
寫實細節：藏青長外套內襯銀灰襯衫、指節繭痕、殘檔筆金屬光澤、紙面浮現金色數據。
無字幕、無商標/Logo/水印（最終字幕以工具疊加）。

鏡頭語法：24–35 空間｜50–75 親密；
光圈 {T2.0–T2.8}；快門角 {180°，重啟跳格時 144°}；
對焦 {層次前→中→後，記憶抽離時短暫呼吸拉焦}。
光影：檔案館冷側光＋金粉體積光；外部樂園柔陽光；廢墟段採側逆冷光；色溫 {4800K/5200K/3600K}；
對比 {中高}；眼神光 {保留微弱高光}。
色調/LUT：膚色優先、陰影偏藍、金色高光增加 8% 飽和，故障時去飽和 6%。
聲音：環境（風、翻頁、遠方倒轉城市噪音）/衣料/筆觸/記憶抽離時頻率掃描；音樂 {氛圍絃樂＋低頻脈衝}，日文配音＋中文字幕。
轉場：直接切搭配 HUD 遮擋與資料粒子匹配，記憶段使用 0.4s 羽化。
安全：無品牌、檔案文字僅顯示虛構編號、字幕固定中下安全區。
```

## Scene Blocks

### Act 1（0.0–4.8s）
意圖：建立世界與重啟樂園的表象
基調：孤獨
節奏域：慢入0.8–1.5
美術要點：無盡檔案館、光屏漂浮城圖、黎燼背影、金色文字塵

#### Beat 1（0.0–1.2s）
重點：檔案館靜止空景
Blocking：無人機鏡緩慢前推，遠處黎燼定格於桌前。
Camera：
- 運鏡：穩定器滑軌直線前推
- 焦段/機位：24mm 眼高俯視微下
- 對焦：層次拉焦 書架→光屏→黎燼
- 快門角：180；拍點：光屏閃爍
光影：冷側光＋金粉體積光
色調/LUT：陰影微藍，高光暖金
聲音：風聲、翻頁迴響、遠處資料嘀嗒
轉場：金色文字塵掃過鏡頭 → 下一段

Angle A
構圖：前景書架形成框景，黎燼位於遠方中央 1/3
內容：靜止書架、懸浮光屏
補充：漂浮文字塵緩慢下降
安全：去可讀真實標誌

#### Beat 2（1.2–2.4s）
重點：黎燼背影與重疊城市地圖
Blocking：鏡頭貼近黎燼後方，他翻頁呼叫多層 HUD。
Camera：
- 運鏡：微推＋懸停
- 焦段/機位：35mm 胸高
- 對焦：單點鎖 HUD 層
- 快門角：180；拍點：HUD 疊加
光影：面前光屏反光塑造冷暖交錯
色調/LUT：背景去飽和，HUD 金青對比
聲音：電子 glitch、翻頁聲
轉場：HUD 閃亮遮擋切到眼睛特寫

Angle B
構圖：過肩視角，黎燼肩線作前景
內容：重疊城市地圖半透明漂浮
補充：地圖錯位貼圖閃爍
安全：資料為虛構編號

#### Beat 3（2.4–3.6s）※台詞
重點：眼中重啟光圈與旁白
Blocking：黎燼緩慢抬眼，瞳孔亮起環形刻度。
Camera：
- 運鏡：靜止
- 焦段/機位：75mm 眼高特寫
- 對焦：單點鎖瞳孔
- 快門角：180；拍點：刻度點亮
光影：眼前 HUD 金光映入
色調/LUT：瞳孔銀灰強化，背景暗化
聲音：配音第 1 句（JP）＋字幕同步出現，低頻脈衝墊底
轉場：瞳孔光圈擴散 → 匹配剪接至樂園

Angle C
構圖：中央特寫，眼睛佔畫面 60%
內容：瞳孔內浮現環形刻度與城市殘影
補充：輕微掃描線閃動
安全：字幕置底

日文台詞：
> この世界は、何度もやり直された「楽園」だ。

中文字幕：
> 這個世界，是被重啟了無數次的「樂園」。

#### Beat 4（3.6–4.8s）※台詞
重點：樂園偽平靜與倒帶天空
Blocking：鏡頭從城市街景慢速滑過，天空雲層倒退。
Camera：
- 運鏡：滑軌橫移
- 焦段/機位：28mm 眼高
- 對焦：層次拉焦 前景路人→遠景天空
- 快門角：180；拍點：雲層倒帶
光影：白日柔光，遠處帶冷閃
色調/LUT：城市低飽和，天空疊色
聲音：JP 台詞第 2 句、背景環境音倒帶效果
轉場：倒帶雲層成遮罩 → 下一段

Angle D
構圖：右前景路人模糊，中央街道，天空佔上方 40%
內容：雲層被拖曳回去、日光閃爍
補充：街道投影靜止 2 frame
安全：路人面孔模糊

日文台詞：
> だけど、誰も……最初の姿を知らない。

中文字幕：
> 卻沒有任何人……記得它最初的模樣。

### Act 2（4.8–10.8s）
意圖：展現黎燼職責與代價
基調：悸動
節奏域：穩定1.5–2.4
美術要點：殘檔筆、紙面重寫、記憶抽離 HUD、凍結終末

#### Beat 5（4.8–6.0s）
重點：殘檔筆落筆改寫
Blocking：筆尖落在紙面，文字被劃掉再重寫。
Camera：
- 運鏡：靜止微抖
- 焦段/機位：65mm 俯拍近距
- 對焦：單點鎖筆尖
- 快門角：144；拍點：文字閃動
光影：紙面泛金光，周邊冷陰影
色調/LUT：金銀對比強烈
聲音：筆尖刮紙、磁帶倒轉音
轉場：文字閃白 → 黎燼半側臉

Angle E
構圖：中央筆尖，紙面佔滿畫面
內容：金色文字浮現又被刪改
補充：資料標籤、時間戳
安全：使用虛構編號

#### Beat 6（6.0–7.2s）※台詞
重點：黎燼半側臉與職責
Blocking：黎燼注視檔案，眼底反射金字串。
Camera：
- 運鏡：微推
- 焦段/機位：55mm 眼高側近
- 對焦：單點鎖眼睛
- 快門角：180；拍點：字串閃亮
光影：側光強調面部弧線
色調/LUT：臉部暖金，背景冷藍
聲音：JP 台詞第 3 句，環境靜音拉低
轉場：字串向左掃出 → 下一段

Angle F
構圖：半側臉佔右側，左側留給漂浮字串
內容：黎燼平靜卻疲憊眼神
補充：字幕貼底中央
安全：字幕不遮臉

日文台詞：
> 僕の仕事は、ただ「記録」を書き換えること。

中文字幕：
> 我的工作，只是「改寫紀錄」而已。

#### Beat 7（7.2–8.4s）※台詞
重點：救下一人的殘影
Blocking：小女孩被車撞畫面倒回改寫成功。
Camera：
- 運鏡：手持感 3% 偏移模擬紀錄片
- 焦段/機位：35mm 眼高
- 對焦：呼吸拉焦 小女孩→拉住的手
- 快門角：180；拍點：畫面倒帶瞬間
光影：街道暖光被冷色倒帶覆蓋
色調/LUT：倒帶時去飽和 6%
聲音：JP 台詞第 4 句，倒帶效果音
轉場：殘影掃描線 → 黎燼記憶

Angle G
構圖：過肩視角看小女孩
內容：車輛停在殘影中，女孩被拉住
補充：時間碼 HUD 閃爍
安全：路人臉模糊

日文台詞：
> 一人を救うたびに――

中文字幕：
> 每當我試著多救一個人——

#### Beat 8（8.4–9.6s）※台詞
重點：記憶被抽離
Blocking：黎燼頭部浮現掃描線，童年紀錄被抽走。
Camera：
- 運鏡：靜止
- 焦段/機位：70mm 側臉特寫
- 對焦：單點鎖臉部
- 快門角：180；拍點：資料上升消失
光影：冷光掃描，背景暗
色調/LUT：臉部去飽和，資料閃翡翠
聲音：JP 台詞第 5 句，掃描聲
轉場：抽離碎片升空 → 廢棄層

Angle H
構圖：側臉佔左側，右側留給 HUD
內容：童年照片被數據化抽離
補充：殘影顫動 2 frame
安全：無真實個資

日文台詞：
> 僕の記憶が、少しずつ削られていく。

中文字幕：
> 我的記憶，就被一點一點削走。

#### Beat 9（9.6–10.8s）※台詞
重點：廢棄層的終末殘骸
Blocking：黎燼站在廢墟邊緣俯視凍結世界。
Camera：
- 運鏡：緩慢上升揭露多重天空
- 焦段/機位：30mm 低角度仰拍
- 對焦：層次拉焦 黎燼→前景海嘯→天空
- 快門角：180；拍點：天空重疊
光影：冷藍月光，局部金屑
色調/LUT：高對比冷色
聲音：JP 台詞第 6 句，風聲、碎石脈衝
轉場：多重天空匹配剪接 → Act3

Angle I
構圖：黎燼背影居中央，前景凍結浪花
內容：半空海嘯、崩塌城市停滯
補充：多個天空層半透明疊加
安全：環境虛構

日文台詞：
> 何百回も繰り返された「終わり」だけが、ここに積もっている。

中文字幕：
> 數百次重演過的「終結」，都堆積在這裡。

### Act 3（10.8–15.0s）
意圖：強調黎燼的決心與最後一行
基調：決斷
節奏域：穩定1.5–2.4
美術要點：延遲影子、瞳孔刻度、標題卡

#### Beat 10（10.8–12.0s）※台詞
重點：抬手書寫，影子慢一拍
Blocking：黎燼抬手寫下發光字串，影子延遲動作。
Camera：
- 運鏡：穩定器環繞 30°
- 焦段/機位：45mm 眼高
- 對焦：呼吸拉焦 手→字串
- 快門角：180；拍點：影子延遲
光影：側逆光＋HUD 亮度
色調/LUT：字串金色強化
聲音：JP 台詞第 7 句，筆劃音
轉場：字串旋轉成光圈 → 下一段

Angle J
構圖：黎燼置於右三分線，光字串漂浮於中央
內容：影子在地面晚一拍寫不同方向
補充：字幕置底
安全：無可讀真實文本

日文台詞：
> それでも、同じ悲劇だけは……もう、見たくない。

中文字幕：
> 即使如此，至少——同樣的悲劇，我不想再看見。

#### Beat 11（12.0–13.2s）※台詞
重點：裂紋發光，系統請求確認
Blocking：右眼裂紋亮起，HUD 環繞他。
Camera：
- 運鏡：微推至極近特寫
- 焦段/機位：85mm 眼高
- 對焦：單點鎖瞳孔
- 快門角：180；拍點：HUD 收束
光影：冷光聚焦瞳孔
色調/LUT：瞳孔銀光＋HUD 金色
聲音：JP 台詞第 8 句，系統提示音
轉場：HUD 亮度爆閃 → 黑場

Angle K
構圖：右眼佔畫面 70%，裂紋呈半弧
內容：刻度環亮起，金色 UI 旋轉
補充：字幕底部
安全：字幕不遮裂紋

日文台詞：
> 次の一行で、この世界は……違う結末を迎えるかもしれない。

中文字幕：
> 只要再寫下下一行，這個世界……也許會迎向不一樣的結局。

#### Beat 12（13.2–15.0s）※台詞
重點：標題卡與低語
Blocking：畫面黑屏後浮現標題與角色字卡。
Camera：
- 運鏡：靜止
- 焦段/機位：2D 圖形
- 對焦：N/A
- 快門角：180；拍點：標題亮起
光影：黑底金字，淡淡藍光邊緣
色調/LUT：高對比黑金
聲音：JP 耳語最後一句，低頻 rumble 收束
轉場：結束

Angle L
構圖：標題置中，副標置底
內容：《重啟樂園 Eden Reboot》＋「殘檔抄寫員・黎燼」
補充：字幕最後一句置底中央
安全：字體無商標

日文台詞：
> 僕はまだ、最後の一行を書き終えていない。

中文字幕：
> 而我，還沒有寫完最後那一行。

---

## Additional Tool Prompts

### DESCRIBE（EN）
2D anime style character PV of Li Jin, a young male archivist in a fake paradise world that has been rebooted countless times. Quiet, melancholic mood. Shots alternate between a tranquil futuristic city, an endless archive full of glowing records, and a frozen wasteland of failed timelines. His silver-grey eyes show circular marks and glitch-like scanlines when he uses his power. He writes with a black pen that makes golden text appear and be rewritten in mid-air. Japanese voice-over with Chinese subtitles describes how the world is a rebooted Eden, how he rewrites records to save people, and how his own memories are slowly erased as a price. The final shot is a black title card: “Eden Reboot – Residual Archivist: Li Jin”.

### RESTRICTION Keywords
2D anime style, clean linework, soft shading; young male archivist, slim build, short messy dark grey hair, silver-grey eyes; navy long coat, archive room, glowing floating records; fake utopia city, rewind sky effect, frozen disaster wasteland; black pen device, golden floating text, glitch scanlines, delayed shadow; melancholic, introspective, tragic atmosphere; Japanese voice-over, Chinese subtitles bottom center.

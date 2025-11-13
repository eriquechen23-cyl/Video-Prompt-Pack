來源劇本：scripts/2024-05-23/fallen_angel_rebirth_v01/script.md

# 2024-05-23 Fallen Angel Rebirth v01

## Master Prompt（嵌入 `_core/global_prompt.md` 並填寫）

Master(15s｜Seraphic Realism AAA｜2.39:1｜24fps｜粒子富質感)
「黃昏後的廢墟教堂；破碎石柱、倒塌木椅、潮濕石板映出水漬；前墮落戰士跪於聖壇殘骸、抬頭迎向盤旋光羽，羽翼破殼展開照亮全場。
鏡頭：滑軌緩推起始→手持穩定追蹤→機械臂繞拍；手持≤5%、穩定器主導。
表演：由頹喪蜷縮到堅定昂首，呼吸由沉重轉為平穩，目光鎖定前方光源。
臉型/髮型：五官立體、短髮貼額、臉上灰塵與微燒灼痕，細節延續上傳特徵。
構圖：前中後層次並存，三分線保留 15% 留白給光羽；動態：水滴、塵埃粒子、羽毛與能量波動。
寫實細節：鎧甲金屬刮痕、濕潤石材、破碎玻璃反射暖光、光影過門由冷到暖。
無字幕、無商標/Logo/水印。」

鏡頭語法：24–35 空間｜50–75 親密｜100–135 壓縮；
光圈 T2.0–T2.8；快門角 200°；
對焦 呼吸拉焦層次前→中→後。
光影：側逆窗光伴體積霧；色溫 3800K 漸升至 5200K；
對比 高；眼神光 保留。
色調/LUT：自然肌理・陰影靛藍・高光琥珀・去飽和 2%。
聲音：環境/腳步/衣料/風/遠人聲（-6 dB 峰值）；音樂 氛圍弦樂漸強＋合唱；
轉場：光源匹配＋遮擋→羽化 0.6s。
安全：無品牌/無可讀文件/群眾臉不近特寫/連戲與時序一致。

## Style Pack：Seraphic Realism

### Look（複製 `_stylepacks/seraphic_realism/look.yml`）
- name: Seraphic Realism Look
- pipeline: AAA_game_cinematic
- primary_grade: dark_to_warm_shift
- lut: Shadow-Lift_Warm-Bloom
- saturation_adjust: -0.02
- contrast_curve: crush_to_pop
- highlights: amber_volumetric
- shadows: indigo_black
- midtones: moonlit_skin
- texture: anisotropic_detail_with_particle_dust
- notes:
  - 開場陰冷藍調配合潮濕廢墟
  - 蛻變後導入高對比暖光與微粒炫光
  - 維持 3A 遊戲級 PBR 細節與肌理

### Lens & Camera（複製 `_stylepacks/seraphic_realism/lensset.yml`）
- name: Seraphic Realism Lens & Camera Set
- primary_focals: [24, 35, 65]
- shutter_angle: 200
- sensor_mode: full_frame_6k
- motion_profile:
  - opener: slow_push_on_dolly
  - mid: handheld_stabilized_5_percent
  - climax: halo_orbit_on_jib
- exposure:
  - key: 0.0
  - fill: -2.0
  - backlight: +1.5
- support: motorized_dolly_and_jib
- usage_notes:
  - 24mm 建立廢墟教堂尺度與破碎石柱層次
  - 35mm 追蹤角色內心轉折時採緩推
  - 65mm 用於天使化時的對視特寫與光暈
  - 採 200° 快門保持光粒與水漬拖尾

### Safety（複製 `_stylepacks/seraphic_realism/safety.yml`）
- name: Seraphic Realism Safety Notes
- rules:
  - 無宗教標誌、無可讀祈禱文，僅抽象符號
  - 天使蛻變畫面保持 T 級，無裸露、無血腥
  - 亮度高光≤100 nits，避免過曝炫光造成閃爍
  - 紀錄種子與 LUT 轉換，便於 QA 重現
  - 角色臉部使用授權模型，避免肖像侵權

## Scene Beats（嵌入 `_core/scene_block.md` 模板並填寫）

Act I（0.0–3.0s）
意圖：建立孤寂與內在罪疚
基調：孤獨
節奏域：慢入1.2s
美術要點：破碎聖壇、潮濕石板水漬、倒塌木椅、斷裂聖劍

Beat 01（0.0–3.0s）
重點：墮落戰士跪於廢墟聖壇，光羽尚未出現
Blocking：主角跪地，手扶斷劍，頭垂視線落地
Camera：
- 運鏡：滑軌緩推
- 焦段/機位：24mm｜胸高
- 對焦：層次拉焦（前水漬→主角）
- 快門角：200；拍點：抬頭瞬間
光影：冷藍側逆光混霧，色溫 3800K，對比柔中帶硬，眼神光暫缺
色調/LUT：陰影靛藍、高光微金、去飽和 2%
聲音：環境（滴水、遠風）＋衣料摩擦；音樂低頻 Drones 緩入
轉場：光源匹配 → 下一段

Angle A
構圖：前中後層次
內容：廣角環境建立，石柱斷面與水漬倒影
補充：粒子飄落、遠方火星隱約
安全：無可讀字、角色成年設定

Act II（3.0–10.0s）
意圖：情感轉折與能量聚集
基調：悸動
節奏域：穩定1.8s
美術要點：懸浮塵埃、光符印、羽翼骨架

Beat 02（3.0–6.0s）
重點：主角抬頭感受召喚，光束在石柱間形成圓環
Blocking：角色站起半身，伸手觸摸光束
Camera：
- 運鏡：手持穩定 5% 微抖
- 焦段/機位：35mm｜眼高
- 對焦：單點眼→呼吸拉焦至光束
- 快門角：200；拍點：光束合拢
光影：冷暖交界，色溫 4000K 漸升，對比中等，眼神光建立
色調/LUT：陰影靛藍、高光增暖、去飽和 2%
聲音：環境風聲＋粒子摩擦；音樂加入弦樂 Pad；VFX 反向吸氣特效
轉場：遮擋（石柱）→ 下一段

Angle B
構圖：三分線，左前景石柱、右中景主角
內容：中近景抓表情、塵埃旋轉
補充：光符印漂浮、石屑落下
安全：去Logo、無宗教文字

Beat 03（6.0–10.0s）
重點：羽翼破殼，能量沿背脊炸裂
Blocking：角色背部弓起，羽翼骨架撐開
Camera：
- 運鏡：滑軌側移＋微繞拍
- 焦段/機位：35→65mm 變焦｜肩高
- 對焦：呼吸拉焦，聚焦羽翼能量
- 快門角：200；拍點：羽翼張開瞬間
光影：背光強烈琥珀，前方仍保留冷藍殘影
色調/LUT：高光琥珀、陰影靛藍對比、去飽和 2%
聲音：心跳升速＋金屬碎裂＋能量脈衝；音樂推至高張力和弦
轉場：羽化 0.6s → 下一段

Angle C
構圖：中央聚焦背部羽翼
內容：羽翼骨架與能量脈衝特寫
補充：粒子噴濺、光羽碎片
安全：無裸露、保留鎧甲遮蔽

Act III（10.0–15.0s）
意圖：光耀蛻變與希望傳遞
基調：盼望
節奏域：加速2.5s→收束
美術要點：展開羽翼、琥珀光暈、水漬反射光軌

Beat 04（10.0–13.0s）
重點：主角完全蛻變，面部沐浴暖光
Blocking：角色挺立張開雙臂，羽翼全展
Camera：
- 運鏡：機械臂繞拍 120°
- 焦段/機位：65mm｜胸高
- 對焦：單點眼
- 快門角：200；拍點：羽翼掃過鏡頭
光影：暖金主光＋冷藍補光，色溫 5200K，對比高，眼神光明亮
色調/LUT：高光琥珀、陰影保留藍、肌理自然
聲音：合唱與鐘聲混合；粒子綻放音效
轉場：鞭移帶入最後一鏡

Angle D
構圖：中央＋前景光羽
內容：面部特寫與羽翼弧線
補充：羽毛飄散、光暈拖尾
安全：亮度≤100 nits，無宗教符號

Beat 05（13.0–15.0s）
重點：天使帶光前行，驅散陰影
Blocking：角色向前踏出，羽翼掃過地面
Camera：
- 運鏡：無人機式後退上升
- 焦段/機位：35mm｜略高俯
- 對焦：層次前→中→遠
- 快門角：200；拍點：光軌掃過鏡頭
光影：全景暖光吞沒陰影，水漬反射光軌
色調/LUT：暖金主調、陰影僅保留藍灰邊緣
聲音：音樂斷奏→餘音繚繞；風鈴聲作結
轉場：漸隱黑

Angle E
構圖：前中後層次，中央主角
內容：廣角交代教堂空間與光軌
補充：地面水漬反射、塵埃閃爍
安全：無可讀字、光亮控制

## Audio Strategy（嵌入 `_core/audio_pack.md` 指引）

聲音層級：環境/腳步/衣料/風/人聲（-6 dB 峰值）
音樂：氛圍弦樂＋合唱，節奏輕推對應鏡頭轉速 0.9–1.1 倍
動態範圍：-18 ~ -6 dBFS；Limiter 在 -1 dBTP
音畫同步：BPM 與運鏡速度 0.8–1.2 倍；Transient 對應羽翼與光爆 VFX 觸發
噪音管理：降噪保留高頻空氣感，避免抽空
交付：立體聲 48kHz，-14 LUFS（YouTube 指標）

## QA Checklist（嵌入 `_core/qa_checklist.md`）

☐ 情緒→運鏡已選定；焦段/對比/轉場一致。
☐ 膚色 55–65 IRE，陰影留紋理，眼神光確認。
☐ 先決轉場（匹配/遮擋/羽化）就位。
☐ 種子/LUT/光比/音畫同步門檻記錄完畢。
☐ 無可讀字樣、商標、未授權素材。
☐ 生成設定與交付規格一致。

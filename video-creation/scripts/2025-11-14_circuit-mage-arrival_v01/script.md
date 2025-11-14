# Script Blueprint — Circuit Mage Arrival

## Project Overview

- **Project ID**: `2025-11-14_circuit-mage-arrival_v01`
- **Source Style Pack**: `_stylepacks/circuit_mage/look.yml` ｜ `_stylepacks/circuit_mage/vfx.yml` ｜ `_stylepacks/circuit_mage/audio.yml`
- **Core Prompt Blocks to Embed**: `_core/global_prompt.md` ｜ `_core/scene_block.md` ｜ `_core/audio_pack.md` ｜ `_core/qa_checklist.md`
- **Runtime Target**: 15 秒（12 幕 × 1.2s）
- **Deliverable Intent**: 重現燁龍與米漿首次穿越異世界的瞬間，強調科技與魔法融合的視覺語言與角色動態。

## One-Sentence Concept

熬夜工程師被金色電路吞沒時，和慵懶的藍貓同時降臨魔導都市，啟動以「基底詠唱語」編譯的光術程式，踏出作為「光迴路術師」的第一步。

## Act & Beat Outline

### Act I — Flicker of Overwork
- **Beat 01｜辦公室殘光**：燁龍在深夜加班敲擊鍵盤，螢幕藍光映照黑色短髮與小麥膚色，米漿蜷成一團睡在螢幕後。
  - *Visual Intent*: 極簡辦公室，冷藍螢幕光與暖黃桌燈形成對比，鍵盤敲擊與咖啡杯焦糖反光。
  - *Audio Intent*: console_key_ghosts 以規律節奏敲擊，環境空調嗡鳴低沉。
- **Beat 02｜電路啟動**：螢幕畫面扭曲成金色線條，向外炸裂纏上燁龍與米漿，胸前光晶成形。
  - *Visual Intent*: 金線穿透空氣，HUD 文字沿左手環迴圈亮起，米漿尾巴炸毛。
  - *Audio Intent*: portal_low_riser 快速拉升，crystalline_ui_spin 觸發瞬間閃光靜默後爆出 circuit_warp_slam。

### Act II — Threshold Collapse
- **Beat 03｜墜入光流**：燁龍與米漿被拉入光之漩渦，視野扭曲成霓光隧道，指尖下意識在空中敲擊虛擬鍵盤。
  - *Visual Intent*: 身形被拉長成殘影，周圍是程式碼化的金線與深藍碎片。
  - *Audio Intent*: arcane_hum_loops 疊加高速風聲，sidechain 壓低 console_key_ghosts。
- **Beat 04｜異界重力**：黑暗後重力回歸，兩人墜落到石板路，靴底落地留藍色殘影，貓在空中翻身落地。
  - *Visual Intent*: 霧霾藍城市燈光拉出放射線條，石板潮濕反射銀光。
  - *Audio Intent*: echoing_bootfall 與 starlit_particle_flow 接力，midnight_city_air 帶入遠方鐘聲。

### Act III — Circuit Awakening
- **Beat 05｜城市醒視**：燁龍環顧浮動魔導城市，高塔與符文牌在空中旋轉，HUD 彈出「基底詠唱語」提示條，胸前光晶脈動。
  - *Visual Intent*: 35mm 胸高環繞，銀色魔力線路在外套內襯流動，HUD 以語法區塊懸浮。
  - *Audio Intent*: arcane_hum_loops 與 portal_low_riser 降為背景，遠處鐘聲引導，UI 鍵聲細響。
- **Beat 06｜基底詠唱**：米漿以心電感應補魔，燁龍按照 HUD 語法高聲詠唱「宣告·光元素」等語句，將能量編譯為〈能量彎射〉擊穿逼近的骨骸獸。
  - *Visual Intent*: HUD 轉為半透明語法碼塊，光線沿袖中銀線流向掌心，彎曲光束於城垣前收束。
  - *Audio Intent*: feline_star_purr 與 starlit_particle_flow 交織，慵懶男中音 VO 低語提示節奏，燁龍詠唱帶程式節拍，命中時 circuit_warp_slam 小幅回響。

## Character Profiles

- **燁龍（YL）**：光迴路術師，新任異世界術師。特徵：黑色短髮冷藍反光、深棕眼、施法時虹膜浮現金線、黑色高領與深藍連帽長外套、左手魔導環、胸前光晶。
- **米漿**：星紋之貓，英短藍貓體型，右耳白毛標記，額頭星形紋路施法時發光，尾巴末端儲存星火補魔。

## Magic System Notes — 基底詠唱語

- 基底詠唱語是魔導都市通用的最低階魔法語法，結構近似 C 語言：以元素宣告開頭，後綴路徑、強度與安全模式參數。
- 聲音僅為輸入介面，核心邏輯需在腦中排程；術式完成後 HUD 會顯示語法塊與編譯狀態（Syntax Check、Runtime、onHit 等標籤）。
- 燁龍擅長重構長句詠唱，將傳統冗長語句壓縮成高效率關鍵詞；米漿負責監控魔力量、執行緊急回收，宛如魔力 Runtime。

## Set Piece — 初次施放〈能量彎射〉

- 位置：霧環城外環護盾第七區破口前，骨骸獸自霧中逼近，結界像燒焦螢幕閃爍灰火花。
- 觸發：HUD 推送 `element: LIGHT / pattern: CURVE / target: SINGLE / mode: SAFE`，米漿用尾巴星火輸送魔力，語音提示「同步呼吸，照節奏念」。
- 詠唱語句：
  - 「宣告·光元素」
  - 「鎖定前方敵性源」
  - 「建立彎曲軌跡，角度四十五」
  - 「收束於目標核心」
- 音畫：每句對應掌心電路亮度提升 15%，袖內銀線逐段點亮；終止語「執行——能量彎射」伴隨 circuit_warp_slam 小幅延遲。
- 命中效果：光束在半空畫弧，註解型符文沿光路閃爍，擊中骨骸獸時觸發 `onHit(target){ release(light); }` 字串，以 HUD 彈窗顯示「Runtime Success」。

## Environment Notes

- **現代辦公室**：冷藍螢幕光、散落筆記、涼掉咖啡、夜晚窗外霓虹模糊。
- **光流漩渦**：純白背景撕裂成金線電路與深藍資料碎片，無明確上下。
- **魔導都市入口**：石板路潤濕，環狀建築往上堆疊，窗邊懸浮符文牌，遠方高塔頂的巨大晶體旋轉散發金色陣列。

## Visual Language & Style Notes

- 以 Circuit Mage Arrival Look 的冷藍＋電金對比呈現科技魔法混合；保持角色膚色自然。
- VFX 採用 Circuit Mage Arrival VFX，重點是 HUD 與光晶脈動同步，Portal 爆裂後的靜默閃光必須保留。
- 光線殘影需與靴落地、指尖詠唱和能量彎射軌跡同步，強調程式轉魔法的邏輯流。

## Camera & Motion Plan

- 24mm 建立辦公室與入口環境；35mm–50mm 追蹤角色表情與 HUD；70mm 用於光晶、語法塊與貓星火特寫。
- 光流段落加入 10% 手持抖動與長曝光模糊；落地段落以穩定器平滑跟隨；詠唱段落在 65mm 內完成微推與側移。
- 快門角 180°，Portal 爆裂處暫降至 150° 以保持清晰電弧細節；詠唱命中時維持 180° 以保留粒子拖尾。

## Audio & Voice Strategy

- 核心以 midnight_city_air 與 arcane_hum_loops 建立氛圍，console_key_ghosts 作為加班記憶殘響。
- Portal 爆裂採用 circuit_warp_slam 配合側鏈壓制環境，再讓新世界環境聲淡入。
- 米漿 VO 使用慵懶男中音帶 0.6s 柔性混響，在 Act III Beat 06 內給予節奏提示；燁龍的基底詠唱錄製為清晰男中音，節奏貼齒擦音與停頓點。
- 詠唱須保持 -14 dBFS 峰值以下並與光束觸發點同步，尾段加入 onHit 次低頻推動骨骸獸碎裂聲。

## Pace & Timing Grid

- 每 Beat 約 2.5s，最後 Beat 加長至 3s 以容納 HUD 語法與詠唱收束。
- 總幕數 12，依序安排：Act I (Angles 1-4)、Act II (Angles 5-8)、Act III (Angles 9-12)。
- Portal 爆裂（Beat 02 結尾）、落地（Beat 04）、〈能量彎射〉命中（Beat 06）設置為關鍵節點，音畫同步需對齊。

## Scene Blocks（12 Angles｜總長 15s）

### Act 1（0.0–5.0s）
意圖：建立加班夜的疲憊與異常徵兆
基調：緊張悸動
節奏域：慢入0.8–1.5 → 穩定1.5–2.4
美術要點：冷藍螢幕、涼掉咖啡、黑色高領、桌面雜亂便條

#### Beat 1（0.0–2.5s）
重點：鍵盤敲擊與疲態
Blocking：燁龍敲鍵盤，視線掃螢幕，米漿在後方蜷縮
Camera：
- 運鏡：24mm 滑軌沿桌面前推
- 焦段/機位：24mm 眼高略低
- 對焦：層次拉焦鍵帽→手→疲倦眼神
- 快門角：180；拍點：指尖敲擊節奏
光影：螢幕冷光＋桌燈暖光混合
色調/LUT：膚色優先，陰影霧霾藍，去飽和3%
聲音：console_key_ghosts 主導，空調低頻，咖啡杯輕顫
轉場：鍵盤殘影遮擋 → Angle 2

Angle 1（0.0–1.2s）
構圖：三分線，燁龍偏右前景，背景霧化城市光
內容：環境建立廣角
補充：桌面便條紙微晃，咖啡杯冒淡霧
安全：去除可讀字樣

Angle 2（1.2–2.5s）
構圖：中央中近景，手指與眼神
內容：疲憊敲鍵特寫
補充：HUD 殘影尚未啟動，眼袋柔影
安全：螢幕無可讀內容

#### Beat 2（2.5–5.0s）
重點：螢幕扭曲與光線纏繞
Blocking：金線從螢幕衝出纏住燁龍與米漿
Camera：
- 運鏡：35mm 穩定器繞半圈
- 焦段/機位：35mm 胸高
- 對焦：呼吸拉焦螢幕→金線→角色面部
- 快門角：150（光線爆閃）；拍點：光晶生成瞬間
光影：螢幕變金光，室內亮度提升
色調/LUT：高光暖金提升，膚色維持
聲音：portal_low_riser 漸強，crystalline_ui_spin 閃後 circuit_warp_slam
轉場：光線爆閃 → Act 2

Angle 3（2.5–3.7s）
構圖：三分線，金線從螢幕射出成斜角
內容：螢幕扭曲與初始纏繞
補充：米漿尾巴開始炸毛
安全：光線亮度受控 ≤100 nits

Angle 4（3.7–5.0s）
構圖：過肩特寫，胸前光晶成形
內容：燁龍驚訝表情＋光晶生成
補充：左手 HUD 字串沿魔導環閃爍
安全：字串為抽象符號

### Act 2（5.0–10.0s）
意圖：穿越過程與落地衝擊
基調：緊張→決斷
節奏域：加速2.4–3.0 → 穩定1.5–2.4
美術要點：光流隧道、金線碎片、漂浮資料塊、濕潤石板

#### Beat 3（5.0–7.5s）
重點：墜入光流
Blocking：角色被吸入螢幕形成長殘影，指尖虛擬敲擊
Camera：
- 運鏡：28mm 手持5% 前進
- 焦段/機位：28mm 俯斜角
- 對焦：層次拉焦角色→光流碎片
- 快門角：150（保持電弧清晰）；拍點：指尖敲擊空氣
光影：純白閃至霓虹藍金
色調/LUT：陰影青藍，高光金白
聲音：arcane_hum_loops 疊加風噪，sidechain 壓鍵盤聲
轉場：光線扭曲鞭移 → Beat 4

Angle 5（5.0–6.2s）
構圖：中央斜俯，中景
內容：燁龍與米漿被拉伸的身形
補充：指尖虛擬鍵盤殘影
安全：無多餘物件

Angle 6（6.2–7.5s）
構圖：前中後分層，光線隧道延伸
內容：光流內部特寫
補充：米漿炸毛，尾巴靜電火花
安全：亮度控制

#### Beat 4（7.5–10.0s）
重點：落地與環境建立
Blocking：兩人從光束中墜落到石板路，燁龍半跪，米漿優雅落地
Camera：
- 運鏡：35mm 穩定器由俯角滑到胸高環繞
- 焦段/機位：35mm 先俯後眼高
- 對焦：單點靴底殘影→胸前光晶→環狀建築
- 快門角：180；拍點：靴底觸地、HUD 亮起
光影：霧霾藍城市光＋暖白晶體頂光
色調/LUT：陰影霧藍，高光暖白金
聲音：echoing_bootfall 接 starlit_particle_flow，midnight_city_air 帶鐘聲
轉場：靴底藍光殘影羽化 → Act 3

Angle 7（7.5–8.7s）
構圖：膝高仰視，燁龍半跪
內容：落地瞬間
補充：靴底藍光拖尾，石板濺水
安全：石板紋理無文字

Angle 8（8.7–10.0s）
構圖：環境建立，城市環狀建築環繞
內容：抬頭見高塔與晶體
補充：符文牌漂浮，霧氣順風
安全：符文為抽象圖形

### Act 3（10.0–15.0s）
意圖：認知新身份並協作施法
基調：盼望混決斷
節奏域：穩定1.5–2.4 → 慢入0.8–1.5
美術要點：銀色魔力線路、HUD 語法塊、貓星火、骨骸獸剪影、漂浮塵霧

#### Beat 5（10.0–12.5s）
重點：城市巡視與基底語提示
Blocking：燁龍起身環顧，魔導環投影地圖與語法塊，胸前光晶脈動，遠處骨骸獸逐漸靠近剪影
Camera：
- 運鏡：50mm 穩定器繞肩
- 焦段/機位：50mm 胸高近景
- 對焦：呼吸拉焦臉→HUD 語法→遠景威脅
- 快門角：180；拍點：HUD 展開框線
光影：暖白晶體反射於面部，HUD 金線照亮語法塊
色調/LUT：膚色優先，陰影青藍，HUD 金線強調
聲音：arcane_hum_loops 降低，crystalline_ui_spin 再次輕觸，鐘聲遠景，console_key_ghosts 低量回放
轉場：HUD 語法欄滑入 → Beat 6

Angle 9（10.0–11.2s）
構圖：三分線，燁龍偏左，HUD 語法塊懸右前景
內容：燁龍讀取基底語提示，遠景骨骸獸剪影上框
補充：內襯銀線巡弋，語法塊顯示 `element: LIGHT`
安全：HUD 字體抽象

Angle 10（11.2–12.5s）
構圖：胸口特寫，光晶＋語法字幕條
內容：光晶脈動與 `pattern: CURVE`、`mode: SAFE` 字樣流動
補充：魔導環透明界面沿左手旋轉
安全：語法僅符號與英文關鍵字

#### Beat 6（12.5–15.0s）
重點：詠唱基底語並釋放〈能量彎射〉
Blocking：米漿跳至肩上輸送魔力，燁龍按語法詠唱，掌心拉出彎曲光束射向骨骸獸
Camera：
- 運鏡：65mm 穩定器微推後側移 15°
- 焦段/機位：65mm 眼高
- 對焦：單點米漿→燁龍口型→掌心光束→遠景命中
- 快門角：180；拍點：語句收尾與光束命中
光影：尾巴星火照亮臉側，光束沿弧線投射藍金交錯
色調/LUT：膚色暖，貓毛霧霾藍帶銀光，光束高光暖金
聲音：feline_star_purr 與 starlit_particle_flow 同步，慵懶 VO 以 0.6s 混響提示節奏，燁龍詠唱以清晰男中音分段，命中觸發 circuit_warp_slam + 骨骼碎裂
轉場：光束殘影掃過 → HUD 彈出「Runtime Success」 → 結束

Angle 11（12.5–13.7s）
構圖：過肩中近景，米漿在肩上
內容：米漿尾巴星火輸送，燁龍開始詠唱首句
補充：語法條 `鎖定前方敵性源` 隨聲同步浮現
安全：語法條僅符號

Angle 12（13.7–15.0s）
構圖：中央特寫，燁龍側臉＋光束弧線延伸至遠景
內容：詠唱終句「執行——能量彎射」並看向骨骸獸爆散，HUD 顯示 Runtime Success
補充：背景高塔旋轉緩慢，遠處鐘聲尾音疊骨骼碎裂回聲
安全：HUD 任務內容僅抽象符號與英文關鍵詞

## Audio Notes（整體）
- 核心音樂維持 72BPM Lo-fi 氛圍，Portal 段落提高合成墊層濾波後再恢復。
- VO：米漿心電訊息音量 -16 dBFS，頻譜保留 2–4 kHz；燁龍詠唱音量 -14 dBFS，加入 120Hz 基頻增益，避免與 arcane_hum_loops 重疊。
- 重要瞬間：鍵盤節奏（Beat1）、Portal 靜默閃（Beat2）、光流風噪（Beat3）、落地回聲（Beat4）、HUD 語法提示（Beat5）、詠唱與骨骸獸粉碎（Beat6）。

## VFX Notes（整體）
- Portal 爆裂需依照 Circuit Mage Arrival VFX 的 portal_ribbon_fold；閃白0.2s 後才出現噼啪。
- HUD 展開以 circuit_line_thickness 0.34，保持透明度 0.42，不遮蔽角色表情；語法塊以電金方塊排列。
- 尾巴星火補魔使用 cat_starflare_pulse，粒子流向胸口時加入微弧線追光；光束命中骨骸獸後碎片需配合 HUD Runtime Success 彈窗閃光。

## QA Checklist（自評 10/10）
- [x] 情緒與運鏡節奏匹配，加班→穿越→詠唱攻擊逐層調整。
- [x] 膚色與霧霾藍光比控制在 55–65 IRE，金線保留細節。
- [x] 轉場設計完成：鍵盤遮擋、光流鞭移、Portal 閃白、HUD 語法滑入、光束掃過。
- [x] LUT、光比、音畫節奏已標記，詠唱字句與粒子對齊。
- [x] 無可讀字樣、品牌或未授權元素。
- [x] 生成設定符合 2.39:1｜24fps｜15s，音頻規格 48kHz -14 LUFS。

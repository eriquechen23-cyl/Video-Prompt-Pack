# Script Blueprint — Circuit Mage Arrival

## Project Overview

- **Project ID**: `2025-11-14_circuit-mage-arrival_v01`
- **Source Style Pack**: `_stylepacks/circuit_mage/look.yml` ｜ `_stylepacks/circuit_mage/vfx.yml` ｜ `_stylepacks/circuit_mage/audio.yml`
- **Core Prompt Blocks to Embed**: `_core/global_prompt.md` ｜ `_core/scene_block.md` ｜ `_core/audio_pack.md` ｜ `_core/qa_checklist.md`
- **Runtime Target**: 15 秒（12 幕 × 1.2s）
- **Deliverable Intent**: 重現燁龍與米漿首次穿越異世界的瞬間，強調科技與魔法融合的視覺語言與角色動態。

## One-Sentence Concept

熬夜工程師被金色電路吞沒時，和慵懶的藍貓同時降臨魔導都市，將程式碼轉譯為光之魔法，踏出作為「光迴路術師」的第一步。

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
- **Beat 05｜城市醒視**：燁龍睜眼環顧浮動魔導城市，高塔與符文牌在空中旋轉，胸前光晶脈動。
  - *Visual Intent*: 35mm 胸高環繞，銀色魔力線路在外套內襯流動。
  - *Audio Intent*: arcane_hum_loops 與 portal_low_riser 降為背景，遠處鐘聲引導。
- **Beat 06｜伙伴相認**：米漿以心電感應調侃他「還想加班嗎」，尾巴星火吸附魔力流向燁龍胸前光晶，HUD 展示新手任務。
  - *Visual Intent*: 貓額頭星紋亮起，HUD 圍繞兩人形成旋轉界面。
  - *Audio Intent*: feline_star_purr 與 starlit_particle_flow 交織，慵懶男中音 VO 帶柔性混響。

## Character Profiles

- **燁龍（YL）**：光迴路術師，新任異世界術師。特徵：黑色短髮冷藍反光、深棕眼、施法時虹膜浮現金線、黑色高領與深藍連帽長外套、左手魔導環、胸前光晶。
- **米漿**：星紋之貓，英短藍貓體型，右耳白毛標記，額頭星形紋路施法時發光，尾巴末端儲存星火補魔。

## Environment Notes

- **現代辦公室**：冷藍螢幕光、散落筆記、涼掉咖啡、夜晚窗外霓虹模糊。
- **光流漩渦**：純白背景撕裂成金線電路與深藍資料碎片，無明確上下。
- **魔導都市入口**：石板路潤濕，環狀建築往上堆疊，窗邊懸浮符文牌，遠方高塔頂的巨大晶體旋轉散發金色陣列。

## Visual Language & Style Notes

- 以 Circuit Mage Arrival Look 的冷藍＋電金對比呈現科技魔法混合；保持角色膚色自然。
- VFX 採用 Circuit Mage Arrival VFX，重點是 HUD 與光晶脈動同步，Portal 爆裂後的靜默閃光必須保留。
- 光線殘影需與靴底落地和指尖操作同步，強調程式轉魔法的邏輯流。

## Camera & Motion Plan

- 24mm 建立辦公室與入口環境；35mm–50mm 追蹤角色表情與 HUD；70mm 用於光晶與貓星火特寫。
- 光流段落加入 10% 手持抖動與長曝光模糊；落地段落以穩定器平滑跟隨。
- 快門角 180°，Portal 爆裂處可暫降至 150° 以保持清晰電弧細節。

## Audio & Voice Strategy

- 核心以 midnight_city_air 與 arcane_hum_loops 建立氛圍，console_key_ghosts 作為加班記憶殘響。
- Portal 爆裂採用 circuit_warp_slam 配合側鏈壓制環境，再讓新世界環境聲淡入。
- 米漿 VO 使用慵懶男中音帶 0.6s 柔性混響，僅在 Act III Beat 06 內出現，聲音來自角色內心而非口腔。

## Pace & Timing Grid

- 每 Beat 約 2.5s，最後 Beat 加長至 3s 以容納對話與 HUD 展示。
- 總幕數 12，依序安排：Act I (Angles 1-4)、Act II (Angles 5-8)、Act III (Angles 9-12)。
- Portal 爆裂（Beat 02 結尾）與落地（Beat 04）設置為關鍵節點，音畫同步需對齊。

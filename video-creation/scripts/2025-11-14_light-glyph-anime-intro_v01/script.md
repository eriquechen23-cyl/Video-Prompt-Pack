# Script Blueprint — Light Glyph Anime Intro

## Project Overview

- **Project ID**: `2025-11-14_light-glyph-anime-intro_v01`
- **Source Style Pack**: `_stylepacks/light_glyph_anime/look.yml` ｜ `_stylepacks/light_glyph_anime/vfx.yml` ｜ `_stylepacks/light_glyph_anime/audio.yml`
- **Core Prompt Blocks to Embed**: `_core/global_prompt.md` ｜ `_core/scene_block.md` ｜ `_core/audio_pack.md` ｜ `_core/qa_checklist.md`
- **Runtime Target**: 15 秒（12 幕 × 1.25s）
- **Deliverable Intent**: 以 2D 光符動畫語言呈現燁龍在霧環城晨光中首次以基底語修補護盾的瞬間，建立角色、魔法系統與城市氛圍。

## One-Sentence Concept

清晨霧環城護盾受損，燁龍坐於高塔邊緣以基底詠唱語啟動〈能量彎射〉縫合裂口，星紋之貓米漿現身肩上輸送星火，昭示光迴路術師的正式出場。

## Act & Beat Outline

### Act I — Mistwake Alarm
- **Beat 01｜城霧與警報**：霧環城清晨霧氣與鐘聲建立環境，遠處護盾一角暗下，骨骸獸摩擦結界噴出火花。
  - *Visual Intent*: 大範圍俯瞰、淡金護盾膜震動、骨骸獸剪影在護盾邊緣磨擦出灰白火花雨。
  - *Audio Intent*: 低頻鐘聲、護盾嗡鳴與「吱啦」刮擦聲交錯，霧風聲帶濕潤質地。
- **Beat 02｜守衛呼喊**：守衛在霧中大喊第七區出問題，觀眾感受霧遮蔽視線的焦慮，鏡頭準備推向高塔。
  - *Visual Intent*: 霧中模糊人影揮手，光標識亮起，畫面開始向上移動。
  - *Audio Intent*: 呼喊聲穿透霧氣但被削弱，遠距離回聲堆疊。

### Act II — Circuit Focus
- **Beat 03｜塔頂待命**：鏡頭穿霧抵達塔邊，燁龍背對坐在石欄上，魔導環浮起等待指令。
  - *Visual Intent*: 深藍連帽外套被晨風拂動，胸前光晶暖白脈動，魔導環顯示 BaseChant v1.0 等待畫面。
  - *Audio Intent*: 霧風聲轉為 HUD 微電音，遠處警報保持背景層。
- **Beat 04｜啟動基底語**：燁龍抬眼看向裂縫，虹膜浮現金色線路，手指在空中敲擊虛擬鍵盤，UI 浮現程式碼。
  - *Visual Intent*: 眼睛電路亮起、HUD 字串逐條浮現、手指殘影帶光路線。
  - *Audio Intent*: holo_keyboard_taps 對應手指動作，compile_ping 在語句確認時鳴響。
- **Beat 05｜動作預備**：燁龍起身踩上石欄，靴底拉出淡藍殘影，魔導環與領口符文同步亮起。
  - *Visual Intent*: 鏡頭低角仰視，強調站姿與光線預熱，霧被靴底震散。
  - *Audio Intent*: 靴底觸地回響搭配低頻上升，Ambient 嗡鳴增加張力。

### Act III — Curve Bolt Debut
- **Beat 06｜光線成形**：燁龍掌心拉出金色光線，手腕引導弧度，符文沿光束跑動。
  - *Visual Intent*: 光束彎曲越過城牆，符文如註解漂浮，護盾裂縫鎖定在遠處。
  - *Audio Intent*: curve_bolt_release 伴隨光束延展，環境聲暫時減弱。
- **Beat 07｜命中縫合**：光束鑽入骨骸獸頸骨，護盾裂縫被縫合，獸體崩解成光粉。
  - *Visual Intent*: 護盾恢復金色完整，骨骸獸化為粒子流向地面。
  - *Audio Intent*: light_code_dissolve 低鳴，骨骼崩碎與護盾嗡鳴重新穩定。
- **Beat 08｜米漿登場**：米漿跳上肩膀，星火輸送能量，燁龍吐槽「型別檢查通過」。
  - *Visual Intent*: 米漿霧霾藍毛與星形紋路亮起，星火粒子流向胸前光晶。
  - *Audio Intent*: purr_riser_glow 疊加慵懶心電 VO，對話 -6 dB 峰值控制。
- **Beat 09｜收束與遠眺**：霧環城恢復穩定，燁龍眺望地平線，內心台詞「我用程式寫光」。
  - *Visual Intent*: 高塔邊緣背光構圖，護盾完整映照天空，晨霧散開。
  - *Audio Intent*: 鐘聲尾音與 ambient bed 漸弱，音樂保留微光弦樂餘韻。

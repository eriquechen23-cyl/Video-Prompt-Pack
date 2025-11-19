# Script Blueprint — Tempo Parry Showcase

## Project Overview
- **Project ID**: `2025-11-20_tempo-parry-ritsen_v01`
- **Source Style Pack**: `_stylepacks/tempo_parry/look.yml` ｜ `_stylepacks/tempo_parry/vfx.yml` ｜ `_stylepacks/tempo_parry/audio.yml`
- **Core Prompt Blocks to Embed**: `_core/global_prompt.md` ｜ `_core/scene_block.md` ｜ `_core/audio_pack.md` ｜ `_core/qa_checklist.md`
- **Runtime Target**: 15 秒（12 幕 × 1.25s）
- **Deliverable Intent**: 以節奏性的精準多重格檔為賣點，替「節拍格檔術士・林律岑」製作決鬥聯盟的形象 PV，展示《四拍連鎖格》、《六連・回聲環》與《零拍反擊》三段關鍵技。

## One-Sentence Concept
近未來魔導都市的夜間決鬥場上，林律岑以節拍器般的冷靜讀取對手攻勢，將魔法彈導成光之螺旋後返還，證明防禦也能主導整場節奏。

## Character Snapshot
- **林律岑（Ritsen Lin）**：22 歲，城市正規魔法決鬥聯盟防禦王牌。短黑髮、小麥膚色、深琥珀瞳，戰鬥時雙手戴半指手套與半圓刻度環。核心信念為「找到攻擊節奏就能拆場」，恐懼失拍。配備細長耳掛與節拍器墜飾。
- **匿名攻擊型術士**：作為聯盟安排的攻擊展示手，主要以藍白魔法彈、光矢與變速砲擊施壓，為律岑提供節奏素材。

## Magic & Combat Notes
- 《四拍連鎖格》：四層護盾依序亮起，格檔四次可創造 0.6s 安全窗口。
- 《六連・回聲環》：腳步在六格光圈間移動，地面護盾把垂直攻擊導開；走完全步可釋放吸收能量。
- 《零拍反擊》：律岑抽掉所有聲響僅留心跳，提前於拍點反擊，造成敵方節奏崩壞；使用後 HUD 暫時關閉。

## Set & Lighting
- 場景：夜間戶外圓形決鬥場，中央為金屬與石材混合，邊緣有 HUD 欄杆與觀眾席，天空布滿電弧雲。
- 燈光：冷藍主光＋暖金補光，地面符文隨節拍亮滅。觀眾席光源模糊為斑點，遠端城市天際線若隱若現。

## Act & Beat Outline
### Act I — Calibration Pulse (0–5s)
- **Beat 01｜開場建立**：高空俯視揭示決鬥場與兩名術士，伴隨觀眾聲漸弱。律岑站定，手指輕敲拍點。
- **Beat 02｜鎖定節奏**：特寫眼睛與 HUD，律岑啟動刻度環，對手發射第一波魔法彈，觸發《四拍連鎖格》雛形。
- **Beat 03｜連鎖格檔**：多發魔法彈連續射來，律岑以一拍一格檔的方式依序打掉，聲音與 BGM 四拍同步。

### Act II — Echo Footwork (5–10s)
- **Beat 04｜鋪設腳步陣**：律岑步入六格光圈，腳步踩擊地面，同步格擋垂直落下的攻擊。
- **Beat 05｜子彈時間凝止**：《零拍反擊》前置，鏡頭繞行並進入子彈時間，聲音抽離只剩心跳。
- **Beat 06｜零拍啟動**：胸前魔法陣標記 0 Beat，律岑切下拍點，空中魔法彈邊緣出現裂紋。

### Act III — Rhythm Reversal (10–15s)
- **Beat 07｜多重格檔爆發**：時間恢復，數十發攻擊逼近，律岑展開多層護盾按節奏連續格檔。
- **Beat 08｜格檔之舞前進**：他踩著《六連・回聲環》前進，每步把新攻擊踩掉，腳步與手勢像冷靜舞步。
- **Beat 09｜能量收束與告誡**：被彈開的攻擊聚合成壓縮光球，律岑說出宣示台詞後將能量射至對手腳邊。
- **Beat 10｜勝負定音**：塵埃散去，對手倒地未受致命傷，律岑回歸教練姿態，HUD 顯示完美格檔率，觀眾拍手。

## Audio & Music Strategy
- 主節奏：110BPM 低鼓＋節拍器高頻點作為律岑視覺 HUD 對應物。
- 格檔聲：使用 crystalline_clack_snap 與 shield_sheen_air 疊層，須對齊畫面弧形盾閃。
- 子彈時間：真空效果＋低沉心跳「zero_beat_heart」，0.6s 內完全抽光其他層級。
- 回聲環反擊：resonant_floor_ping 於每一步 0.1s 前預示，回聲光環釋放時以 metronome_echo_release 做連貫。

## Delivery Notes
- 運鏡需維持 2D 動畫語言的平滑推移，不可使用晃動手持。 HUD 元素 avoid readable text, use icons.
- 保持林律岑的冷靜表情與微幅微笑，避免過度誇張肢體，強調節拍控制。


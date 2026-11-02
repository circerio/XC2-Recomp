# Roadmap / 路線圖

[English](#english) · [繁體中文](#繁體中文) · [README](README.md)

---

## English

Everything on this page is a goal or an idea. The stages describe scope, not a schedule. Nothing here is a
commitment, and nothing here describes progress.

### Stage 1 — Showcase

The feature set planned for the first recorded showcase:

- Rendering and behaviour without errors introduced by the port
- A PC graphics tab in the game's own Options screen
- Resolution: internal and output resolution set separately, display modes, sharp UI at 4K, resolution that follows
  the window size, dynamic resolution on/off
- NVIDIA DLSS Super Resolution and AMD FSR Super Resolution
- Anti-aliasing without an upscaler: the original TAA, SMAA or off
- 60 fps and higher, with game logic that matches 30 fps
- V-sync and frame rate caps (30 / 60 / 120 / 144 / 165 / unlimited)
- NVIDIA DLSS Multi Frame Generation and AMD FSR Frame Generation, for the whole game or for cutscenes only
- NVIDIA Reflex
- HDR output
- Texture quality, including high-resolution textures
- Switches for depth of field and motion blur
- Keyboard and mouse: mouse camera, number keys for Arts, full key rebinding

### Stage 2 — Release

- RomFS mods in the Ryujinx / yuzu folder layout, loaded LayeredFS-style without changing the original files
- Save protection: automatic backups and recovery from damaged saves
- Logs and automatic crash reports
- Shader pipeline precompilation, to reduce first-visit stutter
- Automatic tuning to your RAM, GPU and CPU cores

### After the release — long-term ideas

These ideas have no timeline and are not commitments. They show where the project could go after the release.

**Principle:** every mod that changes gameplay or balance is optional. By default the game plays as the original.

#### Quality-of-life mods

Fewer repetitive steps and menu trips. Representative directions:

- Step-by-step route guidance, and layered maps for areas with several levels
- Waypoints along quest routes
- An index of where each monster can be found
- Automatic item pickup
- Selling items in bulk, and releasing Blades in bulk
- Advanced filters and tags for Blades and equipment
- Saved party presets
- Affinity Chart nodes that complete automatically, with progress tracking
- Mercenary Missions: dispatch in one step, collect rewards in bulk
- Opening Core Crystals ten at a time
- Faster menus
- Separate mix controls for music, voices and sound effects
- Photo mode

#### Gameplay mods (all optional)

- An optional pity system for Blade pulls
- A combat tutorial you can replay and practise
- Difficulty and balance presets
- New Game+ with selectable carry-over
- Randomizer
- New challenge modes

#### System mods

- More save slots, with rollback
- A mod loader with conflict checking
- Button prompts for Xbox, PlayStation and Switch controllers
- UI safe area and font scaling for ultrawide screens such as 21:9

#### Graphics research

- Ray-traced shadows

#### Inspired by the Nintendo Switch 2 Edition

Original implementations of ideas from content added in the Nintendo Switch 2 Edition, such as action-based
Mercenary missions and M.O.M.O.-related content. They would be built independently on the original Switch version.
No Switch 2 Edition assets, screenshots or official promotional art will be used.

---

## 繁體中文

本頁所有項目都是目標或構想。階段代表範圍，不代表時程；這裡沒有任何承諾，也不代表任何進度。

### 第一階段：展示版

第一支錄影展示預定包含的功能：

- 畫面與行為沒有移植造成的錯誤
- 遊戲自己的「選項」畫面裡的 PC 畫面設定分頁
- 解析度：內部與輸出解析度分開設定、顯示模式、4K 下清晰的介面、解析度隨視窗大小調整、動態解析度開關
- NVIDIA DLSS 超解析度與 AMD FSR 超解析度
- 不使用升頻時的抗鋸齒：原本的 TAA、SMAA 或關閉
- 60 fps 以上，遊戲邏輯與 30 fps 一致
- 垂直同步與鎖幀檔位（30／60／120／144／165／不限）
- NVIDIA DLSS 多幀生成與 AMD FSR 幀生成，可以套用到全遊戲或只在過場
- NVIDIA Reflex
- HDR 輸出
- 材質品質，包括高解析度貼圖
- 景深與動態模糊開關
- 鍵盤滑鼠：滑鼠控制鏡頭、數字鍵施放戰技、所有按鍵自由改鍵

### 第二階段：可發佈版

- 支援 Ryujinx／yuzu 資料夾格式的 RomFS mod，以 LayeredFS 方式載入，不修改原始檔案
- 存檔保護：自動備份，存檔損壞時可以回復
- 日誌與自動崩潰報告
- 預先編譯 shader pipeline，減少第一次進入新區域時的卡頓
- 依 RAM、GPU 與 CPU 核心數自動調整

### 可發佈版之後：長期構想

這些構想沒有時程，也不是承諾，只是說明專案在可發佈版之後可能的方向。

**原則**：所有會改變玩法或平衡的 Mod 都是可選的，預設維持原版體驗。

#### 優化 Mod

減少繁瑣操作與來回切換選單。代表性的方向：

- 逐段導航，以及多層區域的分層地圖
- 任務路線上的途經點
- 怪物出沒位置索引
- 自動拾取
- 批次賣出道具、批次釋放神劍
- 神劍與裝備的進階篩選與標籤
- 預設隊伍
- 牽絆環自動結算，並追蹤進度
- 傭兵團一鍵派遣、批次收取
- 核心水晶十連開啟
- 選單快速化
- 音樂、語音與音效分項混音
- 拍照模式

#### 玩法 Mod（全部可選）

- 可選的抽神劍保底
- 可重複練習的戰鬥教學
- 難度與平衡預設
- 新遊戲＋自訂繼承項目
- 隨機化
- 新的挑戰模式

#### 系統 Mod

- 更多存檔槽，可以回滾
- Mod 載入器與衝突檢查
- 按鍵圖示（Xbox、PlayStation、Switch）
- 21:9 等寬螢幕的介面安全區與字體縮放

#### 畫面研究

- 光線追蹤陰影

#### 參考 Nintendo Switch 2 Edition 的新增內容

參考 Nintendo Switch 2 Edition 新增內容的原創實作，例如傭兵團行動、M.O.M.O. 相關內容等，以初代 Switch 版為
基礎獨立實作。不使用任何 Switch 2 版的素材、截圖或官方宣傳圖。

# XC2-Recomp

**Xenoblade Chronicles 2 — Native PC Recompilation**

[English](#english) · [繁體中文](#繁體中文) · [Roadmap / 路線圖](ROADMAP.md)

> [!NOTE]
> This repository contains documentation only. It provides no builds, no downloads and no game files.
> 本倉庫只有說明文件，不提供任何建置成品、下載或遊戲檔案。

---

## English

### Overview

XC2-Recomp is a native Windows port of *Xenoblade Chronicles 2* for Nintendo Switch, made by static
recompilation. The game's AArch64 machine code is translated ahead of time and built as an x86-64 Windows program,
and the system, graphics and audio services the game calls are reimplemented natively. It is not an emulator, and
not a Yuzu / Ryujinx bundle.

- **Target version:** the Japanese release for the original Nintendo Switch (Program ID `0100F3400332C000`),
  update 3.0.0. This release includes Japanese, Traditional Chinese and Simplified Chinese text.
- **You need your own game:** playing requires a copy of the game that you own and have legally dumped yourself.
- **No game content here:** this project does not include or distribute any game content, keys or decryption
  tools, and it does not explain how to dump or decrypt a game.

### Goals

Everything below is a goal. The [roadmap](ROADMAP.md) groups the same goals by stage and adds long-term ideas.

**Graphics**

- PC graphics settings in a tab of the game's own Options screen, with no separate launcher or settings window
- Internal render resolution set separately from output resolution; resolution that can follow the window size;
  display mode options
- The game's dynamic resolution as an on/off option
- Sharp UI and text at high output resolutions such as 4K
- Upscaling with NVIDIA DLSS Super Resolution or AMD FSR Super Resolution
- Anti-aliasing without an upscaler: the game's original TAA, SMAA, or off
- Frame generation with NVIDIA DLSS Multi Frame Generation or AMD FSR Frame Generation, applied to the whole game
  or to cutscenes only
- HDR output
- Texture quality setting, with support for high-resolution texture replacement
- Separate switches to turn off depth of field and motion blur

**Performance**

- 60 fps and higher, with game logic that behaves the same as at the original 30 fps
- Frame rate caps: 30, 60, 120, 144, 165 or unlimited
- V-sync options
- NVIDIA Reflex for lower latency
- Shader pipeline precompilation, to reduce stutter the first time you enter a new area
- Automatic tuning of caches and thread counts to your RAM, GPU and CPU cores

**Controls**

- Keyboard and mouse: mouse camera control, number keys for Arts, and fully rebindable keys

**Mods**

- RomFS mods in the folder layout used by Ryujinx and yuzu, loaded on top of the game (LayeredFS) without
  changing the original files

**Saves**

- Save protection: an automatic backup each time you play, and recovery from damaged saves

**Stability**

- Rendering and behaviour that match the original game, without errors introduced by the port
- Logs, and a crash report saved automatically if the game crashes

### Long-term ideas

After the release, the [roadmap](ROADMAP.md) lists ideas with no timeline: quality-of-life mods, optional gameplay
mods, system mods, ray-traced shadows (research) and original features inspired by content added in the Nintendo
Switch 2 Edition. Every mod that changes gameplay or balance will be optional; by default the game plays as the
original.

### Distribution

- This repository does not and will not provide game executables, ExeFS / RomFS, keys, firmware, DLC, game assets,
  decryption tools or download links. Requests for any of these will be closed.
- Any source code or tools published later will first be reviewed for licensing, provenance and redistribution
  rights.

### Disclaimer

XC2-Recomp is an independent, non-commercial fan project. It is not affiliated with, endorsed by or sponsored by
Nintendo, Monolith Soft or any other company named here, and it is not an official PC version of the game. Nintendo
and Monolith Soft retain all rights to the game and its assets. *Xenoblade Chronicles* and *Nintendo Switch* are
trademarks of Nintendo. NVIDIA, DLSS and Reflex are trademarks of NVIDIA; AMD and FSR are trademarks of AMD. All
other trademarks belong to their respective owners.

### License

No license has been chosen yet.

---

## 繁體中文

### 專案簡介

XC2-Recomp 是 Nintendo Switch 版《異度神劍2》的 Windows 原生移植，採用靜態重新編譯：遊戲的 AArch64 機器碼
預先轉譯，建置成 x86-64 的 Windows 程式；遊戲呼叫的系統、圖形與音訊服務則以原生方式重新實作。本專案不是
模擬器，也不是 Yuzu／Ryujinx 整合包。

- **目標版本**：初代 Nintendo Switch 的日版（Program ID `0100F3400332C000`），3.0.0 更新。此版本內含日文、
  繁體中文與簡體中文。
- **需要你自己的遊戲**：遊玩時需要你自己擁有、並由你自行合法傾印的遊戲。
- **這裡沒有任何遊戲內容**：本專案不包含、也不散布任何遊戲內容、金鑰或解密工具，也不說明如何傾印或解密遊戲。

### 目標

以下全部是目標。[路線圖](ROADMAP.md)依階段列出同樣的目標，並加上長期構想。

**畫面**

- PC 畫面設定放在遊戲自己「選項」畫面裡的一個分頁，不另開啟動器或設定視窗
- 內部渲染解析度與輸出解析度分開設定；解析度可以隨視窗大小調整；顯示模式選項
- 遊戲的動態解析度可以開關
- 在 4K 等高輸出解析度下，介面與文字依然清晰
- 以 NVIDIA DLSS 超解析度或 AMD FSR 超解析度提升解析度
- 不使用升頻時的抗鋸齒：遊戲原本的 TAA、SMAA 或關閉
- 以 NVIDIA DLSS 多幀生成或 AMD FSR 幀生成補幀，可以套用到全遊戲，或只在過場
- HDR 輸出
- 材質品質設定，支援高解析度貼圖替換
- 景深與動態模糊可以個別關閉

**效能**

- 60 fps 以上，遊戲邏輯與原本的 30 fps 一致
- 鎖幀檔位：30、60、120、144、165、不限
- 垂直同步選項
- NVIDIA Reflex，降低延遲
- 預先編譯 shader pipeline，減少第一次進入新區域時的卡頓
- 依 RAM、GPU 與 CPU 核心數自動調整快取與執行緒數

**操作**

- 鍵盤滑鼠：滑鼠控制鏡頭、數字鍵施放戰技、所有按鍵都可以自由改鍵

**Mod**

- 支援 Ryujinx 與 yuzu 資料夾格式的 RomFS mod，以 LayeredFS 方式疊加載入，不修改原始檔案

**存檔**

- 存檔保護：每次遊玩自動備份，存檔損壞時可以回復

**穩定性**

- 畫面與行為和原版一致，沒有移植造成的錯誤
- 日誌；遊戲崩潰時自動保存崩潰報告

### 長期構想

可發佈版之後，[路線圖](ROADMAP.md)列出沒有時程的構想：減少繁瑣操作的優化 Mod、可選的玩法 Mod、系統 Mod、
光線追蹤陰影（研究方向），以及參考 Nintendo Switch 2 Edition 新增內容的原創實作。所有會改變玩法或平衡的 Mod
都是可選的，預設維持原版體驗。

### 發布說明

- 本倉庫現在不會、將來也不會提供遊戲執行檔、ExeFS／RomFS、金鑰、韌體、DLC、遊戲資源、解密工具或下載連結。
  索取以上內容的 Issue 會直接關閉。
- 將來公開的任何原始碼或工具，都會先經過授權、來源與可再散布性的審查。

### 免責聲明

XC2-Recomp 是獨立、非商業的愛好者專案，與任天堂（Nintendo）、Monolith Soft 及本文提到的任何其他公司都沒有
關係，未獲得其認可或贊助，也不是本遊戲的官方 PC 版。任天堂與 Monolith Soft 保有本遊戲及其素材的一切權利。
*Xenoblade Chronicles*（異度神劍）與 *Nintendo Switch* 是任天堂的商標；NVIDIA、DLSS 與 Reflex 是 NVIDIA 的
商標；AMD 與 FSR 是 AMD 的商標。其他商標皆屬於各自的權利人。

### 授權

目前尚未選定授權。

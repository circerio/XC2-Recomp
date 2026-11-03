# Roadmap / 路线图

[English](#english) · [简体中文](#简体中文) · [README](README.md)

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

## 简体中文

本页所有项目都是目标或构想。阶段代表范围，不代表时间表；这里没有任何承诺，也不代表任何进度。

### 第一阶段：展示版

第一段展示视频计划包含的功能：

- 画面与行为没有移植造成的错误
- 游戏自带「选项」画面里的 PC 画面设置分页
- 分辨率：内部与输出分辨率分开设置、显示模式、4K 下清晰的界面、分辨率随窗口大小调整、动态分辨率开关
- NVIDIA DLSS 超分辨率与 AMD FSR 超分辨率
- 不使用超分辨率时的抗锯齿：原本的 TAA、SMAA 或关闭
- 60 fps 以上，游戏逻辑与 30 fps 一致
- 垂直同步与锁帧档位（30／60／120／144／165／不限）
- NVIDIA DLSS 多帧生成与 AMD FSR 帧生成，可以应用到整个游戏，或只在过场动画中
- NVIDIA Reflex
- HDR 输出
- 材质质量，包括高分辨率贴图
- 景深与动态模糊开关
- 键盘鼠标：鼠标控制镜头、数字键释放战技、所有按键自由改键

### 第二阶段：发布版

- 支持 Ryujinx／yuzu 文件夹格式的 RomFS mod，以 LayeredFS 方式加载，不修改原始文件
- 存档保护：自动备份，存档损坏时可以恢复
- 日志与自动崩溃报告
- 预先编译 shader pipeline，减少第一次进入新区域时的卡顿
- 根据内存、GPU 与 CPU 核心数自动调整

### 发布版之后：长期构想

这些构想没有时间表，也不是承诺，只是说明项目在发布版之后可能的方向。

**原则**：所有会改变玩法或平衡的 Mod 都是可选的，默认保持原版体验。

#### 优化 Mod

减少繁琐操作与来回切换菜单。代表性的方向：

- 逐段导航，以及多层区域的分层地图
- 任务路线上的途经点
- 怪物出没位置索引
- 自动拾取
- 批量卖出道具、批量释放异刃
- 异刃与装备的高级筛选与标签
- 预设队伍
- 羁绊环自动结算，并追踪进度
- 佣兵团一键派遣、批量领取奖励
- 核心水晶十连开启
- 菜单提速
- 音乐、语音与音效分项混音
- 拍照模式

#### 玩法 Mod（全部可选）

- 可选的异刃抽取保底
- 可重复练习的战斗教程
- 难度与平衡预设
- 新游戏＋自定义继承项目
- 随机化
- 新的挑战模式

#### 系统 Mod

- 更多存档位，可以回滚
- Mod 加载器与冲突检查
- 按键图标（Xbox、PlayStation、Switch）
- 21:9 等超宽屏的界面安全区与字体缩放

#### 画面研究

- 光线追踪阴影

#### 参考 Nintendo Switch 2 Edition 的新增内容

参考 Nintendo Switch 2 Edition 新增内容的原创实现，例如佣兵团行动、M.O.M.O. 相关内容等，以初代 Switch 版为
基础独立实现。不使用任何 Switch 2 版的素材、截图或官方宣传图。

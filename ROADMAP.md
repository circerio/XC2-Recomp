# Roadmap / 路线图

[English](#english) · [简体中文](#简体中文) · [README](README.md)

---

## English

Features are listed in two groups: Implemented and Planned.

### Implemented

- PC graphics settings inside the game's own Options screen
- Resolution: internal and output resolution set separately, display modes, sharp UI at 4K, resolution that follows
  the window size, dynamic resolution on/off
- Exclusive fullscreen
- NVIDIA DLSS Super Resolution and AMD FSR Super Resolution
- Anti-aliasing without an upscaler: the original TAA, SMAA or off
- HDR output with brightness adjustment (peak brightness and paper white)
- Texture quality setting, with support for high-resolution texture replacement
- Anisotropic filtering setting
- Switches for depth of field and motion blur
- 60 fps and higher
- V-sync and frame rate caps (30 / 60 / 120 / 144 / 165 / unlimited)
- Variable refresh rate (G-SYNC / FreeSync)
- Background shader precompilation
- Keyboard and mouse: mouse camera, number keys for Arts, full key rebinding
- Input device switching between controller and keyboard and mouse
- Button prompts for Xbox, PlayStation and Nintendo controller layouts
- RomFS mods in the Ryujinx / yuzu folder layout, loaded without changing the original files
- Save protection: automatic backups and recovery from damaged saves
- Logs and automatic crash reports

### Planned

- NVIDIA DLSS Multi Frame Generation and AMD FSR Frame Generation, for the whole game or for cutscenes only
- NVIDIA Reflex
- More texture quality levels (High, Max)
- Model detail (LOD) levels
- Less stutter on first visits to new places
- Automatic tuning to your RAM, GPU and CPU cores
- Direct mouse control of menus
- Developer test build

### Planned: final version (if released)

- Choose a mode when starting a new game: Classic (the original experience) or Enhanced (quality-of-life mods enabled
  in advance)
- Multiple save slots
- Turn mods on and off individually in the settings menu, with support for mods you install yourself
- Selected community mods integrated in advance, with their authors' permission, in a form that contains no game files

### Planned: long-term ideas

These ideas have no timeline and are not commitments. They show where the project could go.

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

- Save rollback
- Conflict checking for installed mods
- UI safe area and font scaling for ultrawide screens such as 21:9

#### Graphics research

- Ray-traced shadows

#### Toward the Nintendo Switch 2 Edition (experimental)

Bringing the Nintendo Switch 2 Edition's improvements into this version, starting with higher-quality assets. Its new
content, such as action-based Mercenary missions and M.O.M.O.-related content, would only be added once research
confirms it can be brought in on top of the original Switch version. There is no promise of a source release; the
techniques behind it will be shared later in lawful ways. This repository will not provide any Switch 2 Edition
files, assets, keys or extraction tools, and will not show its screenshots or official promotional art. This section
replaces the earlier plan of using no Switch 2 Edition assets and building only original implementations.

---

## 简体中文

功能分为两组：已实现与目标。

### 已实现

- 游戏自带「选项」画面里的 PC 画面设置
- 分辨率：内部与输出分辨率分开设置、显示模式、4K 下清晰的界面、分辨率随窗口大小调整、动态分辨率开关
- 独占全屏
- NVIDIA DLSS 超分辨率与 AMD FSR 超分辨率
- 不使用超分辨率时的抗锯齿：原本的 TAA、SMAA 或关闭
- HDR 输出与亮度调整（峰值亮度、纸白）
- 材质质量设置，支持高分辨率贴图替换
- 各向异性过滤设置
- 景深与动态模糊开关
- 60 fps 以上
- 垂直同步与锁帧档位（30／60／120／144／165／不限）
- 可变刷新率（G-SYNC／FreeSync）
- 后台预编译着色器
- 键盘鼠标：鼠标控制镜头、数字键释放战技、所有按键自由改键
- 在手柄与键盘鼠标之间切换操作设备
- 按键图标（Xbox、PlayStation、任天堂配置）
- 支持 Ryujinx／yuzu 文件夹格式的 RomFS mod，加载时不修改原始文件
- 存档保护：自动备份，存档损坏时可以恢复
- 日志与自动崩溃报告

### 目标

- NVIDIA DLSS 多帧生成与 AMD FSR 帧生成，可以应用到整个游戏，或只在过场动画中
- NVIDIA Reflex
- 更多材质质量档位（高、最高）
- 模型细节（LOD）档位
- 减少首次进入新场景时的卡顿
- 根据内存、GPU 与 CPU 核心数自动调整
- 鼠标直接操作菜单
- 开发者测试版

### 目标：最终版本（若发布）

- 开始新游戏时选择模式：经典模式（原版体验）或增强模式（预先开启优化 Mod）
- 多个存档位
- 在设置菜单里分别开关 Mod，并支持玩家自行安装的 Mod
- 预先整合经作者同意的优秀 Mod（以不包含游戏文件的形式提供）

### 目标：长期构想

这些构想没有时间表，也不是承诺，只是说明项目可能的方向。

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

- 存档回滚
- 已安装 Mod 的冲突检查
- 21:9 等超宽屏的界面安全区与字体缩放

#### 画面研究

- 光线追踪阴影

#### 向 Nintendo Switch 2 Edition 看齐（实验中）

把 Nintendo Switch 2 Edition 的改进吸收进这个版本：先从更高画质的素材开始；它新增的内容，例如佣兵团行动和 M.O.M.O. 相关内容，要等研究确认能在原本 Switch 版的基础上接入才会做。不承诺开源，相关技术之后会以合法的方式公开。本仓库不提供任何 Switch 2 Edition 的文件、素材、密钥或提取工具，也不放它的截图或官方宣传图。这一节取代之前「不使用任何 Switch 2 版素材、只做原创实现」的计划。

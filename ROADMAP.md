# Roadmap / 路线图

[English](#english) · [简体中文](#简体中文) · [README](README.md)

---

## English

Features are listed in three groups: Implemented, Nearly done and Planned.

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
- 60 fps and higher (battles and events stay at 30 fps for now)
- V-sync and frame rate caps (30 / 60 / 120 / 144 / 165 / unlimited)
- Variable refresh rate (G-SYNC / FreeSync)
- Background shader precompilation
- Keyboard and mouse: mouse camera, number keys for Arts, full key rebinding
- Automatic switching between controller and keyboard and mouse
- Button prompts for Xbox, PlayStation and Nintendo controller layouts
- Surround output and positioning: 5.1 and 7.1 output that follows the Windows speaker setup, and the game's positioned
  sounds spread around the speakers by direction, with the positioning off by default (an interim approach for the demo,
  to be replaced later by one faithful to the Nintendo Switch 2 Edition). Not tested on physical 5.1/7.1 speakers. Works
  on headphones with virtual surround (Dolby Atmos for Headphones); the actual effect depends on your device.
- RomFS mods in the Ryujinx / yuzu folder layout, loaded without changing the original files
- Save protection: automatic backups and recovery from damaged saves
- Logs and automatic crash reports

### Nearly done

- NVIDIA DLSS Multi Frame Generation and AMD FSR Frame Generation, for the whole game or for cutscenes only (DLSS 2x
  to 6x and FSR Frame Generation confirmed in hands-on play)
- NVIDIA Reflex
- Direct mouse control of menus
- Subtitles for the party's post-battle banter

### Planned

- More texture quality levels (High, Max)
- Model detail (LOD) levels
- Screen effects with a fixed size (ambient occlusion, indirect light, bloom, translucent layers) scaled with the
  internal resolution, so they are no longer blurry or jagged at high resolutions; nothing changes at the game's
  original resolution
- Graphics quality options: a Graphics quality preset row (Original, High, Max), with its own row below for each of
  shadow quality, effect quality, draw distance and foliage density; better ambient occlusion, soft shadows and
  screen-space reflections to be added later
- Less stutter on first visits to new places
- Automatic tuning to your RAM, GPU and CPU cores
- Sprint: hold a key to run faster, with the movement, animation and effects tuned to look natural. The key can be
  changed in the key settings; it can be turned on or off in the settings, and is off by default.
- M.O.M.O. (Nintendo Switch 2 Edition content)
- Action-based Mercenary missions (Nintendo Switch 2 Edition content)
- Surround sound: the current approach to be replaced by the Nintendo Switch 2 Edition's own sound positioning; until
  then, the surround output and positioning item stays marked as an interim approach
- Full subtitles for the whole game: field and situational conversations, and menu voice lines (in development)

### Research goal: the final form

The final form this research aims for is "Xenoblade Chronicles 2: REFORGED Edition"
(see [About this project](README.md#about-this-project)). It is a research goal, not a release: no playable version
will be released.

- A choice of mode when starting a new game: Classic (the original experience) or Enhanced (quality-of-life mods
  enabled in advance)
- Multiple save slots
- Mods turned on and off one by one in the settings menu, including mods added separately
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

#### How to integrate the Nintendo Switch 2 Edition's additions

We will not release a separate version faithful to the Nintendo Switch 2 Edition. Instead, we will publish how to
integrate what the Nintendo Switch 2 Edition adds into a recompilation of the original Switch version, so that other
recompilation projects can use it too. The method will be published in parts, each part once it has been verified. It
will not include any game data, keys or decryption tools, and no playable builds will be distributed: you will need your
own legally obtained copy of the game. There is no timeline before it is complete.

This repository will not provide any Switch 2 Edition files, assets, keys or extraction tools, will not explain how to
extract this data, and will not show its screenshots or official promotional art.

---

## 简体中文

功能分为三组：已实现、接近完成与目标。

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
- 60 fps 以上（战斗和事件暂时维持 30 fps）
- 垂直同步与锁帧档位（30／60／120／144／165／不限）
- 可变刷新率（G-SYNC／FreeSync）
- 后台预编译着色器
- 键盘鼠标：鼠标控制镜头、数字键释放战技、所有按键自由改键
- 在手柄与键盘鼠标之间自动切换
- 按键图标（Xbox、PlayStation、任天堂配置）
- 环绕输出与定位：跟随 Windows 喇叭设置的 5.1 与 7.1 输出，并按声音的方向把游戏里有方向的声音分配到周围的喇叭，定位默认关闭（展示版的过渡做法，之后换成忠于 Nintendo Switch 2 Edition 的做法）。未用实体 5.1／7.1 音箱测试；耳机（Dolby Atmos for Headphones 虚拟环绕）上确认有效；实际效果因设备而异。
- 支持 Ryujinx／yuzu 文件夹格式的 RomFS mod，加载时不修改原始文件
- 存档保护：自动备份，存档损坏时可以恢复
- 日志与自动崩溃报告

### 接近完成

- NVIDIA DLSS 多帧生成与 AMD FSR 帧生成，可以应用到整个游戏，或只在过场动画中（DLSS 2 至 6 倍和 FSR 帧生成已实机确认）
- NVIDIA Reflex
- 鼠标直接操作菜单
- 战斗后队友对话的字幕

### 目标

- 更多材质质量档位（高、最高）
- 模型细节（LOD）档位
- 固定尺寸的画面效果（环境光遮蔽、间接光、光晕、半透明层）跟着内部分辨率放大，高分辨率下不再模糊、不再有锯齿；在游戏原本的分辨率下画面不变
- 画质选项：一行「画面质量」预设（原版、高、最高），下面阴影质量、效果质量、描绘距离、植被密度各自一行；之后再加入更好的环境光遮蔽、柔和阴影和屏幕空间反射
- 减少首次进入新场景时的卡顿
- 根据内存、GPU 与 CPU 核心数自动调整
- 冲刺：按住按键跑得更快，移动、动作和演出都会调整得自然。按键可以在按键设置里更改；可以在设置里开关，默认关闭。
- M.O.M.O.（Nintendo Switch 2 Edition 的内容）
- 佣兵团行动（Nintendo Switch 2 Edition 的内容）
- 环绕声：用 Nintendo Switch 2 Edition 自己的声音定位取代现在的做法；在那之前，环绕输出与定位仍标明是过渡做法
- 整个游戏的全字幕：野外和情境对话、菜单语音（开发中）

### 研究目标：最终形态

这项研究想达到的最终形态是《异度神剑 2：REFORGED Edition》（见[关于这个项目](README.md#关于这个项目)）。这是研究目标，不是发布计划：不会发布可游玩的版本。

- 开始新游戏时可以选择模式：经典模式（原版体验）或增强模式（预先开启优化 Mod）
- 多个存档位
- 在设置菜单里分别开关 Mod，并支持另外加入的 Mod
- 预先整合经作者同意的优秀 Mod（不包含游戏文件）

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

#### 整合 Nintendo Switch 2 Edition 新增内容的方法

我们不会另外发布忠于 Nintendo Switch 2 Edition 的版本，改为公开把 Nintendo Switch 2 Edition 新增的内容整合进原版 Switch 重编译的方法，让其他重编译项目也能使用。方法会分成几个部分，每一部分验证完成后发布；不包含任何游戏数据、密钥或解密工具，也不发布可游玩的构建，需要使用你自己合法取得的游戏。完成前不提供时间表。

本仓库不会提供任何 Switch 2 Edition 的文件、素材、密钥或提取工具，也不说明如何取出这些数据，也不会放它的截图或官方宣传图。

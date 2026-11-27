# Roadmap / 路线图

[English](#english) · [简体中文](#简体中文) · [README](README.md)

---

## English

Features are listed in three groups: Implemented, Nearly done and Planned.

### Implemented

- PC settings (graphics, controls, sound output, text language) inside the game's own Options screen
- Resolution: internal and output resolution set separately, display modes, resolution that follows the window size,
  dynamic resolution on/off; at 4K, the interface and text drawn directly at the output resolution, with cleaner text
  edges (the game's own interface images and glyphs keep their original size, so they look softer when enlarged)
- Exclusive fullscreen
- NVIDIA DLSS Super Resolution and AMD FSR Super Resolution
- Anti-aliasing without an upscaler: the original TAA, or off
- HDR output with brightness adjustment (off by default; peak brightness and paper white)
- Texture quality setting
- Anisotropic filtering setting
- Switches for depth of field and motion blur
- NVIDIA DLSS Multi Frame Generation and AMD FSR Frame Generation, for the whole game, for cutscenes only or for
  everything except cutscenes (DLSS 2x to 6x, FSR Frame Generation and switching frame generation without a restart
  confirmed in hands-on play; FSR Frame Generation in cutscenes not confirmed in hands-on play yet)
- 60 fps and higher in the first town; other areas, battles and events stay at 30 fps for now (30 by default, chosen in
  the settings)
- V-sync and frame rate caps (30 / 60 / 120 / 144 / 165 / unlimited; above 30, only in the first town for now; with
  frame generation on, the cap counts the frames shown)
- Variable refresh rate (confirmed on a G-SYNC Compatible display; AMD FreeSync not tested)
- Shaders compiled ahead of time in the background while the game runs, to reduce stutter (new content can still bring a
  brief pause the first time)
- NVIDIA Reflex (off, on, on + boost)
- Smoother play in busy and crowded scenes and when moving into new areas, and steadier frame pacing at a locked frame
  rate
- Keyboard and mouse: mouse camera and number keys for Arts
- Controller and keyboard and mouse can be used at the same time; the button prompts and the mouse pointer follow the
  device used last
- Button prompts for Xbox, PlayStation and Nintendo controller layouts, and for keyboard and mouse
- Surround output and positioning: 5.1 and 7.1 output that follows the Windows speaker setup, and the game's positioned
  sounds spread around the speakers by direction, with the positioning off by default (an interim approach for the demo,
  to be replaced later by one faithful to the Nintendo Switch 2 Edition). Not tested on physical 5.1/7.1 speakers. On
  headphones with virtual surround (Dolby Atmos for Headphones), left and right can be told apart, but front and back
  are not reliable; the actual effect depends on your device.
- Pre-rendered videos in 4K (Nintendo Switch 2 Edition content): requires your own legally obtained copy of the game; no
  files are provided; without them, the original videos play
- Text language: choose Japanese, Traditional Chinese, Simplified Chinese or Korean in the game's settings; it takes
  effect after restarting the game (voices stay Japanese). With Korean, the game shows its own Korean text with its own
  Korean font; the settings and help text we added come in these four languages too, with no missing characters
- Save protection: each time you play, an automatic backup before the first save is written; if the game crashes while
  writing, the next start restores the last complete save
- Logs, and automatic crash reports if the program crashes (if the graphics card hangs, there is only the log)
- If frame generation cannot start, the game keeps running without it and says so; choosing it again in the settings
  tries again

### Nearly done

- SMAA as an anti-aliasing option when no upscaler is used
- Direct mouse control of menus (a few screens, such as the choice boxes in story dialogue, are not supported yet)
- Rebinding the keyboard and mouse: the field and battle keys, and the menus' confirm and back
- Subtitles for the party's post-battle banter (an option, off by default; the subtitle text does not come with the
  project)

### Planned

- High-resolution textures for the whole game, with more texture quality levels (High, Max) (in development)
- High-resolution UI images for the whole game (in development)
- Fonts that need no magnification at 4K (in development)
- Screen effects with a fixed size (ambient occlusion, indirect light, bloom, translucent layers) scaled with the
  internal resolution, so they are no longer blurry or jagged at high resolutions; nothing changes at the game's
  original resolution (in development)
- Graphics quality options (in development): a Graphics quality preset row (Original, High, Max), with its own row below
  for each of shadow quality, effect quality, draw distance (including model detail, LOD) and foliage density; better
  ambient occlusion, soft shadows and screen-space reflections to be added later
- Less flicker and jaggedness on eyebrows and eyelashes in cutscenes (under investigation)
- High frame rate on every map, with the whole game scanned for timings fixed at 30 fps and each one fixed (in
  development)
- Even less stutter on first visits to new places
- Automatic tuning to your RAM, free video memory and CPU cores (partly implemented)
- Further performance improvements (in development)
- Sprint: hold a key to run faster; it can be turned on or off, is off by default, and its key can be changed. The
  running animation is still being tuned (in development).
- Enhanced mode (in development): choose Classic (no enhancements) or Enhanced when starting a new game. Enhanced mode
  only cuts repetitive steps; it does not change the difficulty or the in-game economy, and each of its features can be
  turned on or off separately in the settings. The pity system for Blade pulls is an exception: it has its own switch,
  on by default in Enhanced and off in Classic. Other enhancements that change the rules have their own switches, off
  by default.
- Photo mode: a free camera while the game is paused
- M.O.M.O. (Nintendo Switch 2 Edition content; in development)
- Action-based Mercenary missions (Nintendo Switch 2 Edition content; the entry is in development, and the battle part
  has not been started)
- New outfits for Pyra and Mythra (Nintendo Switch 2 Edition content)
- A PC alternative to the amiibo rewards (Nintendo Switch 2 Edition content)
- The Nintendo Switch 2 Edition's changes to the game rules
- Screenshots without the UI (Nintendo Switch 2 Edition content)
- Controller rumble that follows the scene in cutscenes (Nintendo Switch 2 Edition content)
- The new tips pages, tutorials and information pages (Nintendo Switch 2 Edition content)
- The Nintendo Switch 2 Edition's sound (in development)
- Surround sound: the current approach to be replaced by the Nintendo Switch 2 Edition's own sound positioning; until
  then, the surround output and positioning item stays marked as an interim approach
- Full subtitles for the whole game: field and situational conversations, and menu voice lines (being researched)

### Research goal: the final form

The final form this research aims for is "Xenoblade Chronicles 2: REFORGED Edition"
(see [About this project](README.md#about-this-project)). It is a research goal, not a release: no playable version
will be released.

- Multiple save slots
- Ideas from community mods, rewritten as our own switches (containing no mod files or game data)

### Planned: long-term ideas

These ideas have no timeline and are not commitments. They show where the project could go.

**Principle:** every enhancement that changes gameplay or balance is optional. Classic mode turns on no enhancements; in
Enhanced mode, each enhancement that changes the rules can be turned on or off separately.

#### Quality-of-life features

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

#### Gameplay features (all optional)

- An optional pity system for Blade pulls
- A combat tutorial you can replay and practise
- Difficulty and balance presets
- New Game+ with selectable carry-over
- Randomizer
- New challenge modes

#### System features

- Save rollback
- UI safe area and font scaling for ultrawide screens such as 21:9

#### Graphics research

- Ray-traced shadows
- Dynamic sun shadows: shadows that change direction over the course of the day

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

- 游戏自带「选项」画面里的 PC 设置（画面、操作、声音输出、文字语言）
- 分辨率：内部与输出分辨率分开设置、显示模式、分辨率随窗口大小调整、动态分辨率开关；4K 下界面和文字直接以输出分辨率绘制，文字边缘更利落（游戏自带的界面图片和字形仍是原本的尺寸，放大后会比较软）
- 独占全屏
- NVIDIA DLSS 超分辨率与 AMD FSR 超分辨率
- 不使用超分辨率时的抗锯齿：原本的 TAA，或关闭
- HDR 输出与亮度调整（默认关闭；峰值亮度、纸白）
- 材质等级设置
- 各向异性过滤设置
- 景深与动态模糊开关
- NVIDIA DLSS 多帧生成与 AMD FSR 帧生成，可以应用到整个游戏、只在过场动画中，或过场以外（DLSS 2 至 6 倍、FSR 帧生成，以及帧生成的即时切换已实机确认；FSR 帧生成在过场中还没有实机确认）
- 第一个城镇里 60 fps 以上；其他地方、战斗和事件暂时维持 30 fps（默认 30，在设置里选择）
- 垂直同步与锁帧档位（30／60／120／144／165／不限；30 以上目前只在第一个城镇生效；开帧生成时按显示的帧数计算）
- 可变刷新率（在 G-SYNC Compatible 显示器上确认；AMD FreeSync 未测试）
- 运行时在后台提前编译着色器，减少卡顿（首次进入新内容仍可能短暂停顿）
- NVIDIA Reflex（关、开、开 + 加速）
- 忙碌和拥挤的场景、进入新区域时更流畅，锁帧时帧节奏更稳
- 键盘鼠标：鼠标控制镜头、数字键释放战技
- 手柄与键盘鼠标可以同时使用，按键提示和鼠标指针跟随最后使用的设备
- 按键图标（Xbox、PlayStation、任天堂配置，以及键盘鼠标）
- 环绕输出与定位：跟随 Windows 喇叭设置的 5.1 与 7.1 输出，并按声音的方向把游戏里有方向的声音分配到周围的喇叭，定位默认关闭（展示版的过渡做法，之后换成忠于 Nintendo Switch 2 Edition 的做法）。未用实体 5.1／7.1 音箱测试；耳机（Dolby Atmos for Headphones 虚拟环绕）上左右可以分辨，前后不稳定；实际效果因设备而异。
- 4K 预渲染影片（Nintendo Switch 2 Edition 的内容）：需要使用你自己合法取得的游戏，不提供任何文件；没有时播放原版影片
- 文字语言：在游戏的设置里选择日文、繁体中文、简体中文或韩文，重新启动游戏后生效（语音维持日文）。选韩文时，游戏显示它自己的韩文文字和韩文字体；我们加的设置和说明也有这四种语言，没有缺字
- 存档保护：每次游玩在第一次写入存档之前自动备份；写入途中崩溃时，下次启动会自动恢复到上次完整保存的内容
- 日志；程序崩溃时自动保存崩溃报告（显卡卡死时只有日志）
- 帧生成无法启动时，游戏不使用帧生成继续运行并显示说明；在设置里再选一次会重新尝试

### 接近完成

- 不使用超分辨率时的抗锯齿选项 SMAA
- 鼠标直接操作菜单（剧情对话里的选项框等少数画面还不支持）
- 键盘鼠标改键：场景和战斗的按键、菜单的确定和返回
- 战斗后队友对话的字幕（选项，默认关闭；字幕文字不随项目提供）

### 目标

- 全游戏的高分辨率贴图，以及更多材质等级（高、最高）（开发中）
- 全游戏的高分辨率界面图片（开发中）
- 4K 下不必放大的字体（开发中）
- 固定尺寸的画面效果（环境光遮蔽、间接光、光晕、半透明层）跟着内部分辨率放大，高分辨率下不再模糊、不再有锯齿；在游戏原本的分辨率下画面不变（开发中）
- 画质选项（开发中）：一行「画面质量」预设（原版、高、最高），下面阴影质量、效果质量、描绘距离（包括模型细节 LOD）、植被密度各自一行；之后再加入更好的环境光遮蔽、柔和阴影和屏幕空间反射
- 减少过场中眉毛和睫毛的闪烁与锯齿（正在调查）
- 所有地图的高帧率：扫描整个游戏里写死 30 fps 的时间，逐项修正（开发中）
- 进一步减少首次进入新场景时的卡顿
- 根据内存、显存余量与 CPU 核心数自动调整（部分已实现）
- 进一步提升性能（开发中）
- 冲刺：按住按键跑得更快，可以开关，默认关闭，按键可以更改。跑步动作还在调整（开发中）。
- 增强模式（开发中）：开新游戏时选择经典（不开启增强功能）或增强。增强模式只减少重复操作，不改变难度和游戏内的经济，每一项都可以在设置里分别开关。异刃保底是例外：有自己的开关，增强模式默认开启，经典模式关闭。其他会改变规则的增强功能另外设开关，默认关闭。
- 拍照模式：暂停时自由移动镜头
- M.O.M.O.（Nintendo Switch 2 Edition 的内容，开发中）
- 佣兵团行动（Nintendo Switch 2 Edition 的内容；入口开发中，战斗部分还没开始）
- 焰与光的新服装（Nintendo Switch 2 Edition 的内容）
- amiibo 奖励的 PC 替代入口（Nintendo Switch 2 Edition 的内容）
- Nintendo Switch 2 Edition 的规则调整
- 不带界面的截图（Nintendo Switch 2 Edition 的内容）
- 过场中随场景的手柄震动（Nintendo Switch 2 Edition 的内容）
- 新增的提示页、教学和说明页（Nintendo Switch 2 Edition 的内容）
- Nintendo Switch 2 Edition 的声音（开发中）
- 环绕声：用 Nintendo Switch 2 Edition 自己的声音定位取代现在的做法；在那之前，环绕输出与定位仍标明是过渡做法
- 整个游戏的全字幕：野外和情境对话、菜单语音（研究中）

### 研究目标：最终形态

这项研究想达到的最终形态是《异度神剑 2：REFORGED Edition》（见[关于这个项目](README.md#关于这个项目)）。这是研究目标，不是发布计划：不会发布可游玩的版本。

- 多个存档位
- 参考社区 Mod 的想法，改写成我们自己的开关（不包含任何 Mod 的文件或游戏数据）

### 目标：长期构想

这些构想没有时间表，也不是承诺，只是说明项目可能的方向。

**原则**：所有会改变玩法或平衡的增强功能都是可选的。经典模式不开启任何增强功能；增强模式里会改变规则的增强功能都可以单独开关。

#### 优化功能

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

#### 玩法功能（全部可选）

- 可选的异刃抽取保底
- 可重复练习的战斗教程
- 难度与平衡预设
- 新游戏＋自定义继承项目
- 随机化
- 新的挑战模式

#### 系统功能

- 存档回滚
- 21:9 等超宽屏的界面安全区与字体缩放

#### 画面研究

- 光线追踪阴影
- 动态光影：阴影随一天的时间改变方向

#### 整合 Nintendo Switch 2 Edition 新增内容的方法

我们不会另外发布忠于 Nintendo Switch 2 Edition 的版本，改为公开把 Nintendo Switch 2 Edition 新增的内容整合进原版 Switch 重编译的方法，让其他重编译项目也能使用。方法会分成几个部分，每一部分验证完成后发布；不包含任何游戏数据、密钥或解密工具，也不发布可游玩的构建，需要使用你自己合法取得的游戏。完成前不提供时间表。

本仓库不会提供任何 Switch 2 Edition 的文件、素材、密钥或提取工具，也不说明如何取出这些数据，也不会放它的截图或官方宣传图。

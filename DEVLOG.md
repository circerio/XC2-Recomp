# 开发日志 / Development log

这里按天记录项目的变化：解决了哪些问题、加入了哪些功能、还在调查什么。还没有在实机上试玩确认的内容，都会照实标明「等待实机验证」。

A daily record of what changed: problems fixed, features added, and what is still being looked into. Anything not yet confirmed in hands-on play is marked as awaiting hands-on testing.

## 2026-11-10

### 简体中文

#### 已解决的问题

- 开启 HDR 后，在部分显示器上，峰值高于纸白时画面会明显发灰。送给显示器的 HDR 元数据写的亮度高过这个显示模式的额定值时，全屏画面会变灰；现在默认不送了。实机试玩已确认，全屏和窗口都不再发灰。

#### 新加入的功能（已合并，等待实机验证）

- **帧生成**：支持 DLSS 多帧生成和 FSR 帧生成，并加入 Reflex 低延迟。设定里新增四个选项：DLSS 多帧生成（倍数视显卡支持而定）、FSR 帧生成、套用范围（整个游戏或只在过场）和 Reflex。生成帧时会另外提供不含游戏界面的画面，用来减少界面拖影。默认关闭。FSR 帧生成的整体流程参考了 AksharDP 的 [xc2-recomp](https://github.com/AksharDP/xc2-recomp)。
- **贴图串流移到后台**：新贴图载入时的转换改在后台线程进行，不再占用画面的处理时间，减少移动时的慢帧。现在默认开启。
- **键盘、鼠标和手柄**：
  - 设定里不用再选操作装置，会跟着你正在用的装置自动切换。
  - 改键的入口换了更清楚的名字，并标示可以打开。
  - 手柄也能改键，改键在场景和战斗中生效。手柄配置可选任天堂、Xbox 或 PlayStation，按键提示会显示对应的图标。菜单里用哪个手柄键确定、哪个键返回也可以选，菜单、提示画面和对话都会跟着。
  - 更多可以改的键：十字键的动作默认用方向键，鼠标中键重设视角；鼠标滚轮也能绑定，并可以用滚轮拉近拉远镜头。
  - 标题画面的所有选项和游戏开头的各个画面都能用鼠标操作；对话可以用左键推进；道具页面可以用鼠标，清单可以用滚轮滚动；过场暂停时可以用左键跳过。

#### 正在调查

- 开启帧生成时，画面送出的节奏目前不均匀。正在查原因。
- 锁帧时一边移动一边转动视角偶尔会卡一下：原因已经查到。第一次到新的地方时，大多是在准备新的着色器；去过的地方，主要是贴图串流和游戏本身偶尔较慢。贴图串流的部分已经改在后台处理（见上），其余的还在看。

#### 已公开的指南更新

- [HDR 指南第 2 节](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/hdr#2-stage-1-the-sdr-picture-on-an-hdr-swapchain)：不要在交换链上设定 HDR 元数据，以及我们设定时显示器发生了什么；检查 HDR 时，全屏和窗口都要看。
- [VRR 指南第 5 节](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/vrr#5-the-refresh-meter-jumps-at-a-locked-frame-rate)：开启送出节奏后刷新率读数的表现，以及读数跳动背后的慢帧。

### English

#### Fixed

- With HDR on, the picture turned noticeably grey on some displays when the peak was above paper white. When the HDR metadata sent to the display claimed more brightness than the display mode is rated for, the picture turned grey in fullscreen; it is no longer sent by default. Confirmed in hands-on play: no grey in fullscreen or in a window.

#### New (merged, awaiting hands-on testing)

- **Frame generation**: DLSS Multi Frame Generation and FSR frame generation, plus Reflex for lower latency. Four new settings: DLSS multi-frame generation (the multiplier depends on the graphics card), FSR frame generation, where it applies (the whole game or cutscenes only), and Reflex. Frame generation also gets a copy of the picture without the game's interface, meant to reduce smearing of the interface. Off by default. The FSR frame generation flow follows AksharDP's [xc2-recomp](https://github.com/AksharDP/xc2-recomp).
- **Texture streaming in the background**: converting newly loaded textures now happens on a background thread instead of taking time from drawing the frame, for fewer slow frames while moving. Now on by default.
- **Keyboard, mouse and gamepad**:
  - No more choosing a control device in the settings: it switches automatically to whatever you are using.
  - The key rebinding entry has a clearer name and shows that it opens a page.
  - Gamepad buttons can be rebound too, for the field and battle. The gamepad layout can be Nintendo, Xbox or PlayStation, and button prompts show the matching icons. Which gamepad button confirms and which goes back in menus can also be chosen, and menus, prompt screens and dialogue follow it.
  - More keys can be rebound: D-pad actions default to the arrow keys and the middle mouse button resets the camera; the mouse wheel can be bound, and it can zoom the camera in and out.
  - Every option on the title screen and the screens at the start of the game work with the mouse; left click advances dialogue; the item page works with the mouse and its lists scroll with the wheel; left click skips from a paused cutscene.

#### Under investigation

- With frame generation on, frames currently reach the display at uneven intervals. Looking into the cause.
- At a locked frame rate, moving while turning the camera occasionally hitches: the cause has been found. In a place visited for the first time it is mostly new shaders being prepared; in places already visited it is mainly texture streaming and the game itself occasionally running late. The texture streaming part now runs in the background (see above); the rest is still being looked at.

#### Guide updates

- [HDR guide, section 2](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/hdr#2-stage-1-the-sdr-picture-on-an-hdr-swapchain): don't set HDR metadata on the swapchain, what our display did when we set it, and why HDR should be checked in fullscreen as well as in a window.
- [VRR guide, section 5](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/vrr#5-the-refresh-meter-jumps-at-a-locked-frame-rate): what the refresh meter showed with frame pacing on, and the slow frames behind its jumps.

## 2026-11-09

### 简体中文

#### 已解决的问题

- 帧率上限高于 30 时，打捞潜入云海的镜头会闪过一帧残影。实机试玩已确认消失。
- HDR 的高光在接近峰值时会偏色。现在会按峰值亮度和纸白的比例，自动决定两种高光压缩方式各占多少。在最亮的颜色通道上压缩、再把两种结果按比例混合的思路，学自 jmars125 在 xcx-recomp 的 [PR #103](https://github.com/jmars125/xcx-recomp/pull/103)。已合并，等待实机验证。

#### 新加入的功能（已合并，等待实机验证）

- **HDR「高光压缩」设定**：可选「自动」或「标准」。设为「自动」时，会按峰值亮度和纸白的比例自动选择：比例合适时改用保亮度方式，较暗的高光保持原本的亮度，只压缩最亮的部分。设定里会显示目前用的是哪一种。
- **锁帧时的送出节奏**：锁帧时，画面按固定的节奏送出，让显示器的刷新率更稳定，现在默认开启。实机试玩时，锁 60 大致稳定，移动并转动视角时偶尔还会跳（见「正在调查」）。
- **繁忙区域更稳定**：三项效能改善现在默认开启。其中显存分配的做法参考了 [xcx-recomp](https://github.com/jmars125/xcx-recomp)，并使用 AMD 的 [Vulkan Memory Allocator](https://github.com/GPUOpen-LibrariesAndSDKs/VulkanMemoryAllocator)。短时间实机试玩没有发现问题。
- **后台预编译着色器**：遇到还没准备好的着色器时，会在后台提前准备同一画面接下来要用的着色器，减少第一次看到新画面时的卡顿。后台线程数按 CPU 的实体核心数调整，现在默认开启。做法参考了 Monado。
- **键盘和鼠标**：
  - Esc 按情境动作：在场景里打开主菜单，在过场里暂停（再按一次继续）；战斗、打捞和读取时不会有反应，避免误操作。
  - 新增改键页面，菜单的「确定」和「返回」也能改键，改键页会说明改动会影响哪里。实机试玩时没找到改键的入口，正在调整。
  - 用键盘和鼠标时，按键提示会显示键盘按键，并跟着玩家的改键设定；按键冲突或被菜单占用时显示「?」。
  - 标题画面、主菜单、系统菜单和存档画面可以用鼠标指向和点击；设定画面的滑杆可以用鼠标点击和拖动。

#### 正在调查

- 开启 HDR 后，在部分显示器上，峰值高于纸白时画面会明显发灰。原因已经找到，正在准备修正。
- 锁帧时一边移动一边转动视角，偶尔会卡一下，显示器的刷新率也会跟着跳。正在查原因。

#### 已公开的指南更新

- [HDR 指南](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/hdr)：补充两种高光压缩方式的混合、我们比较过的其他做法，以及这个项目现在在较亮显示器上的做法。
- [VRR 指南第 5 节](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/vrr#5-the-refresh-meter-jumps-at-a-locked-frame-rate)：锁帧时的送出节奏，加入开和关的实测对比；这个功能现在默认开启。

### English

#### Fixed

- Above a 30 frame cap, a one-frame ghost image flashed during salvage dives into the Cloud Sea. Confirmed gone in hands-on play.
- HDR highlights shifted in hue near the peak. The share of two highlight roll-offs is now set automatically from the ratio of peak brightness to paper white. The idea of compressing on the brightest colour channel and blending two results by strength comes from jmars125's [PR #103](https://github.com/jmars125/xcx-recomp/pull/103) to xcx-recomp. Merged, awaiting hands-on testing.

#### New (merged, awaiting hands-on testing)

- **HDR "Highlight compression" setting**: Auto or Standard. On Auto, the ratio of peak brightness to paper white decides: in the right range a keep-brightness mode is used, which leaves dimmer highlights at their original brightness and compresses only the brightest. The setting shows which one is in use.
- **Frame pacing at a locked frame rate**: frames go to the display on a fixed schedule so its refresh rate stays steadier, now on by default. In hands-on play at a 60 cap it was mostly steady, with occasional jumps while moving and turning the camera (see Under investigation).
- **Steadier in busy areas**: three performance improvements are now on by default. The video memory allocation approach comes from [xcx-recomp](https://github.com/jmars125/xcx-recomp), using AMD's [Vulkan Memory Allocator](https://github.com/GPUOpen-LibrariesAndSDKs/VulkanMemoryAllocator). A short hands-on play turned up no problems.
- **Background shader precompiling**: when a shader is not ready yet, the ones the rest of the frame needs are prepared ahead in the background, cutting hitches the first time something new is on screen. The number of background threads follows the CPU's physical core count; now on by default. The approach follows Monado.
- **Keyboard and mouse**:
  - Esc depends on the situation: in the field it opens the main menu, in a cutscene it pauses (press again to resume); during battles, salvaging and loading it does nothing, to avoid mistakes.
  - A key rebinding page; menu Confirm and Back can be rebound too, and the page explains what a change affects. In hands-on play the rebinding option was hard to find; this is being adjusted.
  - With keyboard and mouse, button prompts show keyboard keys and follow the player's bindings; a "?" appears where a key conflicts or a menu has taken it.
  - The title screen, main menu, system menu and save screen work with the mouse, and sliders in the settings can be clicked and dragged.

#### Under investigation

- With HDR on, the picture turns noticeably grey on some displays when the peak is above paper white. The cause has been found and a fix is being prepared.
- At a locked frame rate, moving while turning the camera occasionally hitches, and the display's refresh rate jumps with it. Looking into the cause.

#### Guide updates

- [HDR guide](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/hdr): how the two highlight roll-offs are blended, other approaches we compared, and what this project now does on brighter displays.
- [VRR guide, section 5](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/vrr#5-the-refresh-meter-jumps-at-a-locked-frame-rate): frame pacing at a locked frame rate, with measurements on and off; it is now on by default.

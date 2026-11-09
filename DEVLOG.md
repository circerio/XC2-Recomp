# 开发日志 / Development log

这里按天记录项目的变化：解决了哪些问题、加入了哪些功能、还在调查什么。还没有在实机上试玩确认的内容，都会照实标明「等待实机验证」。

A daily record of what changed: problems fixed, features added, and what is still being looked into. Anything not yet confirmed in hands-on play is marked as awaiting hands-on testing.

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

# 开发日志 / Development log

这里按天记录项目的变化：解决了哪些问题、加入了哪些功能、还在调查什么。还没有在实机上试玩确认的内容，都会照实标明「等待实机验证」。

A daily record of what changed: problems fixed, features added, and what is still being looked into. Anything not yet confirmed in hands-on play is marked as awaiting hands-on testing.

## 2026-11-13

### 简体中文

#### 已解决的问题

- 在我们的设定页里，对会打开下一页的选项按左或右，游戏会闪退（2026-11-12 记下的）：现在不会闪退了。已合并，等待实机验证。
- 渲染分辨率高于 100%（2026-11-12 记下的）：找到的两个原因已经修正，已合并，等待实机验证。4K 输出时，150% 和 200% 现在会用更大的分辨率渲染，但看起来和 100% 几乎一样。游戏的动态分辨率也会影响这一项，它的新默认见下。
  - 超过上限的值，以前会悄悄退回默认的大小；现在会压到上限，并在那一行说明。
  - 渲染画面大于输出时，窗口用的贴图不再跟着放大；选 150% 或 200% 时，不再缺少界面或出现黑边。
- 菜单的鼠标操作（2026-11-12 记下的问题和意见）。已合并，等待实机验证。
  - 世界地图上点空白处，游戏不再问要不要传送。
  - 游戏自己的指针跟着鼠标时，鼠标指针会隐藏。
  - 角色的牵绊圆环点一下就学；异刃的牵绊圆环仍然是一秒内点两下才算确定。
  - 商店的数量画面按 Enter 也能购买。
  - 用滚轮滚动清单后，鼠标停留的位置不再抢走选取。
  - 卖出清单点到饰品的分类时鼠标指针会消失：只有分页列的画面现在会保留鼠标指针，分页也能点。当时的情况没有重现。
  - 花的定制里，「零件制造」和「设置零件」的分类可以用鼠标选；分类里的清单还不行。
  - 任务清单左右两个翻页箭头可以点了。

#### 新加入的功能（已合并，等待实机验证）

- 任务完成的画面可以用左键跳过。
- **游戏的动态分辨率**：选了渲染分辨率，或输出大于游戏原本的 1280×720 时，默认关闭；在设定里设成「开」仍会打开。开启超分辨率或帧生成时一律关闭。

#### 正在调查

- 部分场景的植被出现黑色碎片，原因已找到：这款游戏画植被时，会把顶点写出来，之后的绘制再读回来；我们目前还没有做这一步。修正的做法已经设计好。
- 商店数量画面双击购买的提示：试过的做法会和标题重叠，暂时拿掉了。

#### 已公开的指南更新

- [内部与输出分辨率指南第 7 节](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/resolution#7-the-games-own-dynamic-resolution)：画面不是游戏原本的大小时，游戏自己的动态分辨率默认关闭，以及为什么。
- [原版设定画面内的 PC 设定指南第 6 节](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/settings#6-rows-that-say-what-they-can-do)：超出范围的值压到上限，并在那一行说明；动态分辨率这类默认值跟着其他设定的选项，不写成固定值，让它继续跟着变。

### English

#### Fixed

- In our settings pages, pressing left or right on a row that opens another page crashed the game (noted on 2026-11-12): it no longer crashes. Merged, awaiting hands-on testing.
- Render resolution above 100% (noted on 2026-11-12): the two causes found are fixed; merged, awaiting hands-on testing. At a 4K output, 150% and 200% now render larger, but look almost the same as 100%. The game's dynamic resolution also affects this; its new default is below.
  - A value above the limit used to fall back to the default size without a word; it is now held to the limit, and the row says so.
  - When the rendered picture is larger than the output, the textures used for the window are no longer enlarged with it; at 150% or 200%, the interface is no longer missing and there are no black borders.
- Mouse in menus (problems and feedback noted on 2026-11-12). Merged, awaiting hands-on testing.
  - On the world map, a click on empty space no longer makes the game ask whether to use Skip Travel.
  - The mouse cursor hides while the game's own pointer follows the mouse.
  - On a character's Affinity Chart, one click learns; the Blade Affinity Chart still takes a double click within a second to confirm.
  - On the quantity screen in shops, Enter buys too.
  - After scrolling a list with the wheel, the hovered item no longer takes the selection.
  - The mouse cursor disappeared when the accessories category of the sell list was clicked: screens with only a tab bar now keep the mouse cursor, and the tabs can be clicked. The original case was not reproduced.
  - In Poppiswap, the Create Parts and Set Parts categories can be selected with the mouse; the lists inside them can't yet.
  - The two page arrows of the quest list can be clicked.

#### New (merged, awaiting hands-on testing)

- Left click skips the quest-complete screen.
- **The game's dynamic resolution**: off by default when a render resolution is chosen or the output is larger than the game's 1280×720; setting it to On in the settings still turns it on. With super resolution or frame generation on, it is always off.

#### Under investigation

- In some scenes, foliage shows black fragments; the cause has been found. When the game draws foliage, it writes the vertices out and a later draw reads them back; we don't do that step yet. A fix has been designed.
- A prompt for double-click buying on the shop quantity screen: the version we tried overlapped the title, so it is out for now.

#### Guide updates

- [Internal and output resolution guide, section 7](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/resolution#7-the-games-own-dynamic-resolution): the game's own dynamic resolution off by default when the picture is not at the game's size, and why.
- [PC settings guide, section 6](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/settings#6-rows-that-say-what-they-can-do): a value out of range held to the limit, with the row saying so; a setting whose default follows other settings, such as dynamic resolution, is not written as a fixed value, so it keeps following them.

## 2026-11-12

### 简体中文

#### 已解决的问题

- 4K 时游戏文字比按键图标模糊（2026-11-11 记下的）：4K 下文字的边缘收窄，变得更清楚；720p 的画面不变。做法写在[内部与输出分辨率指南第 8 节](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/resolution#8-distance-field-text)。实机试玩已确认。
- 角色页面不能用鼠标（2026-11-11 记下的）：实机试玩已确认。
  - 角色选择的卡片点一下就进入：点御刃者进入角色设置，点异刃进入异刃设置。
  - 角色设置的图标、武技强化和饰品装备都能用鼠标选。
  - 有多位御刃者时，可以点右上的头像换人，也可以点两端的 LT／RT 箭头换上一位或下一位。
- 帧率高于 30 时，有两个短暂的等待会变短（60 fps 时只有一半）：地标语音过多久才能再响，以及某些动作之后过多久才能再跳。现在任何帧率下都和 30 fps 一样长。程序量测已确认；差别很小，肉眼看不出。

#### 实机试玩已确认

- 之前记为等待实机验证、这次实机试玩确认了的：
  - 任天堂配置下十字键改键后的按键图标，以及 Xbox、PlayStation 配置的肩键和扳机键图标。
  - 开启帧生成（2 倍）时画面顺畅，没有黑帧。
- 这次新加入、实机试玩已确认的：
  - **各向异性过滤默认改成 16x**，角色的毛发也一样；阴影等用不到的地方仍用游戏原值。远处斜看的木板在 16x 下仍看得出板缝。设定里随时可以改回游戏原值。
  - 商店的数量画面：点 ‹ › 增减数量；点数字一下不会买，一秒内再点一下就直接买下。
  - 异刃设置：武器晶片、辅助核心的格子和清单都能用鼠标选；右上的 LT／RT 箭头可以换上一位或下一位异刃。
  - 游戏自己的指针跟着鼠标：角色和异刃的牵绊圆环里，指针跟着鼠标，一秒内点两下才算确定。世界地图上指针也跟着鼠标，滚轮缩放，点地点图标或地点清单里的地点一下，游戏会问要不要传送（点空白处的问题见下）。

#### 正在调查

- 实机试玩中发现、正在修正的：
  - 在我们的设定页里，对会打开下一页的选项（例如改键、帧生成）按左或右，游戏会闪退。这是最优先的修正。
  - 渲染分辨率高于 100% 时，画面和 50% 一样模糊，应该更清楚才对。
  - 世界地图上点空白处也会被当成确定，游戏一样会问要不要传送。
  - 卖出清单点到饰品的分类时，鼠标指针会消失。
  - 花的定制里，「零件制造」和「设置零件」页面还不能用鼠标；任务清单左右两个翻页箭头点不到。
  - 根据实机试玩的意见，接下来会调整：角色的牵绊圆环改成点一下就学；数量画面双击购买时给提示，Enter 也能购买；游戏自己的指针跟着鼠标时不再显示鼠标指针；用滚轮滚动清单时，鼠标停留的位置不再抢走选取。
- 移动时画面有残影：关掉超分辨率和帧生成后仍然会出现，原因正在查。
- 帧率高于 30 时，事件和战斗的计时（例如 QTE、连打、必杀技、Chain Attack 和镜头晃动）：
  - 修正已经做好，自动回归通过，已合并。
  - 现在事件和战斗仍然锁在 30 fps，这些修正只在解除锁定时作用，默认设定不变。
  - 实际的战斗和大部分事件里还没有验证。

#### 已公开的指南更新

- [任意帧率下的自动曝光](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/exposure)：确认亮度量测有送回 CPU，以及在任何帧率下都让眼睛适应保持 30 fps 时的速度。
- [内部与输出分辨率](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/resolution)：场景用自己的分辨率，界面和文字用屏幕的分辨率，以及让距离场文字更清楚的一步。
- [存档保护与崩溃报告](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/saves)：找回主机存档「提交」语义的日志、每次游玩前的备份，以及会说明自己包含什么的崩溃报告。
- [原版设定画面内的 PC 设定](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/settings)：不散布游戏文件，在游戏自己的设定画面加入分页；PC 设定不写进存档；每个选项会说明为什么变灰；改键规则。
- [VRR 指南第 5 节](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/vrr#5-the-refresh-meter-jumps-at-a-locked-frame-rate)：新贴图的转换改到后台线程后，移动时贴图上传造成的慢帧明显减少；没有新贴图的帧会稍微慢一点。

### English

#### Fixed

- At 4K, game text was blurrier than button icons (noted on 2026-11-11): at 4K the text's edges are narrowed, so it looks sharper; the picture at 720p is unchanged. How it works is in [section 8 of the internal and output resolution guide](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/resolution#8-distance-field-text). Confirmed in hands-on play.
- The character pages did not work with the mouse (noted on 2026-11-11): confirmed in hands-on play.
  - On the Characters screen, one click on a card opens it: a Driver opens Character Setup, a Blade opens Blade Setup.
  - In Character Setup, the icons, Enhance Arts and Accessories can be selected with the mouse.
  - With several Drivers, click a portrait at the top right to switch, or the LT/RT arrows at either end for the previous or next one.
- Above 30 fps, two short waits were too short (half as long at 60 fps): how soon a landmark voice line can play again, and how soon you can jump again after some actions. They now take as long as at 30 fps, at any frame rate. Confirmed by measurement; the difference is too small to see.

#### Confirmed in hands-on play

- Listed earlier as awaiting hands-on testing, now confirmed:
  - The button icons after rebinding the D-pad with the Nintendo layout, and the shoulder and trigger icons of the Xbox and PlayStation layouts.
  - Frame generation (2x) is smooth, with no black frames.
- New this time, and confirmed in hands-on play:
  - **Anisotropic filtering now defaults to 16x**, fur included; shadows and other places that don't need it keep the game's value. At 16x, the gaps between distant planks seen at an angle stay visible. The setting can be changed back to the game's value at any time.
  - The quantity screen in shops: click ‹ › to change the amount. One click on the number does not buy; a second click within a second buys at once.
  - Blade Setup: Core Chips, Aux Core slots and the Aux Core list can be selected with the mouse; the LT/RT arrows at the top right switch to the previous or next Blade.
  - The game's own pointer follows the mouse: on the Affinity Charts of characters and Blades, a double click within a second confirms. On the world map the pointer follows the mouse too, the wheel zooms, and one click on a location icon or on a location in the list makes the game ask whether to use Skip Travel (for clicks on empty space, see below).

#### Under investigation

- Found in hands-on play, being fixed:
  - In our settings pages, pressing left or right on a row that opens another page (such as key rebinding or frame generation) crashes the game. This is the first fix.
  - Render resolution above 100% looks as blurry as 50%; it should look sharper.
  - On the world map, a click on empty space also counts as confirm, and the game still asks whether to use Skip Travel.
  - In the sell list, the mouse cursor disappears when the accessories category is clicked.
  - In Poppiswap, the Create Parts and Set Parts pages don't work with the mouse yet, and the two page arrows of the quest list can't be clicked.
  - Based on hands-on feedback, these will change: one click learns on a character's Affinity Chart; a double click to buy gets a prompt, and Enter buys too; the mouse cursor hides while the game's own pointer follows the mouse; scrolling a list with the wheel no longer lets the hovered item take the selection.
- The picture shows ghosting while moving: it still appears with super resolution and frame generation off; the cause is being looked into.
- Event and battle timing above 30 fps (QTEs, button mashing, Specials, Chain Attacks and camera shake, for example):
  - The fixes are done, passed the automatic regression, and are merged.
  - Events and battles are still locked at 30 fps, and these fixes only take effect when that lock is lifted, so the default settings don't change.
  - Most of them have not been checked in real battles and events yet.

#### Guide updates

- [Auto exposure at any frame rate](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/exposure): checking that the brightness measurement reaches the CPU, and keeping eye adaptation at 30 fps speed at any frame rate.
- [Internal and output resolution](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/resolution): the scene at its own resolution and the interface and text at the screen's, plus one more step for sharper distance-field text.
- [Save protection and crash reports](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/saves): a journal that brings back the console's save commit, backups before each run, and crash reports that say what they contain.
- [PC settings in the game's own menu](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/settings): pages in the game's own Options screen without shipping game files, PC settings kept out of the save data, rows that say why they are greyed, and key rebinding.
- [VRR guide, section 5](https://github.com/circerio/XC2-Recomp-Contributions/tree/main/guides/vrr#5-the-refresh-meter-jumps-at-a-locked-frame-rate): converting new textures on a background thread clearly cut the slow frames from texture uploads while moving, at a small cost on frames without new textures.

## 2026-11-11

### 简体中文

#### 已解决的问题

- 用键盘同时按住两个移动方向的键时，角色现在会斜着走，之前只会直着走。实机试玩已确认。
- 主菜单里还没解锁（显示「???」）的项目，鼠标移上去不再亮起，点了也不会打开。实机试玩已确认。
- 任天堂配置下，L、R、ZL、ZR 的按键图标改成了和游戏原本一样的外形，实机试玩已确认。Xbox 和 PlayStation 配置的肩键和扳机键图标也一起改了，这部分等待实机验证。
- 任天堂配置下，十字键改键后，按键提示改为显示游戏原本的图标（之前显示的是箭头）；4K 时，文字里的按键图标都换成了清楚的版本。已合并，等待实机验证。

#### 实机试玩已确认

- 2026-11-09 和 2026-11-10 记为等待实机验证的键盘、鼠标和手柄功能，这次实机试玩确认了这些：
  - 设定里不用再选操作装置；改键的入口能打开。
  - 标题画面的选项和游戏开头的各个画面能用鼠标操作；对话能用左键推进；道具页面能用鼠标；过场暂停时能用左键跳过。
  - 方向键、鼠标中键重设视角，以及用滚轮拉近拉远镜头。
  - 场景里的 Esc。
  - 手柄配置选 Xbox 时的按键图标。
  - 菜单「确定」的改键。
- 这次新加入、实机试玩已确认的：
  - 用手柄操作菜单时，鼠标指针会隐藏；一动鼠标就会再出现。
  - 商店：选择买或卖、商品清单和卖出清单都能用鼠标操作，卖出清单换了分类页后也一样。
  - 任务日志：可以用鼠标打开任务、选择缩略图、查看任务内容和返回；切换显示方式的分页，以及缩略图和列表的切换，也能用鼠标，切到列表后同样可以用。
  - 世界地图：地图和区域清单，以及传送画面右边的地点清单，都能用鼠标选择。

#### 新加入的功能（已合并，等待实机验证）

- **各向异性过滤**：图形设定多了一行，可以选游戏原值、2x、4x、8x 或 16x，改了下一帧就生效。默认是游戏原值。用来让远处斜看的地面和甲板在较高的倍率下保留更多细节，例如木纹和板缝。
- 缺少 DLSS 多帧生成或 Reflex 需要的文件时，设定里这两个选项会变灰，并标示无法使用。

#### 正在调查

- 2026-11-10 记下的开启帧生成时画面送出节奏不均匀：重新自动量测后，送出的节奏是均匀的。原本不均匀的原因还没有确定。实际的手感和画面还等实机确认。
- 实机试玩时，角色设置还不能用鼠标，修正正在测试。
- 4K 时，游戏文字比按键图标模糊：原因已经找到，修正正在测试。

### English

#### Fixed

- Holding two movement keys at once now walks diagonally; before, the character only walked straight. Confirmed in hands-on play.
- Main menu entries that are still locked (shown as "???") no longer light up under the mouse, and clicking them does not open them. Confirmed in hands-on play.
- With the Nintendo layout, the L, R, ZL and ZR button icons now have the same shapes as in the original game; confirmed in hands-on play. The shoulder and trigger icons of the Xbox and PlayStation layouts changed too; that part awaits hands-on testing.
- With the Nintendo layout, after the D-pad is rebound, button prompts show the game's own icons (they used to show arrows); at 4K, button icons inside text are all replaced with sharp versions. Merged, awaiting hands-on testing.

#### Confirmed in hands-on play

- Keyboard, mouse and gamepad features listed as awaiting hands-on testing on 2026-11-09 and 2026-11-10 that hands-on play has now confirmed:
  - No control device to choose in the settings; the key rebinding entry opens.
  - The title screen options and the screens at the start of the game work with the mouse; left click advances dialogue; the item page works with the mouse; left click skips from a paused cutscene.
  - The arrow keys, the middle mouse button resetting the camera, and zooming the camera with the wheel.
  - Esc in the field.
  - Button icons with the Xbox gamepad layout.
  - Rebinding menu Confirm.
- New this time, and confirmed in hands-on play:
  - When menus are used with a gamepad, the mouse cursor hides; it comes back as soon as the mouse moves.
  - Shops: choosing to buy or sell, the goods list and the sell list work with the mouse, including the sell list after switching category tabs.
  - Quest log: the mouse opens quests, selects thumbnails, shows quest details and goes back; the display tabs and the switch between thumbnails and list work with the mouse too, and so does the list view.
  - World map: the maps, the area list and the location list on the right of the fast travel screen can all be selected with the mouse.

#### New (merged, awaiting hands-on testing)

- **Anisotropic filtering**: a new row in the graphics settings: the game's value, 2x, 4x, 8x or 16x; a change takes effect from the next frame. The default is the game's value. Meant to keep more detail, such as wood grain and plank gaps, on distant ground and decks seen at an angle at the higher levels.
- When files needed by DLSS Multi Frame Generation or Reflex are missing, those two settings are greyed out and marked as unavailable.

#### Under investigation

- The uneven frame pacing with frame generation noted on 2026-11-10: automatic measurements taken again showed even pacing. Why it was uneven before is not established. How it feels and looks in play still awaits hands-on testing.
- In hands-on play, the character pages still don't work with the mouse; a fix is being tested.
- At 4K, game text is blurrier than button icons: the cause has been found, and a fix is being tested.

## 2026-11-10

### 简体中文

#### 已解决的问题

- 开启 HDR 后，在我们测试的显示器上，全屏时画面会明显发灰。我们送给显示器的 HDR 信息（HDR10 元数据）写的亮度高过这个显示模式的额定亮度时就会这样。现在默认不再送这份信息，实机试玩已确认全屏和窗口都不再发灰。

#### 新加入的功能（已合并，等待实机验证）

- **帧生成**：支持 DLSS 多帧生成和 FSR 帧生成，并加入 Reflex 低延迟。设定里新增四个选项：DLSS 多帧生成（倍数视显卡支持而定）、FSR 帧生成、套用范围（整个游戏或只在过场）和 Reflex。生成帧时会另外提供不含游戏界面的画面，用来减少界面拖影。默认关闭。FSR 帧生成的整体流程参考了 AksharDP 的 [xc2-recomp](https://github.com/AksharDP/xc2-recomp)。
- **贴图串流移到后台**：新贴图载入时的转换改在后台线程进行，减少移动时的慢帧。现在默认开启。
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

- With HDR on, on the display we tested, the picture turned noticeably grey in fullscreen. This happens when the HDR information we send to the display (HDR10 metadata) states a brightness above the rated brightness of that display mode. It is no longer sent by default; confirmed in hands-on play: no grey in fullscreen or in a window.

#### New (merged, awaiting hands-on testing)

- **Frame generation**: DLSS Multi Frame Generation and FSR frame generation, plus Reflex for lower latency. Four new settings: DLSS multi-frame generation (the multiplier depends on the graphics card), FSR frame generation, where it applies (the whole game or cutscenes only), and Reflex. Frame generation also gets a copy of the picture without the game's interface, to reduce interface smearing. Off by default. The FSR frame generation flow follows AksharDP's [xc2-recomp](https://github.com/AksharDP/xc2-recomp).
- **Texture streaming in the background**: converting newly loaded textures now happens on a background thread, for fewer slow frames while moving. Now on by default.
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

[WebGAL 文档](https://docs.openwebgal.com/)[如何开始制作 WebGAL？](https://docs.openwebgal.com/getting-started.html)

# 如何开始制作 WebGAL？

[Mahiru](https://github.com/MakinoharaShoko)2024年1月21日大约 2 分钟

------

此页内容

- [方法1：使用 WebGAL Terre 可视化编辑器（推荐，但可自定义程度低）](https://docs.openwebgal.com/#方法1-使用-webgal-terre-可视化编辑器-推荐-但可自定义程度低)
- [方法2：从源代码开始调试（适用于想要更高自定义程度的制作者）](https://docs.openwebgal.com/#方法2-从源代码开始调试-适用于想要更高自定义程度的制作者)

注意

无论你使用何种方式制作 WebGAL 游戏，你都应该花一点时间将开发指引的全部内容阅读一遍。这不需要多长时间，并且将有利于你避开一些因操作不当导致的问题。

你知道吗，大多数你感到疑惑的问题都可以在文档中找到答案。如果你坚信你遇到了 Bug，请在 [issuesopen in new window](https://github.com/MakinoharaShoko/WebGAL/issues) 提出问题或者发送电子邮件联系 [contact@openwebgal.com](mailto:contact@openwebgal.com)，你也可以在网站的右上角的“更多”一栏找到加入 WebGAL 讨论社区的方法。

警告

请使用现代浏览器 (Chrome / Firefox / Edge) 打开 WebGAL 和编辑器。使用其他浏览器所可能产生的问题，将不会得到解决。

## [#](https://docs.openwebgal.com/getting-started.html#方法1-使用-webgal-terre-可视化编辑器-推荐-但可自定义程度低)方法1：使用 WebGAL Terre 可视化编辑器（推荐，但可自定义程度低）

**WebGAL Terre 可视化编辑器是创建、制作并发布一个 WebGAL 的最佳方式。**

在下载 WebGAL Terre 可视化编辑器后，请解压压缩包并启动 WebGAL_Terre 可执行文件。WebGAL Terre 将会自动打开默认浏览器，如果没有打开，请输入 [http://localhost:3001/open in new window](http://localhost:3001/) 打开编辑器。

下载 WebGAL Terre 可视化编辑器：

[WebGAL 主页（推荐）open in new window](https://openwebgal.com/zh-cn/download/)

[GitHub Releasesopen in new window](https://github.com/MakinoharaShoko/WebGAL_Terre/releases)

提示

WebGAL Terre 可视化编辑器默认 **不支持 Windows 7**。
Windows 7 用户请参考 **[Windows 7 使用可视化编辑器开始制作的方法](https://docs.openwebgal.com/win7)**。

## [#](https://docs.openwebgal.com/getting-started.html#方法2-从源代码开始调试-适用于想要更高自定义程度的制作者)方法2：从源代码开始调试（适用于想要更高自定义程度的制作者）



```bash
git clone https://github.com/MakinoharaShoko/WebGAL.git
```

安装并使用 yarn 安装依赖



```bash
npm install yarn -g
yarn
```

WebGAL 使用 vite 作为打包与调试工具，你可以通过运行以下脚本启动开发服务器



```bash
yarn dev
```

推荐使用 VS Code 进行开发，并使用插件来实现语法高亮：

[语法高亮插件的商店地址open in new window](https://marketplace.visualstudio.com/items?itemName=c6h5-no2.webgal-script-basics)

[语法高亮插件的源代码仓库open in new window](https://github.com/C6H5-NO2/webgal-script-basics)

如果你要打包，请使用



```bash
yarn build
```

打包产物在 packages/webgal/dist 目录下

提示

在你完成自定义后，如果你想要使用 WebGAL 编辑器来方便地实时预览和进行资源管理，你可以将打包后的产物复制粘贴并替换掉编辑器目录下的 `packages/terre2/assets/templates/WebGAL_Template`，这样你可以将 WebGAL 编辑器内置的引擎换成自己定制过的。如果你的 WebGAL 仓库 和 WebGAL_Terre 仓库在同一目录下，你可以使用 `release-to-terre` 快捷脚本来执行

[WebGAL 文档](https://docs.openwebgal.com/)[管理游戏资源](https://docs.openwebgal.com/resources.html)

# 管理游戏资源

[Mahiru](https://github.com/MakinoharaShoko)2024年1月21日小于 1 分钟

------

提示

如果你使用图形化编辑器，你可以在左侧的工具栏中直接打开对应的资源文件夹。如果你基于源代码开发，该文件夹在 `public` 下。

你的所有游戏剧本、图片、立绘都应该放在游戏工程对应的 `game` 文件夹下，目录对应的资源说明如下：

| 文件夹     | 存放的资源                   |
| :--------- | :--------------------------- |
| animation  | 动画描述文件                 |
| background | 用于存放背景图片、标题页背景 |
| figure     | 用于存放人物立绘             |
| scene      | 用于存放用户剧本             |
| bgm        | 用于存放背景音乐             |
| vocal      | 用于存放配音文件             |
| video      | 用于存放视频                 |
| tex        | 用于存放特效纹理文件d        |

# 编辑游戏配置

[Mahiru](https://github.com/MakinoharaShoko)2024年1月21日小于 1 分钟

------

在 `game` 文件夹下，有一个名为 `config.txt` 的文件，你可以在这个文件中填写你游戏的相关信息（使用图形化编辑器可以直接编辑）。

| 参数          | 描述                                             |
| :------------ | :----------------------------------------------- |
| Game_name     | 游戏名称                                         |
| Game_key      | 游戏识别码，长度 6-10 字符，不要与别的游戏重复   |
| Title_img     | 标题图片，放在 `background` 文件夹               |
| Title_bgm     | 标题背景音乐，放在 `bgm` 文件夹                  |
| Game_Logo     | 游戏 Logo，可以显示多个，用 \| 分割              |
| Textbox_theme | 游戏对话框风格，可选择 imss 风格或 standard 风格 |

以下是配置文件示例：



```text
Game_name:WebGAL; 
Game_key:0f33fdGr;
Title_img:Title.png;
Title_bgm:夏影.mp3;
Game_Logo:WebGalEnter.png|bg.png;
Textbox_theme:imss;
```

[WebGAL 文档](https://docs.openwebgal.com/)[WebGAL 技术介绍](https://docs.openwebgal.com/tech/)

# WebGAL 技术介绍

[Mahiru](https://github.com/MakinoharaShoko)2024年1月21日大约 10 分钟

------

此页内容

- [场景系统与预加载](https://docs.openwebgal.com/#场景系统与预加载)
- - [场景获取](https://docs.openwebgal.com/#场景获取)
  - [预加载场景中的资源](https://docs.openwebgal.com/#预加载场景中的资源)
- [WebGAL 解析器](https://docs.openwebgal.com/#webgal-解析器)
- - [语句解析 Ⅰ 拆分场景](https://docs.openwebgal.com/#语句解析-i-拆分场景)
  - [语句解析 Ⅱ 脚本类型解析](https://docs.openwebgal.com/#语句解析-ii-脚本类型解析)
  - [语句解析 Ⅲ 对话的特殊处理](https://docs.openwebgal.com/#语句解析-iii-对话的特殊处理)
  - [语句解析 Ⅳ 参数解析](https://docs.openwebgal.com/#语句解析-iv-参数解析)
  - [语句解析 Ⅴ 资源处理与预加载](https://docs.openwebgal.com/#语句解析-v-资源处理与预加载)
- [流程控制系统](https://docs.openwebgal.com/#流程控制系统)
- - [准备阶段：步进前操作](https://docs.openwebgal.com/#准备阶段-步进前操作)
  - [正式阶段 Ⅰ：读指令、执行条件判断](https://docs.openwebgal.com/#正式阶段-i-读指令、执行条件判断)
  - [正式阶段 Ⅱ：调用、获取演出控制模块送演出控制器](https://docs.openwebgal.com/#正式阶段-ii-调用、获取演出控制模块送演出控制器)
  - [结束阶段：处理连续演出、更新 Backlog](https://docs.openwebgal.com/#结束阶段-处理连续演出、更新-backlog)
  - [自动与快进](https://docs.openwebgal.com/#自动与快进)
- [演出控制](https://docs.openwebgal.com/#演出控制)
- - [WebGAL 演出类型](https://docs.openwebgal.com/#webgal-演出类型)
  - [演出的自动销毁、结束判断、阻塞逻辑](https://docs.openwebgal.com/#演出的自动销毁、结束判断、阻塞逻辑)
- [舞台控制器与动画控制](https://docs.openwebgal.com/#舞台控制器与动画控制)
- - [数据驱动的 Pixi 舞台控制器](https://docs.openwebgal.com/#数据驱动的-pixi-舞台控制器)
  - [动画与“变换”控制](https://docs.openwebgal.com/#动画与-变换-控制)
  - [数据驱动的滤镜管理器](https://docs.openwebgal.com/#数据驱动的滤镜管理器)
- [存读档、回溯与用户数据](https://docs.openwebgal.com/#存读档、回溯与用户数据)
- - [WebGAL 舞台状态表介绍](https://docs.openwebgal.com/#webgal-舞台状态表介绍)
  - [演出状态的存储与恢复](https://docs.openwebgal.com/#演出状态的存储与恢复)
  - [存档与其他用户数据的存储](https://docs.openwebgal.com/#存档与其他用户数据的存储)
- [鉴赏模块，以及一些细枝末节](https://docs.openwebgal.com/#鉴赏模块-以及一些细枝末节)
- - [鉴赏模块](https://docs.openwebgal.com/#鉴赏模块)
  - [离开浏览器状态保持与“继续游戏”](https://docs.openwebgal.com/#离开浏览器状态保持与-继续游戏)
  - [快捷键与鼠标操作](https://docs.openwebgal.com/#快捷键与鼠标操作)

## [#](https://docs.openwebgal.com/tech/#场景系统与预加载)场景系统与预加载

### [#](https://docs.openwebgal.com/tech/#场景获取)场景获取

WebGAL 的场景是以文件为单位的，一般来说是后缀名为`.txt`的WebGAL 脚本文件。就像很多编程语言有一个 `main`函数作为入口一样，WebGAL 的入口场景是`start.txt`。WebGAL 会首先尝试获取 `start.txt`，然后调用WebGAL 解析器将脚本文件解析为 WebGAL 引擎可以执行的场景对象。在任何一个场景中，都可以使用`choose`、`changeScene`、`callScene`这样的方式切换或“调用”场景。切换场景会直接替换当前的场景，而“调用”场景则会向场景调用栈中推入一个新的场景开始执行，并在执行后回到调用该场景的父场景。

### [#](https://docs.openwebgal.com/tech/#预加载场景中的资源)预加载场景中的资源

在 WebGAL 解析场景的同时，场景所包含的资源也会被解析出来。对于每个场景文件，WebGAL 都会将其包含的所有资源，包括图片、音频以及视频文件。这些文件会在场景被解析完后开始预加载，以尽可能减少用户在游戏流程中等待资源加载的可能性。同时，为了使游戏在切换场景时更为顺畅，WebGAL 也会加载被当前的场景文件引用的场景文件的资源。为了防止资源浪费，WebGAL 只会拓展一层场景做预加载。

## [#](https://docs.openwebgal.com/tech/#webgal-解析器)WebGAL 解析器

### [#](https://docs.openwebgal.com/tech/#语句解析-i-拆分场景)语句解析 Ⅰ 拆分场景

WebGAL 场景文件主要是以行来区分脚本的。在解析的一开始，WebGAL 解析器就会按照换行符将脚本分割开。如果有分号，则会取分号前的字符。所以，WebGAL 脚本的注释方式就是将脚本写在分号后。

### [#](https://docs.openwebgal.com/tech/#语句解析-ii-脚本类型解析)语句解析 Ⅱ 脚本类型解析

WebGAL 的脚本一般是形如



```text
command:content -arg1 -arg2 ......;comment
```

的形式。

其中，command 代表语句指令，比如 `bgm`、`changeFigure`、`choose`这样的指令，用于标明该语句对应的控制动作。而 `content`则代表语句的主要内容比如 `bgm:Teabreak.mp3`表示的是播放一段音频文件作为 bgm。

### [#](https://docs.openwebgal.com/tech/#语句解析-iii-对话的特殊处理)语句解析 Ⅲ 对话的特殊处理

WebGAL 的对话一般以如下形式书写：



```text
森川由绮:胸につかえていることを、时は解决してくれない。忘却のラベルを贴るだけで -voice_1.ogg;
```

对于视觉小说来说，由于对话一般是脚本的主要组成部分，所以 WebGAL 设计了一个语法糖。如果任何一个脚本的 command 部分无法被解析为任何一种指令，那么 WebGAL 就会将其视为对话。而语音也可以简写其参数，只需要给出文件名即可。如上的对话实际上最终会被解析成 `say` 指令。

所以，这段对话的真正表示应该为：



```text
say:胸につかえていることを、时は解决してくれない。忘却のラベルを贴るだけで -speaker=森川由绮 vocal=voice_1.ogg;
```

除此以外，如果对话由一个人物发出，那么在对话人发生改变前，还可以省略人物名称：



```text
森川由绮:胸につかえていることを;
时は解决してくれない;
忘却のラベルを贴るだけで;
```

对于对话的特殊处理大大提高了脚本编写的效率。

### [#](https://docs.openwebgal.com/tech/#语句解析-iv-参数解析)语句解析 Ⅳ 参数解析

在 content 后以` -`分隔的是附加参数。格外需要注意的是，附加参数的连字符`-`前需要有空格，否则 WebGAL 可能会认为这不是一个参数而是一个正常的连字符。

WebGAL 的参数是以 `-key=value`的形式表示的，其中，`key` 的类型为`string`，而`value`的类型则可以动态决定，并可以以下三种可能的类型存在： `string`、`number`、`boolean`。

比如 `-key=s`的`value`是 `string`；`-key=1`的`value`是`number`，`-key=true`或`-key=false`的`value`是`boolean`。

其中，只写出 `key`而省略`value`的参数会被解析成 `-key=true`，这是一个简写的语法糖。这个语法糖非常重要，因为WebGAL 中有一个重要参数 `-next`，用于表示在执行完当前语句后立刻执行下一条语句。如果没有省略表示，则每次都需要书写`-next=true`。

### [#](https://docs.openwebgal.com/tech/#语句解析-v-资源处理与预加载)语句解析 Ⅴ 资源处理与预加载

在进行语句解析的时候，就可以获得语句所需要的资源了。比如，`bgm`语句一般需要音频资源，`playVideo`语句一般需要视频资源，`changeBg`语句一般需要图片资源。WebGAL 场景解析器会将所有场景中语句需要的资源合并起来，用于交给预加载器来预加载资源。同时，当遇到形如`changeScene`、`choose`、`callScene`等需要调用子场景的情况时，子场景也会被扫描出，解析并对其中的资源进行预加载。

## [#](https://docs.openwebgal.com/tech/#流程控制系统)流程控制系统

### [#](https://docs.openwebgal.com/tech/#准备阶段-步进前操作)准备阶段：步进前操作

流程控制模块从场景指令存储模块（这个模块是场景管理模块的子模块）获取一条指令，并进行步进前操作和检查。步进前操作主要包括停止在上一个流程中没有结束的动画、视频等带有持续时间的视觉效果。这个操作是因为当用户在上一个流程还没有结束时就点击鼠标或按下键盘的指定快捷键，意味着用户可能并不想等待到这个流程在抵达持续时间后正常结束，而是想跳过这个流程。这个时候，流程控制系统就会调用对应的提前停止流程函数（每个视觉效果都需要提供一个用于卸载这个效果的函数，调用这个函数将完全卸载这个视觉效果）。而检查则主要包括检查是否存在不能被跳过的视觉效果和检查是否已经到达当前场景的最后一条语句。如果存在不能被跳过的视觉效果（部分视觉效果脚本由于其特殊性，不能被跳过，由文章维护人员设置），则用户必须等待到抵达持续时间结束后，才可以进入下一个流程。而如果当前已经抵达场景的最后一条语句，流程控制模块会检查场景调用栈是否为空，如果不为空，则将栈顶的元素（一个场景对象）替换当前的场景存储模块中存储的场景，并将“当前语句”的指针指向场景的第一条语句，随后执行这一条语句。而如果场景调用栈为空，则可以视为互动阅读流程已经结束，这时候引擎将会跳转回互动阅读的主界面。

### [#](https://docs.openwebgal.com/tech/#正式阶段-i-读指令、执行条件判断)正式阶段 Ⅰ：读指令、执行条件判断

在这个阶段，指令将会被读取并进行条件判断。由于每一条指令都可能包含描述执行条件的参数（when参数），所以在每次执行指令时，都要进行条件判断。此时流程控制模块将描述执行条件的参数送到变量与条件判断模块请求条件判断。条件判断模块会解析条件判断表达式，结合引擎存储的内部变量进行条件判断，最终返回一个条件判断结果（真或假）。流程控制模块根据这个结果判断这条指令要不要执行。如果不执行，则跳过接下来的所有流程中的步骤，并重新回到准备阶段，准备读取下一条指令。

如果条件判断给出了真的结果，则流程控制模块进入正式阶段II。

### [#](https://docs.openwebgal.com/tech/#正式阶段-ii-调用、获取演出控制模块送演出控制器)正式阶段 Ⅱ：调用、获取演出控制模块送演出控制器

在这个阶段，将正式执行语句的指令所要执行的动作。每一种类型的指令都对应这一种动作，这个动作被存储在指令配置和执行模块。在指令配置和执行模块中，存有指令所对应的动作的配置。动作的配置主要包括指令需要执行哪些状态修改的操作（比如修改“舞台”背景或切换某个位置的人物图像）、哪些动画或特殊效果操作（比如为背景或人物图像添加一段动画效果或启动一段下雨或下雪的特殊效果）、播放一段多媒体资源等。这个配置会被送入指令执行器，具体地被指令执行器执行对应的动作。每个指令执行器执行指定的动作后，都会返回一个“演出控制模块”，这里的“演出”所表示的就是一个具有持续时间的视觉效果。“演出控制模块”主要描述当前流程中正在执行的视觉效果的描述信息和用于卸载这个视觉效果的函数，这个函数会在视觉效果抵达持续时间后被自动调用，或者在用户提前发出指令中断后提前调用。这个模块会被送入“演出控制器”，这个控制器负责维护“演出控制模块”，包括在持续时间抵达后自动卸载“演出”和在用户操作后被处于准备阶段的流程控制器调用提前结束“演出”的方法。

### [#](https://docs.openwebgal.com/tech/#结束阶段-处理连续演出、更新-backlog)结束阶段：处理连续演出、更新 Backlog

在指令执行结束后，进入结束阶段。在这个阶段，主要处理阅读历史记录的维护。因为我们需要在阅读的过程中记录用户阅读的历史记录，以方便用户在任何时候都可以查看自己的阅读历史，并回到某个记录节点。在传统的纸质图书或图文混排的阅读方式中，用户通常以往回翻页或向上滚动鼠标滚轮的方式来回到一个之前阅读的位置。而互动阅读由于阅读的流程可能会随着用户操作而改变，因此不能使用传统的记录方式（记录页码或滚动位置等）。因此，在每个结束阶段，流程控制模块都会记录当前阅读位置（一般来说是某个场景的第n条指令），以及当前的变量信息和场景状态信息。这样，当用户想要回到过去阅读的某个记录节点时，就可以很方便地读取并恢复到之前阅读的位置。

### [#](https://docs.openwebgal.com/tech/#自动与快进)自动与快进

自动阅读和快进系统本质上就是在指定的间隔内试图代替用户执行步进。自动和快进的主要区别在于，其发出的指令的优先程度和间隔不一样。

自动模式下，每隔一段时间（取决于自动模式被设置的速度），就会发出指令给流程控制系统，要求“步进”。自动模式的优先级较低，所以当遇到阻塞自动的演出（绝大多数演出，比如视频播放、对话、动画等都是阻塞自动模式的演出）时，将不会执行，直到没有演出阻塞自动模式。

而在快进模式下，绝大多数演出会被跳过，只有像选择支这样的必须用户执行一些操作的演出，不会被跳过。快进模式的触发间隔也明显较短。

## [#](https://docs.openwebgal.com/tech/#演出控制)演出控制

### [#](https://docs.openwebgal.com/tech/#webgal-演出类型)WebGAL 演出类型

### [#](https://docs.openwebgal.com/tech/#演出的自动销毁、结束判断、阻塞逻辑)演出的自动销毁、结束判断、阻塞逻辑

## [#](https://docs.openwebgal.com/tech/#舞台控制器与动画控制)舞台控制器与动画控制

### [#](https://docs.openwebgal.com/tech/#数据驱动的-pixi-舞台控制器)数据驱动的 Pixi 舞台控制器

### [#](https://docs.openwebgal.com/tech/#动画与-变换-控制)动画与“变换”控制

### [#](https://docs.openwebgal.com/tech/#数据驱动的滤镜管理器)数据驱动的滤镜管理器

## [#](https://docs.openwebgal.com/tech/#存读档、回溯与用户数据)存读档、回溯与用户数据

### [#](https://docs.openwebgal.com/tech/#webgal-舞台状态表介绍)WebGAL 舞台状态表介绍

### [#](https://docs.openwebgal.com/tech/#演出状态的存储与恢复)演出状态的存储与恢复

### [#](https://docs.openwebgal.com/tech/#存档与其他用户数据的存储)存档与其他用户数据的存储

## [#](https://docs.openwebgal.com/tech/#鉴赏模块-以及一些细枝末节)鉴赏模块，以及一些细枝末节

### [#](https://docs.openwebgal.com/tech/#鉴赏模块)鉴赏模块

### [#](https://docs.openwebgal.com/tech/#离开浏览器状态保持与-继续游戏)离开浏览器状态保持与“继续游戏”

### [#](https://docs.openwebgal.com/tech/#快捷键与鼠标操作)快捷键与鼠标操作
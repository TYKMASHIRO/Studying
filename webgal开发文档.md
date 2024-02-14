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
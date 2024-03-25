# 编辑器语法高亮 Obsidian 插件
这是一个为 [Obsidian](https://obsidian.md) 设计的插件，它允许在编辑器中对代码块进行语法高亮。

![Screenshot](https://github.com/deathau/cm-editor-syntax-highlight-obsidian/raw/main/screenshot.png)

导入了来自 [CodeMirror](https://github.com/codemirror/CodeMirror/) 的代码。

### 兼容性

自定义插件仅适用于 Obsidian v0.9.7+。

此存储库的当前 API 面向 Obsidian **v0.9.7**。

### 注意事项
当前版本仍处于试验阶段，因此某些部分可能无法正常工作。

这导入了一堆 [CodeMirror 的语法高亮模式](https://github.com/codemirror/CodeMirror/tree/5.58.2/mode)，以及 [yonce](https://github.com/codemirror/CodeMirror/blob/5.58.2/theme/yonce.css) 主题用于暗色模式。

## 安装

### 从 Obsidian 内部
从 Obsidian v0.9.8 开始，您可以通过以下步骤在 Obsidian 内部激活此插件：
- 打开设置 > 第三方插件
- 确保安全模式为 **关闭**
- 点击浏览社区插件
- 搜索 "Syntax Highlight"
- 点击安装
- 安装完成后，关闭社区插件窗口并激活新安装的插件
#### 更新
您可以按照相同的步骤来更新插件

### 从 GitHub
- 下载 [最新版本](https://github.com/deathau/cm-editor-syntax-highlight-obsidian/releases/latest)
- 从 zip 文件中提取 `cm-editor-syntax-highlight-obsidian` 文件夹到您的 vault 的插件文件夹：`<vault>/.obsidian/plugins/`  
注意：在某些机器上，`.obsidian` 文件夹可能是隐藏的。在 MacOS 上，您可以按 `Command+Shift+Dot` 以在 Finder 中显示该文件夹。
- 重新加载 Obsidian
- 如果提示安全模式问题，您可以禁用安全模式并启用插件。
否则，请前往设置，第三方插件，确保安全模式已关闭，并从那里启用插件。

## 开发

此项目使用 TypeScript 提供类型检查和文档。
该存储库依赖于最新的 [插件 API](https://github.com/obsidianmd/obsidian-api) 的 TypeScript 定义格式，其中包含了描述其功能的 TSDoc 注释。

**注意：** Obsidian API 仍处于早期阶段，随时可能更改！

如果您想要参与开发和/或只是自定义它以适应您自己的调整，您可以执行以下操作：
- 克隆此存储库。
- 运行 `npm i` 或 `yarn` 安装依赖项
- 运行 `npm run build` 进行编译。
- 将 `manifest.json`、`main.js` 和 `styles.css` 复制到您的插件文件夹的子文件夹中（例如，`<vault>/.obsidian/plugins/cm-editor-syntax-highlight-obsidian/`）
- 重新加载 Obsidian 以查看更改

或者，您可以直接将存储库克隆到插件文件夹中，并一旦安装了依赖项，就可以使用 `npm run dev` 启动监视模式中的编译。
您可能需要重新加载 Obsidian (`ctrl+R`) 来查看更改。

## 定价
哈？这是我为了 *好玩* 而制作的开源插件。它完全免费。
但是，如果您因为喜欢它而 *非得* 给我寄钱，那么可以通过 [PayPal](https://paypal.me/deathau) 投一些硬币，或者通过 [GitHub 赞助](https://github.com/sponsors/deathau) 赞助我。

# 版本历史
## 0.1.3
- 修复了 elixir 模式（抱歉这么晚才发布，它早就修复了...）
- 为 `dataviewjs` 块添加了 JavaScript 语法高亮（感谢 @dbarenholz）
- 为 `dataview` 和 `tracker` 块添加了 YAML 语法高亮（感谢 @KjellConnelly）

## 0.1.2
- 添加了 elixir 模式（感谢 James Dalton）

## 0.1.1
- 将 codemirror 主题也应用于 latex 数学

## 0.1.0
- 调整了深色 codemirror 主题，以便也应用于 frontmatter
- 在加载时重新加载编辑器模式，以便在启用时显示语法高亮
- 在卸载时删除编辑器模式，以便在禁用时隐藏语法高亮

## v0.0.1
初始发布。
从 [CodeMirror 5.58.2](https://github.com/codemirror/CodeMirror/tree/5.58.2/mode) 复制和导入编辑器模式。由于导入 `markdown` 和 `gfm` 时出现编译错误，因此暂时不可用。

## 补充说明
- `comment`：注释，位于 * ; 或 /* */ 内的文本
- `keyword`：SAS 语言变量
- `variable`：以 '&' 开头的宏变量或变量格式
- `variable-2`：DATA Step、proc 或宏名称
- `string`：位于 ' ' 或 " " 内的文本
- `operator`：数值运算符 + / - * ** le eq ge 等等
- `builtin`：proc %macro data run mend
- `atom`
- `def`

该插件导入了 CodeMirror 的多种语法高亮模式，并提供了暗色模式的 yonce 主题。

欢迎使用此插件并提供反馈！



# Editor Syntax Highlight Obsidian Plugin
A plugin for [Obsidian](https://obsidian.md) which allows syntax highlighting for code blocks in the editor.

![Screenshot](https://github.com/deathau/cm-editor-syntax-highlight-obsidian/raw/main/screenshot.png)

Imports code from [CodeMirror](https://github.com/codemirror/CodeMirror/)

### Compatibility

Custom plugins are only available for Obsidian v0.9.7+.

The current API of this repo targets Obsidian **v0.9.7**. 

### Notes
This is all very expermental at the moment, so parts might not work, etc.

This imports a bunch of [syntax highlighting modes from CodeMirror](https://github.com/codemirror/CodeMirror/tree/5.58.2/mode), as well as the [yonce](https://github.com/codemirror/CodeMirror/blob/5.58.2/theme/yonce.css) theme for dark mode.

## Installation

### From within Obsidian
From Obsidian v0.9.8, you can activate this plugin within Obsidian by doing the following:
- Open Settings > Third-party plugin
- Make sure Safe mode is **off**
- Click Browse community plugins
- Search for "Syntax Highlight"
- Click Install
- Once installed, close the community plugins window and activate the newly installed plugin
#### Updates
You can follow the same procedure to update the plugin

### From GitHub
- Download the [Latest release](https://github.com/deathau/cm-editor-syntax-highlight-obsidian/releases/latest)
- Extract the `cm-editor-syntax-highlight-obsidian` folder from the zip to your vault's plugins folder: `<vault>/.obsidian/plugins/`  
Note: On some machines the `.obsidian` folder may be hidden. On MacOS you should be able to press `Command+Shift+Dot` to show the folder in Finder.
- Reload Obsidian
- If prompted about Safe Mode, you can disable safe mode and enable the plugin.
Otherwise head to Settings, third-party plugins, make sure safe mode is off and
enable the plugin from there.

## Development

This project uses Typescript to provide type checking and documentation.  
The repo depends on the latest [plugin API](https://github.com/obsidianmd/obsidian-api) in Typescript Definition format, which contains TSDoc comments describing what it does.

**Note:** The Obsidian API is still in early alpha and is subject to change at any time!

If you want to contribute to development and/or just customize it with your own
tweaks, you can do the following:
- Clone this repo.
- `npm i` or `yarn` to install dependencies
- `npm run build` to compile.
- Copy `manifest.json`, `main.js` and `styles.css` to a subfolder of your plugins
folder (e.g, `<vault>/.obsidian/plugins/cm-editor-syntax-highlight-obsidian/`)
- Reload obsidian to see changes

Alternately, you can clone the repo directly into your plugins folder and once
dependencies are installed use `npm run dev` to start compilation in watch mode.  
You may have to reload obsidian (`ctrl+R`) to see changes.

## Pricing
Huh? This is an open-source plugin I made *for fun*. It's completely free.
However, if you absolutely *have* to send me money because you like it that
much, feel free to throw some coins in my hat via
[PayPal](https://paypal.me/deathau) or sponsor me via
[GitHub Sponsors](https://github.com/sponsors/deathau)

# Version History
## 0.1.3
- Fixed elixir mode (sorry this took me so long to release, it was fixed AAAGES ago...)
- Added javascript syntax highlighting for `dataviewjs` blocks (thanks @dbarenholz)
- Added YAML syntax highlighting for `dataview` and `tracker` blocks (thanks @KjellConnelly)

## 0.1.2
- Added elixir mode (thanks to James Dalton)

## 0.1.1
- Apply codemirror theme to latex math also

## 0.1.0
- Adjusted the dark codemirror theme to also apply to frontmatter
- Reload the editor modes on load, so syntax highlighting is shown on enable
- Delete editor modes on unload, so syntax highlighting is hidden on disable

## v0.0.1
Initial Release.  
Copy-pasted and imported editor modes from [CodeMirror 5.58.2](https://github.com/codemirror/CodeMirror/tree/5.58.2/mode). Got compiler errors importing `markdown` and `gfm`, so those aren't available for now.

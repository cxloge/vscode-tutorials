# 42_VSCode渲染出空格符和制表符

**VSCode 渲染出空格符和制表符**，这里我们可以先一起来玩一个“大家来找茬”的游戏：

**图1是使用没有修改过任何编辑器设置的 VS Code 打开的一个 JavaScript 的文件**

![VSCode 渲染出空格符和制表符](https://img.geek-docs.com/vscode/tutorials/optimized-editor-original.png)

**图2是使用经过了不少的个性化定制的编辑器打开的同一个文件**
![VSCode 渲染出空格符和制表符](https://img.geek-docs.com/vscode/tutorials/optimized-editor-after.png)

在图2中你能够在不少代码行前面看到灰色的“点”，这每一个“点”都代表着一个空格符。你可以通过设置 `editor.renderWhitespace: all` 让编辑器将所有的空格符、制表符等全部都渲染出来。这样你就能够一眼看出这个文件中使用的究竟是制表符还是空格符，以及有没有在哪里不小心多打了一个空格等。
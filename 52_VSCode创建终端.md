# 52_VSCode创建终端

**VSCode 创建终端**，VS Code 在设计之初，就一直在思考如何让 VS Code 和终端能够更紧密联系在一起。其第一种方式就是从终端中以命令行的形式打开 VS Code。第二种方式，就是允许用户从资源管理器里调出系统终端。

首先，我们要做的第一件事情就是，打开和创建一个集成终端。最简单的方式就是按一下 Ctrl + ` 键，一个新的终端就被创建出来了。

![VSCode 创建终端](https://img.geek-docs.com/vscode/terminal/terminal-1.gif)

在这个终端被创建出来后，我们还可以通过再次按下 Ctrl + ` 键将其隐藏。如果查看一下快捷键绑定，或者使用命令面板的话，我们会发现这个命令其实是 “切换集成终端”（Toggle Integrated Terminal）。它的作用是：如果还没有任何集成终端存在，那么它将创建一个新的，然后显示出来；如果已经有几个集成终端了，那么就把终端面板调出来；而如果我们的光标就在集成终端里，那么这个命令会将终端面板隐藏。

当然，若我们希望创建出一个新的终端来，而不是上面描述的切换命令，那就需要按下 Ctrl + Shift + `，或者在命令面板里搜索 “新建集成终端”（Create New Intergrated Terminal）并运行。

![VSCode 创建终端](https://img.geek-docs.com/vscode/terminal/terminal-2.gif)

正如我们在上面的动图里看到的，当我们的光标在一个集成终端里，按下“新建集成终端”的命令时，我们会在终端面板里看到一个崭新的终端。

![VSCode 创建终端](https://img.geek-docs.com/vscode/terminal/terminal-3.png)

在这个面板的最上方，我们能够看到一个下拉框。下拉框里现在显示的是 `2：bash`，它的意思是，我们现在正在使用的是第二个集成终端，而它里面运行的是 bash。

如果我们点击这个下拉框，就能够看到所有的集成终端。

![VSCode 创建终端](https://img.geek-docs.com/vscode/terminal/terminal-4.png)

我们除了可以使用这一个下拉列表来实现在不同的集成终端之间切换，还可以从命令面板里运行 “聚焦于下一终端” （Focus Next Terminal）或者 “聚焦于上一终端” （Focus Previous Terminal）进行切换。从下面的动图中我们可以看到，这两个命令并没有绑定快捷键，但是我推荐大家给它们绑定上顺手的快捷键，比如 Ctrl + Tab，来进行一键切换。

![VSCode 创建终端](https://img.geek-docs.com/vscode/terminal/terminal-5.gif)

当然，如果我们的电脑屏幕足够大，或者我们希望在同一界面上看到多个运行的脚本，我们也可以把一个终端面板进行切分。我们只需按下 Cmd + \ 或者运行 “拆分终端”（Split Terminal），就能够将当前的终端一分为二；如果再次按下这个快捷键，就能够将当前的面板平均分为三份……

![VSCode 创建终端](https://img.geek-docs.com/vscode/terminal/terminal-6.gif)

在这三个拆分终端之间切换的快捷方式，与上面集成终端之间的切换也是非常类似的，它们是 命令面板里的“聚焦于下一个窗格” (Focus Next Pane)、“聚焦于上一个窗格” (Focus Previous Pane)。如此一来，在多个终端和窗格之间切换就一共有四个命令了，要给它们搭配好快捷键，可就需要下一番功夫了。

![VSCode 创建终端](https://img.geek-docs.com/vscode/terminal/terminal-7.gif)
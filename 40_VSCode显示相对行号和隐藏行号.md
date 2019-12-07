# 40_VSCode显示相对行号和隐藏行号

**VSCode 显示相对行号和隐藏行号**，这里我们可以先一起来玩一个“大家来找茬”的游戏：

**图1是使用没有修改过任何编辑器设置的 VS Code 打开的一个 JavaScript 的文件**

![VSCode 显示相对行号和隐藏行号](https://img.geek-docs.com/vscode/tutorials/optimized-editor-original.png)

**图2是使用经过了不少的个性化定制的编辑器打开的同一个文件**
![VSCode 显示相对行号和隐藏行号](https://img.geek-docs.com/vscode/tutorials/optimized-editor-after.png)

编辑器最左侧的行号。在图1中，行号代表的是每一行代码所处的位置，也就是在当前文件中处于第几行，是绝对行数。而在图2中，行号则显示的是每一行代码相对于当前光标所在位置的行的距离，是相对行数。经常使用 Vim 的用户一定非常熟悉这个功能。

除了改变行号的值以外，你还能够将行号完全隐藏起来，也就是使整体代码不显示行号。这控制整个行号显示与否及如何显示对应的编辑器设置是 `editor.lineNumbers`。
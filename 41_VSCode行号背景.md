# 41_VSCode行号背景

**VSCode 行号背景**，这里我们可以先一起来玩一个“大家来找茬”的游戏：

**图1是使用没有修改过任何编辑器设置的 VS Code 打开的一个 JavaScript 的文件**

![VSCode 行号背景](https://img.geek-docs.com/vscode/tutorials/optimized-editor-original.png)

**图2是使用经过了不少的个性化定制的编辑器打开的同一个文件**
![VSCode 行号背景](https://img.geek-docs.com/vscode/tutorials/optimized-editor-after.png)

在图 1 中，第五行的代码下有一个绿色的背景色。通过这样一个背景色的改变，你能够清楚地看到哪一行代码是当前光标所在的位置。

而在图 2 中，我则是通过更改设置 `editor.renderLineHighlight: "all"` 把当前代码行的行号下的背景色也修改了，所以你可以看到图 2 的行号 5 的背景色也成为了绿色，整体上看起来更统一。
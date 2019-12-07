# 44_VSCode光标样式

**VSCode 光标样式**，这里我们可以先一起来玩一个“大家来找茬”的游戏：

**图1是使用没有修改过任何编辑器设置的 VS Code 打开的一个 JavaScript 的文件**

![VSCode 光标样式](image/optimized-editor-original.png)

**图2是使用经过了不少的个性化定制的编辑器打开的同一个文件**
![VSCode 光标样式](image/optimized-editor-after.png)

在图1中，光标是一条竖线，而在图2中光标则相对粗一些。编辑器中的光标样式有非常多种，你可以控制粗细，也可以控制它怎么闪烁。你需要调整的设置是 `editor.cursorBlinking` `editor.cursorStyle` 和 `editor.cursorWidth`。
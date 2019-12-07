# 17_VSCode快速修复

**VS Code快速修复**,语言服务除了在书写代码的时候提供提示以外，还能够帮我们分析当前的代码，检测出他们潜在的问题，然后提供快速修复的方案。比如在下面的 CSS 代码中，我们拼错了 padding 这个属性。

```css
.foo {
 font-size: 5px;
 margin: 5px;
 pading: 1;
}
```

CSS

编辑器中，我们能在 `pading` 下看到了绿色的波浪线，并且在这行的行首，看到一个灯泡的图标。

![代码提示的灯泡图标](https://img.geek-docs.com/vscode/language-support/code-hint-icon.png)

点击这个灯泡的图标，我们就能看到一个新的列表，列表里就是语言服务提供的修复这个错误的操作建议。

![修复错误相关的建议](https://img.geek-docs.com/vscode/language-support/repair-error-suggest.png)

在这个例子里，我们要做的就是选择第一个操作建议，把pading换成 padding。除了点击这个黄色的灯泡图标，我们也可以按下 “ `Cmd+.` ” （Windows 上是 `Ctrl + .` ）来调出这个快速修复的建议列表。

![通过快捷键调出建议列表](https://img.geek-docs.com/vscode/language-support/pop-suggest-list.gif)

在之前的学习过程中，就有同学留言问过，不确定什么时候能够看到这个黄色的灯泡图标。编辑器在你把光标移动到这个错误或者警告所在的代码上时才会展示这个图标。
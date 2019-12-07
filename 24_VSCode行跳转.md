# 24_VSCode行跳转

**VS Code行跳转**,打开某一个文件之后，你的另外一个需求可能就是要快速跳转到这个文件的某一行。你可能会想，VS Code是不是可以像Vim那样，输入“:13”就能跳转到第13行。是的，VS Code也提供了一种极为简单的方式来支持行跳转，你只需要按下 “Ctrl + g”，紧接着编辑器就会出现一个输入框。如下图所示：

![按下 “Ctrl + g”，调出行输入框](https://img.geek-docs.com/vscode/language-support/ctrl-g-line-jump.png)
按下 “Ctrl + g”，调出行输入框

你会惊喜地发现，这个输入框的第一个字符就是 “ `:` ”，在这之后输入数字，你就能够将光标快速地移动到那一行。是不是很便捷？

![输入行数3，跳转到第3行](https://img.geek-docs.com/vscode/language-support/jump-to-line-3.gif)
输入行数3，跳转到第3行

接下来我再给你介绍一个高阶组合技巧。如果你想跳转到某个文件的某一行，你只需要先按下 “Cmd + P”，输入文件名，然后在这之后加上 “:”和指定行号即可。

![跳转到指定文件的指定行数](https://img.geek-docs.com/vscode/language-support/specify-file-line-jump.gif)
跳转到指定文件的指定行数
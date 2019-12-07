# 25_VSCode符号跳转

**VS Code符号跳转**，文件跳转和行跳转，是代码跳转的基本操作，也是日常编码中的高频操作。不过有的时候，你可能会希望能够立刻跳转到文件里的类定义，或者函数定义的位置。为了支持这种跳转，VS Code 提供了一套 API 给语言服务插件，它们可以分析代码，告诉 VS Code 项目或者文件里有哪些类、哪些函数或者标识符（我们把这些统称为符号）。

如果要在一个文件里的符号之间跳转，你只需按下 “Cmd + Shift + O” （Windows 上是 Ctrl + Shift + O），就能够看到当前文件里的所有符号。

![使用 “Cmd + Shift + O”组合键，调出当前文件的符号](https://img.geek-docs.com/vscode/language-support/ctrl-shif-o-symbols.png)
使用 “Cmd + Shift + O”组合键，调出当前文件的符号

使用方向键，或者搜索，找到你想要的符号后，按下回车，就能够立刻跳转到那个符号的位置。如下图所示：

![通过符号功能跳转到指定的代码位置](https://img.geek-docs.com/vscode/language-support/jump-by-symbols.gif)
通过符号功能跳转到指定的代码位置

请注意，在按下 “Cmd + Shift +O”后，输入框里有一个 “@”符号，这个符号在这里的意义，我会在后面的章节里去介绍，你可以先留个心眼。这时，如果你输入 “:”，就可以将当前文件的所有符号，进行分类，这样搜索符号也就更加方便。

![对当前文件的所有符号进行分类](https://img.geek-docs.com/vscode/language-support/category-symbols.gif)
对当前文件的所有符号进行分类

有些语言除了提供单个文件里的符号，还支持在多个文件里进行符号跳转。比如在 VS Code 里，如果你打开了多个 JavaScript 文件，就可以按下 “Cmd + T” （Windows 上是 Ctrl + T），搜索这些文件里的符号。

![通过“Cmd + T”，搜索多个文件的符号](https://img.geek-docs.com/vscode/language-support/ctrl-t-search-symbols.gif)
通过“Cmd + T”，搜索多个文件的符号
# 23_VSCode文件跳转

**VS Code文件跳转**，当你在开发一个新功能或者修复一个 Bug的时候，你同时在阅读和修改的文件可能就有几个或者十几个。从资源管理器里打开文件固然方便，但是如果这个项目里的文件非常多，并且经常需要在资源管理器里寻找文件，那“眼花缭乱”的，肯定要浪费你不少宝贵的时间。

在VS Code中，解决这个问题的第一个方法，就是按下 “Ctrl+Tab”，然后继续按着 “Ctrl”键但是松开 “Tab” 键，这样你就可以打开一个文件列表，这个列表罗列了当前打开的所有文件。接下来，你可以通过按下 “Tab”键在这个列表里跳转，选择你想要打开的文件。最后选到你想打开的文件后，松开 “Ctrl” 键，这个文件就被打开了。

![通过“Ctrl+Tab”组合键选择并打开文件](https://img.geek-docs.com/vscode/language-support/ctrl-tab-select-open-file.gif)
通过“Ctrl+Tab”组合键选择并打开文件

不过，使用这个方式切换文件，最大的问题在于，文件一旦多了，你就得不停地按 “Tab” 键，没完没了地上下跳转和挑选，这会是一个恼人的耗费时间和眼力的操作。

还好，VS Code 在命令面板里提供了一种支持搜索的文件跳转方式。当你按下 “Cmd + P” （Windows 上是 Ctrl + P）时，就会跳出一个最近打开文件的列表，同时在列表的顶部还有一个搜索框。

看到这里想必你应该明白了，你可以使用这个搜索框来快速地找到你想要的文件，然后按下 “Enter” 键直接打开，这整个过程简单而且顺畅。

![按下“Cmd + P”打开最近打开的文件列表](https://img.geek-docs.com/vscode/language-support/ctrl-p-recent-opened-files.gif)
按下“Cmd + P”打开最近打开的文件列表

在这里，我再分享给你一个小技巧，当你找到目标文件后，可以按下 “Cmd + Enter ” （Windows 上是 Ctrl + Enter）组合键。你会发现与上面不一样的是，这个文件在一个新的编辑器窗口中打开了。

![按下 “Cmd + Enter ”组合键在新窗口中打开文件](https://img.geek-docs.com/vscode/language-support/ctrl-enter-new-window-open.gif)
按下 “Cmd + Enter ”组合键在新窗口中打开文件
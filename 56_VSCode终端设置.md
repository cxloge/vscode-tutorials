# 56_VSCode终端设置

**VSCode 终端设置**，我们一起看一下如何设置集成终端，让它能够符合我们平时的终端使用习惯。

文章目录

- [1 在终端里使用什么样的 Shell](https://geek-docs.com/vscode/vscode-tutorials/vscode-terminal-settings.html#_Shell)
- [2 集成终端在创建时给 Shell 脚本传入参数](https://geek-docs.com/vscode/vscode-tutorials/vscode-terminal-settings.html#_Shell-2)
- [3 环境变量](https://geek-docs.com/vscode/vscode-tutorials/vscode-terminal-settings.html#i)
- [4 terminal.integrated.scrollback](https://geek-docs.com/vscode/vscode-tutorials/vscode-terminal-settings.html#terminalintegratedscrollback)
- [5 优化终端的样貌](https://geek-docs.com/vscode/vscode-tutorials/vscode-terminal-settings.html#i-2)

## 在终端里使用什么样的 Shell

默认情况下，在 Windows 10 上我们会使用 PowerShell，而如果是 Win 10 以下的版本那么默认的 Shell 则会是 Cmd。macOS 和 Linux 下 VS Code 会检测你的默认 Shell 是什么，比如在我的系统上，我就是使用 Zsh，而如果没有找到的话，终端则会使用 Bash 或者 sh 作为启动时的 Shell 环境。

如果 VS Code 挑选的 Shell 不是你想要的，那么你可以修改 `terminal.integrated.shell.windows`、`terminal.integrated.shell.osx` 或者 `terminal.integrated.shell.linux`，这个设置的值就是你想要使用的 Shell 在系统上的路径。

## 集成终端在创建时给 Shell 脚本传入参数

比如说我们想在 Linux 环境下创建 Bash 的时候，使用登陆 Shell （login shell），那我们就可以把 `terminal.integrated.shellArgs.linux` 修改为 -l 来实现。

## 环境变量

第三个非常常用的集成终端设置就是环境变量了，我们既可以把环境变量写到脚本里去，也可以使用 `terminal.integrated.env.osx`、`terminal.integrated.env.linux` 或者 `terminal.integrated.env.windows` 来控制集成终端创建 Shell 时，该使用哪些特殊的环境变量。如果你希望在 VS Code 和系统终端里使用不同的环境变量，那么这个设置就能帮助到你。

此外，集成终端还从各种终端模拟器那里学习到不少有用的设置，比如 `terminal.integrated.cwd` 用于控制 Shell 启动时的初始目录；`terminal.integrated.rightClickBehavior` 控制鼠标右键点击时的行为；`terminal.integrated.enableBell` 可以控制当脚本出错时是否要发出响声。

## `terminal.integrated.scrollback`

终端在运行脚本时，只会保存最近输出的 1000 行结果。有的时候，当我们跑一些测试，1000 行根本不够用，测试跑完了，想往上翻页看看前面的结果，却发现只有 1000 行，没法看到全部的结果。那这时我们就可以把这个设置修改为一个较高的值，比如我就把这个值改成了 5000。集成终端的代码实现还是很不错的，所以我一点也不担心把这个值调大后会影响 VS Code的整体性能。当然，如果我们觉得集成终端里的输出结果已经不需要了，也可以按下快捷键 “`Cmd + K`”来清除所有的输出结果。

## 优化终端的样貌

在下图中，我们能够轻松的看出，我的 Shell 现在是在 vscode-sample 这个文件夹下，同时这个项目是使用 Git 进行版本管理的，当前的分支是 master，你还能够看到特殊的符号。这里我使用的是 zsh 和 oh-my-zsh 插件，你也可以试试。对了，我在 Windows 上会使用 Posh-Git 来完成类似的效果。

![VSCode 终端设置](image/terminal/terminal-15.png)
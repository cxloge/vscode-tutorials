# 22_VSCode悬停提示窗口

**VS Code悬停提示窗口**,相信你在 VS Code 的编辑器里使用鼠标的过程中，早就发现了，当你的鼠标移动到某些文本上之后，稍待片刻就能看到一个悬停提示窗口。这个窗口里会显示跟鼠标下文本相关的信息。

比如，在我们的示例代码中，当我们把鼠标移动到第五行 foo 上后，悬停提示窗口里展示了 foo的类型信息，它告诉我们 foo是一个函数，不需要任何的参数，返回值是 void。

![了解函数的类型信息](https://img.geek-docs.com/vscode/mouse-operation/function-type-info.gif)

如果我们把鼠标移动到 foo 上面时，按下 Cmd 键（Windows 上是 Ctrl），则能够在悬停提示窗口里直接看到 foo的实现。

![按下Cmd键，辅助以鼠标，查看函数实现](https://img.geek-docs.com/vscode/mouse-operation/function-impl.gif)

我们能看到这样的信息，是因为这个功能也被包含在了 VS Code 的语言接口之中。VS Code 会告诉语言服务，当前鼠标所在位置的信息，语言服务会根据当前的项目情况和代码提供有用的信息。

在 JavaScript 或者 Java 这样的编程语言中，当我们把鼠标移动到某个变量上时，我们能够看到这个变量的定义信息。而在 CSS 中，当我们把鼠标移动到一个 CSS 规则上时，我们能看到的则是一段能够让这个 CSS 规则生效的 HTML 的样例代码。

![了解CSS对应的HTML代码样例](https://img.geek-docs.com/vscode/mouse-operation/css-in-html-sample.gif)

当然，除了语言服务，任何 VS Code 上的插件都能够控制悬浮窗口里的内容。
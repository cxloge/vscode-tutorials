# 26_VSCode定义和实现间跳转

**VS Code定义和实现跳转**，符号跳转依托于语言插件对代码的分析，已经算得上具备一定的智能特性，但是它还是不够精确。比如说我们看到某个函数的调用，想要知道这个函数的接口定义是什么样的，它的实现细节是什么样的，光靠符号跳转，还是会不方便。我们需要的是直接跳转到定义和实现的位置，Java程序员看到这里一定会深有感触。

当然，这个功能也需要语言本身的支持。比如说当你在使用 TypeScript 时，按下 F12，就可以跳转到函数的定义处。

F12跳转到函数定义的位置
![F12跳转到函数定义的位置](https://img.geek-docs.com/vscode/language-support/f12-function-definition-jump.gif)

也可以按下 “Cmd + F12” （Windows 上是 Ctrl + F12），跳转到函数的实现的位置。

Cmd + F12 跳转到函数实现的位置
![Cmd + F12 跳转到函数实现的位置](https://img.geek-docs.com/vscode/language-support/ctrl-f12-function-impl.gif)

而在书写 JavaScript 时，因为并没有接口（interface）的概念，定义和实现恰好是相同的。

JavaScript 里 F12 和 Cmd + F12 效果一样
![JavaScript 里 F12 和 Cmd + F12 效果一样](https://img.geek-docs.com/vscode/language-support/js-ctrl-f12-f12-same.gif)
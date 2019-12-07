# 73_VSCode支持Node.js

**VSCode 支持Node.js**，VS Code 的各种 JavaScript 功能，是通过 TypeScript 的编译器来实现的，但是它并没有局限JavaScript 代码是前端项目还是后端项目，VS Code 对它们的语言支持都是一致的。不过，这里不得不提 VS Code 的 Node.js 调试器。它是 VS Code 里的第一个代码调试器，可以说，VS Code 的代码调试 API，Node.js 是支持得最好的。从这个角度看，Node.js 在 VS Code 项目的地位，可以跟 TypeScript 比肩了。

那么，我们就来看看，VS Code 里对于 Node.js 调试，有哪几个有趣且实用的功能。

文章目录

- [1 代码调试 Auto Attach](https://geek-docs.com/vscode/vscode-tutorials/vscode-node-js-support.html#_Auto_Attach)
- [2 记录点 Logpoints](https://geek-docs.com/vscode/vscode-tutorials/vscode-node-js-support.html#_Logpoints)

## 代码调试 Auto Attach

第一个就是代码调试（Auto Attach）了。在前面介绍 VS Code 的代码调试功能时，我举的第一个例子，就是打开一个 JavaScript 文件，以 Node.js 环境进行调试运行，然后又介绍了如何书写 launch.json 来提供相对复杂的代码调试配置。

其实，Node.js 调试器则更进一步。如果我们在 VS Code 的集成终端里以命令行的形式调试代码的话，则可以无需 launch.json，直接将调试器挂载到运行的代码上。

首先，我们将 index.js 代码调整成 Node.js 支持的格式（请注意，这里我暂时不再引用 app.js 模块，而是只使用 index.js 内的函数）：

```javascript
// @ts-check

function foo() {
    bar("Hello World");
}

/**
 * bar
 * @param {string} str 
 */
function bar(str) {
    console.log(str);
}

foo()
```

JavaScript

然后打开命令面板，执行 “切换开关自动附加” （Toggle Auto Attach）命令；

![VSCode Node.js的支持](https://img.geek-docs.com/vscode/language/js-nodejs-17.gif)

然后我们在 index.js 的第 15 行插入一个断点。

![VSCode Node.js的支持](https://img.geek-docs.com/vscode/language/js-nodejs-18.gif)

最后，我们打开集成终端，输入 Node.js 的调试命令：

```javascript
node --inspect-brk index.js
```

JavaScript

可以看到 VS Code 立刻进入了调试模式，然后在第 15 行停了下来。

![VSCode Node.js的支持](https://img.geek-docs.com/vscode/language/js-nodejs-19.gif)

所以，如果你平时就是使用 JavaScript 直接写 Node.js，相信这个命令肯定能给你省去很多调整 `launch.json` 的麻烦。

## 记录点 Logpoints

下一个功能，叫做记录点（Logpoints），这个看名字不太好理解呢。不过相信你在开发 JavaScript 的过程中，肯定会经常在代码中输入 console.log() 来输出变量值以便调试。即使现在编辑器和浏览器的调试功能都已经非常强大了，但是很多同学依然喜欢这种简单的方式来调试代码。

Node.js 调试的 Logpoints 功能，就是将 console.log 和断点结合起来，把 console.log 要输出的信息，通过类似于条件断点的方式执行并打印出来。具体操作是如何的呢？

首先我们在第 12 行行号前右击，从上下文菜单里选择“添加记录点”，然后从左侧的选择列表里，选择表达式。在输入框里输入我们想要输出的内容并且用花括号包裹 `{ str + “!” }`，按下回车。

![VSCode Node.js的支持](https://img.geek-docs.com/vscode/language/js-nodejs-20.gif)

接着，我们 F5 调试当前这个文件，选择 Node.js 这个环境。由于我们其实并没有真正创建断点，所以代码很快执行结束。我们不妨打开调试面板看看。

![VSCode Node.js的支持](https://img.geek-docs.com/vscode/language/js-nodejs-21.gif)

我们能在调试面板里看到两个输出结果：

```
Hello World!        index.js:12
Hello World         index.js:12
```

第一条结果就来自记录点 Logpoints，而第二条则是我们代码中的 console.log(str)。看到这里，相信你就明白这个功能的用途了，你可以将原本需要写在代码里的 console.log ，放到记录点 Logpoints 中，一样可以得到输出结果，而且还不改变原有的代码。
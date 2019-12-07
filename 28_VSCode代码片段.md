# 28_VSCode代码片段

**VSCode代码片段**，有的时候，我们经常输入的代码是业务强相关的，语言服务没法做出优化；或者是一些我们经常使用的定式，比如循环语句、创建一个新的类或者一个 UI 控件，我们经常写类似的代码，只不过每次都要做细微的修改。对于这些代码，我们可以将它们抽象成模板，保存起来，等下次要使用的时候直接调用即可。

这就是我们今天要讲的主题：**代码片段（code snippet）**。

接下来我们给大家详解如何配置和使用VSCode代码片段，分为四个部分：

1. [VSCode代码片段Tab Stop](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-tab-stop.html)
2. [VSCode代码片段占位符](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-placeholder.html)
3. [VSCode代码片段多光标](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-multi-cursor.html)
4. [VSCode代码片段预设变量](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-preset-variables.html)

代码片段是对常用代码的一个抽象，它保留了大部分不变的代码，然后把需要经常变动的部分，换成变量，这样等下次调用它的时候，只需要把这些变量换成我们需要的就可以了。

上面的这段描述，可能还是太抽象了，下面我们通过一个例子来看看代码片段究竟长什么样，以及是怎么来使用的。

首先，我们打开命令面板，搜索“**配置用户代码片段**”（Configure User Snippets）并且执行。这时候我们会看到一个列表，让我们选择语言。这里我们依然选择 JavaScript 作为我们的示例语言，不用担心，代码都是非常简单和易于理解的。

![命令面板，搜索“配置用户代码片段”并且执行](https://img.geek-docs.com/vscode/code-snippet/01.png)

命令面板，搜索“配置用户代码片段”并且执行

选择完语言后，我们就能看到一个 JSON 文件被打开了，这个文件里的内容，现在都是被注释掉的。我们可以选中第七行到第十四行，按下 `Cmd+ /` 取消注释。

![JavaScript 代码片段模版](https://img.geek-docs.com/vscode/code-snippet/02.png)

JavaScript 代码片段模版

此时，呈现在我们面前的这个 JSON 文件，就是我们今天要讲的主角：**代码片段**。

```javascript
{
"Print to console": {
"prefix": "log",
"body": [
"console.log('$1');",
"$2"
],
"description": "Log output to console"
}
}
```

JavaScript

你已经看到了，这个代码片段文件，是一个 JSON 文件，它的根对象下面的所有子节点都是一个单独的代码片段，并能够被我们调用和插入编辑器。这个代码片段对象的键（key）是这个代码片段的名字，我们在书写时只要保证这个名字跟当前文件里的其他代码片段不冲突就可以了。

在上面的例子里，这个代码片段的名字叫做 `Print to console` 。这个代码片段对象的值，也就是花括号里的代码，必须要包含 “prefix” 前缀和 “body” 内容这两个属性。同时，这个值还可以包含 “description” 描述这个属性，但这个属性不是必须的。

“prefix” 的作用是，当我们在编辑器里打出跟 “prefix” 一样的字符时，我们就能在建议列表里看到这个代码片段的选项，然后我们按下 Tab 键，就能够将这个代码片段的 “body” 里面的内容插入到编辑器里。如果这个代码片段有 “description” 这个属性的话，那么我们还能够在建议列表的快速查看窗口里看到这段 “description”。

比如现在我们可以打开一个 JavaScript 文件（还以之前的一段代码为例），然后输入 log，你就能够在建议列表里看到 `Print to console` 这个建议。

![输入 log 即可看到 Print to console 代码片段](https://img.geek-docs.com/vscode/code-snippet/03.png)

输入 log 即可看到 Print to console 代码片段

然后再按下回车或者 Tab 键，就能够将这个代码片段插入编辑器了。
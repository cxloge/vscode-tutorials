# 29_VSCode代码片段Tab_Stop

**VSCode代码片段Tab Stop**，VSCode代码片段里的“body” 里的内容，并不只是一个纯文本，它其实是一个模板。要让它像模板一样工作，我们就需要先理解一个概念，叫做 **Tab Stop** 。

------

VSCode代码片段专题包含如下内容：

1. [VSCode代码片段](https://geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-intro.html)
2. [VSCode代码片段Tab Stop](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-tab-stop.html)
3. [VSCode代码片段占位符](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-placeholder.html)
4. [VSCode代码片段多光标](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-multi-cursor.html)
5. [VSCode代码片段预设变量](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-preset-variables.html)

------

像我们现在研究的这个代码片段里，当 `body` 内容被插入到编辑器后，你会发现，内容里 的 `$1` 和 `$2` 不见了，取而代之的是两个竖线。这 `$1` 和 `$2` 就是 Tab Stop，意思是，当我们按下 Tab 键之后，光标移动到的位置。当这段代码片段被插入到编辑器后，编辑器会把光标移动到 `$1` 所在的位置，然后如果你再按一次 Tab 键，光标则会立刻移动到 `$2` 的位置。

如果没有这个功能，我们输入 log 后，只能自动地把 `console.log()` 插入到编辑器里，接下来我们需要手动地把光标移动到括号里面，然后填入我们想要打印的参数。这之后，当我们需要新起一行写代码时，还得按下 `Cmd + Enter` 创建新的一行并将光标移动到下一行。但有了 Tab Stop后，上面的这些繁琐的操作就可以简化为一次 “Tab” 键了。

在下面的动图里，我们可以看到，代码片段被插入编辑器中后，光标就被自动地放到了引号的中间；我们输入 “bar” 后，按下了 Tab 键，光标就又自动地移动到了下一行的开头，然后我们就可以继续输入代码了。

![代码片段被插入编辑器中后，光标被自动地放到了引号的中间](https://img.geek-docs.com/vscode/code-snippet/04.gif)

代码片段被插入编辑器中后，光标被自动地放到了引号的中间

将光标移动到上一个 Tab Stop 的位置的快捷键也很好记，我们只要按下 `Shift + Tab` 就可以了。

但要注意的是，Tab Stop 的作用，并不只是简单地减少重复操作，它还能够真正发挥模板的功效。

当我们插入一段常用的代码，或循环语句，或Switch 语句，虽然大部分代码都是一样，但是也有很多地方需要根据当前的上下文修改，比如说参数的名字。在这样的代码片段中，我们可以在所有需要修改的地方插入 Tab Stop，当代码片段被插入编辑器后，我们只需要通过按下 “Tab”键，就可以快速地跳到这些位置，将它们修改成我们需要的值。
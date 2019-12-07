# 32_VSCode代码片段预设变量

**VSCode代码片段预设变量**，上面我们提到了，在每个 Tab Stop 的位置，我们可以提供占位符，也就是提前预设好一些值。但这些占位符是我们提前写在代码片段里的，跟当前代码的上下文往往没什么关系。不过，VS Code 的代码片段支持里，还提供了一种模板，叫做**预设变量**。

------

VSCode代码片段专题包含如下内容：

1. [VSCode代码片段](https://geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-intro.html)
2. [VSCode代码片段Tab Stop](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-tab-stop.html)
3. [VSCode代码片段占位符](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-placeholder.html)
4. [VSCode代码片段多光标](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-multi-cursor.html)
5. [VSCode代码片段预设变量](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-preset-variables.html)

------

比如说，我们想在代码片段里的某个位置使用剪切板的内容，那么我们在那个位置写上 `$CLIPBOARD` 就好了，如果我们希望插入代码片段后自己可以修改这个值，也可以将它放在一个 Tab Stop 里面，语法则是 `${1:$CLIPBOARD}` 。

除了剪切板，VS Code 还支持其他数十个预设值，大家可以按需自行[查看文档](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_variables)，

![VSCode预设变量](image/code-snippet/08.png)

VSCode预设变量
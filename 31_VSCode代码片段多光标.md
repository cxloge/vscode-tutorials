# 31_VSCode代码片段多光标

**VSCode代码片段多光标**，在前面的文章中，我们已经知道多光标能够大幅度减少重复劳动，而在代码片段里，我们也可以使用多光标的特性。

------

VSCode代码片段专题包含如下内容：

1. [VSCode代码片段](https://geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-intro.html)
2. [VSCode代码片段Tab Stop](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-tab-stop.html)
3. [VSCode代码片段占位符](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-placeholder.html)
4. [VSCode代码片段多光标](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-multi-cursor.html)
5. [VSCode代码片段预设变量](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-preset-variables.html)

------

上面提到我们可以用 `${1:label}` 来指定 Tab Stop 和占位符，但其实我们也可以在代码片段的多个位置使用同样的 Tab Stop 。

举个例子，我们可以在代码片段中三个不同的位置插入 `$1`，这样编辑器就会为这三个不同的位置，分别创建一个光标，然后当我们打字的时候，他们就会被一起修改。

下面，我们就一起来给上面的代码片段加上多光标的特性。

```javascript
 "Print to console": {
"prefix": "log",
"body": [
"console.log(${1:i});",
"console.log(${1:i} + 1); // ${1:i} + 1",
"$2"
],
"description": "Log output to console"
}
for (var j = 0; j < 5; j++) {

}
```

JavaScript

![插入了 log 这个代码片段，然后将循环的 index 换成了 j](image/code-snippet/07.gif)

插入了 log 这个代码片段，然后将循环的 index 换成了 j。
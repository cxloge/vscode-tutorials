# 30_VSCode代码片段占位符

**VSCode代码片段占位符** ， 在我们插入 Tab Stop 的时候，除了 `$1` 、 `$2` 这样的语法，我们还可以填入 `${1:label}` ，在这个格式下，代码片段被插入编辑器里时，`$1` 的位置处，会预先填入 label这个值，并且 label 会被选中。

------

VSCode代码片段专题包含如下内容：

1. [VSCode代码片段](https://geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-intro.html)
2. [VSCode代码片段Tab Stop](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-tab-stop.html)
3. [VSCode代码片段占位符](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-placeholder.html)
4. [VSCode代码片段多光标](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-multi-cursor.html)
5. [VSCode代码片段预设变量](http://www.geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-preset-variables.html)

------

对于这个值我们称之为占位符，顾名思义，这个值是我们在代码片段中预先设置好的。如果我们觉得这个值可以用，那就不需要修改了，直接按 Tab 键跳到下一个 Tab Stop 继续编辑。如果觉得要换成一个新的值，那么也只需直接打字就可以将其替换，因为这个占位符已经被光标选中了。

这里我们对上面的代码片段进行一点修改：

```javascript
 "Print to console": {
"prefix": "log",
"body": [
"console.log(${1:i});",
"$2"
],
"description": "Log output to console"
}
```

JavaScript

我们将 `$1` 改成了 `${1:i}` ，那么当log 这个代码片段被插入时，我们将看到 `console.log(i);` ，同时 i 被选中。比如在下面的循环语句里，我们就不用更改i了。

```javascript
for (var i = 0; i < 5; i++) {

}
```

JavaScript

![插入代码片段后，无需更改占位符](image/code-snippet/05.gif)

插入代码片段后，无需更改占位符

而在接下来这个循环语句里，循环的 index 是 j，所以我们就需要将i换成 j。

```javascript
for (var j = 0; j < 5; j++) {

}
```

JavaScript

![插入代码片段后，将占位符改为 j](image/code-snippet/06.gif)

插入代码片段后，将占位符改为 j

上面我们提到了，有的时候如果占位符刚好是我们想要的，我们就不需要再做任何的修改了，我们可以按住 Tab 键，不断地跳过各个 Tab Stop，也可以直接按下 Escape 键，跳出代码片段的编辑模式，之后继续我们的其他编辑操作。
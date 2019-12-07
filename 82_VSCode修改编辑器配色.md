# 82_VSCode修改编辑器配色

**VSCode 修改编辑器配色**，除了工作区的配色，你也可以修改编辑器内代码的颜色。这个就真的强大了，因为为代码书写语法文件和配色文件，都是非常复杂的，但是在 VS Code 中，你依然有非常简单的方式去完成部分修改。

文章目录

- [1 基本类型颜色修改](https://geek-docs.com/vscode/vscode-tutorials/vscode-modify-editor-color-matching.html#i)
- [2 TextMate 规则修改](https://geek-docs.com/vscode/vscode-tutorials/vscode-modify-editor-color-matching.html#TextMate)

## 基本类型颜色修改

首先，你要做的，就是知道你想要修改的代码，是属于什么基本类型。你可以将光标移动到某段你想要修改颜色的代码上，比如将光标移动到一段字符串上，
![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-5.png)

然后，在命令面板里运行 “检查TM作用域”（Inspect TM Scopes）命令。

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-6.gif)

此时，编辑器中出现一个新的悬浮窗。这个窗口里呈现的，就是当前这个代码片段所对应的语言、语法类型以及当前的颜色和背景色等。

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-7.png)

比如在上图里，这个窗口呈现了以下信息：

- 当前的 token 是 hello，它的类型是 String；
- 它的颜色是 #ce9178ff ，背景色是 #1e1e1eff；
- 它所属的语法作用域由内而外分别是 string.quoted.double.js，meta.var.expr.js，source.js。

如果你想要将所有字符串都变成红色，那么就需要修改String这个作用域的颜色。下面，你可以再次打开个人设置（JSON），输入 editor.tokenColorCustomizations；

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-8.gif)

然后把光标放入这个 JSON 对象中，按下 “Ctrl + Space” 触发建议列表，就能够看到如下的建议。

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-9.gif)

建议列表中首先出现的，就是你可以在 VS Code 中使用的所有的主题的名字。通过选择它们，你可以只覆盖某个主题中的某个颜色。这里你可以滚动这个列表，看看下面还有别的什么建议。

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-10.png)

你可以看到如下几个选项：

- comments 代表着注释的颜色；
- functions 代表着函数的寒色；
- keywords 代表着关键字的颜色；
- numbers 代表着数字的颜色；
- strings 代表着字符串的颜色；
- types 代表着类型的颜色；
- variables 代表着变量的颜色；
- textMateRules 我下面会再介绍。

为了修改字符串的颜色，你只需选择 strings 即可，然后将其修改为红色，也就是：

```json
"editor.tokenColorCustomizations": {
        "strings": "#FF0000",
    }
```

JSON

保存设置后，你再回到刚才的 JavaScript 文件时，就可以看到字符串颜色都变了。

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-11.png)

## TextMate 规则修改

在上面的建议列表里，还有个 textMateRules选项，这个属性是做什么用的呢？让我们再来看下刚才在 JavaScript 文件里运行 “Inspect TM Scopes” 看到的信息。

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-12.png)

在这个窗口的最下方，就是 TextMate 的语法规则作用域了。hello 这个词所处的 TextMate 语法作用域**由内而外**分别是 string.quoted.double.js，meta.var.expr.js，source.js。VS Code 的主题插件在配置编辑器内代码的颜色时，就是针对这些作用域进行设置的。而你要修改某个作用域所对应的颜色，就是在设置中修改 textMateRules 。

比如说，你只想修改双引号内的字符串的颜色为红色，其他的字符串都不修改，那么就需要修改 string.quoted.double.js 这个作用域的颜色。

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-13.gif)

在上面的动图里， 你可以看到：输入引号，然后自动补全填入了 TextMate 语法设置的模板，这之后，再将 scope 的值修改成了 string.quoted.double.js 。保存设置后，当你再次打开之前的 JavaScript 文件，

![VSCode 修改编辑器配色](https://img.geek-docs.com/vscode/theme/theme-14.png)

“hello” 是红色的，但是如果你输入

```javascript
var b = 'hello'
```

JavaScript

单引号内的 hello 依然是原来的颜色。
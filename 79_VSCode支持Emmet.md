# 79_VSCode支持Emmet

**VSCode 支持Emmet**，我们介绍过[代码片段](https://geek-docs.com/vscode/vscode-tutorials/vscode-code-snippet-intro.html)（Code Snippet），你可以通过预定义代码的模板来省去重复代码的输入。但是有的时候，预定义好的模板也还是有局限性。尤其是在书写 HTML 的时候，你输入的代码，并不是 if 条件语句、for 循环语句这种常见的定式，而是根据你想要在网站上展示的效果而临时决定的 HTML 结构。换句话说，你书写的 HTML 其实反映的是业务逻辑，而这往往是无法通过代码片段来提前预测的。

Emmet 就是要解决这样的问题，为你的 HTML、CSS 书写提供类似于代码片段的输入方式，你只需输入一小段缩写，然后将其展开成最终的代码。Emmet 的语法类似于 CSS 选择器，你通过写一段接近于 CSS 选择器的代码缩写，然后使用 Emmet 引擎将它展开成复杂但完整的 HTML 或者 CSS 代码。举个最简单的例子，比如说你在 HTML 中写了 ul，然后 Emmet 就能够把它展开成下面的 HTML：

```markup
<ul></ul>
```

HTML

这样，你就不需要重复地输入 <> 尖括号，匹配开关节点等。不过这个例子还是太简单了，下面我们来看看，如何使用 CSS 选择器的语法来创造更复杂的 Emmet 缩写。

文章目录

- [1 Child: > 子节点操作符](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#Child_gt)
- [2 兄弟节点操作符 Sibling: +](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#_Sibling)
- [3 乘法操作 Multiplication: *](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#_Multiplication)
- [4 Class Name, ID](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#Class_Name_ID)
- [5 Emmet in VS Code](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#Emmet_in_VS_Code)
- 6 展开缩写
  - [6.1 建议列表](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#i-2)
  - [6.2 使用缩写包围](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#i-3)
  - [6.3 多光标](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#i-4)
  - [6.4 其他操作](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#i-5)
  - [6.5 如何在某个语言中打开 Emmet 支持](https://geek-docs.com/vscode/vscode-tutorials/vscode-emmet-support.html#_Emmet)

## Child: `>` 子节点操作符

首先是子节点操作符，通过 `>` 符号来指明节点之间的层级关系。你可以将

```markup
ul>li
```

HTML

展开为：

```markup
<ul>
  <li></li>
</ul>
```

HTML

## 兄弟节点操作符 Sibling: `+`

而如果你希望创建兄弟节点的话，则需要 `+` 操作符。比如，

```markup
div+p+bq
```

HTML

会被展开成：

```hmtl
<div></div>
<p></p>
<blockquote></blockquote>
```

Hmtl

## 乘法操作 Multiplication: `*`

除了创建单个节点以外，你还可以通过 `*` 和数字，来创建多个节点。比如，

```markup
ul>li*3
```

HTML

会被展开成：

```markup
<ui>
  <li></li>
  <li></li>
  <li></li>
</ui>
```

HTML

## Class Name, ID

另外，在书写 HTML 的时候，你不可避免地需要给节点添加属性，比如 id 和类。在 Emmet 中，它们的书写也很方便。

比如，

```markup
ul#list>li*3
```

HTML

你就可以通过 `#list` 来指定 `ul` 这个节点的 id 名。那么这个表达式会被展开为：

```markup
<ul id="list">
  <li></li>
  <li></li>
  <li></li>
</ul>
```

HTML

相信通过上面的例子，你已经看出了 Emmet 的强大之处。本质上，你可以通过类似于 CSS 选择器的语法来组织最终 HTML 文档的结构，并利用乘法、组合等操作符来执行重复的操作。

这就是 HTML、CSS 这两门语言的一个进阶版的代码片段。最后我们看下官方文档里提供的第一个例子：

```markup
#page>div.logo+ul#navigation>li*5>a{Item $}
```

HTML

这段代码里，`#` 指定了 `id`，`.logo` 指定了类的名字，`*5` ，所以，这段代码最终会被展开成：

```markup
<div id="page">
    <div class="logo"></div>
    <ul id="navigation">
        <li><a href="">Item 1</a></li>
        <li><a href="">Item 2</a></li>
        <li><a href="">Item 3</a></li>
        <li><a href="">Item 4</a></li>
        <li><a href="">Item 5</a></li>
    </ul>
</div>
```

HTML

看完上面的这些示例，你是不是十分心动，想要试一试 Emmet 这个工具呢？关于更多 Emmet 的知识，推荐你阅读官方的文档。虽然是英文的，但是还是非常好理解的。

## Emmet in VS Code

接下来，就到了我们专栏的核心内容。我们一起看看， 在VS Code 中Emmet 有哪些调用方式。

## 展开缩写

首先，在各个编辑器里，最通用的展开 Emmet 缩写的方式，就是按下 Tab 键。不过由于 VS Code 中对 Tab 键的使用非常频繁，默认并没有打开这个功能。所以，如果你要用这个功能，就需要通过 `emmet.triggerExpansionOnTab` 将这个设置打开。

修改完配置后，当你在 CSS 文件里输入 `p10`， 然后按下 `Tab` 键时，`p10` 就会被替换成 `padding: 10px;`

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-9.gif)

其次，你也可以在命令面板中搜索 “展开缩写”（Expand Abbreviation）并执行。

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-10.gif)

### 建议列表

如果你刚学习 Emmet，对 Emmet 的语法还不熟悉，那么你一定希望知道自己写的缩写，最终被展开时是什么效果。VS Code 的建议列表已经做到了这一点，当你在编辑器里书写缩写时，你能够实时地看到 Emmet 给的展开建议。

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-11.gif)

如果你不希望在建议列表中使用 Emmet 的话，也可以通过配置”emmet.showExpandedAbbreviation”: “never”来禁用。

### 使用缩写包围

缩写展开已经非常强大了，但是 Emmet 里还有一个 “使用缩写包围” 命令，它是干什么用的呢？比如说，你已经写好了一段 HTML：

```markup
<span>Hello</span>
```

HTML

然后你希望把它放到一个列表中。你当然可以先写一个 li，展开缩写，接着把上面的 HMTL 片段剪切到列表中。你也可以选中这段 HTML 片段，在命令面板中执行 “使用缩写包围”（Wrap with Abbreviation） 命令。接着，VS Code 就会显示一个输入框，你可以在这个输入框内填入 Emmet 缩写，这个缩写展开后，会自动把我们选中的 HTML 放在其中。

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-12.gif)

在上面的动图中，相信你还发现了，当你在输入框中填入 Emmet 缩写时，编辑器里会自动根据最新的缩写进行更新，这样你就能够实时地预览 Emmet 缩写被展开后的效果了。

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-13.gif)

### 多光标

Emmet 操作同样也支持多光标，如果你创建了多个光标，你可以同时在它们上面执行 “使用缩写包围” 命令。

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-14.gif)

### 其他操作

除了能够展开 Emmet 缩写，Emmet 工具还提供了几个 HTML 的快捷命令。

第一个就是在 open 节点和 close 节点之间进行跳转，命令是 “Emmet: 转制匹配对”。

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-15.gif)

第二个就是删除节点。在 HTML 中删除 HTML 节点最麻烦的就是你需要把开、关两个节点都删除掉，否则 HTML 结构就不完整了。通过命令 “Emmet：移除标签”，你就可以同时将开、关两个节点都删除掉。

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-16.gif)

你还可以通过 “Emmet：更新标签“来同时更新一对开关节点（open/close tag）。

![VSCode 支持Emmet](https://img.geek-docs.com/vscode/language/css-emmet-17.gif)

这些命令是不是在 HTML 编辑器时非常实用呢？

### 如何在某个语言中打开 Emmet 支持

默认情况下，你可以直接在 html、haml、jade、slim、jsx、xml、xsl、css、scss、sass、less、stylus、handlebars、php 和 javascriptreact 中使用 Emmet 。但对于其他语言，你也可以通过如下的设置来将其打开。

```json
"emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "vue-html": "html",
    "razor": "html",
    "plaintext": "jade"
}
```

JSON

这段设置的要点就是，将某个 Emmet 默认不支持的语言，映射到一个 Emmet 支持的语言上。比如上面的设置里，我们把 vue-html 映射成了 html，那么当你在 vue-html 使用 Emmet 时，Emmet 就会把它当作 html 来处理了。
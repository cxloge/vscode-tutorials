# 78_VSCode支持CSS

**VSCode 支持CSS**，介绍两个比较实用的功能：取色器 Color Picker和CSS 选择器的预览。

文章目录

- [1 取色器 Color Picker](https://geek-docs.com/vscode/vscode-tutorials/vscode-support-css.html#_Color_Picker)
- [2 CSS 选择器的预览](https://geek-docs.com/vscode/vscode-tutorials/vscode-support-css.html#CSS)

## 取色器 Color Picker

首先，你可以在书写 HTML 和 CSS 时使用取色器。

在书写 HTML 和 CSS 的时候，你可能经常需要修改元素的颜色。VS Code 为修改颜色，提供了一个图形化的界面，其中包含了颜色相关的属性。

当你打开一段 HTML 或者 CSS 代码时，你可以看到，VS Code 在颜色的前面画了一个方块（我们称作**颜色装饰器 Color Decorator**），用于展示这段颜色属性所对应的最终效果。

![VSCode 支持CSS](https://img.geek-docs.com/vscode/language/css-emmet-1.png)

同时，当你把鼠标移动到这段代码上时，一个**颜色选择器**窗口就显示出来了。

![VSCode 支持CSS](https://img.geek-docs.com/vscode/language/css-emmet-2.png)

这个窗口包括了**五个主要的部件**。首先，就是左下角最大的那个长方体，你可以通过在其中移动光标来调整颜色的饱和度（Saturation）。

![VSCode 支持CSS](https://img.geek-docs.com/vscode/language/css-emmet-3.gif)

其次，在窗口的右侧，还有两个竖条，对应两个部件。左边的竖条是用于调整透明度（opacity）。

![VSCode 支持CSS](https://img.geek-docs.com/vscode/language/css-emmet-4.gif)

右边的那个则是用于调整色相（hue）。

![VSCode 支持CSS](https://img.geek-docs.com/vscode/language/css-emmet-5.gif)

最后，在取色器的最上方，也有两个部件。

左侧的部件上，显示了当前颜色对应的代码。当你点击这个部件时，你可以选择不同的书写这个颜色的方式。比如对于颜色 RGB(0,0,0) ，在 CSS 里你也可以写成 `#000`，这样你就可以通过点击这个部件进行切换。

![VSCode 支持CSS](https://img.geek-docs.com/vscode/language/css-emmet-6.gif)

右侧的部件，则是用于在取色器里修改颜色时，回退到之前的值。

![VSCode 支持CSS](https://img.geek-docs.com/vscode/language/css-emmet-7.gif)

除了在 HTML 和 CSS 中使用取色器以外，你还可以在任何需要书写颜色的代码里使用，只要这个语言插件实现了相应的 API。

## CSS 选择器的预览

第二个非常实用的功能是CSS 选择器的预览。

比如，当你书写了一段 CSS 选择器后，有的时候会发现这段 CSS 没有生效。这可能是因为你的 HTML 结构有问题，从而导致这个 CSS 选择器不能生效。

为了解决这个问题，VS Code 的 CSS 预览（Hover）里提供了一段 HTML 代码片段，这个代码片段则可以让这个 CSS 选择器生效。

![VSCode 支持CSS](https://img.geek-docs.com/vscode/language/css-emmet-8.gif)

虽然上面这两个技巧非常实用，但是它们还是不够强大。要说到 VS Code 里书写 HTML 和 CSS最厉害的地方，那就属于 Emmet 支持了。那什么是 Emmet 呢？
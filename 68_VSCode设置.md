# 68_VSCode设置

**VSCode 设置**，VS Code 是以文件和文件夹为核心的，用户的设置、快捷键绑定等，也都是以文件的形式存储在用户的机器上。同时，VS Code 把这一切都开放给用户，也就是说你可以直接对这些文件进行修改。

相信你已经尝试过了修改代码片段（Code Snippet）配置、修改快捷键绑定以及修改个人设置等操作。不过还有些操作我还没有做过介绍。

文章目录

- [1 设置的文本界面](https://geek-docs.com/vscode/vscode-tutorials/vscode-settings.html#i)
- [2 设置的图形界面](https://geek-docs.com/vscode/vscode-tutorials/vscode-settings.html#i-2)
- [3 工作区支持](https://geek-docs.com/vscode/vscode-tutorials/vscode-settings.html#i-3)

## 设置的文本界面

VS Code 的最新稳定版里，有两个不同的设置编辑器。下面，让我们先打开命令面板，搜索 “打开设置(JSON)”`[Open Settings(JSON)]`，然后执行。

![VSCode 设置 - 文本界面](https://img.geek-docs.com/vscode/setting/setting-1.gif)

此时，我们能看到并排的两个编辑器。

![VSCode 设置 - 文本界面](https://img.geek-docs.com/vscode/setting/setting-2.png)

编辑器左侧是 VS Code 支持的各种设置；而右侧，则是我们非常熟悉的 JSON 文本。而且在整个界面的最上方，还有一个输入框，以供我们搜索设置。

VS Code 早期修改设置的方式有两种。第一种就是在左侧找到设置，然后“复制粘贴”到右侧。第二种是直接在右侧修改，VS Code 为右侧的编辑器提供了自动补全功能。

![VSCode 设置 - 文本界面](https://img.geek-docs.com/vscode/setting/setting-3.gif)

在上面的动图中你能看到，我通过输入 fontsize，依靠自动补全找到了 editor.fontSize 这个设置，然后输入到文件中，保存后编辑器的字体大小很快发生了改变。所以通过修改这个设置文件，我们就能够第一时间看到修改设置后的变化。

当然，我们也可以直接在搜索框里输入设置的名称，找到对应设置后，将鼠标移动到行号附近；这时候我们能看到一个铅笔形状的图标，点击它，就能够看到这个设置允许的值有哪些；选择好我们想要的那个配置后，这个设置就会被自动写到右侧的 JSON 文件里。

![VSCode 设置 - 文本界面](https://img.geek-docs.com/vscode/setting/setting-4.gif)

说到设置的搜索，其实最初 VS Code 只会进行单词的模糊匹配，也就是说如果你不小心打错字了，VS Code 就找不到合适的设置了。不过，很快 VS Code 就为这个搜索增加了自然语言的处理。还是使用上面的例子，当我想修改字体的大小时，我可以在搜索框里输入 how to set editor font size。即便我不小心把 font size 打错成了 fontize ，VS Code 也能找到正确的设置项。

![VSCode 设置 - 文本界面](https://img.geek-docs.com/vscode/setting/setting-5.gif)

虽然VS Code有很不错的搜索和自动补全，但是我刚使用它的时候，还是挺不适应的。不过这属于 VS Code 设置思路的一部分，就是把细节暴露给用户，让用户也知道设置是如何存储的、格式是怎样的，等等。像我自己在习惯这套搜索方式后，再跑到某些默认打开就是图形化设置界面的编辑器时，反而有点手足无措，我会纠结该如何才能找到我想要的设置。

当然，做产品不能固步自封。对于陪伴 VS Code 一路走来的用户而言，他们已经非常熟悉和习惯这套理念和操作方式了。可是对于新用户而言，VS Code 基于文本的设置方式，之于他们反而成为了一个障碍。很多新用户会觉得，“我不过是想改一个字体大小，为什么 VS Code 要给我打开两个并排的编辑器，甚至有的时候还需要我自己去修改设置文件？”

## 设置的图形界面

**VSCode 设置 – 图形化界面**，VS Code 在最近的几个版本里添加了一个图形化界面。我们可以在命令面板搜索 “打开设置(UI)”并执行。

![VSCode 设置 - 图形化界面](https://img.geek-docs.com/vscode/setting/setting-6.gif)

使用这样的图形化界面进行设置修改，好处当然也是很明显的：它能尽可能地减少修改配置的难度，并减少我们犯错的可能。

这里值得注意的是，图形化设置界面是在自然语言搜索之后才出现的，也就是说，虽然我们现在面对的是下拉框、复选框之类的，但我们依然能够使用跟前面一样强大的搜索功能。

## 工作区支持

在上面的操作截图里，我们可以看到VS Code 的窗口里并没有打开任何的文件夹。而如果我们打开了一个文件夹，而且这个文件夹下有 `.vscode/settings.json` 文件的话，此时我们再打开设置界面，则能够看到一些变化。

比如在基于文本的设置界面里，我们可以在右侧的 JSON 编辑器里看到 “用户设置”和“工作区设置”两个选项。如果我们修改工作区设置的话，它会立刻被保存到 `.vscode/settings.json` 里。

![VSCode 设置 - 图形化界面](https://img.geek-docs.com/vscode/setting/setting-7.png)

而在图形化设置界面里，我们也同样可以在搜索框下进行个人和工作区设置的选择。

![VSCode 设置 - 图形化界面](https://img.geek-docs.com/vscode/setting/setting-8.png)
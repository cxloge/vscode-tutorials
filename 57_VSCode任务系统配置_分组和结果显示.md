# 57_VSCode任务系统配置_分组和结果显示

**VSCode 任务系统配置 – 分组和结果显示**，来学习一下任务系统配置里的其他属性。在下面的任务里，我们能够看到 “label”“type”“command” 这几个熟悉的属性，它们的意思是，在 shell 下运行 `./scripts/test.sh` 这个脚本。不过又多了三个属性 “group” “presentation” 和 “options”，它们分别是干什么的呢？

```json
{
 "version": "2.0.0",
 "tasks": [
  {
   "label": "test shell",
   "type": "shell",
   "command": "./scripts/test.sh",
   "windows": {
    "command": ".\\scripts\\test.cmd"
   },
   "group": "test",
   "presentation": {
    "reveal": "always",
    "panel": "new"
   },
   "options": {
    "cwd": "",
    "env": {},
    "shell": {
     "executable": "bash"
    }
   }
  }
 ]
}
```

JSON

**“group” 属性就是分组**，我们可以通过这个属性指定这个任务被包含在哪一种分组当中。关于分组，我们有三种选择：“build” 编译生成、“test”测试和 “none”。

在这个例子里，我们把它设置为了 “test”。那么，当我们在命令面板里搜索 “运行测试任务” (Run Test Task) 时，只有这个任务会被显示出来。

![VSCode 任务系统配置 - 分组和结果显示](https://img.geek-docs.com/vscode/task-system/workflow-01-10.gif)

如果我们把这个分组 group 改为 “build”，那么在我们执行 “运行生成任务” （Run Build Task）时，则同样能够看到它。

分组的意思很好理解，但是你可能感觉还是不够意思，因为虽然有专门的命令去执行生成任务，或者测试任务，但是它们还是调出了一个列表让我们进行选择，多此一举，有没有办法一键运行？

当然没问题，我们只需将分组 “group” 的值改成下面这样即可。“isDefault” 代表着这条任务是不是这个分组中的默认任务，“kind” 则是代表分组。

```json
"group": {
    "isDefault": true,
    "kind": "test"
   },
```

JSON

当把“group”改成以上的值后，再当我们执行 “运行测试任务” (Run Test Task) 命令时，我们会发现这条测试任务被直接执行了。

![VSCode 任务系统配置 - 分组和结果显示](https://img.geek-docs.com/vscode/task-system/workflow-01-11.gif)

而 “运行生成任务” 就更方便了，这个命令已经绑定了一组快捷键。我们只需按下 `Cmd + Shift + B` （Windows 上是 `Ctrl + Shift + B`）就可以自动运行默认的那个生成任务了（build task）。

接下里的两个属性：`presentation` 是用于控制任务运行的时候，是否要自动调出运行的界面，让我们看到结果，或者是否要新创建一个窗口执行任务；而 `options` 则是用于控制任务执行时候的几个配置，比如控制任务脚本运行的文件夹地址 `cwd`，控制环境变量 `env`，或者控制任务脚本运行的时候使用哪个 shell 环境。

你可以看到，在上面的例子里，我把 shell 环境指定为了 bash，那么这个脚本运行的时候，虽然还是使用的集成终端，但是它会使用 bash 而不是 zsh 来运行这个脚本。
---
title: Python 的安装、配置与卸载
comment: giscus
math: true
hide: false
date: 2023-04-10 21:13:47
updated: 2023-04-10 21:15:40
excerpt: 简单记录一下 Python 的安装、配置与卸载
categories:
tags:
index_img:
banner_img:
sticky:
---


### 下载

下载地址: [https://www.python.org/downloads/](https://www.python.org/downloads/).

根据个人需求下载  Windows, Linux/UNIX, macOS, Other 等等不同平台、不同版本、安装版或是稳定版的 python 安装包。然后根据程序指示进行操作，或是将解压内容放在合适的位置。

#### 配置环境变量

{% note danger %}
**To Be Continued:**

还没写完涅。
{% endnote %}

假装直接安装 Anaconda 一步到位。

### VS code + python

#### 下载安装 vscode
**Visual Studio Code** 下载地址：[Visual Studio Code | Download](https://code.visualstudio.com/Download).

一般选择的都是 `Windows` + `User Installer` + `x64`，选择 `Windows` 下面 `User Installer` 后面的 `x64` 点一下就开始下载。

后面安装看界面就行，按步骤安装。


#### 扩展

主要下载的是用于 python 的扩展和汉化扩展。

扩展下载位置是 vscode 左边应该是第四个图标 —— 有四个正方形，三个挨在一起，第四个在右上角的图标，那就是扩展管理的地方。

安装下述扩展的话，就，直接先搜索，然后找到名称对应的点击`安装`，即可进行安装。

需要安装的扩展：

+ Chinese (Simplified) (简体中文) Language Pack for Visual Studio Code
+ Python

安装完上述的扩展，那就行了。

#### 配置

现在配置 vscode 让其可以轻易编辑 python 代码并执行。

我直接按照 vscode 官方文档的步骤开始操作。

首先，打开你的`终端`，执行命令：

```bash
mkdir hello
cd hello
code .
```

意思为创建 hello 文件夹，进入 hello 的路径，并使用 vscode 打开 hello 文件夹。

##### 创建虚拟环境

文档上说，Python 开发人员最佳实践是使用特殊的项目 - 即使用**虚拟环境**。

激活该环境后，随后安装的任何软件包都将与其他环境（包括全局解释器环境）隔离，从而减少了软件包版本冲突可能带来的许多复杂性。

可以使用 `Venv` 在 VS Code 中创建非全局虚拟环境。

然后就是打开命令面板 （Ctrl+Shift+P），开始键入要搜索的“Python： 创建环境”命令，然后选择该命令。

再选择下面中含有 Venv 字样的一行。

接下来就是选择 Python 解释器：随便选择下面中的一个就行。

稍微等一会，虚拟环境就创建成功了，具体进度可以看看 vscode 右下角的的提示窗口，直到出现文字：已选择以下环境~，等等。

此时可以看见左边的资源管理器中出现了一个名为 `.venv` 的文件夹，如果没看到资源管理器，那就按快捷键：`Ctrl + Shift + E`。

##### 创建 py 文件

现在就可以开始创建 py 文件，并编辑 py 文件了。

尽你所能在左边的资源管理器创建一个文件，名为：`hello.py`。

然后你就可以开始编辑 `hello.py` 文件，如果知道在哪里编辑的话，不知道就算了。

编辑的内容，如下：

```python
msg = "Hello World, Hello Python."
print(msg)
```

可以直接复制，也可以自己敲。完成后，按 `Ctrl + S` 保存。

接下来就是运行了，现在 vscode 又好了很多，它在右上角有个图标，像是播放器的播放图标一样的三角形，点击一下就可以运行了。此时你就发现 vscode 下方出现了终端窗口，并且还出现了字样：`Hello World, Hello Python.`。 那就说明运行成功了。

也可以在编辑界面中鼠标右键，选择下面的 `运行 Python`，再选择 `在终端中运行 Python 文件`。

同样可以出现上述结果。

##### 配置调试器

一般来说，编辑代码还是需要调试的，所谓调试，就是 py 文件中设置一个断点，当我们以调试模式运行 py 文件时，运行到设置断点位置的代码时，就会暂停，方便我们查看程序后续的执行情况 —— 即和数据的变化情况，查看是否符合我们想编辑出的代码的预期结果。

如何设置断点呢：就在代码那行左边的数字的左边位置点一下，就会出现一个**红点**，出现红点后，就说明我们在这个位置设置了一个断点。

如何以调试模式运行呢：按 `F5`，或是 vscode 左上角点击`运行`，选择`启动调试`。（按 F5 没有效果的话，试试按键盘中的 Fn + F5，有些笔记本需要这样，因为设置了 Fn 功能按键）

此时，出现选择项 —— `选择调试配置`，直接选择第一个 —— `Python 文件`。

不出意外的话，就会发现，界面发生了变化：

+ 左边资源管理器位置变成了变量
+ 编辑界面上方出现了几个按钮 —— 分别表示 —— 继续执行、逐过程执行、单步调试、单步跳出、重启（重新启动调试）、停止。
    + 继续执行：讲剩下的代码执行完
    + 逐过程执行：将过程视为一个基本单位来执行，执行完一个语句后再继续执行下一个语句
    + 单步调试：一次执行一个语句
    + 单步跳出：跳出函数内部
+ 还有就是，最下面的一行变了颜色

我们还可使用 `调试控制台` 使用变量（调试控制台的位置在下面位置，有着调试控制台的文字，点一下就行）：

##### 安装和使用包（packages）

安装包呢，在下方的终端执行：`py -m pip install <package name>`，将 `<package name>` 替换为想要安装的包，如安装 `numpy`：`py -m pip install numpy`。

这是在虚拟环境下安装包。

使用呢就是：`import numpy as np`，意为，导入名为 `numpy` 的包，并将其命名为 `np` —— 即，下文中，可以使用 `ny` 代指 `numpy` 进行使用。

```python
import numpy as np

msg = "Roll a dice"
print(msg)

print(np.random.randint(1,9))
```

执行结果：

```bash
Roll a dice
2
```
OK。

##### 暂告一段落

到现在呢，咱们就可以在 vscode 上面编辑并运行简单的 python 代码了。

再说一下步骤：

1. 使用 vscode 打开文件夹作为工作区
2. 创建 python 的虚拟环境
3. 创建 py 文件或者复制文件过来
4. 如果使用 import 导入某些包时，就需要进行安装，使用命令：`py -m pip install <package name>`
5. 运行或者调试

大致就是这样了。

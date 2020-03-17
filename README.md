# 项目进度



## 二、扩展计算交点功能（by 何瑞）

### 项目要求（Undo）

- 对新增功能涉及到的函数进行单元测试。（Undo）
- 回归测试所有以前的功能，保证以前的功能还能继续工作。(Undo)
- 在完成这一阶段的任务之后，使用 `git tag step1` 标记，并在 push 到Github 上时使用 `--tags` 参数把 tag 也推送到 Github，例如`git push origin --tags`。(undo)

### 博客要求

- 详细介绍新增功能的实现。
- 选择部分单元测试代码发布在博客中，并说明测试的函数，构造测试数据的思路。
- 将单元测试得到的测试覆盖率截图，发表在博客中。要求总体覆盖率到 90% 以上，否则单元测试部分视作无效。







## 三、将扩展后的功能封装为独立模块(by 何瑞)

### 项目要求（undo）

- 以需要支持接入 GUI 模块为前提，自行设计求解几何对象交点的接口集合。

- 对设计的接口进行测试。(Undo)

- 保持命令行程序在封装完成后仍然可用。(Done)

- 在完成这一阶段的任务之后，使用 `git tag step2` 标记，并在 push 到 Github 上时使用 `--tags` 参数把 tag 也推送到 Github。

  

### 博客要求

- 看 Design by Contract，Code Contract 的内容，描述这些做法的优缺点，说明你是如何把它们融入结对作业中的。
- 看教科书和其它资料中关于 Information Hiding，Interface Design，Loose Coupling 的章节，说明你们在结对编程中是如何利用这些方法对接口进行设计的。
- 详细说明所设计的接口，并阐明设计的理由。
- 选择部分测试代码发布在博客中，并说明测试的函数，构造测试数据的思路。









## 四、支持异常处理（by 叶志翔（UI部分），何瑞（文件读取部分））

在扩展核心功能一节中，题目对输入的格式与范围进行了限定，可认为是合法输入。错误处理的目标是区别合法输入和非法输入，同时对非法输入进行一定的提示以帮助用户改正。

**在本节中，需要考虑的输入为以大小写字母，数字，空格，`-`，`\n` 组成的文本。**

### 项目要求（undo）

- 设计好异常的种类与错误提示，例如让程序支持“坐标范围超限”，“直线定义中两点重合”或“有无穷多交点”异常。
- 在 core 模块中实现抛出异常的功能，并撰写测试用例：传进去一个非法输入，期望能捕获一个特定异常。如果没有，测试就报错。
- 回归测试所有以前的功能，保证以前的功能还能继续工作。
- 在完成这一阶段的任务之后，使用 `git tag step3` 标记，并在 push 到 Github 上时使用 `--tags` 参数把 tag 也推送到 Github。

### 博客要求

- 在博客中详细介绍对哪些异常进行了处理以及每种异常的设计目标。
- 每种异常都要选择一个单元测试样例发布在博客中，并指明错误对应的场景





## 五、添加界面模块（叶志翔，何瑞）

### 项目要求

- 新建一个工程，把 core 核心模块作为一个 DLL（动态链接库）引用在新工程中。
- 开发一个 UI 模块，实现如下需求： 
  1. 支持从文件导入几何对象的描述。（undo）
  2. 支持几何对象的添加、删除。 （undo）
  3. 支持绘制现有几何对象。 （Undo）
  4. 支持求解现有几何对象交点并绘制。（undo）
- 将 UI 模块与 core 模块对接。（undo）
- 在完成这一阶段的任务之后，使用 `git tag step4` 标记，并在 push 到 Github 上时使用 `--tags` 参数把 tag 也推送到 Github。（undo）

### 博客要求

详细地描述 UI 模块的设计与两个模块的对接，并在博客中截图实现的功能。







## 六、界面模块，测试模块和核心模块的松耦合【附加题】（待定）

在前面的工作中，每个小组都使用了命令行，保证了程序的正确性，同时在此基础上绘制了 GUI  界面。既然各组同学都写了高质量的各个模块，而且模块之间的关系是明确定义的，一致的，那么，小组 A 的测试模块就可以测试小组 B 的核心模块；小组 C 的用户界面模块就可以和小组 B 的核心模块结合起来，正常运行。

那么现在，请你（假设为 A）寻找另外一个小组（假设为 B），与他们交换核心模块与界面模块，并测试一下下面的情况：

- A 的核心模块，加上 B 的测试模块和用户界面模块（命令行和 GUI）
- B 的核心模块，加上 A 的测试模块和用户界面模块（命令行和 GUI）

### 项目要求（undo）

根据与合作小组对接过程中出现的问题，寻找并改进模块中的 bug。这部分修改需要另开一个新的分支 `dev-combine`，并 push 到 Github上。

### 博客要求

在博客中指明合作小组两位同学的学号，截图展示互换后的运行结果和测试结果。此外，博客中还需分析两组不同的模块合并之后出现的问题，为何会出现这样的问题，以及是如何根据反馈改进自己模块的。

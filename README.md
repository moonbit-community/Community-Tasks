# PLCT 实验室-MoonBit-J139-可做任务清单

该清单为 PLCT 实验室 J139 MoonBit 软件开发实习生的可做任务清单、技术栈要求及对应的参考资料。

大家可以在群里说或者发 PR 来认领任务，任务的参与人数是不限的，但是要保证你们合作的成员之间有足够的沟通和交流。

## MoonBit Core 社区贡献

Publisher: @Lampese

Assignment: -

### 任务内容

MoonBit Core 是 MoonBit 目前的标准库，在它的 Issues 中有许多标着 Good First Issue 这样 Label 的 Issue，它的意思是鼓励参与社区贡献的新人参与的，和其他部分耦合程度不高，比较容易完成的任务。

我们可以选择其中自己可以完成的部分去完成，通过提交 Pull Request 来参与贡献。

### 要求

需要一定的社区沟通能力和进阶的 Git 操作能力

### 参考资料
- MoonBit Core: https://github.com/moonbitlang/core

## XML/YAML Parser

Publisher: @Lampese

Assignment(XML): -

Assignment(YAML): -

### 任务内容

XML (Extensible Markup Language) 与 YAML (YAML Aint Markup Language) 均为现在市面上较为常用的标记语言 (虽然 YAML 说他们重心不在这里)，前者被广泛用于信息传递，而后者广泛用于配置文件的编写。而编写他们的 Parser (即完成从 Text -> MoonBit enum) 是十分有意义的工作。

另外，JSON (JavaScript Object Notation) 是一种数据交换格式，MoonBit 的标准库 Core 中已经编写了其 Parser，用于 JSON 文本的解析。

### 要求

需要一定的学习技能和资料查询能力

### 任务预期

初步编写 XML 或 YAML 的解析器并存在放某个仓库中，可以优先学习和尝试 Parser-Combinator 的方法来体验 Functional-Programming 的乐趣 :)，但是不用它也可以，最后编写相关测试确保解析库运行正常。

项目完善后可以向 moonbitlang/x 提出 PR 并且合并该功能进入存储库，作为 MoonBit 标准库拓展的一部分。

### 额外任务

MoonBit 官方提供了一个属性测试框架 moonbitlang/quickcheck，对于测试 Parser 类的软件非常有用，可以自己学习并且用它来测试我们写的 Parser。

也可以考虑不止支持从 String 中进行解析而是从 Iter[Char] 中解析来获得更高的性能。

### 参考资料

这部分资料明显不全，希望大家可以自己发挥自己的能力运用搜索引擎和 AI 查找编写 Parser 的方法等等。

- XML: https://zh.wikipedia.org/wiki/XML
- YAML: https://zh.wikipedia.org/wiki/YAML
- MoonBit Core 中的 JSON Parser: https://github.com/moonbitlang/core/tree/main/json
- MoonBit 社区的 Parser Combinator: https://mooncakes.io/docs/#/peter-jerry-ye/parser-combinator/
- MoonBit X: https://github.com/moonbitlang/x
- MoonBit Quickcheck: https://github.com/moonbitlang/quickcheck
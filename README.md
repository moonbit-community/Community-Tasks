# PLCT 实验室-MoonBit-J139-可做任务清单

该清单为 中科院软件所 PLCT 实验室甲辰计划 J139 MoonBit 软件开发实习生岗位的可做任务清单、技术栈要求及对应的参考资料。

大家可以在群里和我说或者发 PR 来认领任务，任务的参与人数是不限的，但是要保证你们合作的成员之间有足够的沟通和交流。

也欢迎各位 MoonBit 社区成员和实习生来这里发布自己的需求和任务！(就是不保证会做就是了哈哈哈)

而且在有 Assignment 之后也可以给对应的产出仓库发 pr，因为它们不一定做完了所有要求或者额外任务。

[目前我们岗位还很缺人！很缺人！很缺人！欢迎在校生来投递简历！](https://github.com/plctlab/weloveinterns/blob/master/open-internships.md#j139-moonbit-%E5%BA%94%E7%94%A8%E5%BC%80%E5%8F%91%E5%AE%9E%E4%B9%A0%E7%94%9F20241104%E5%BC%80%E6%94%BE100%E5%90%8D)

## MoonBit Core 社区贡献

- Publisher: @Lampese

- Assignment: -

#### 任务内容

MoonBit Core 是 MoonBit 目前的标准库，在它的 Issues 中有许多标着 Good First Issue 这样 Label 的 Issue，它的意思是鼓励参与社区贡献的新人参与的，和其他部分耦合程度不高，比较容易完成的任务。

我们可以选择其中自己可以完成的部分去完成，通过提交 Pull Request 来参与贡献。

#### 要求

需要一定的社区沟通能力和进阶的 Git 操作能力。

#### 参考资料
- MoonBit Core: https://github.com/moonbitlang/core

## XML/YAML Parser

- Publisher: @Lampese
- Assignment(XML): @RuifengFu
- Assignment(YAML): @E-M-T-F

#### 任务内容

XML (Extensible Markup Language) 与 YAML (YAML Aint Markup Language) 均为现在市面上较为常用的标记语言 (虽然 YAML 说他们重心不在这里)，前者被广泛用于信息传递，而后者广泛用于配置文件的编写。而编写他们的 Parser (即完成从 Text -> MoonBit enum) 是十分有意义的工作。

另外，JSON (JavaScript Object Notation) 是一种数据交换格式，MoonBit 的标准库 Core 中已经编写了其 Parser，用于 JSON 文本的解析。

#### 要求

需要一定的学习技能和资料查询能力。

#### 任务预期

初步编写 XML 或 YAML 的解析器并存在放某个仓库中，可以优先学习和尝试 Parser-Combinator 的方法来体验 Functional-Programming 的乐趣 :)，但是不用它也可以，最后编写相关测试确保解析库运行正常。

项目完善后可以向 moonbitlang/x 提出 PR 并且合并该功能进入存储库，作为 MoonBit 标准库拓展的一部分。

#### 额外任务

MoonBit 官方提供了一个属性测试框架 moonbitlang/quickcheck，对于测试 Parser 类的软件非常有用，可以自己学习并且用它来测试我们写的 Parser。

也可以考虑不止支持从 String 中进行解析而是从 Iter[Char] 中解析来获得更高的性能。

#### 参考资料

这部分资料明显不全，希望大家可以自己发挥自己的能力运用搜索引擎和 AI 查找编写 Parser 的方法等等。

- XML: https://zh.wikipedia.org/wiki/XML
- YAML: https://zh.wikipedia.org/wiki/YAML
- MoonBit Core 中的 JSON Parser: https://github.com/moonbitlang/core/tree/main/json
- MoonBit 社区的 Parser Combinator: https://mooncakes.io/docs/#/peter-jerry-ye/parser-combinator/
- MoonBit X: https://github.com/moonbitlang/x
- MoonBit Quickcheck: https://github.com/moonbitlang/quickcheck

#### 产出
xml: https://github.com/RuifengFu/XMLParser

## libtorch 的 MoonBit 绑定

- Publisher: @Lampese @tonyfettes
- Assignment: @liuly0322

#### 产出

WIP，欢迎尝试/issue/PR！

tch-mbt: <https://github.com/liuly0322/tch-mbt>

#### 任务内容

libtorch 是 pytorch 的 C++ 版本，支持 CPU 端和 GPU 端的部署和训练，发行方式为 dll 或者 so，在 C++ 上可以非常简单的使用。

当前 MoonBit 在计算需求上需要在 Native 后端上增加一个 libtorch 的绑定，让 MoonBit 代码编译为 Native 代码之后也可以调用 libtorch，这可能还会帮助 torch.mbt 的进一步开发。

#### 要求

需要一定的 C 编程能力，对 pytorch 或者 libtorch 的 API 比较熟悉。

#### 任务预期

用 C 配合 MoonBit 编写出 libtorch 的 MoonBit Bindings，并且发布到 mooncakes。

可以先支持某个系统(如 Windows 或 Linux)的某个计算平台(如 CUDA 或 CPU 甚至 ROC)，然后再编写另一个平台的 bindings。

#### 额外任务

可以尝试使用自己辨析的 libtorch 库复现一些十分简单的论文和 torch 的需求。

#### 参考资料

- MoonBit Native FFI 的方法: https://github.com/moonbitlang/x/tree/main/fs/internal/ffi
- MoonBit Native Headers (在下载的压缩包中): https://www.moonbitlang.com/download/
- libtorch: https://pytorch.org/

## MoonBit 字符串格式化库

- Publisher: @Lampese
- Assignment: @kesmeey

#### 任务内容

很多编程语言都有一个输出流函数叫做 prinf，它的意思是 print with format，也就是按照某种格式输出，比如我们在 C/C++ 中想要输出一个保留三位小数的 double 类型变量，我只需要这样做：

```cpp
double xunyoyo = 1114514.19190810;
printf("%.3lf", xunyoyo);
```

也有其他语言提供了更加泛化的思路，他们提供了一个单独的 fmt 库（比如 Go，虽然它们也做了 fmt.Printf），你可以用 fmt 来格式化字符串并输出。

我们的任务就是做出这样一个库，来更加方便字符串的格式化输出。

#### 要求

需要一定的学习技能和资料查询能力。

#### 任务预期

编写一个 MoonBit 的 fmt 库并发布在 mooncakes 上。

Formatter 的格式模仿 C/Cpp 或者其他语言均可，可以在 API 设计上下功夫，看看如何设计更加合理。

该库完全有机会加入 moonbitlang/x 甚至 moonbitlang/core。

#### 额外任务

我 (Lampese) 之前写过一个把字符串加上终端格式或者字体样式的库 moonbit-chalk，可以把它拿过来用并且给 fmt 加一个颜色/格式语法。

#### 参考资料

- C/C++ printf: https://en.cppreference.com/w/c/io/fprintf
- Go fmt：https://pkg.go.dev/fmt
- moonbit-chalk: https://github.com/Lampese/moonbit-chalk

#### 产出

https://github.com/kesmeey/fmt

## MoonBit Path 路径处理库

- Publisher: @Lampese

- Assignment: @xunyoyo @kesmeey @CMoonBack

#### 任务内容

在各种各样语言的标准库中 Path 仓库经常是一个不可或缺的存在，它们是一种路径的抽象，可以对路径之间进行拼接或者安全的 back 和 forward 操作。

注意所有在此之中的过程都应该是纯函数，而不应该涉及系统 IO。

 该需求的仓库完全有需求合入 moonbitlang/x。

#### 要求

（可能）需要对不同平台的路径有一定了解，包括对转义和他们之间的差异。（其实接到任务之后开始学习也可以的）

#### 参考资料
- Rust std::path(推荐): https://doc.rust-lang.org/std/path/struct.Path.html
- Nodejs path module: https://nodejs.org/docs/latest/api/path.html
- Python pathlib: https://docs.python.org/3/library/pathlib.html

## calculus-numerical 微积分数值求解库

- Publisher: @Lampese @KCN-judu
- Assignment(Doc): -
- Assignment(Complex): -
- Assignment(Linear Algebra): -
- Assignment(Numerical Integration): -
- Assignment(ODE solver): -

#### 任务内容

这是一个使用[**MoonBit**](https://www.moonbitlang.cn/)编写的微积分数值求解库，旨在填补MoonBit生态在科学计算领域的空白。

库内实现了常见的微积分操作，包括但不限于数值积分、微分等。通过提供多种数值解法和高效的算法实现，本库可以应用于科学计算、工程模拟、数据分析等多个领域。

参与贡献的方法详见 README.md的 **How to Contribute（如何参与贡献）** 章节

详细任务内容参考[TODO.md](https://github.com/moonbit-community/calculus-numerical/blob/main/TODO.md)

#### 要求

需要一定的学习技能和资料查询能力。

目前阶段有多个方向可供选择，只需要擅长至少一个即可（如果愿意接到任务开始学习也很欢迎）：

- 文档编写
- 复数运算
- 线性代数
- 数值积分
- 微分方程求解
- 多项式
- 泰勒展开

#### 参考资料

主要参考对象是[GNU Scientific Library](https://www.gnu.org/software/gsl/#development)

这是[GSL的仓库](https://savannah.gnu.org/git/?group=gsl)

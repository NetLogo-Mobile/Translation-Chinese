*** Machine Translated
`breed`是一个特殊的关键字，只能放在netlogo代码选项卡的顶部。使用`breed` ，你可以自定义各种或龟的*品种*。当您有不同的海龟组，每个海龟组需要各自的行为，并且希望有一种简单的方法来引用代码中的每个组时，此功能非常有用。

要创建一种新的海龟，请使用一个关键字`breed`后跟一个开方括号`[` ，该种类的复数形式，一个空格，该种类的单数形式和一个闭方括号`]` 。例如，`breed [dogs dog]` ，`breed [buildings building]`和`breed [cars car]` 。

NetLogo需要一个种类的复数形式和单数形式，因为：

- 不同的口语对于复数和单数词可能有不同的约定
- 有些事物可能具有复数形式和单数形式的非常规形式，例如`breed [cacti cactus]` ，`breed [mice mouse]`或`breed [leaves leaf]` 。


`breed`也很特别，因为它创建了其他相关命令，可在以后的代码中使用。例如，如果您创建了**dogs**种类，则可以使用诸如`create-dogs` ，`dogs-here` ，`hatch-dogs` ，`sprout-dogs`关键字。

您可以在模型中创建任意数量的品种。您还可以使用`link-breed`关键字来创建不同的链接组。
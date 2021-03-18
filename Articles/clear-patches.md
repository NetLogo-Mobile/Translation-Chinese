*** Machine Translated
`Clear-patches`是一次重置所有`Clear-patches`的关键字。它将自定义格子变量（使用`patches-own`定义）的值恢复为其默认初始值，并使所有格子变黑。此关键字的简写版本是`cp` 。

仅当我们不想使用*clear-all*时才使用`clear-patches` 。例如，如果您想清除格子但保留一些全局变量的值并使现有的海龟保持相同，则可以使用`clear-patches` 。

在下面的模型示例中，我们有两个按钮。第一个使格子的颜色变为绿色，并在随机位置上创建一些母牛。第二个按钮仅运行`clear-patches`基元以清除格子，但使母牛保持不变。
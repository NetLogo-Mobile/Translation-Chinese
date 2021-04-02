*** Machine Translated
`of`是一个关键字，使您可以接触到主体并提取其拥有的某些变量的值。通常，主体变量（例如`color` ，`size` ，`shape`以及用`<agent>-own`命令定义的变量）是在主体上下文中访问的，即在`ask turtles [...]`或`ask patches [...]`块。`of`将让你得到这样一个块之外的变量，或者得到一个主体集合每个主体的所有值的一次。

`of`与`[]`块内的返回指令程序一起使用，例如：

`[reporter] of agent` or `[reporter] of agentset`

例如，如果我们想让格子的`pcolor`在世界的中心，我们会说`[pcolor] of patch 0 0` ，因为`pcolor`是我们想要获取的变量的名称，而`patch 0 0`是主体我们要从中获取变量。如果我们想要获取每只海龟的`size`值，我们将编写`[size] of turtles`并获取每只海龟大小的列表。

注意：您的返回者可能比获取变量的值更复杂。您可以像对待Netlogo中的任何其他代码一样，将返回指令块中的代码视为必需，并在其中编写完整的表达式。例如，假设每个海龟的直径都存储在一个`diameter`变量中，而您想获取每个海龟半径的列表。一种简单的方法是写`[diameter / 2] of turtles` 。
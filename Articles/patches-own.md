*** Machine Translated
`Patches-own`定义仅属于模型格子的变量。（有关定义海龟变量`turtles-own` ，请参见其对应的`turtles-own` 。）变量通常是斑块的特征或特征。例如，如果您的面片代表模型中的土壤，则可以使用面`patches-own [ nutrients ]` 。它具有以下形式：

`patches-own [ variable1 variable2 ... ]`

并且可以包含多个变量，只要它们在方括号内即可。像全局变量和其他主体变量一样，它必须在任何过程定义之前的代码顶部定义。**注意**：格子变量也可以由位于该格子上的海龟访问。

在下面的模型中，我们正在用花建模花园。花将根据其土壤的格子多少营养成分有增长，所以我们创建一个名为格子可变`nutrients`使用`patches-own` 。
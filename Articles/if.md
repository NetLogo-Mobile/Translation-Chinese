*** Machine Translated
`If`要有条件地运行命令，请使用`If` 。它具有以下形式：

`if condition [ command ], or `if this-is-true [ then run these commands ]`

如果条件为**True** ，则命令将运行。如果条件为**False** ，则命令将不会运行，并且如果该值解析为true或false以外的任何其他值，则会发生错误。例如，

`ask turtles [ if time = night [ sleep ]`

意思是“如果是晚上，那么海龟就会入睡”。只要它们都包含在同一个`[ ]` ，就可以执行多个命令。

在下面的模型中，人们正在玩“地板是熔岩”游戏。我们创建一个使用条件语句`if`确定一个人是安全的（在蓝色格子）或出局（熔岩格子）。
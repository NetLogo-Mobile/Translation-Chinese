*** Machine Translated
`one-of`用于从主体集合或列表随机选择一个主体。它采取以下形式：

`one-of <agentset/list>`

例如，`ask one-of patches [ set pcolor red ]`会使一个随机格子变成红色。`One-of`也可以随机从提供的列表中选择一个项。例如，要将每只海龟的颜色随机更改为红色，黄色或蓝色，我们可以说：

`ask turtles [set color one-of [ red yellow blue ] ]`

**注意**：如果`one-of`在其上不具有一个主体集合被使用（例如，`ask turtles with [color = red]`但没有红龟），将发生错误。`nobody`到如何防止该错误。

在下面的模型中，疾病正在传播。它始于一个被随机选择的感染者。为了选择一个人来开始疾病传播，我们使用`one-of`随机选择了一只海龟。
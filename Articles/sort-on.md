*** Machine Translated
`sort-on`允许我们根据报告指令（例如主体特征（例如`size` ， `xcor` ）或自定义主体变量（例如`age` ， `speed` ））对座席集中的主体集合进行排序。它的语法是： `sort-on [ variable-or-reporter ] agentset` 。例如，如果我们想创建一个地震搜救模型，其中救援人员首先检查最大的建筑物，我们将编写以下代码：



```
let buildings-sorted sort-on [size] buildings
ask rescuers [
	move-to last buildings-sorted
]
```


使用`sort-on`时要记住的事情：

- `sort-on`总是按升序排序，因此，如果您希望结果按降序排序，则可以将输出传递给`reverse`输出，例如`reverse sort-on [size] turtles` 。
- 尽管在上面的示例中我们使用了简单的主体特征，但是报告指令可以包括更高级的报告器。例如，如果我们想根据海龟的x坐标与0的接近程度对海龟进行排序，则可以`sort on [abs xcor] turtles`进行`sort on [abs xcor] turtles`这将在传递到排序算法之前获得xcor的绝对值。
- `sort-on`的输出将始终是新创建的列表-根本不会修改原始主体集合。
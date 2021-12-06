*** Machine Translated
`sort-on`允许我们基于一个报告指令主体集合主体排序诸如主体特性（例如， `size` ， `xcor` ）或定制主体变量（例如`age` ， `speed` ）。它的语法是： `sort-on [ variable-or-reporter ] agentset` 。例如，如果我们想创建一个地震搜救模型，其中救援人员首先检查最大的建筑物，我们将编写以下代码：



```
let buildings-sorted sort-on [size] buildings
ask rescuers [
	move-to last buildings-sorted
]
```


使用`sort-on`时要记住的事情：

- `sort-on`将始终按升序排序，因此如果您希望结果按降序排列，则可以将输出传递到`reverse`例如`reverse sort-on [size] turtles` 。
- 虽然我们在上面的例子中使用了一个简单的主体特征，但报告指令可以包括更高级的报告者。例如，如果我们想根据海龟的 x 坐标与 0 的接近程度对海龟进行排序，我们可以`sort on [abs xcor] turtles`使用`sort on [abs xcor] turtles`这将在传递到排序算法之前获得 xcor 的绝对值。
- `sort-on`的输出将始终是一个新创建的列表——它根本不会修改原始主体集合。
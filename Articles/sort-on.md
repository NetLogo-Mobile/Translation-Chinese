`sort-on`允许我们基于一个报告指令对主体集合进行排序，诸如主体变量（例如， `size` ， `xcor` ）或自定义主体变量（例如`age` ， `speed` ）。它的语法是： `sort-on [ variable-or-reporter ] agentset` 。例如，如果我们想创建一个地震搜救模型，其中救援人员会首先检查最大的建筑物，我们将编写以下代码：



```
let buildings-sorted sort-on [size] buildings
ask rescuers [
	move-to last buildings-sorted
]
```


使用`sort-on`时要记住的事情：

- `sort-on`将始终按升序排序，因此如果您希望结果按降序排列，则可以把输出`reverse`，例如`reverse sort-on [size] turtles` 。
- 虽然我们在上面的例子中使用了一个简单的主体变量，但报告指令可以使用更高级的函数。例如，如果我们想根据海龟的 x 坐标与 0 的接近程度对海龟进行排序，我们可以使用`sort on [abs xcor] turtles`这将在输入到排序算法之前计算 xcor 的绝对值。
- `sort-on`的输出将始终是一个新创建的列表——它完全不会修改已有的主体集合。

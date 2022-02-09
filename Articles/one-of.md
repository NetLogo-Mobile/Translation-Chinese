`one-of`会返回从提供的主体集合或列表中随机选择的一个主体或随机的一个项。例如，如果我们要创建一个森林火灾模型，其中在随机的一个格子上会发生火灾，我们将编写以下代码：



```
create-trees 100 [
	set shape "tree"
	set color green
	move-to one-of patches
]
ask one-of trees [
	set color red
]
```


使用`one-of`时要记住的事情：

- 我们还可以将`one-of`与列表一起使用。例如，如果我们希望每只海龟都从预定列表选择随机颜色，则可以编写以下代码： `ask turtles [set color one-of [red green blue yellow]]` 。
- 如果`one-of`作用于一个空主体集合或空列表时，编译器会显示一个错误：你的格式是错误的。


在下面的模型示例中，我们有一些代表健康的人的蓝色海龟。我们使用`one-of`将随机挑选一只海龟并把它变成红色，这表示被感染的人（即患者）。

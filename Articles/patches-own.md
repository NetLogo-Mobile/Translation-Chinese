`patches-own`是一个特殊的 NetLogo 关键字，它允许我们定义专门属于模型中的格子的变量。这些变量是对于每个单独的格子具有唯一值的变量。 `patches-own`有助于对环境变量进行建模。例如，如果我们想创建一个污染模型，其中工厂会污染紧邻它们的格子：



```
patches-own [pollution]
create-turtles 1 [
	set shape "factory"
	ask patches in-radius 3 [
		set pollution 100
	]
]
```


使用`patches-own`时要记住的事情：

- 通过用空格分隔每个变量，我们可以在`patches-own`定义任意数量的变量，例如`patches-own [water nutrients heavy-metals altitude]` 。
- 海龟可以直接访问当前格子的变量。例如， `ask turtles [set pollution 100]`与`ask turtles [ ask patch-here [set pollution 100] ]` 。


在下面的模型示例中，我们正在建造一个有鲜花的花园。我们为我们的格子定义了一个*营养素*变量，并为每个格子分配了一个介于 0 和 10 之间的随机*营养素*数量。我们还根据每个格子的营养多少改变每个补丁的`pcolor` ，更深的格子表示更高的营养水平。最后，我们在每个格子上发芽一朵花。最初，每朵花都有相同的大小，但是当点击 go 按钮时，每朵花都会根据其格子的营养的多少生长。

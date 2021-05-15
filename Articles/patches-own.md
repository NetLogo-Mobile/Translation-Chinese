*** Machine Translated
`patches-own`是一个特殊的NetLogo关键字，它使我们能够定义仅属于模型中的修补程序的特征。这些特性是对每个格子都有唯一值的变量。 `patches-own`有助于建模环境变量。例如，如果我们想创建一个污染模型，工厂将污染附近的斑块：



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

- 通过用空格分隔每个变量，我们可以在`patches-own`范围内定义任意数量的变量，例如`patches-own [water nutrients heavy-metals altitude]` 。
- 海龟可以直接访问其当前格子的特征。例如， `ask turtles [set pollution 100]`与`ask turtles [ ask patch-here [set pollution 100] ]` 。


在下面的模型示例中，我们正在用花建模花园。我们为补丁定义了一种*营养素*特征，并为每个格子分配了0到10之间的任意数量的养分。我们还根据其格子水平更改了其补丁的`pcolor` ，以使较暗的补丁指示更高的养分。最后，我们在每个格子上都开出一朵花。最初，每朵花具有相同的大小，但是当单击“执行”按钮时，每朵花都会根据其格子的营养水平进行生长。
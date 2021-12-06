*** Machine Translated
`turtles-own`允许我们为模型中的所有海龟定义自定义海龟特征（变量）（除了默认的海龟特征，如`color` 、 `size`和`heading` ）。尽管所有海龟的特征名称都相同，但每只海龟的这些自定义特征的值都不同。一旦我们创建了这样的自定义特征，我们就可以使用`set`关键字来改变它的值。例如，如果我们想创建一个电动汽车模型，其中每辆车的剩余电量不同，我们将编写以下代码：



```
turtles-own [remaining-battery passengers]
to setup
	clear-all
	create-turtles 100 [
		set shape "car"
		set remaining-battery random 100
		set passengers one-of [1 2 3]
	]
	reset-ticks
end
to go
	ask turtles [
		if remaining-battery > 0 [
			forward 1
			set remaining-battery remaining-battery - 1
		]
	]
	tick
end
```


使用`turtles-own`时要记住的事情：

- 您应该始终在代码的开头、代码选项卡的顶部使用`turtles-own` 。
- 通过用空格分隔每个特征，我们可以在`turtles-own`关键字中定义多个特征。
- 您可以按照`<breed>-owns`格式创建特定于种类的特征。例如，如果我们有一个包含*银行*和*客户*的模型，我们可以编写`banks-own [balance customer-list] customers-own [income]` 。如果您的模型中有多个品种，则使用`turtles-own`定义的特征将适用于所有海龟，而不管它们的种类如何。


在下面的模型示例中，我们在三个平行的道路上有三辆汽车。每辆车的油箱中都有不同数量的汽油，每辆车旁边都有一个标签。当点击*go*按钮时，每辆车开始向前移动，直到它们用完油。
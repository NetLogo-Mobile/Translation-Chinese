*** Machine Translated
`turtles-own`允许我们为模型中的所有乌龟定义自定义海龟特征（变量）（除了默认的海龟特征，例如`color` ， `size`和`heading` ）。尽管所有乌龟的特征名称都相同，但是对于这些自定义特征，每只海龟将具有不同的值。一旦创建了此类自定义特征，就可以使用`set`原语更改其值。例如，如果我们要创建一个电动汽车模型，其中每辆汽车的剩余电池电量不同，则可以编写以下代码：



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

- 在代码标签的顶部，您应该始终在代码的开头使用`turtles-own` 。
- 通过用空格分隔每个特征，我们可以在`turtles-own`原始图中定义多个特征。
- 您可以按照`<breed>-owns`格式创建特定于种类的特征。例如，如果我们有一个包含*银行*和*客户*的模型，则可以写成`banks-own [balance customer-list] customers-own [income]` 。如果您的模型中有多个品种，则使用“ `turtles-own`定义的特征将应用于所有乌龟，无论它们的种类如何。


在下面的模型示例中，我们在三条平行的道路上有三辆汽车。每辆汽车的油箱中都有不同数量的汽油，旁边带有标签。单击“*执行”*按钮后，每辆汽车开始向前行驶，直到用完汽油为止。
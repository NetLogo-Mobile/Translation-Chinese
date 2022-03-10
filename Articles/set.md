`set`可以把变量的值更改为提供的新值。我们可以使用`set`来更改所有变量的值：使用`globals`创建的全局变量、使用`let`创建的局部变量、内置的主体变量（例如`pcolor` ， `size`和`xcor`）、或是使用`turtles-own`、`patches-own`或`links-own`创建的自定义主体变量。例如，如果我们想为每只海龟分配一个随机的年龄并将老年（65岁以上的）海龟设为蓝色，我们将编写以下代码：

```
turtles-own [age]
to setup
	clear-all
	create-turtles 100 [
		set color green
		set age random 80
		if age > 65 [
			set color blue
		]
	]
	reset-ticks
end
```

在下面的模型示例中，有一个带有一些棕色格子的花园，棕色格子代表了浆果植物生长的区域。我们的农民随机走动，采摘浆果。每种植物都有不同数量的浆果。在此模型中，我们将`set`用于各种目的：首先，我们使用`set`更改主体变量，例如农夫的图形（shape），格子的pcolor和植物的图形（shape）。其次，我们使用`set`来计算农民收集的浆果总量。

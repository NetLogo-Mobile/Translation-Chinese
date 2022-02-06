当我们要从主体集合中随机选择特定数量的主体时，使用`n-of` 。这类似于`one-of`的工作方式。例如，如果我们要创建一个模型，其中，我们希望有90只黄鸟和10只红鸟，我们将编写以下代码，而不是两次使用`create-turtles` ：



```
create-turtles 100 [
	set shape "bird"
	set color yellow
	setxy random-xcor random-ycor
]
ask n-of 10 turtles [
	set color red
]
```


使用`n-of`时要记住的事情：

- 如果一个主体集合少于提供的主体数，则NetLogo将显示错误。例如，如果我们的模型中有5只海龟，则以下代码将显示错误： `ask n-of 10 turtles [move]` 。


在下面的模型示例中，我们使用`n-of`随机选择50个格子来`sprout` 50株植物。我们还将在草原上放牧5头奶牛。我们还使用`n-of`使我们的两头牛变成紫罗兰色。

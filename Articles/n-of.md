*** Machine Translated
当我们要从主体集中随机选择特定数量的元素时，使用`n-of` 。这类似于`one-of`工作方式。例如，如果我们要创建一个模型，其中希望有90只黄鸟和10只红鸟，我们将编写以下代码，而不是两次使用`create-turtles` ：



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

- 如果一个主体集合少于提供的主体数，则NetLogo将显示错误。例如，如果我们的模型中有5只海龟，则以下代码将给出错误： `ask n-of 10 turtles [move]` 。


在下面的模型示例中，我们使用`n-of`随机选择50个斑块来`sprout` 50株植物。我们还将在该草原上放牧5头奶牛。我们还使用`n-of`使我们的两头母牛变成紫罗兰色。
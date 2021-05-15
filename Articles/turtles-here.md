*** Machine Translated
`turtles-here`报告了一个**主体集合**，其中包含与原始乌龟在同一格子上的所有海龟，包括原始海龟本身。例如，如果我们要创建一个传染性疾病模型，其中红海龟将疾病传播给同一格子上的所有海龟，我们将编写以下代码：



```
ask turtles with [color = red][
	ask turtles-here [
		set color red
	]
]
```


使用`turtles-here`时要牢记的注意事项：

- 它往往是不希望的，原来海龟在主体集合是`turtles-here`报告。在极少数情况下，它甚至可能导致错误。例如，以下代码将显示错误消息， `ask turtles [ create-links-with turtles-here ]`因为原始的海龟会尝试与其自身创建链。在这种情况下，我们可以使用`other`原语。例如，以下代码不会显示错误： `ask turtles [ create-links-with other turtles-here ]`
- 我们始终可以使用`with`原语来缩小`turtles-here`所报告的主体集合。例如，以下代码将只返回与原始乌龟在同一格子上的红色海龟： `turtles-here with [color = red]` 。
- 您还可以通过将术语*乌龟*（种类的复数名称更改为`<breed>-here`来使用`turtles-here`为自定义品种）。例如： `ask goats [ if any? plants-here [ eat ] ]` 。


在下面的模型示例中，我们有三个代表医院的白色补丁和一些代表人的乌龟。我们的一些乌龟是绿色的，这表明它们是健康的，而另一些是紫色/紫色的，则表明疾病。我们使用`turtles-here`要求白色斑块治愈紫罗兰色的人。
`turtles-here`报告一个**主体集合**，其中包含与来源海龟位于同一格子上的所有海龟，包括来源海龟本身。例如，如果我们想创建一个传染病模型，其中红海龟将疾病传播给同一格子上的所有海龟，我们将编写以下代码：



```
ask turtles with [color = red][
	ask turtles-here [
		set color red
	]
]
```


在使用`turtles-here`时要记住的事情：

- `turtles-here`返回的主体集合拥有来源海龟通常是不可取的。它甚至可能在少数情况下导致错误。例如，以下代码会显示错误`ask turtles [ create-links-with turtles-here ]`因为来源海龟会尝试与自己创建链接。在这种情况下，我们可以使用`other`关键字。例如，以下代码不会显示错误： `ask turtles [ create-links-with other turtles-here ]`
- 我们总是可以使用`with`关键字来缩小由`turtles-here`报告的主体集合。例如，以下代码将仅返回与来源海龟位于同一格子上的红海龟： `turtles-here with [color = red]` 。
- 您还可以将`turtles-here`与自定义种类一起使用，方法是将*turtles*替换成自定义种类的复数名称，即`<breed>-here` 。例如： `ask goats [ if any? plants-here [ eat ] ]` 。


在下面的模型示例中，我们有三个代表医院的白色格子和一些代表人的海龟。我们的一些海龟是绿色的，这表明它们是健康的，而有些是紫色的，这表明它们生病了。我们使用`turtles-here`来使白色格子治疗紫色的人。

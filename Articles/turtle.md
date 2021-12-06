*** Machine Translated
海龟是 NetLogo 中的移动主体，可以放置在世界任何地方，可以看起来像任何东西（例如，图形、颜色、大小），并且可以四处移动。它们是 NetLogo 模型中的主要主体类型。

`turtle`关键字报告具有给定编号的特定海龟。例如，如果我们想创建一个只有两只海龟的模型，一只是猫，另一只是一只老鼠，我们可以编写以下代码。请注意，当我们创建海龟时，编号从零开始。



```
create-turtles 2
ask turtle 0 [
	set shape "cat"
]
ask turtle 1 [
	set shape "mouse"
]
```


`turtles`关键字报告模型中的所有补丁。这个关键字有助于要求所有海龟做同样的事情（例如，移动、改变图形）或使用它与`with`关键字一起缩小海龟的子集。例如，如果我们想创建一个森林火灾模型，其中一些绿海龟代表健康的树木，一些黄色的海龟代表枯死/干枯的树木，并且想从一棵干枯的树开始生火，我们将编写以下代码：



```
create turtles 100 [
	set shape "tree"
	setxy random-xcor random-ycor
	set color one-of [green yellow]
]
ask one-of turtles with [color = yellow][
	set color red
]
```


使用`turtle`和`turtles`时要记住的事情：

- 原始`turtles`将始终返回相同的主体集合（除非海龟死亡），但每次使用时海龟的顺序将是随机的。
- 海龟有一些默认特征，对于每只海龟可以是不同的值。一些特征是预先构建的（例如， `color` 、 `xcor` 、 `ycor` 、 `label` 、 `size` 、 `heading` ），但我们也可以使用`turtles-own`关键字定义自定义特征，例如`turtles-own [minerals water]` 。
- 我们还可以使用诸如`breed [trees tree]`类的`breed`关键字来创建自定义海龟品种。


在下面的模型示例中，我们有许多海龟，每只海龟代表一个不同的主体。我们有一只代表房子的大海龟，一些代表植物的绿海龟，一些代表狗的五颜六色的海龟，一些代表人的海龟，还有一些代表云的顶部的海龟。房子和植物保持静止，而人、狗和云在移动。另一方面，植物在每次周期一点一点地生长。
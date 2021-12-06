*** Machine Translated
海龟是NetLogo中的移动主体，可以放置在世界任何地方，可以看起来像任何东西（例如图形，颜色，大小），并且可以四处移动。它们是NetLogo模型中主体的主要类型。

`turtle`图元报告具有给定编号的特定海龟。例如，如果我们要创建一个仅包含两只海龟（一只猫，另一只鼠标）的模型，则可以编写以下代码。请注意，当我们创建海龟时，编号从零开始。



```
create-turtles 2
ask turtle 0 [
	set shape "cat"
]
ask turtle 1 [
	set shape "mouse"
]
```


`turtles`图元报告模型中的所有修补程序。此关键字有助于要求所有海龟做同样的事情（例如，四处移动，改变图形），或将其与`with`关键字一起使用，以缩小一部分海龟的范围。例如，如果我们要创建一个森林火灾模型，其中一些绿色的海龟代表健康的树木，而一些黄色的海龟代表枯树/枯树，并想从枯树开始生火，我们将编写以下代码：



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

- 原始`turtles`将始终返回相同的主体集合（除非海龟死亡），但是每次使用时，海龟的顺序将是随机的。
- 海龟具有一些默认特征，对于每个海龟，它们可以具有不同的值。预先构建了一些特征（例如`color` ， `xcor` ， `ycor` ， `label` ， `size` ， `heading` ），但是我们还可以使用诸如`turtles-own [minerals water]`类的`turtles-own`原始图元来定义自定义特征。
- 我们还可以使用`breed`关键字（例如， `breed [trees tree]`创建自定义的海龟。


在下面的模型示例中，我们有许多海龟，每只海龟代表一个不同的主体。我们有一只代表房屋的大海龟，一些代表植物的绿海龟，一些代表狗的多彩海龟，一些代表人的海龟，以及一些顶部的代表云的海龟。房屋和植物静止不动，而人，狗和云层则在移动。另一方面，植物在每个周期上都一点一点地生长。
海龟是 NetLogo 中可以移动的主体，你可以把它们理解为动点。它们可以放置在世界任何地方，可以看起来像任何东西（你可以更改它们的样子，例如图形，颜色，大小），并且可以四处移动。它们是 NetLogo 模型中最常使用的主体。

`turtle` 函数返回具有给定编号的特定海龟。例如，如果我们要创建一个仅包含两只海龟（一只是猫，另一只是老鼠）的模型，则可以编写以下代码。请注意，当我们创建海龟时，编号从零开始。

```
create-turtles 2
ask turtle 0 [
	set shape "cat"
]
ask turtle 1 [
	set shape "mouse"
]
```

`turtles`函数返回模型中的所有海龟。通过`ask turtles`，你可以要求所有海龟做同样的事情（例如，四处移动，改变图形）。如果你想筛选出符合条件的海龟，也可以与`with`关键字一起使用。例如，如果我们要创建一个森林火灾模型，其中一些绿色的海龟代表健康的树木，而一些黄色的海龟代表枯树，并在枯树上生火，我们可以试试：

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

- 函数`turtles`将始终返回相同的主体集合（除非新建了海龟或有海龟死亡），但是每次使用时，海龟的顺序将是随机的。
- 海龟具有一些自带的变量，对于每个海龟，它们可以具有不同的值。我们可以使用预先构建的一些变量（例如`color` ， `xcor` ， `ycor` ， `label` ， `size` ， `heading` 等），我们还可以使用诸如`turtles-own [minerals water]`这样的`turtles-own`命令来定义自定义变量。
- 我们还可以使用`breed`关键字（例如， `breed [trees tree]`创建自定义的海龟种类。

下面的模型示例中有许多海龟，每只海龟代表一个不同的主体。我们有一只代表房屋的大海龟，一些代表植物的绿海龟，一些代表狗的彩色海龟，一些代表人的海龟，以及一些顶部的代表云的海龟。房屋和植物静止不动，而人，狗和云层则在移动。另外，植物在每个周期上都会一点一点地生长。

`ask`是 NetLogo 中的基本关键字之一。它允许我们*要求*一个或多个主体（即海龟、链接、补丁）执行一组提供的命令。当`ask`与多个主体一起使用时，每个主体将以*随机顺序*轮流执行命令。

例如，以下代码将使模型中的所有海龟向前移动一个单位，并使模型中的所有格子变为粉红色。 

```
ask turtles [ fd 1 ] 
ask patches [ set pcolor pink ]
```


我们还可以在`ask`关键字的命令块中放入多条命令。例如，下面的代码就可以把所有的海龟把自己的`pen-down` ，然后通过十度右转，前进一个单位的36倍，这将画一个圆。 

```
ask turtles [
	pen-down
	repeat 36 [
	   right 10
	   forward 1
	]
]
```


使用`ask`时`ask`记住的事情：

- 您可以将`ask`关键字与您使用`breed`关键字定义的自定义海龟类型一起使用。
- 您可以使用形式`turtle n`要求单个海龟跟随一组规则，例如`ask turtle 1 [...]` ， `ask turtle 2 [...]`
- 您可以使用`patch x y`形式要求单个补丁跟随一组规则，例如`patch 3 0 [...]` 。
- 您可以使用`with`关键字访问比给定主体的更小的子集，例如`ask turtles with [color = red][ ... ]`或`ask patches with [pxcor = 5][ ... ]` 。
- 您可以将`ask`用于`turtles` 、 `links`和`patches` 。
- 如果您在 ask 语句之外编写代码，NetLogo 将尝试以`observer`（观察者）运行代码，但您不能编写诸如`ask observer [...]`类的代码。
- 请注意，每个 NetLogo 关键字都有一个*范围*。如果在 ask 语句中使用目标主体不兼容的关键字，NetLogo 将报错。关键字可以是观察者专用（例如， `create-turtles` ， `diffuse` ），海龟专用（例如， `forward` ， `hatch` ），格子专用（例如， `sprout` ， `max-pxcolor` ）或链接专用（例如， `tie` ， `thickness` ）。另一方面，一些关键字可以在多个范围的主体内使用（例如， `pcolor` ， `neighbors` ），而函数关键字是独立于范围的（例如， `mean` ， `with` ）。


在下面的模型中，我们希望鱼随机游动，星星只是旋转，我们希望所有的海龟（鱼 + 星星）一点一点地变大。为了让它们执行这些动作，我们只需使用`ask`关键字！

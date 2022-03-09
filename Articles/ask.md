`ask`是 NetLogo 中的基本关键字之一。它允许我们*要求*一个或多个主体（即海龟、链接、补丁）执行一组命令。当`ask`应用到多个主体时，将按照*随机顺序*轮流执行命令。

例如，以下代码将使模型中的所有海龟向前移动 1 步，并使模型中的所有格子变为粉红色。 

```
ask turtles [ fd 1 ] 
ask patches [ set pcolor pink ]
```

我们还可以在`ask`关键字后中放入多条命令。例如，下面的代码将使所有海龟落下画笔（`pen-down`），然后重复 36 次“右转 10 度，前进 1 个单位”——这样一来，每只海龟都会画一个圆。

```
ask turtles [
	pen-down
	repeat 36 [
	   right 10
	   forward 1
	]
]
```

使用`ask`时需要记住：

- 可以将`ask`关键字与使用`breed`关键字定义的自定义海龟类型一起使用。
- 可以将`ask`用于`turtles` 、 `links`和`patches`。
- 可以使用`turtle n`让单只海龟执行命令。例如`ask turtle 1 [...]`，`ask turtle 2 [...]`。
- 可以使用`patch x y`让一个格子执行命令。例如`patch 3 0 [...]`。
- 可以使用`with`关键字访问比给定主体的更小的子集，例如`ask turtles with [color = red][ ... ]`或`ask patches with [pxcor = 5][ ... ]`。
- 如果您在 ask 语句之外编写代码，NetLogo 将尝试以`observer`（观察者）运行代码，但您不能编写诸如`ask observer [...]`类的代码。
- 请注意，每个 NetLogo 关键字都有一个*范围*。如果在 ask 语句中使用目标主体不兼容的关键字，NetLogo 将报错。关键字可能是观察者专用（例如， `create-turtles` ， `diffuse`），海龟专用（例如， `forward` ， `hatch`），格子专用（例如， `sprout` ， `max-pxcolor`）或链接专用（例如， `tie` ， `thickness`）。另一方面，一些关键字可以在多个范围的主体内使用（例如，`pcolor` ，`neighbors`），而函数关键字则是通用的（例如，`mean`， `with`）。

在下面的模型中，我们希望鱼随机游动，星星只会旋转，并且所有的海龟（鱼 + 星星）逐渐变大。只需使用`ask`关键字就能做到啦。

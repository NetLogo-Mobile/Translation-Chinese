*** Machine Translated
`ask`是NetLogo中的基本关键字之一。它允许我们*要求*一个或多个主体（例如，海龟，链接，格子）跟随提供的一组规则。当`ask`与多个主体一起使用时，每个主体将以随机顺序轮流使用。

例如，以下代码将使模型中的所有海龟向前移动一个单元，并使模型中的所有格子变为粉红色。

```
ask turtles [ fd 1 ] 
ask patches [ set pcolor pink ]
```


您还可以提供多个带有`ask`关键字的命令。例如，下面的代码就可以把所有的海龟把自己的`pen-down`，然后通过十度右转，前进一个单位的36倍，这将画一个圆。

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

- 您可以将`ask`关键字与在`breed`关键字中定义的自定义海龟类型一起使用。
- 您可以要求海龟使用`turtle n`形式跟随一组规则，例如，`ask turtle 1 [...]` ，`ask turtle 2 [...]`。
- 您可以使用`patch xy`的形式要求单个格子跟随一组规则，例如`patch 3 0 [...]` 。
- 您可以使用`with`关键字来询问给定主体的更小的子集，例如`ask turtles with [color = red][ ... ]`或`ask patches with [pxcor = 5][ ... ]` 。
*** Machine Translated
`ask`是NetLogo中的基本原语之一。它使我们可以*要求*一个或多个代理（例如，乌龟，链接，补丁）跟随提供的一组规则。当`ask`与多个代理一起使用时，每个主体将以随机顺序轮流使用。

例如，以下代码将使模型中的所有海龟向前移动一个单元，并使模型中的所有补丁变为粉红色。 

```
ask turtles [ fd 1 ] 
ask patches [ set pcolor pink ]
```


我们还可以为一个`ask`原语提供多个命令。例如，下面的代码就可以把所有的海龟把自己的`pen-down` ，然后通过十度右转，前进一个单位的36倍，这将画一个圆。 

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

- 您可以将`ask`原语与您使用`breed`原语定义的自定义海龟类型一起使用。
- 您可以要求乌龟使用`turtle n`形式跟随一组规则，例如， `ask turtle 1 [...]` ， `ask turtle 2 [...]`
- 您可以使用`patch xy`的形式要求单个补丁跟随一组规则，例如`patch 3 0 [...]` 。
- 您可以使用`with`原语来询问给定代理的更小的子集，例如`ask turtles with [color = red][ ... ]`或`ask patches with [pxcor = 5][ ... ]` 。


在下面的模型中，我们希望鱼随机游动，而星星只是旋转，我们希望所有海龟（鱼+星）一点一点地生长。为了使他们跟随这些动作，我们只需要使用`ask`原语！
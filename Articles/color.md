*** Machine Translated
`color`是内置的海龟特征，代表NetLogo模型中每只海龟的颜色。每次我们创建新的海龟时，每只海龟都会被分配一种随机的颜色。我们可以结合使用`set`关键字和`color`关键字来更改海龟的颜色，如下所示： `set color red` 。



```
ask turtles [
	ifelse size > 2 [
		set color red
	][
		set color green
	]
]
```


`color`也是报告指令;我们可以使用它来访问海龟的颜色，如下所示： 

```
ask turtles with [color = red][
	set size 5
]
```


使用`color`时要记住的事情：

- NetLogo使用自定义编号方案来表示颜色。您可以通过单击“*工具”*菜单并选择“*色样”*选项来访问此颜色编号方案。
- 如您在上面的示例中所注意到的，您可以在代码中直接使用常见颜色的名称。这些名称是： `red` ， `green` ， `blue` ， `brown` ， `black` ， `pink` ， `white` ， `violet` ， `magenta` ， `cyan`和`gray` 。
- 您应该直接写出一种颜色的名称，而在颜色名称（ `""` ）周围不要加上任何引号。
- 由于NetLogo对颜色使用简单的编号方案，因此您实际上可以将颜色名称视为数值。这使我们可以通过简单的数学运算来控制颜色的亮度。例如， `green + 2`将导致绿色变浅，而`green - 2`将导致绿色变深。您还可以使用非整数来获得更精确的颜色，例如`red + 0.25`或`blue - 1.85` 。


在下面的模型示例中，我们有一只白羊和一些植物。我们使用`color`关键字使一些植物变成绿色和黄色。我们使用`ask turtles with [color = white]`的`ask turtles with [color = white]`来要求绵羊移动，而植物则保持静止。我们的羊随机地走动。当在同一格子上有黄色植物时，我们的羊只会忽略它。但是，如果在同格子地上有绿色植物，我们的羊会吃掉绿色植物。
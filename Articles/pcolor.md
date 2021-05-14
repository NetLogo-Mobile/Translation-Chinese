*** Machine Translated
`pcolor`是一个内置在报告格子的格子变量。因为`pcolor`是一个变量，而且是一个报告指令，所以可以使用`set`来更改它。可以通过简单地说明颜色（例如，棕色，黄色，红色；请注意颜色名称周围没有引号）或NetLogo颜色（单个数字）来设置`pcolor` 。例如，如果我们想将补丁设为蓝色代表海洋，然后在中间创建一个岛，则可以编写以下代码：



```
ask patches [
	set pcolor blue
	if distancexy 0 0 < 5 [
		set pcolor brown
	]
]
```


如果我们想在我们的岛上放一些树， `pcolor`会很有用，如下所示：



```
create-trees 10 [
	move-to one-of patches with [pcolor = green]
]
```


使用`pcolor`时要记住的事情：

- 海龟可以直接访问其格子的`pcolor` 。例如， `ask turtles [set pcolor green]`的结果与`ask turtles [ ask patch-here [ set pcolor green ] ]` 。
- NetLogo使用自定义编号方案来表示颜色。您可以通过单击“*工具”*菜单并选择“*色样”*选项来访问此颜色编号方案。
- 如您在上面的示例中所注意到的，您可以在代码中直接使用常见颜色的名称。这些名称是： `red` ， `green` ， `blue` ， `brown` ， `black` ， `pink` ， `white` ， `violet` ， `magenta` ， `cyan`和`gray` 。
- 您应该直接写出一种颜色的名称，而在颜色名称（ `""` ）周围不要加上任何引号。
- 由于NetLogo对颜色使用简单的编号方案，因此您实际上可以将颜色名称视为数值。这使我们可以通过简单的数学运算来控制颜色的亮度。例如， `green + 2`将导致绿色变浅，而`green - 2`将导致绿色变深。您还可以使用非整数来获得更精确的颜色，例如`red + 0.25`或`blue - 1.85` 。


在下面的模型示例中，我们有一些绵羊随机游荡。我们使用`pcolor`使我们的某些色块变为棕色，以表示地面，而我们的某些色块表示为草。绵羊只有在贴有草的格子上才能吃东西，因此，只有`if pcolor = green`时，它们才能吃东西。该模型不仅使用`set`更改了格子的`pcolor` ，而且显示了如何在条件语句中使用`pcolor` 。
`pcolor`是一个内置的格子变量。因为`pcolor`既是一个变量，也是一个报告指令，你可以使用`set`来改变它。 `pcolor`可以通过简单地表示颜色（例如，棕色：brown、黄色：yellow、红色：red；注意颜色名称周围没有引号）或 NetLogo 颜色（单个数字）来设置。例如，如果我们想让我们的格子变成蓝色代表海洋，然后在中间创建一个岛屿，我们将编写以下代码：



```
ask patches [
	set pcolor blue
	if distancexy 0 0 < 5 [
		set pcolor brown
	]
]
```


如果我们想在岛上放一些树， `pcolor`会很有用，如下所示：



```
create-trees 10 [
	move-to one-of patches with [pcolor = green]
]
```


使用`pcolor`时要记住的事情：

- 海龟可以直接访问其格子的`pcolor` 。例如， `ask turtles [set pcolor green]`的结果与`ask turtles [ ask patch-here [ set pcolor green ] ]` 一致。
- NetLogo 使用自定义编号方案来表示颜色。如果您是netlogo desktop端，可以通过单击“*工具*”菜单并选择“*色板*”选项来访问此颜色编号方案，如果您是海龟实验室端，则可以在实验区找到用户自制的取色器。
- 正如您在上面的示例中注意到的，您可以直接在代码中使用常用颜色的名称。所有的名称： `red` 、 `green` 、 `blue` 、 `brown` 、 `black` 、 `pink` 、 `white` 、 `violet` 、 `magenta` 、 `cyan`和`gray` 。
- 您应该直接写出颜色的名称，而不要在颜色名称周围加上任何引号 ( `""` ) 。
- 由于 NetLogo 编译器使用简单的颜色编号方案，您实际上可以将颜色名称视为数值。这使我们可以通过简单的数学运算来操纵颜色的亮度。例如， `green + 2`将产生较浅的绿色，而`green - 2`将产生较深的绿色。您还可以使用非整数来获得更精确的颜色，例如`red + 0.25`或`blue - 1.85` 。


在下面的模型示例中，我们有一些随机游荡的绵羊。我们使用`pcolor`使我们的一些补丁`brown`代表地面，我们的一些补丁`green`代表草。当他们在上面有草格子羊只能吃，所以他们只能吃`if pcolor = green` 。该模型不仅使用`set`更改格子的`pcolor` ，而且还展示了如何在条件语句中使用`pcolor` 。

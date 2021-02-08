*** Machine Translated
`pcolor`是一个内置在返回格子的格子变量。由于`pcolor`既是变量又是返回指令，因此可以使用`set`进行更改。可以通过简单地说明颜色（例如，棕色，黄色，红色；请注意颜色名称周围没有引号）或NetLogo颜色（单个数字）来设置`pcolor` 。例如，您可以编写`ask patches [set pcolor pink]`或`ask patches [ set pcolor 15]` 。海龟可以使用此关键字直接访问并更改其所格子的颜色。例如： `ask turtles [ set pcolor yellow]` 。要更改海龟的颜色，请参见[*color*](http://ccl.northwestern.edu/netlogo/docs/dictionary.html#color) 。

在下面的模型中，有羊在附近闲逛并吃草。绵羊只有在有草的格子上时才能进食，因此，只有`if [ pcolor ] of patch-here = green`时，它们才能进食。该模型不仅使用`set`更改了格子的`pcolor` ，而且显示了如何在条件语句中使用`pcolor` 。
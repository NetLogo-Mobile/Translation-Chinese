*** Machine Translated
`myself`是一个原始的，当我们想主体指本身，同时努力解决内部的不同的主体或主体集合是有用的`ask`命令或报告指令（如`of` ， `with` ）。例如，如果我们要创建一个模型，在其中一个具有相同颜色的海龟试图互相寻找，我们将编写以下代码：



```
ask turtles [
	face one-of turtles with [color = [color] of myself]
	forward 1
]
```


在下面的模型示例中，我们具有与流行的在线游戏[*agar.io*](https://en.wikipedia.org/wiki/Agar.io)相似的模型。我们有很多乌龟代表圆圈，它们随机移动。当两只乌龟互相接触时，大海龟*吞食*小海龟。我们将`myself`用于两个目的：首先比较`ask`语句中的两只海龟，以选择较大的一只，然后将两只海龟的大小相加。
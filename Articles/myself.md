`myself`是一个关键字，当我们想用一个关键字指代上级主体本身，同时，代码在不同的主体或主体集合的`ask`命令或报告指令（如`of` ， `with` ）中，`myself`会很有用。例如，如果我们要创建一个模型，要使两个具有相同颜色的海龟试图互相靠近，我们将编写以下代码：



```
ask turtles [
	face one-of turtles with [color = [color] of myself]
	forward 1
]
```


在下面的模型示例中，我们有一个与比较流行的网页游戏[*agar.io*](https://en.wikipedia.org/wiki/Agar.io)相似的模型。我们有很多海龟代表圆圈，它们随机移动。当两只海龟互相接触时，较大的海龟会*吞食*较小的那个海龟。我们将这样使用`myself`：首先比较`ask`语句中的两只海龟，以选择较大的一只，然后将两只海龟的大小相加。

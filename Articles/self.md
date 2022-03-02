当我们需要一个主体在`ask`语句中引用自身时， `self`是一个非常有用的关键字。 `self`在将一只海龟分配给全局变量时非常有用。例如，如果我们有一个所有顾客都需要去的代表餐厅格子，那么我们将编写以下代码 

```
globals [the-restaurant]
to setup
 	ask one-of patches [
 		set color yellow
 		set the-restaurant self
 	]
end
to go 
	ask turtles [
		facer the-restaurant
		forward 1
	]
end
```


在下面的模型示例中，我们有一个与先前比较流行的在线游戏[*agar.io*](https://en.wikipedia.org/wiki/Agar.io)相似的模型。我们有很多海龟代表圆圈，它们会随机移动。当两只海龟互相接触时，较大的那个海龟会*吞食*较小的那个海龟。我们将`self`用于两个目的：首先比较`ask`语句中的两只海龟，以选择较大的海龟，然后将两只海龟的大小相加。

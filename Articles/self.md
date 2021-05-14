*** Machine Translated
当我们需要主体在`ask`语句中引用自身时， `self`是一个非常有用的原语。 `self`在将一只海龟分配给全局变量时非常有用。例如，如果我们有一个所有客户都需要去的餐厅格子，那么我们将编写以下代码 

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


在下面的模型示例中，我们具有与流行的在线游戏[*agar.io*](https://en.wikipedia.org/wiki/Agar.io)相似的模型。我们有很多乌龟代表圆圈，它们随机移动。当两只乌龟互相接触时，大海龟*吞食*小海龟。我们将`self`用于两个目的：首先比较`ask`语句中的两只海龟，以选择较大的海龟，然后将两只海龟的大小相加。
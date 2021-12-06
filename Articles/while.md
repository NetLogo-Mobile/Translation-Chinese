*** Machine Translated
只要给定的报告指令报告为真， `while`无限期地重复提供的一组规则（如`ask` ）。如果报告指令报告**false** ， `while`停止重复提供的规则。例如，如果我们想创建一个房地产市场模型，每个买家继续寻找房子，直到找到足够便宜的房子，我们将编写以下代码：



```
ask turtles [
	let found-home? false
	while [not found-home?] [
		move-to one-of patches with [residents = 0]
		if [price] of patch-here < my-budget [
			set found-home? true
		]
	]
]
```


在下面的模型示例中，我们将许多海龟放置在网格布局。每只海龟要么是紫色的要么是绿色的，每只海龟要么开心要么悲伤，这取决于周围的海龟数量。如果一只海龟有超过 2个不同颜色的邻居，我们使用`while`关键字让每只海龟在网格中移动，直到它们找到一个让它们开心的地方。